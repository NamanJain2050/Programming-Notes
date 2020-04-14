# Selection Algorithms
A selection algorithm is an algorithm for finding the kth smallest number in a list or array. <br>

<b> 1. Quickelect Algorithm </b> <br>
Code: https://gist.github.com/NamanJain2050/e9bde5fdbed25d0c2e8f477837e092ad
- Like quicksort it was developed by Tony Hoare and it works like quicksort
- Quicksort recurs for both subarrays, here we only recur for one subarray. 
- We recur for the subarray in which we think the kth smallest element will lie.
- Time Complexity (just like QuickSort)=> Best: O(n) | Average: O(n) | Worst: O(n^2)
