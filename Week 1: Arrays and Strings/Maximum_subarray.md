## Problem Statement:
Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

Example:
Input: [-2,1,-3,4,-1,2,1,-5,4]

Output: 6

Explanation: [4,-1,2,1] has the largest sum 6.

Solution:
The problem can be solved using the Kadane's algorithm. The basic idea is to iterate through the array and keep track of the maximum subarray sum seen so far. The maximum subarray sum at any index can either be the element at that index or the element plus the maximum subarray sum seen so far. We also keep track of the maximum subarray sum seen so far.

Here's the Python code for the solution:

## python
Copy code
def maxSubArray(nums):
    max_sum = nums[0]  # to keep track of maximum sum seen so far
    curr_sum = nums[0]  # to keep track of current sum
    
    for i in range(1, len(nums)):
        curr_sum = max(nums[i], curr_sum + nums[i])
        max_sum = max(max_sum, curr_sum)
        
    return max_sum
In the above code, we initialize the max_sum and curr_sum variables to the first element of the array. We then iterate through the array starting from the second element. At each index, we calculate the current sum by taking the maximum of the element at that index and the element plus the current sum seen so far. We also update the maximum sum seen so far. Finally, we return the maximum sum seen so far.

This algorithm has a time complexity of O(n), where n is the length of the array.

## java
public static int maxSubArray(int[] nums) {
    int maxSum = nums[0]; // to keep track of maximum sum seen so far
    int currSum = nums[0]; // to keep track of current sum

    for (int i = 1; i < nums.length; i++) {
        currSum = Math.max(nums[i], currSum + nums[i]);
        maxSum = Math.max(maxSum, currSum);
    }

    return maxSum;
}
