[Leetcode 70.爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/)

一、暴力解法：

```
class Solution {
  //分别列举出不同台阶会有多少种步法，归纳法总结出，符合斐波那契数列 F(n) = F(n-2) + F(n-1)
    public int climbStairs(int n) {
        if (n < 2) {
            return 1;
        }
        return climbStairs(n - 2) + climbStairs(n - 1);
    }
}
```

复杂度分析

- 时间复杂度：O(2^n)，树形递归的大小为 2^n

- 空间复杂度：O(n)，递归树的深度可以达到 n

  

  n=5的递归示意图

  ![n=5的递归示意图](https://pic.leetcode-cn.com/07a21d45a33309d39925127eb0a8611fce5212cb932e4a6fe9914b30c885d1f6-file_1555697913334)

二、备忘录解法

又可称为剪枝法。

把每一步的结果存储在 memo 数组之中，每当函数再次被调用，我们就直接从 memo 数组返回结果.。这样最后大小减少到 n 

```
public class Solution {
    public int climbStairs(int n) {
        int m[] = new int[n + 1];
        return climb_Stairs(0, n, m);
    }
    public int climb_Stairs(int i, int n, int m[]) {
        if (n < 2) {
            return 1;
        }
        if (m[i] > 0) {
            return m[i];
        }
        m[i] = climb_Stairs(i + 1, n, m) + climb_Stairs(i + 2, n, m);
        return m[i];
    }
}
```

**复杂度分析**

- 时间复杂度：O(n)，树形递归的大小可以达到 n

- 空间复杂度：O(n)，递归树的深度可以达到 n

  

三、动态规划

```
public class Solution {
    public int climbStairs(int n) {
        if (n == 1) {
            return 1;
        }
        int[] dp = new int[n + 1];
        dp[1] = 1;
        dp[2] = 2;
        for (int i = 3; i <= n; i++) {
            dp[i] = dp[i - 1] + dp[i - 2];
        }
        return dp[n];
    }
}
```



四，斐波那契公式



![](https://p2.ssl.qhimg.com/t01012cd57e744214f5.png)



```java
public class Solution {
    public int climbStairs(int n) {
        double sqrt5 = Math.sqrt(5);
        double fibn = Math.pow((1 + sqrt5) / 2,n+1) - Math.pow((1 - sqrt5) / 2,n+1);
        return (int)(fibn / sqrt5);
    }
}
```

复杂度分析

- 时间复杂度：O(log(n))，pow 方法将会用去 log(n) 的时间。
- 空间复杂度：O(1)，使用常量级空间。