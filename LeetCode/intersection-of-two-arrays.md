```java
class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        Set<Integer> set1 = new HashSet<Integer>();
        Set<Integer> set2 = new HashSet<Integer>();

        for(int n : nums1){
            set1.add(n);
        }

        for(int n : nums2){
            set2.add(n);
        }

        set1.retainAll(set2);

        return set1.stream().mapToInt(Integer::intValue).toArray();
    }
}
```
