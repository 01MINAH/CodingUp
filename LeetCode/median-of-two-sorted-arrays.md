```java
class Solution {
    public double findMedianSortedArrays(int[] nums1, int[] nums2) {
        // 1. 병합
        int m = nums1.length, n = nums2.length;
        int[] merged = new int[m + n];

        int idx = 0;
        for (int num : nums1) merged[idx++] = num;
        for (int num : nums2) merged[idx++] = num;
        
        // 2. 정렬
        Arrays.sort(merged);

        int len = merged.length;

        // 3. 홀수 / 짝수 판단
        if (len % 2 == 1) {
            return merged[len / 2];
        } else { // 4. 짝수면 중간 값 두 개 더해서 나누기
            return (merged[len / 2 - 1] + merged[len / 2]) / 2.0;
        }

    }
}
```
