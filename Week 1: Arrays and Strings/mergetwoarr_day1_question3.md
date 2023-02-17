## Merge Sorted Array

### Problem

Given two sorted integer arrays `nums1` and `nums2`, merge `nums2` into `nums1` as one sorted array.

The number of elements initialized in `nums1` and `nums2` are `m` and `n` respectively. You may assume that `nums1` has enough space (size that is equal to `m + n`) to hold additional elements from `nums2`.

### Solution

The solution to this problem is to use a two-pointer approach. We start with two pointers, `i` and `j`, that point to the last element of `nums1` and `nums2`, respectively. We also have a third pointer, `k`, that points to the last empty position in `nums1`.

We compare the last elements of `nums1` and `nums2`, and place the larger of the two at `nums1[k]`. We then decrement the corresponding pointer and `k`. We continue this process until all elements of `nums2` have been merged into `nums1`.

If there are still remaining elements in `nums1`, we do not need to do anything, since they are already in their correct positions.

### Code

Here's the code for the `merge` method:

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = nums1.length - 1;

        while (j >= 0) {
            if (i >= 0 && nums1[i] > nums2[j]) {
                nums1[k] = nums1[i];
                k--;
                i--;
            } else {
                nums1[k] = nums2[j];
                k--;
                j--;
            }
        }
    }
}


This code uses a two-pointer approach to merge two sorted arrays. It merges the elements of nums2 into nums1 in place, without using any extra memory. The resulting nums1 array is also sorted.