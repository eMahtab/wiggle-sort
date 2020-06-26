# Wiggle Sort
### https://www.lintcode.com/problem/wiggle-sort

Given an unsorted array nums, reorder it in-place such that nums[0] <= nums[1] >= nums[2] <= nums[3]....
For example, given nums = [3, 5, 2, 1, 6, 4], one possible answer is [1, 6, 2, 5, 3, 4].

### Approach :
If we carefully see the pattern in the question. 

We can see that A[0] <= A[1] >= A[2] <= A[3] >= A[4] <= A[5]

So we could actually observe that there is pattern
`A[even] <= A[odd]` and `A[odd] >= A[even]`

Therefore we can iterate over the array and compare the elements at index `i` and `i+1`.
If we find that above condition is not satisfied at index `i` in the array, then we can just swap the elements at index `i` and `i+1`.

### Implementation :

```java
  class Solution {
    public void wiggleSort(int[] nums) {
        if (nums == null || nums.length < 2)
            return;
        for(int i = 0; i < nums.length - 1; i++) {
            if(i % 2 == 0 && nums[i] > nums[i+1])
                swap(nums, i, i+1);
            else if(i % 2 == 1 && nums[i] < nums[i+1])
                swap(nums, i, i+1);
        }
    }
    
    private void swap(int[] nums, int i , int j) {
        int temp = nums[i];
        nums[i] = nums[j];
        nums[j] = temp;
    }
}
```
Above implementation have runtime complexity of O(n) and space complexity of O(1)

```
Runtime Complexity = O(n)
Space Complexity   = O(1)
```

## References:
http://buttercola.blogspot.com/2015/09/leetcode-wiggle-sort.html
