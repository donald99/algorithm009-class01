two-sum

```java
//暴力法很简单，遍历每个元素 xx，并查找是否存在一个值与 target - x 相等的目标元素。时间复杂度O(n^2),空间复杂度：O(1)。
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (target - nums[i] == nums[j]) {
                    return new int[] { i, j };
                }
            }
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}
```



```java
//一遍hash法时间复杂度：O(n)，空间复杂度：O(n)
//只遍历含有 n 个元素的列表一次。在表中进行的每次查找只花费 O(1) 的时间。
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i];
            if (map.containsKey(complement)) {
                return new int[] { map.get(complement), i };
            }
            map.put(nums[i], i);
        }
        throw new IllegalArgumentException("No two sum solution");
    }
}
```