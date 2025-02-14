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


Image :
![Uploading image.png…]()
