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

- This scheme is attributed to Nico Lomuto and also mentioned in CLRS (https://en.wikipedia.org/wiki/Quicksort#Lomuto_partition_scheme)
- This scheme chooses pivot as the last element of array

Complete code of Quicksort using this scheme: https://gist.github.com/NamanJain2050/72b2cd52bdd9cc4ad3cd3df46e96f24e
