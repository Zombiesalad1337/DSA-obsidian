
Complexity: $\Theta(n)$ moves and examinations

**Definition:** Rearrange elements in an [[Array]] into three groups: bottom, middle, and top.

**Generalization** (I am a kind of ...)  
[_partition_](https://xlinux.nist.gov/dads/HTML/partition.html).

**Aggregate parent** (I am a part of or used in ...)  
[_multikey Quicksort_](https://xlinux.nist.gov/dads/HTML/multikeyQuicksort.html).

#### Pseudocode
***
Three-way partitioning. 0 based indexing.
It uses three indices i, j and k, maintaining the invariant that _i_ ≤ _j_ ≤ _k_.

- Entries from 0 up to (but not including) i are values less than mid,
- entries from i up to (but not including) j are values equal to mid,
- entries from j up to (and including) k are values not yet sorted, and
- entries from k + 1 to the end of the array are values greater than mid.

```
procedure three-way-partition(A : array of values, mid : value):
    i ← 0
    j ← 0
    k ← size of A - 1

    while j <= k:
        if A[j] < mid:
            swap A[i] and A[j]
            i ← i + 1
            j ← j + 1
        else if A[j] > mid:
            swap A[j] and A[k]
            k ← k - 1
        else:
            j ← j + 1
```

***
_Note: Using this algorithm in [[Quicksort]] to [_partition_](https://xlinux.nist.gov/dads/HTML/partition.html) elements, with the middle group being elements equal to the pivot, lets quicksort avoid "resorting" elements that equal the pivot.

in particular, variants of the [[Quicksort]] algorithm that must be [robust to repeated elements](https://en.wikipedia.org/wiki/Quicksort#Repeated_elements "Quicksort") may use a three-way partitioning function that groups items less than a given key (red), equal to the key (white) and greater than the key (blue). Several solutions exist that have varying performance characteristics, tailored to sorting arrays with either small or large numbers of repeated elements.

### Problems
***
1. [75. Sort Colors](https://leetcode.com/problems/sort-colors/)
