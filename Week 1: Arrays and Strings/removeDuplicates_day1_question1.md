## Remove Duplicates from Sorted Array

### Problem

Given a sorted array `nums`, remove the duplicates in-place such that each element appears only once and returns the new length.

You must do this by modifying the input array in-place with O(1) extra memory.

### Solution

The solution uses a two-pointer approach to keep track of the current and next elements in the array. We start by initializing `index` to 1, since the first element in the array is always unique.

Then we iterate over the array using a for loop, comparing each element with the next element. If the current element is less than the next element, we know that the next element is unique and we can assign it to the `index` position in the array. We then increment `index` to move to the next position.

At the end of the loop, `index` will represent the new length of the modified array. We then return this value.

### Code

Here's the code for the `removeDuplicates` method:

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        int index = 1;

        for (int i = 0; i < nums.length - 1; i++) {
            if (nums[i] < nums[i + 1]) {
                nums[index] = nums[i + 1];
                index++;
            }
        }

        return index;
    }
}
