## Two Sum

### Problem

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

### Solution

The solution uses a brute-force approach to find the indices of two elements in the input array that add up to the target value. We use two nested loops to iterate over all possible pairs of elements in the array.

For each pair of elements, we check if their sum is equal to the target value. If it is, we assign the indices of the two elements to an array and return it.

### Code

Here's the code for the `twoSum` method:

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int[] result = new int[2];

        for (int i = 0; i < nums.length - 1; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    result[0] = i;
                    result[1] = j;
                    break;
                }
            }
        }

        return result;
    }
}


it uses brute force approach
