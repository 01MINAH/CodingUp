```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode sortList(ListNode head) {

        int temp = 0;
        ListNode current = head;

        while (current != null) {

            ListNode next = current.next;
            ListNode min = current;

            while (next != null) {
                if (min.val > next.val) {
                    min = next;
                }
                next = next.next;
            }

            temp = current.val;
            current.val = min.val;
            min.val = temp;

            current = current.next;
        }

        return head;
    }
}
```
