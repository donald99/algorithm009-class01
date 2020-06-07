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

