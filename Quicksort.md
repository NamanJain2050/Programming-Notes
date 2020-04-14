# Quicksort

Divide and Conquer Algorithm to sort a list of numbers. Developed by Tony Hoare in 1959.

<b> 1. Introduction </b> <br>
The idea is to select a 'pivot' element from the array and 'partition' other elements into two subarrays, according to whether they are less than or greater than the 'pivot'. Than we do the same procedure for each subarray.

<b> 2. How to pick a pivot? </b> <br>
Given a list of numbers we have to choose a pivot element around which we can partition. Common choices of pivot are:
- First number of array
- Last number of array
- Pick randomly
- Pick median of array

<b> 3. Partition procedure </b> <br>
Given a 'pivot' element, now we need to partition our array around this pivot. <br>

<b> 3.1. Lomuto partition scheme </b> <br>

Code: https://gist.github.com/NamanJain2050/72b2cd52bdd9cc4ad3cd3df46e96f24e <br>

- This scheme is attributed to Nico Lomuto and also mentioned in CLRS (https://en.wikipedia.org/wiki/Quicksort#Lomuto_partition_scheme)
- This scheme chooses pivot as the last element of array

<b> 4. Time Complexity Analysis </b> <br>
T(n) = T(k) + T(n-k-1) + \theta(n) <br>
where k is the size of left subarray and can range from 0 to n - 1;

<b> 4.1. Best Case scenario </b> <br>
T(n) = 2T(n/2) + \theta(n) <br>
Pivot gives a balanced split of subarrays. This will give time complexity of O(nlogn).

<b> 4.2. Worst Case scenario </b> <br>
T(n) = T(0) + T(n-1) + \theta(n) <br>
Pivot is either the largest or smallest element of array. This will give time complexity if O(n^2).

<b> 4.3. Average Case scenario </b> <br>
T(n) = T(n/100) + T(99n/100) + \theta(n) <br>
Even if we get such a split (better than worst case but much worse than best case) we'll get time complexity of O(nlogn).
