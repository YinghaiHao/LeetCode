# Double Pointer

1. [Two sum II-Input array is sorted](https://github.com/YingkaiHao/LeetCode/blob/main/Algorithm/double%20pointer.md#1-two-sum-ii-input-array-is-sorted)

## 1. Two sum II-Input array is sorted

Given an array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number.

Return the indices of the two numbers (1-indexed) as an integer array answer of size 2, where 1 <= answer[0] < answer[1] <= numbers.length.

The tests are generates such that there is exactly one solution. You may not use the same element twice.(problem 167)

Example 1:

Iuput: numbers = [2, 7, 11, 15], target = 9

Output: [1, 2]

Explanation: The sum of 2 and 7 is 9. Therefore index1 = 1, index2 = 2.

Example 2:

Input: numbers = [2, 3, 4], target = 6

Output: [1, 3]

**We use double pointer to solve this problem. One pointer point to the head of the array and traverse from head to tail. Another pointer point to the tail of the array and traverse from the tail to head. We do adjustment below when we face specific situations.**

**1. when sum == target, we get the right result.**

**2. when sum > target, we move the large element to make sum a little smaller.**

**3. when sum < target, we move the small element to make sum a little larger.**

```java
class Solution{
  public int[] twoSum(int[] numbers, int target){
    if(numbers == null) return null;
    int i = 0;
    int j = numbers.length - 1;
    while(i < j){
      int sum = numbers[i] + numbers[j];
      if(sum == target){
        int[] newList = new int[]{i+1, j+1}
        return newList;
      }else if(sum < target){
        i++;
      }else{
        j--;
      }
    }
    return null;
  }
}
```
