Code : 
```
class Solution {
public:
    ListNode* merge(ListNode* left, ListNode* right) {
        ListNode* dummy = new ListNode(0);
        ListNode* curr = dummy;

        // Merge the two lists
        while (left && right) {
            if (left->val < right->val) {
                curr->next = left;
                left = left->next;
            } else {
                curr->next = right;
                right = right->next;
            }
            curr = curr->next;
        }

        // Add remaining elements
        if (left) curr->next = left;
        if (right) curr->next = right;

        return dummy->next;
    }

    ListNode* mergeSort(ListNode* head) {
        if (!head || !head->next) return head; // Base Case

        //middle of list
        ListNode* slow = head;
        ListNode* fast = head->next;
        while (fast && fast->next) {
            slow = slow->next;
            fast = fast->next->next;
        }

        ListNode* right = mergeSort(slow->next); 
        slow->next = nullptr; 
        ListNode* left = mergeSort(head); 

        return merge(left, right);
    }

    ListNode* sortList(ListNode* head) {
        return mergeSort(head);
    }
};
```
![image](https://github.com/user-attachments/assets/e7367d23-ca16-49de-8d62-e7a161b3d2bd)

