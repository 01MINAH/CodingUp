### *Pointers in C*
*문제*<br>
Complete the function void update(int *a,int *b). <br>
It receives two integer pointers, int* a and int* b. <br>
Set the value of  to their sum, and  to their absolute difference. <br>
There is no return value, and no return statement is needed.<br>
![image](https://github.com/minahLim/CodingTest/assets/146914181/b60374cf-4bf3-44bf-a361-b93a64e848fe)<br>
![image](https://github.com/minahLim/CodingTest/assets/146914181/f5981aeb-9104-406e-894f-a97b3cde0ff5)<br>
<br>
```c
#include <stdio.h>
#include <stdlib.h>

void update(int* a, int* b) { 
    int sum = *a + *b;
    int sub = abs(*a - *b);

    *a = sum;
    *b = sub;
}

int main() {
    int a, b;
    int* pa = &a, * pb = &b;

    scanf("%d %d", &a, &b);
    update(pa, pb);
    printf("%d\n%d", a, b);

    return 0;
}
```
<p>
 포인터 변수를 인자값으로 함수의 매개변수로 이용하고, 함수 내에서 합과 차를 구한다. 이때 차는 절대값으로 음수가 나올 수 없도록 한다.
c언어에서 절대값은 <stdlib.h> 헤더 파일을 include하여 <strong>abs()</strong>함수를 사용해 구한다.   
</p>

<hr>
출처: 해커랭크<br>
https://www.hackerrank.com/challenges/pointer-in-c/problem?isFullScreen=true


