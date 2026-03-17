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
        
        List<Integer> output = new ArrayList<>();

        // inorder left -> root -> right
        if (root == null) return output;
        dfs(root, output);
        return output;
    }

    private void dfs(TreeNode root, List<Integer> output) {
        if(root == null) return;

        dfs(root.left, output);
        output.add(root.val);
        dfs(root.right, output);
    }
}
```
