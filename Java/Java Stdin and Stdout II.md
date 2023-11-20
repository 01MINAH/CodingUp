### *Java Stdin and Stdout II*
*문제*<br>
<pre>
There are three lines of output:

On the first line, print String: followed by the unaltered String read from stdin.
On the second line, print Double: followed by the unaltered double read from stdin.
On the third line, print Int: followed by the unaltered integer read from stdin.
</pre>
![image](https://github.com/minahLim/CodingTest/assets/146914181/479436db-8251-4f39-8aca-13922600d2de)
```java
import java.util.Scanner;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in); 
        
        int i = scan.nextInt();
        double d = scan.nextDouble();
        scan.nextLine();
        String s = scan.nextLine();

        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```
<pre>
<strong>문자열은 왜 scan.nextLine(); 를 더 붙일까?</strong>
-> chatGPT 답변
Scanner 클래스의 nextInt() 또는 nextDouble() 메서드는 숫자를 읽어오지만, 엔터(\n)를 읽지 않습니다.
따라서, 예를 들어 사용자가 nextInt()로 정수를 입력하고 엔터 키를 누르면, 엔터 키(\n)가 남아있어서 다음 nextLine()이 곧바로 엔터를 읽어버리게 됩니다.
그래서 nextLine()을 추가하여 엔터 키를 소비(consume)하여 사용자가 엔터 키를 입력하더라도 그것이 읽히지 않도록 하는 것이 일반적인 패턴입니다. 
이렇게 함으로써 다음 nextLine()이 사용자로부터 직접 문자열을 입력받을 수 있게 됩니다.

요약:
nextInt()를 호출하여 정수를 읽는다.
nextDouble()을 호출하여 실수를 읽는다.
scan.nextLine();을 호출하여 엔터 키를 소비한다.
nextLine()을 호출하여 사용자로부터 문자열을 입력받는다.
</pre>
<hr>
출처: 해커랭크<br>
https://www.hackerrank.com/challenges/java-stdin-stdout/problem?isFullScreen=true
