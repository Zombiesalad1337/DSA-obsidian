
**Definition**: A 2-pass sort algorithm that is **efficient when the number of distinct keys is small compared to the number of items.** The first pass counts the occurrences of each key in an auxiliary array, and then makes a running total so each auxiliary entry is the number of preceding keys. The second pass puts each item in its final place according to the auxiliary entry for that key. 

**Generalization** (I am a kind of ...)  
[_histogram sort_](https://xlinux.nist.gov/dads/HTML/histogramSort.html).

_Note: 
A [[Bucket Sort]] uses fixed-size buckets.
A [[Histogram Sort]] sets up buckets of exactly the right size in a first pass. 
A [[Counting Sort]] is a histogram sort with one bucket per possible key value.
A [[Pigeonhole sort]] is a counting sort that moves items to the auxiliary array instead of counting them._

Used as subroutine in [[Radix Sort]]

### Problems
****
1. https://leetcode.com/problems/height-checker/
2. https://leetcode.com/problems/relative-sort-array/
3. https://leetcode.com/problems/sort-characters-by-frequency/
4. [2037. Minimum Number of Moves to Seat Everyone](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/)
