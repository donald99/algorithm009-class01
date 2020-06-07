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

