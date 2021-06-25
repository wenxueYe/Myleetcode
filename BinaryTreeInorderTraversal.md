> https://leetcode.com/problems/binary-tree-inorder-traversal/
>
> Binary Tree Inorder Traversal

```java

/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode() {}
 *     TreeNode(int val) { this.val = val; }
 *     TreeNode(int val, TreeNode left, TreeNode right) {
 *         this.val = val;
 *         this.left = left;
 *         this.right = right;
 *     }
 * }
 */
class Solution {
    public List<Integer> inorderTraversal(TreeNode root) {
        List<Integer> result = new ArrayList<>();
        Stack<TreeNode> stack = new Stack<>();
        TreeNode tmp = root;
        /*
            如果栈不为空，或者树不为空
            1.沿着根的左孩子，依次入栈，直到左孩子为空；
            2.栈顶元素出栈
                1.如果右孩子为空，则继续执行2
                2.如果右孩子不为空，则执行1
        */
        while(tmp!=null || !stack.isEmpty()) {
            while(tmp!=null) {
                stack.push(tmp);
                tmp = tmp.left;
            }
            tmp = stack.pop();
            result.add(tmp.val);
            tmp = tmp.right;
        }
        return result;
    }
}
```

