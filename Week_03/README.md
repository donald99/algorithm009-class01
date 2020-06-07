### 推荐一个Blog

https://leetcode.wang/

https://zhuanlan.zhihu.com/leetcode1024



## 递归

**递归解题三部曲**

什么是递归？程序反复调用自身即是递归。

递归是一个反复调用自身的过程，这就说明它每一级的功能都是一样的，**因此我们只需要关注一级递归的解决过程即可。**

![](https://p2.ssl.qhimg.com/t01d9cb90e49d853fdf.png)

**解递归题的三部曲：**

1. **找整个递归的终止条件：递归应该在什么时候结束？**
2. **找返回值：应该给上一级返回什么信息？**
3. **本级递归应该做什么：在这一级递归中，应该完成什么任务？**

### 思维要点：

1、人肉暴力递归（千万不要进入这个误区，人类大脑不擅长这样，会把自己绕晕）

2、找到最近最简单的方法，将其拆分为可以重复的问题（重复子问题，放鞭炮🧨）人在制造人类的时候，也是具有重复性的。

3、数学归纳法总结（最开始最简单的条件成立，比如n=1、n=2成立，且能够证明n成立的时候，可以推导出n+1也是成立的，放鞭炮🧨）



**Java 代码模板**(<u>必须记住</u>)

```java
// Java
public void recur(int level, int param) { 
  // terminator 递归的终止条件
  if (level > MAX_LEVEL) { 
    // process result  找返回值
    return; 
  }
  // process current logic 本级递归应该做什么
  process(level, param); 
  // drill down      下一级递归
  recur( level: level + 1, newParam); 
  // restore current status  清扫当前状态
}
```

#### 

#### 递归的基本性质：

   函数调⽤本身

   把⼤规模的问题不断地变⼩，再进⾏推导的过程





## 举例子：

0、[括号生成](https://leetcode-cn.com/problems/generate-parentheses/) 

```java
class GenerateParenthesis {

    public static void main(String[] args) {
        GenerateParenthesis g1 = new GenerateParenthesis();
//        g1.generate(0,2 * 3, "");
        g1.generate(0, 0 , 3, "");
    }

    ArrayList<String> list = new ArrayList<>();

    // 这里好像前序遍历？？？
    void generate(int left , int right , int n , String str) {
        //条件：1、left 个数别超过n ； 2、left括号 个数 > right括号 个数

        if (left == n && right == n) {
            System.out.println(str);
            list.add(str);
            return ;
        }

        //process current login : right , left

        //drill down
        if (left < n) {
            generate( left + 1, right, n, str + "(");
        }

        if (left > right && right < n) { //  right < left < n
            generate( left,right + 1 , n, str + ")");
        }

        //restore states
    }

    //level 当前等级，max 最大level个数 2 * n ，这个方法不验证合法性的，看一下输出结果
    void generate(int level,int max,String str) {
        //terminator
        if(level >= max){
            System.out.println(str);
            return ;
        }
//        process current login : right , left
        String s1 = str + "(";
        String s2 = str + ")";

//        drill down
        generate(level + 1, max, s1);

        generate(level + 1, max, s2);

//        restore states

    }
}
// @lc code=end

// Java
// public void recur(int level, int param) { 
//     // terminator 递归的终止条件
//     if (level > MAX_LEVEL) { 
//       // process result  找返回值
//       return; 
//     }
//     // process current logic 本级递归应该做什么
//     process(level, param); 
//     // drill down      下一级递归
//     recur( level: level + 1, newParam); 
//     // restore the current status  清扫当前状态
//   }
```





### 1、**求二叉树的最大深度**

![](https://p4.ssl.qhimg.com/t0128741e6315e0b456.png)

```java
// Java
// public void recur(int level, int param) { 
//     // terminator 递归的终止条件
//     if (level > MAX_LEVEL) { 
//       // process result  找返回值
//       return; 
//     }
//     // process current logic 本级递归应该做什么
//     process(level, param); 
//     // drill down      下一级递归
//     recur( level: level + 1, newParam); 
//     // restore the current status  清扫当前状态
//   }

class Solution {
    public int maxDepth(TreeNode root) {
        //1、终止条件：当树为空时结束递归，并返回当前深度0
        if(root == null){
            return 0; //2、返回值
        }
      
        //3、root的左、右子树的最大深度
        int leftDepth = maxDepth(root.left);
        int rightDepth = maxDepth(root.right);
        ///3、返回的是左右子树的最大的深度+1
        int max = Math.max(leftDepth, rightDepth) + 1;
      
        return max;
    }
  
  public int maxDepth(TreeNode root) {
        return root == null ? 0 : Math.max(maxDepth(root.left), maxDepth(root.right)) + 1;
    }
}
```



### 2、两两交换链表中的节点

![](https://p4.ssl.qhimg.com/t01f7dd50b786184bc5.png)

```java
class Solution {
    public ListNode swapPairs(ListNode head) {
      	//终止条件：链表只剩一个节点或者没节点了，没得交换了。返回的是已经处理好的链表
        if(head == null || head.next == null){
            return head;
        }
      	//一共三个节点:head, next, swapPairs(next.next)
      	//下面的任务便是交换这3个节点中的前两个节点
        ListNode next = head.next;
        head.next = swapPairs(next.next);
        next.next = head;
      	//根据第二步：返回给上一级的是当前已经完成交换后，即处理好了的链表部分
        return next;
    }
}
```

### 3、平衡二叉树

什么是平衡二叉树？

平衡二叉树即左右两棵子树   高度差不大于1   的二叉树。

而对于一颗树，它是一个平衡二叉树需要满足三个条件：

**a、它的左子树是平衡二叉树，**

**b、它的右子树是平衡二叉树，**

**c、它的左右子树的高度差不大于1**。

换句话说：如果它的左子树或右子树不是平衡二叉树，或者它的左右子树高度差大于1，那么它就不是平衡二叉树。

```java
class Solution {
    //这个ReturnNode是参考我描述的递归套路的第二步：思考返回值是什么
    //一棵树是BST等价于它的  左、右俩子树都是BST  且俩子树高度差不超过 1
    //因此我认为返回值应该包含当前树是否是BST和当前树的高度这两个信息
    private class ReturnNode{
        boolean isB;
        int depth;
        public ReturnNode(int depth, boolean isB){
            this.isB = isB;
            this.depth = depth;
        }
    }
    //主函数
    public boolean isBalanced(TreeNode root) {
        return isBST(root).isB;
    }
    //参考递归套路的第三部：描述单次执行过程是什么样的
    //这里的单次执行过程具体如下：
    //是否终止?->没终止的话，判断是否满足不平衡的三个条件->返回值
    public ReturnNode isBST(TreeNode root){
        if(root == null){
            return new ReturnNode(0, true);
        }
        //不平衡的情况有3种：左树不平衡、右树不平衡、左树和右树差的绝对值大于1
        ReturnNode left = isBST(root.left);
        ReturnNode right = isBST(root.right);
        if(left.isB == false || right.isB == false){
            return new ReturnNode(0, false); 
        }
        if(Math.abs(left.depth - right.depth) > 1){
            return new ReturnNode(0, false);
        }
        //不满足上面3种情况，说明平衡了，树的深度为左右俩子树最大深度 + 1
        return new ReturnNode(Math.max(left.depth, right.depth) + 1, true);
    }
}
```



[Leetcode 101. 对称二叉树](https://leetcode-cn.com/problems/symmetric-tree/comments/)

```java
class Solution {
	public boolean isSymmetric(TreeNode root) {
		if(root == null) {
			return true;
		}
		//调用递归函数，比较左节点，右节点
		return dfs(root.left,root.right);
	}
	
	boolean dfs(TreeNode left, TreeNode right) {
		//递归的终止条件: 是两个节点都为空
		if(left == null && right == null) {
			return true;
		}
    //递归的终止条件: 两个节点中有一个为空
		if(left == null || right == null) {
			return false;
		}
    //递归的终止条件: 两个节点的值不相等
		if(left.val != right.val) {
			return false;
		}
		//再递归的比较  左节点的左孩子 和 右节点的右孩子
		//      比较  左节点的右孩子 和 右节点的左孩子
		return dfs(left.left,right.right) && dfs(left.right,right.left);
	}
}
```



[Leetcode 111. 二叉树的最小深度](https://leetcode-cn.com/problems/minimum-depth-of-binary-tree/)

```java
class Solution {
    public int minDepth(TreeNode root) {
        //递归条件终止条件1.root==null直接返回0
        if(root == null) return 0;
        //递归条件终止条件1.左孩子和有孩子都为空的情况，说明到达了叶子节点，直接返回1即可
        if(root.left == null && root.right == null) return 1;
        int md1 = minDepth(root.left);
        int md2 = minDepth(root.right);
        //递归条件终止条件3.这里其中一个节点为空，说明m1和m2有一个必然为0，所以可以返回m1 + m2 + 1;
        if(root.left == null || root.right == null) return md1 + md2 + 1;
        //最后，也就是左右孩子都不为空，返回最小深度 +1 即可
        return Math.min(md1,md2) + 1; 
    }
}
```



[Leetcode 226. 翻转二叉树](https://leetcode-cn.com/problems/invert-binary-tree/)

这个题的备注是最骚的。

Mac OS下载神器homebrew的大佬作者去面试谷歌，没做出来这道算法题，然后被谷歌面试官怼了：”我们90％的工程师使用您编写的软件(Homebrew)，但是您却无法在面试时在白板上写出翻转二叉树这道题，这太糟糕了。”

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */

public TreeNode invertTree(TreeNode root) {
    if (root == null) {
        return null;
    }
    TreeNode right = invertTree(root.right);
    TreeNode left = invertTree(root.left);
    root.left = right;
    root.right = left;
    return root;
}

//时间复杂度就是 O(n)
//空间复杂度为 O(n)
```



[Leetcode 617. 合并二叉树](https://leetcode-cn.com/problems/merge-two-binary-trees/)



[Leetcode 654. 最大二叉树](https://leetcode-cn.com/problems/maximum-binary-tree/)



[Leetcode 83. 删除排序链表中的重复元素](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-list/)

[Leetcode 297.二叉树的序列化与反序列化](https://leetcode-cn.com/problems/serialize-and-deserialize-binary-tree/)



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




[Leetcode 263 二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/)



[Leetcode 105 从前序与中序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal)



[Leetcode 77 组合](https://leetcode-cn.com/problems/combinations/)



[Leetcode 46 全排列](https://leetcode-cn.com/problems/permutations/)



[Leetcode 47 全排列 II ](https://leetcode-cn.com/problems/permutations-ii/)



参考链接：https://lyl0724.github.io/2020/01/25/1/



## 分治（Divide & Conquer）

### 分治的思想

本质是递归，在递归状态树的时候，对一个问题会化解成好几个子问题，

![](https://pic4.zhimg.com/v2-c31c5d563df322aadcefdfde685510b3_r.jpg)

把上图的问题先拆分成子问题，每个子问题就是相应每个字符，需要将每一个字符都转换成大写，最后再拼回去。

### 代码模版

```python
def divide_conquer(problem, param1, param2, ...):
    # recursion terminator 终止条件
    if problem is None:
        print_result
        return
    # prepare data  处理当前层逻辑
    data = prepare_data(problem)
    subproblems = split_problem(problem, data)
    # conquer subproblems  调用函数下探到下一层，解决更细节的子问题
    subresult1 = self.divide_conquer(subproblems[0], p1, ...)
    subresult2 = self.divide_conquer(subproblems[1], p1, ...)
    subresult3 = self.divide_conquer(subproblems[2], p1, ...)
    ...
    # process and generate the final result
    result = process_result(subresult1, subresult2, subresult3, ...)

    # revert the current level states
    # 与泛型递归不同就是在drill down与revert state中间加了一步
    # ---> 就是把drill down得到的子结果要合并在一起，返回回去。
```



#### [169. 多数元素](https://leetcode-cn.com/problems/majority-element/)

给定一个大小为 n 的数组，找到其中的多数元素。多数元素是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。

你可以假设数组是非空的，并且给定的数组总是存在多数元素。

#### 思路

如果数 a 是数组 nums 的众数，如果我们将 nums 分成两部分，那么 a 必定是至少一部分的众数。

我们可以使用反证法来证明这个结论。假设 a 既不是左半部分的众数，也不是右半部分的众数，那么 a 出现的次数少于 l / 2 + r / 2 次，其中 l 和 r 分别是左半部分和右半部分的长度。由于 l / 2 + r / 2 <= (l + r) / 2，说明 a 也不是数组 nums 的众数，因此出现了矛盾。所以这个结论是正确的。

这样以来，我们就可以使用分治法解决这个问题：将数组分成左右两部分，分别求出左半部分的众数 a1 以及右半部分的众数 a2，随后在 a1 和 a2 中选出正确的众数。

#### 算法

我们使用经典的分治算法递归求解，直到所有的子问题都是长度为 1 的数组。长度为 1 的子数组中唯一的数显然是众数，直接返回即可。如果回溯后某区间的长度大于 1，我们必须将左右子区间的值合并。如果它们的众数相同，那么显然这一段区间的众数是它们相同的值。否则，我们需要比较两个众数在整个区间内出现的次数来决定该区间的众数。



## 回溯（Backtracking）

回溯本质：

  利⽤递归的性质

  从问题的起始点出发，不断尝试

  返回⼀步甚⾄多步再做选择，直到抵达终点的过程



暴力搜索法中的一种，递归的一种问题，不断地在每一层去试，每一层有不同的办法，类似于一个一个去试，看这个方法是否可行。

对于某些计算问题而言，回溯法是一种可以找出所有（或一部分）解的一般性算法，尤其适用于约束满足问题（在解决约束满足问题时，我们逐步构造更多的候选解，并且在确定某一部分候选解不可能补全成正确解之后放弃继续搜索这个部分候选解本身及其可以拓展出的子候选解，转而测试其他的部分候选解）。

在经典的教科书中，**[八皇后问题](https://zh.wikipedia.org/wiki/八皇后问题)**展示了回溯法的用例。（八皇后问题是在标准国际象棋棋盘中寻找八个皇后的所有分布，使得没有一个皇后能攻击到另外一个。）

![](https://www.cxyxiaowu.com/wp-content/uploads/2020/04/1586003157-e18fa33aa575f63-1.png)

![八皇后](https://p5.ssl.qhimg.com/t01d8762c4cb7203719.png)

回溯法采用[试错](https://zh.wikipedia.org/wiki/试错)的思想，它尝试分步的去解决一个问题。在分步解决问题的过程中，当它通过尝试发现现有的分步答案不能得到有效的正确的解答的时候，它将取消上一步甚至是上几步的计算，再通过其它的可能的分步解答再次尝试寻找问题的答案。回溯法通常用最简单的[递归](https://zh.wikipedia.org/wiki/递归)方法来实现，在反复重复上述的步骤后可能出现两种情况：

- 找到一个可能存在的正确的答案
- 在尝试了所有可能的分步方法后宣告该问题没有答案

在最坏的情况下，回溯法会导致一次[复杂度](https://zh.wikipedia.org/wiki/计算复杂性理论)为[指数时间](https://zh.wikipedia.org/wiki/指數時間)的计算。



八个皇后在8x8棋盘上共有4,426,165,368（[64C8](https://zh.wikipedia.org/wiki/組合)）种摆放方法，但只有92个**互不相同**的解。如果将旋转和对称的解归为一种的话，则一共有12个独立解，具体如下：

![](https://p5.ssl.qhimg.com/t01be1e4eee194b6e07.png)

