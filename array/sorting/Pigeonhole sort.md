#sort

| Class                       | [[Sorting Algos]]                                                            |
| --------------------------- | ---------------------------------------------------------------------------- |
| Data structure              | [[Array]]                                                                    |
| Worst-case performance      | $O(N + n)$<br>where _N_ is the range of key values and _n_ is the input size |
| Worst-case space complexity | $O(N + n)$                                                                   |
| Optimal                     | iff $N = O(n)$                                                               |

**Generalization** (I am a kind of ...)  
[_range sort_](https://xlinux.nist.gov/dads/HTML/rangesort.html).

**Specialization** (... is a kind of me.)  
[_rapid sort_](https://xlinux.nist.gov/dads/HTML/rapidSort.html).

**Definition:** A 2-pass [_sort_](https://xlinux.nist.gov/dads/HTML/sort.html) algorithm that is efficient when the range of [_keys_](https://xlinux.nist.gov/dads/HTML/key.html) is approximately equal to the number of items. 
1. Given an array of values to be sorted, set up an auxiliary array of initially empty "pigeonholes", one pigeonhole for each key in the [range](https://en.wikipedia.org/wiki/Range_(computer_science) "Range (computer science)") of the keys in the original array.
2. Going over the original array, put each value into the pigeonhole corresponding to its key, such that each pigeonhole eventually contains a list of all values with that key.
3. Iterate over the pigeonhole array in increasing order of keys, and for each pigeonhole, put its elements into the original array in increasing order.

Similar to [[Counting Sort]], but differs in that:
>  _Pigeonhole sort moves items twice: once to the bucket array and again to the final destination. Counting sort builds an auxiliary array then uses the array to compute each item's final destination and move the item there._
>  _Since [[Rapid Sort]] only sorts keys, "moving an item in its key's bucket" is just incrementing a count and "moving each item to the destination" is writing the proper number of keys._

The difference between pigeonhole sort and [[Counting Sort]] is that in counting sort, the auxiliary array does not contain lists of input elements, only counts.

For arrays where _N_ is much larger than _n_, [[Bucket Sort]] is a generalization that is more efficient in space and time.

### Problems
1. [1051. Height Checker](https://leetcode.com/problems/height-checker/) 