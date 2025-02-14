```
class Solution {
public:
    ListNode* deleteMiddle(ListNode* head) {
        if (head == NULL || head->next == NULL) {
            return NULL;
        }

        ListNode* slow = head;
        ListNode* fast = head;
        ListNode* prev = NULL; 

        while (fast != NULL && fast->next != NULL) {
            prev = slow;
            slow = slow->next;
            fast = fast->next->next;
        }

        // Remove the middle node
        if (prev != NULL && prev->next != NULL) {
            prev->next = prev->next->next;
        }

        return head;
    }
};

```
Image :- ![image](https://github.com/user-attachments/assets/8ff2b24e-1ab6-4229-aaa1-e60e7c51f7af)
