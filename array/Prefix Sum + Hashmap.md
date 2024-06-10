Problems related to Subarrays:

1. Count the subarrays with some condition
2. Find Maximum Length Subarray with some condition
3. Check if subarray exists with some given condition

Mainly the problems dealing with **Subarray sum** .

Using regular prefix sum array, you access prefix sum based on index.
Using hashmap, *you access index using prefix sum.*

`map<sum, index>`

Wtf does bottom text mean?
#### _Why we need this approach of Hashmap +Prefix Sum ?_

So basically for subarray related problems Brute Force method takes O(n^2) time to process each subarray + extra time in processing .  
But with this approach only O(n) time is taken .  
Now you might wonder that what is stopping you from using Sliding window approach for such problems

> Sliding window is only applicable when we know for sure if the prefixsum is an increasing or decreasing function(i.e. Monotonous in nature)

So for problems where negative input is given this approach of PrefixSum + Hashmap is the best way to solve such problems.

