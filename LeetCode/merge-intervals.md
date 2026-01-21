```java
import java.util.*;

class Solution {
    public int[][] merge(int[][] intervals) {
        
        if (intervals.length <= 1) {
            return intervals;
        }

        // 1. 시작점 기준으로 정렬
        Arrays.sort(intervals, (a, b) -> a[0] - b[0]);

        // [선언] 결과 저장 리스트
        List<int[]> merged = new ArrayList<>();

        // 2. 첫 번재 구간을 기준으로 시작
        int start = intervals[0][0];
        int end = intervals[0][1];

        // 3. 두 번째 구간부터 순회
        for (int i = 1; i < intervals.length; i++) {
            int nextStart = intervals[i][0];
            int nextEnd = intervals[i][1];

            // 4. 겹치는 경우
            if (nextStart <= end) {
                end = Math.max(end, nextEnd);
            } else { // 5. 겹치지 않는 경우
                merged.add(new int[]{start, end});

                // 새 구간 시작
                start = nextStart;
                end = nextEnd;
            }
        }

        // 6. 마지막 구간 => 반복문 밖에서 추가
        merged.add(new int[]{start, end});

        // 7. List -> int[][] 로 변환
        return merged.toArray(new int[merged.size()][]);
    }
}
```
