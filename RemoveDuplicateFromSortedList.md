```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        // Empty list 
        if(head == NULL){
            return NULL;
        }
        // Non-Empty List 
        ListNode* curr = head;
        while(curr != NULL){
            if(curr->next != NULL && curr->val == curr->next->val){
                ListNode* nodetoremove = curr->next;
                ListNode* next_node = curr->next->next;
                delete nodetoremove;
                curr->next = next_node;
            } else {
                curr = curr->next;
            }
        }
        return head;
    }
};


```
IMAGE :- ![image](https://github.com/user-attachments/assets/01156b2f-c0cd-42ab-9aca-7a16e17610da)

