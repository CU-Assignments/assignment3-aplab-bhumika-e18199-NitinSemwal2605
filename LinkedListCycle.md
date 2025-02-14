Code :-
```
class Solution {
public:
    bool hasCycle(ListNode *head) {
        if (head == nullptr)
            return false;

        ListNode* slow = head;
        ListNode* fast = head;

        while (fast != nullptr && fast->next != nullptr) {
            slow = slow->next;
            fast = fast->next->next;

            // cycle hai
            if (slow == fast) {
                return true;
            }
        }

        // No cycle found
        return false;
    }
};
```

Image :- ![image](https://github.com/user-attachments/assets/90f8bbfb-4c9e-4c2a-afc1-a4b39d855d52)
