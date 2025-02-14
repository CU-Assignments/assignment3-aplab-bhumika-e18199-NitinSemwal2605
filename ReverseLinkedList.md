```
class Solution {
public:
    ListNode* reverse(ListNode* head) {
        if (head == NULL) {
            return NULL;
        }
        // Base Case
        if (head->next == NULL) {
            return head;
        }

        ListNode* reversedHead = reverse(head->next); // 2->3->4->5->NULL
        head->next->next = head; // 2->1
        head->next = NULL; // 1->NULL

        return reversedHead; 
    }

    ListNode* reverseList(ListNode* head) { return reverse(head); }
};

```
Image :![image](https://github.com/user-attachments/assets/16de3fd1-5cf7-4463-b97e-711e6f17e569)

