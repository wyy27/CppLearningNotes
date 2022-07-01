## 移除链表元素
给你一个链表的头节点 head 和一个整数 val ，请你删除链表中所有满足 Node.val == val 的节点，并返回 新的头节点 。
示例：
输入：head = [1,2,6,3,4,5,6], val = 6
输出：[1,2,3,4,5]

### 解题思路
添加虚拟头节点，方便统一操作链表。
注意指针的箭头的使用，与定义的实体区分。

### 代码

```cpp
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        ListNode dummyHead; // 设置虚拟节点（定义实体）
        dummyHead.next = head;   //将虚拟头节点指向head
        ListNode* cur = &dummyHead;
        while(cur->next != NULL) {
            if (cur->next->val == val){
                ListNode* tmp = cur->next;
                cur->next = cur->next->next;
                delete tmp;
            } else {
                cur = cur->next;
            }
        }
        return dummyHead.next; //返回头节点
    }
};
```
