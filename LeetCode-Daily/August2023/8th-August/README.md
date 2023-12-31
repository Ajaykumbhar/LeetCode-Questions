## 33. Search in Rotated Sorted Array | Link <a href="https://leetcode.com/problems/search-in-rotated-sorted-array/"><img src="https://leetcode.com/_next/static/images/logo-dark-c96c407d175e36c81e236fcfdd682a0b.png" alt="LeetCode Logo" width="18"> </a>

### Understanding the Rotated Array:

We are given a sorted array that has been rotated at an unknown pivot point. This means that the array is divided into two segments, each of which is sorted.
For instance, consider the array [4, 5, 6, 6, 7, 0, 1, 2, 4, 4]. This array can be divided into two sorted segments: [4, 5, 6, 6, 7] and [0, 1, 2, 4, 4].

### Approach: Modified Binary Search

#### What? 

- We will use a modified version of the binary search algorithm to efficiently find the target element's index in the rotated sorted array.
  
#### Why?

##### The modified binary search algorithm quickly reduces the number of elements it needs to check in each step.
  > Making it efficient in finding the target element's index in the rotated sorted array.
    
##### The time complexity of this algorithm is O(log n), where `n` is the number of elements in the array.

#### How? 

##### The algorithm uses two pointers, `start` and `end`, to search for the target element in the array. It starts with the entire array as the search space.

- Calculate mid:
  - In each iteration of the loop, the algorithm calculates the midpoint mid between the str and end pointers.
  - The midpoint mid is calculated as (str + end) / 2.

  - If `mid` is equal to the target, the target is found, and the algorithm returns its index.

##### Comparison of Midpoint and Boundaries:
  > The algorithm performs a comparison of the elements at indices str and mid to determine which half of the array might be sorted.

##### If the left half of the search space is sorted (nums[str] <= nums[mid]):
    
  - If the `target` >= `nums[str]` and <= `nums[mid]`, it must be in the `left half` of the array
      
      - So, the end pointer is updated to `mid - 1` to narrow down the search space to the left half.
        
  - Otherwise, the target must be in the right half, So, the str pointer is updated to mid + 1.

 ##### If the right half of the search space is sorted:
   - If the target is within this sorted right half, the search space is narrowed to the right half.
   - Otherwise, the target must be in the left half, so the search space is narrowed to the left half.

 ##### The algorithm repeats steps 1 to 4 until it finds the target or exhausts the search space.
 #####  If the target is not found, the algorithm returns -1.

