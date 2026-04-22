```java
// 백트랙킹(dfs)

class Solution {
    public List<String> generateParenthesis(int n) {
        List<String> result = new ArrayList<>();
        String current = "";

        dfs(result, current, 0, 0, n);

        return result;

    }

    void dfs(List<String> result, String current, int open, int close, int n) {
        if(current.length() == 2 * n) {
            result.add(current);
            return;
        }

        if(open < n) {
            dfs(result, current + "(", open+1, close, n);
        }

        if(close < open) {
            dfs(result, current + ")", open, close + 1, n);
        }
    }
}
```
