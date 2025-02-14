Code :
```
class Solution {
public:
    ListNode* reverseBetween(ListNode* head, int left, int right) {
        ListNode* Dummy = new ListNode(0);
        Dummy->next = head;

        ListNode* LeftPrev = Dummy; // Node before Left 
        ListNode* curr = head;

        for (int i = 0; i < left - 1; i++) {
            LeftPrev = curr; // Prev of Left 
            curr = curr->next; // to left 
        }

        ListNode* prev = nullptr;
        for (int i = 0; i < right - left + 1; i++) {
            ListNode* tempNext = curr->next;
            curr->next = prev;
            prev = curr;
            curr = tempNext;
        }

        LeftPrev->next->next = curr;
        LeftPrev->next = prev;
        return Dummy->next;
    }
};
```

Image :- ![image](https://github.com/user-attachments/assets/0b9d4496-00a4-4ef1-9476-2f748c1d57d9)
