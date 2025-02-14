Code :-
```
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        // If List1 is null then return the second list.
        if(list1  == NULL){
            return list2;
        }
        
        // If list2 is null then return the first list .
        if(list2 == NULL){
            return list1;
        }
        
        // If value from 1st pointer is less the equal to second list then call l1 -> next = whole list 2.4
        if(list1 -> val <= list2 -> val ){
            list1 -> next = mergeTwoLists(list1 -> next, list2);
			return list1;
        }
        // we will call recursive list1 whole list and l2 -> next.
         else
        {
			list2 -> next = mergeTwoLists(list1, list2 -> next);
			return list2;            
		}
    }
};
```
Image :-
![image](https://github.com/user-attachments/assets/679cc5eb-1186-42bd-a7d4-94d73e7d4088)
