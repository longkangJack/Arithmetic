#### [剑指 Offer 18. 删除链表的节点](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)

```c++
class Solution {
public:
    ListNode* deleteNode(ListNode* head, int val) {
        ListNode* p = head;
        if(head->val == val)
        {
            return head->next;
        }
        else
        {
            while(p)
            {
                if(p->next->val == val)
                {
                    p->next = p->next->next;
                    break;
                }
                p = p->next;
            }
            return head;
        }
    }
};
```

题目中由于头节点也存在数值，所以需要再定义一个指针用来查找。

题目很简单没什么写的必要。