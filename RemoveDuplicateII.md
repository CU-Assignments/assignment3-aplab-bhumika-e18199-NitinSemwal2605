Code :
```
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        // Dummy node to head
        ListNode dummy(0);
        dummy.next = head;

        ListNode* prev = &dummy;  // Previous at dummy
        ListNode* current = head; // Current at head

        while (current != nullptr) {
            // If duplicates
            if (current->next != nullptr &&
                current->val == current->next->val) {
                // Skip all duplicates
                while (current->next != nullptr &&
                       current->val == current->next->val) {
                    current = current->next;
                }
                // Link prev to next
                prev->next = current->next;
            } else {
                // Move prev to current if no duplicates found
                prev = current;
            }
            // Move to next
            current = current->next;
        }

        return dummy.next; // Return new head
    }
};
```

Image :-
![image](https://github.com/user-attachments/assets/15b18ded-448c-424a-a355-4d85f54978f1)
