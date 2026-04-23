```java
class Solution {
    public int myAtoi(String s) {
        if(s==null || s.length() == 0) return 0;

        int i = 0;
        int n = s.length();

        while(i < s.length() && s.charAt(i) == ' ') i++;

        int sign = 1;
        if( i < n && (s.charAt(i) == '+' || s.charAt(i) == '-')) {
            sign = (s.charAt(i) == '-') ? -1 : 1;
            i++;
        }

        // 숫자 변환
        // Character.isDigit(char ch) 형식으로 사용하여, 숫자인 경우 true, 아니면 false를 리턴
        int result = 0;
        while(i < n && Character.isDigit(s.charAt(i))) { 
            int digit = s.charAt(i) - '0';

            // 오버플로우 체크(int 범위 넘는지 체크)
            if (result > Integer.MAX_VALUE / 10 || (result == Integer.MAX_VALUE / 10 && digit > 7)) {
                return (sign == 1) ? Integer.MAX_VALUE : Integer.MIN_VALUE;
            }

            result = result * 10 + digit;
            i++;
        }
        return result * sign;

    }
}
```
