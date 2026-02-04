```java
import java.util.*;
import java.io.*;

class Solution {

    static int[] number;
    static String[] symbol;

    static int[] arr;

    public String intToRoman(int num) {

        number = new int[]{1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};
        symbol = new String[]{"M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"};

        return calcNum(num);


    }

    static public String calcNum(int num) {
        StringBuilder sb = new StringBuilder();

        for(int i = 0; i < number.length; i++) {
            while( num>=number[i]) {
                sb.append(symbol[i]);
                num -= number[i];
            }
        }

        return sb.toString();
    }
}
```
