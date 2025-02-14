Code :
```
class Solution {
public:
    ListNode* rotateRight(ListNode* head, int k) {

        if(head== NULL || head-> next == NULL)  // Edge Cases
            return head;
        // Count number of Nodes
        int count = 0;
        ListNode*temp = head;

        while(temp){
            count ++;
            temp = temp->next;
        }
        k = k%count ;     // In Case K is Large
            if (k== 0)
                return head;
        count -=k;


        ListNode*curr=head;   // us k tk traverse karo 
        ListNode*prev=NULL;

        while(count --){
            prev = curr;
            curr = curr-> next;
        };

        prev->next=NULL;
        ListNode*Tail = curr;   // now curr ko tail bolde 

        while(Tail-> next != NULL){  // now come to tail end 
            Tail = Tail -> next;
        };

        Tail-> next = head;  // link it with head and return curr
        return curr;

    }
};
```


![image](https://github.com/user-attachments/assets/1411b1e1-7e24-4189-bae3-ba5f300cf4ee)
