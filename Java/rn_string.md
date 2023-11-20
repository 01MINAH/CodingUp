### *rny_string*

*문제*
'm'과 "rn"이 모양이 비슷하게 생긴 점을 활용해 문자열에 장난을 하려고 합니다. 
문자열 rny_string이 주어질 때, rny_string의 모든 'm'을 "rn"으로 바꾼 문자열을 return 하는 solution 함수를 작성해 주세요.

```java
class Solution {
    public String solution(String rny_string) {
        String answer = "";
        answer = rny_string.replace("m", "rn");
        return answer;
    }
}
```

출처: 프로그래머스 코딩테스트 사이트
https://school.programmers.co.kr/learn/courses/30/lessons/181863?language=java

