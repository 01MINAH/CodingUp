내가 푼 방법은 아래처럼 풀었는데, 해쉬맵으로 더 gydbfwjrdmfh 풀 수 있다고 한다.

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int sum;

        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] {i, j};
                }
            }
        }
        return new int[] {};
    }
}
```

해쉬맵은 다음과 같다고한다.<br>
아직 해쉬맵을 응용하기엔 더 많은 연습이 필요할 것 같다.<br>
조건을 보자! 1. 중복 X 2. map에 값 저장으로 인한 효율적인 계산 
```java
import java.util.*;

class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> map = new HashMap<>();

        for (int i = 0; i < nums.length; i++) {
            int complement = target - nums[i]; // 필요한 값
            if (map.containsKey(complement)) {
                return new int[] {map.get(complement), i};
            }
            map.put(nums[i], i); // 현재 숫자와 인덱스 저장
        }

        return new int[] {}; // 없을 경우
    }
}
---
📌 containsKey(Object key)

역할: 맵 안에 특정 key가 존재하는지 확인

리턴 타입: boolean (있으면 true, 없으면 false)
```
