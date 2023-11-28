### *Java If-Else*

*문제*<br>
<pre>
Given an integer, n, perform the following conditional actions:

If n is odd, print Weird
If n is even and in the inclusive range of 2 to 5, print Not Weird
If n is even and in the inclusive range of 6 to 20, print Weird
If n is even and greater than 20, print Not Weird
Complete the stub code provided in your editor to print whether or not n is weird.
</pre>
  ![image](https://github.com/minahLim/CodingTest/assets/146914181/116a273f-52cf-4393-ad45-fcd6cd679639)
<br>
```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");
        
        if (N % 2 == 0) { 
            if (2 <= N && N <= 5) {
                System.out.println("Not Weird");
            } else if (6 <= N && N <= 20) {
                System.out.println("Weird");
            } else if (N > 20) {
                System.out.println("Not Weird");
            }
        } else {
            System.out.println("Weird"); 
        }

        scanner.close();
    }
}
```
<pre>
분석:
n이 홀수 : Weird
n이 짝수 and 2~5 사이 : Not Weird
n이 짝수 and 6~20사이: Weird
n이 짝수 and 20보다 위: Not Weird

*홀수는 무조건 Weird
*짝수 6~20 Werid
</pre>

<hr>
출처: 해커랭크<br>
https://www.hackerrank.com/challenges/java-if-else/problem?isFullScreen=true
