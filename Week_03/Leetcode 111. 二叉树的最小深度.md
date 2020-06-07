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

