```java
class Solution {
    int max = 0;

    public int maxDepth(TreeNode root) {
        dfs(1, root);
        return max;
    }

    private void dfs(int depth, TreeNode root) {
        if (root == null) {
            return;
        }

        // 최대 깊이 갱신
        max = Math.max(max, depth);

        dfs(depth + 1, root.left);
        dfs(depth + 1, root.right);
    }
}
```
