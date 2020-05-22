1. Find duplicate in array: https://www.interviewbit.com/problems/find-duplicate-in-array/ => Tortoise-Hare approach
2. Kth Largest element in stream: https://leetcode.com/problems/kth-largest-element-in-a-stream/ => Min heap
3. Third Maximum number: https://leetcode.com/problems/third-maximum-number/ => Use set to maintain three elements. Operations on set will be O(1) not O(longn)
4. Sort array of 0s 1s and 2s: https://leetcode.com/problems/sort-colors/ => Dutch national flag algorithm
5. Wiggle Sort II: https://leetcode.com/problems/wiggle-sort-ii/ => Virtual indexing
6. Happy numbers: https://www.geeksforgeeks.org/happy-number/ => Fast pointer/slow pointer
7. All paths from source to dest: https://www.geeksforgeeks.org/find-paths-given-source-destination/

## BST
1. Sorted array to BST

Notes:<br>
Way1 (if we need to create an actual tree) => <br>
  a. Convert sorted array to BST (using mid as root and recur)
  b. Print preOrder of this created BST.
Way2 (if we do not need to create an actual tree) => <br>
  a. Recur directly while creating.

2. Sorted LL to BST
