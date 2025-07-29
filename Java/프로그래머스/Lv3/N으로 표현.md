```java
import java.io.*;
import java.util.*;

class Solution {
    public int solution(int N, int number) {
        int answer = 0;
        
        // N 숫자만을 이요해 number 만들기, 출력은 경우의 수!
        // N 최대 8번
        // DP는 중복 허용 X, therefor HashSet 필요
        
        if ( N == number ) return 1;
        
        List<Set<Integer>> dp = new ArrayList<>();
        
        for (int i = 0; i <= 8; i++) {
            dp.add(new HashSet<>());
        }
        
        for (int i = 1; i <= 8; i++) {
            int num = Integer.parseInt(String.valueOf(N).repeat(i));
            dp.get(i).add(num);
            
            for (int j = 1; j < i; j++) {
                for (int a : dp.get(j)) {
                    for (int b : dp.get(i - j)) {
                        dp.get(i).add(a + b);
                        dp.get(i).add(a - b);
                        dp.get(i).add(a * b);
                        if (b != 0) dp.get(i).add(a / b);
                    }
                }
            }
            
            if (dp.get(i).contains(number)) return i;
        }
        
        return -1;
    }
}
```
