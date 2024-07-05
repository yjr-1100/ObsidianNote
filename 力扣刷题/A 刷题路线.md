
## 刷题路线

[代码随想录](https://programmercarl.com/)

[labuladong的算法笔记](https://labuladong.online/algo/)

----
## 数组


- **数组下标都是从0开始的。**
- **数组内存空间的地址是连续的**
- **数组的元素是不能删的，只能覆盖**

使用C++的话，要注意vector 和 array的区别，vector的底层实现是array，严格来讲vector是容器，不是数组。

[[1.1 二分查找]]
[[1.2 移除元素]]
[[1.3 长度最小的子数组]]
[[1.4 螺旋矩阵II]]

---
## 链表

**单链表** 

链表是一种通过指针串联在一起的线性结构，每一个节点由两部分组成，一个是数据域一个是指针域（存放指向下一个节点的指针），最后一个节点的指针域指向null（空指针的意思）。

**双链表**

每一个节点有两个指针域，一个指向下一个节点，一个指向上一个节点，双链表 既可以向前查询也可以向后查询

**循环链表**

循环链表，顾名思义，就是链表首尾相连。循环链表可以用来解决约瑟夫环问题

**链表的定义**

```cpp
// 单链表
struct ListNode {
    int val;  // 节点上存储的元素
    ListNode *next;  // 指向下一个节点的指针
    ListNode(int x) : val(x), next(NULL) {}  // 节点的构造函数
};

```

[[2.1 移除链表元素]]
[[2.2 设计链表]]
[[2.3 反转链表]]
[[2.4 交换链表中的节点]]
[[2.5 删除链表的倒数第N个节点]]
[[2.6 链表相交]]
[[2.7 环形链表]]

合并链表
[21. 合并两个有序链表](https://leetcode.cn/problems/merge-two-sorted-lists/)
[23. 合并 K 个升序链表](https://leetcode.cn/problems/merge-k-sorted-lists/)
[86. 分隔链表](https://leetcode.cn/problems/partition-list/)



---

##  