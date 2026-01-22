```java
class Solution {
    public int search(int[] nums, int target) {
        int low=0;
        int high= nums.length-1; // 배열은 0부터 시작하니까 -1

        return binerySearch(target, low, high, nums);
        
    }

    static int binerySearch(int target, int low, int high, int[] nums) {
        if(low <= high) {
            int mid = (low + high) / 2;

            if(target == nums[mid]) {
                return mid;
            } else if ( target < nums[mid] ) {
                return binerySearch(target, low, mid-1, nums); // 왼쪽
            } else {
                return binerySearch(target, mid+1, high, nums); // 오른쪽
            }
        }
        return -1; // 실패 시 반환되는 '-1'
    }
    
}
```
