#```연산자``` #```operator```
# Sum of Digits of a Five Digit Number
**문제** 
### Objective
The modulo operator, %, returns the remainder of a division. For example, 4 % 3 = 1 and 12 % 10 = 2. The ordinary division operator, /, returns a truncated integer value when performed on integers. For example, 5 / 3 = 1. To get the last digit of a number in base 10, use  as the modulo divisor.

### Task
Given a five digit integer, print the sum of its digits.

### Input Format
The input contains a single five digit number, .

### Constraints
10000<=n<=99999

### Output Format
Print the sum of the digits of the five digit number.
<br><br>
* 원활한 이해를 위해 printf나 주석 추가
```c
#include <stdio.h>
#include <string.h>
#include <math.h>
#include <stdlib.h>

int main() {

    int n, sum = 0;
    scanf_s("%d", &n);

    if (n >= 10000 && n <= 99999) {
        while (n > 0) {
            printf("n % 10: %d\n", n % 10); // 나머지
            printf("n /= 10: %d\n\n", n / 10); // 몫

            sum += n % 10;
            n /= 10;
        }
        printf("sum: %d\n", sum);
    }
    else {
        printf("please enter a valid five-digit integer.\n");
    }
    return 0;

    return 0;
}
```
<hr>
출처: 해커랭크
https://www.hackerrank.com/challenges/sum-of-digits-of-a-five-digit-number/problem?isFullScreen=true
