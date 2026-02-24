```java
class Solution {
    public int hammingDistance(int x, int y) {
        return Integer.bitCount(x ^ y);
    }
}
```

Integer.bitCount함수가 있다는 것을 알게 되었다.
