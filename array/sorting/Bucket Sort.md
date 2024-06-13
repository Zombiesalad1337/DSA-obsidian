#sort

| Class                       | [[Sorting Algos]]                                                                                                                          |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Data structure              | [[Array]]                                                                                                                                  |
| Worst-case performance<br>  | $O(n^2)$                                                                                                                                   |
| Average performance         | $O(n + \frac{n^2}{k} + k)$<br>where $k$ is the number of buckets<br><br>$O(n)$, when $k = \Theta(n)$ (given a uniformly distributed input) |
| Worst-case space complexity | $O(n+k)$                                                                                                                                   |
|                             |                                                                                                                                            |

**Generalization** (I am a kind of ...)  
[_distribution sort_](https://xlinux.nist.gov/dads/HTML/distributionSort.html).

**Specialization** (... is a kind of me.)  
[_histogram sort_](https://xlinux.nist.gov/dads/HTML/histogramSort.html),[[Counting Sort]], [_top-down radix sort_](https://xlinux.nist.gov/dads/HTML/topdownRadixSort.html), [_postman's sort_](https://xlinux.nist.gov/dads/HTML/postmansort.html), [_distributive partitioning sort_](https://xlinux.nist.gov/dads/HTML/distributivePartitioningSort.html).

**Definition:** A [_distribution sort_](https://xlinux.nist.gov/dads/HTML/distributionSort.html) where input elements are initially distributed to several [_buckets_](https://xlinux.nist.gov/dads/HTML/bucket.html) based on an interpolation of the element's [_key_](https://xlinux.nist.gov/dads/HTML/key.html). Each bucket is sorted if necessary (using different sorting algo or by recursively applying bucket sort), and the buckets' contents are concatenated.


Generalization of [[Pigeonhole sort]] that allows **multiple keys per bucket**.
A cousin of [[Radix Sort]] in the most-to-least significant digit flavor.

Computational complexity depends on:
1. Algo used to sort each bucket
2. The number of buckets to use
3. Whether the input is uniformly distributed

Bucket sort works as follows:
1. Set up an array of initially empty "buckets".
2. **Scatter**: Go over the original array, putting each object in its bucket.
3. Sort each non-empty bucket.
4. **Gather**: Visit the buckets in order and put all elements back into the original array.

```
function bucketSort(array, k) is
    buckets ← new array of k empty lists
    M ← 1 + the maximum key value in the array
    for i = 0 to length(array) do
        insert _array[i]_ into _buckets[floor(k × array[i] / M)]_
    for i = 0 to k do 
        nextSort(buckets[i])
    return the concatenation of buckets[0], ...., buckets[k]
```
One can compute the maximum key value in [linear time](https://en.wikipedia.org/wiki/Linear_time "Linear time") by iterating over all the keys once.

The function _nextSort_ is a sorting function used to sort each bucket.  Conventionally [[Insertion Sort]] is used.
Using _bucketSort_ itself as _nextSort_ produces a relative of [[Radix Sort]]; in particular, the case _n = 2_ corresponds to [[Quicksort]] (although potentially with poor pivot choices).

## Analysis

#### Worst-case analysis
When the input contains several keys that are close to each other (**clustering**), those elements are likely to be placed in the same bucket, which results in some buckets containing more elements than average. **The worst-case scenario occurs when all the elements are placed in a single bucket.** The overall performance would then be dominated by the algorithm used to sort each bucket, for example, $O(n^2)$ [[Insertion Sort]] or  $O(nlog(n)$ comparison sort algorithms, such as [[Merge Sort]].

### Optimizations
A common optimization is to put the unsorted elements of the buckets back in the original array _first_, then run [[Insertion Sort]] over the complete array; because insertion sort's runtime is based on how far each element is from its final position, the number of comparisons remains relatively small, and the memory hierarchy is better exploited by storing the list contiguously in memory.

****
If the input distribution is known or can be estimated, buckets can often be chosen which contain constant density (rather than merely having constant size). This allows $O ( n )$ average time complexity even without uniformly distributed input.
****