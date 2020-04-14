# Selection Algorithms
A selection algorithm is an algorithm for finding the kth smallest number in a list or array (kth order statistic). <br>

<b> 1. Quickelect Algorithm </b> <br>
Code: https://gist.github.com/NamanJain2050/e9bde5fdbed25d0c2e8f477837e092ad
- Like quicksort it was developed by Tony Hoare and it works like quicksort
- Quicksort recurs for both subarrays, here we only recur for one subarray. 
- We recur for the subarray in which we think the kth smallest element will lie.
- Time Complexity (just like QuickSort)=> Best: O(n) | Average: O(n) | Worst: O(n^2)

<b> 2. Median-of-Medians Algorithm </b> <br>
- In quickselect even we if choose the pivot randomly we get O(n^2) in worst case. What if we consistenly choose good pivots at each step and every time.
- The median is a good pivot – the best for sorting, and the best overall choice for selection – decreasing the search set by half at each step.
- If we can compute the median in linear time, this only adds linear time to each step, and thus the overall complexity of the algorithm remains linear.
- This is an algorithm that finds <b> approximate median in constant time </b>. We can choose this median as pivot and rest of the algorithm works as usual.
- Time Complexity (just like QuickSort)=> Best: O(n) | Average: O(n) | Worst: O(n)

<b> 2.1. Working </b> <br>
1. Divide the array into ⌈n/5⌉ groups where size of each group is 5 except possibly the last group which may have less than 5 elements = > O(n).
2. Sort the above created ⌈n/5⌉ groups and find median of all groups. We'll have ⌈n/5⌉ medians one for each group => O(n).
3. Recursively find the median of this medians array (MoMs)=> T(n/5).
4. Use this MoMs as pivot and partition around this => O(n)
5. Recur for one subarray (just like quickselect)
