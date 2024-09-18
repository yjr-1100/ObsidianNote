
## 刷题路线

[代码随想录](https://programmercarl.com/)

[labuladong的算法笔记](https://labuladong.online/algo/)

----
## 1 数组


- **数组下标都是从0开始的。**
- **数组内存空间的地址是连续的**
- **数组的元素是不能删的，只能覆盖**

使用C++的话，要注意vector 和 array的区别，vector的底层实现是array，严格来讲vector是容器，不是数组。

[[1.1 二分查找]]
[[1.2 移除元素]]
[[1.3 长度最小的子数组]]
[[1.4 螺旋矩阵II]]

---
## 2 链表

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
[[2.8 合并链表]]

---
##  3 哈希表

> 哈希表是根据关键码的值而直接进行访问的数据结构。一般哈希表都是用来快速判断一个元素是否出现集合里。

[哈希表基础知识](https://programmercarl.com/%E5%93%88%E5%B8%8C%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html#%E5%93%88%E5%B8%8C%E8%A1%A8)

**常见的三种哈希结构**

- 数组
- 集合（set)
- map（映射）

具体底层实现的差别会影响使用时的选择

[[3.1 有效的字母异位]]
[[3.2 两个数组的交集]]
[[3.3 快乐数]]
[[3.4 两数之和]]
[[3.1 有效的字母异位#^5481df|3.5 赎金信]]
[[3.4 两数之和#^f52812|3.6 三数之和]]
[[3.4 两数之和#^43294b|3.7 四数之和]]

----
## 4 字符串

[[4.1 花式反转字符串]]
[[4.2 替换数字]]
[[4.1 花式反转字符串#^eb97eb|4.3 翻转字符串中的单词]]
[[4.1 花式反转字符串#^65412c|4.4 右旋转字符串]]
[[4.5 kmp算法]]

----
# 5 双指针专题

[[1.2 移除元素|移除元素]]
[[4.1 花式反转字符串|反转字符串]]
[[4.2 替换数字|替换数字]]
[[4.1 花式反转字符串#^eb97eb|翻转字符串中的单词]]
[[2.3 反转链表|翻转链表]]
[[2.5 删除链表的倒数第N个节点|删除链表的倒数第N个节点]]
[[2.6 链表相交|链表相交]]
[[2.7 环形链表|环形链表]]
[[3.4 两数之和#^f52812|三数之和]]
[[3.4 两数之和#^43294b|四数之和]]
[双指针总结](https://programmercarl.com/%E5%8F%8C%E6%8C%87%E9%92%88%E6%80%BB%E7%BB%93.html)

---
# 6 栈和队列

[[6.1 用栈实现队列]]
[[6.2 用队列实现栈]]
[[6.3 有效的括号]]
[[6.4 删除字符串中所有的重复项]]
[[6.3 有效的括号#^ca047f|6.5 逆波兰式表达式求值]]
[[6.6 单调队列]]
[[6.7 优先队列]]

---
# 7 二叉树

**二叉树的种类**   满二叉树，完全二叉树，二叉搜索树，平衡二叉搜索树

**C++中map、set、multimap，multiset的底层实现都是平衡二叉搜索树**，所以map、set的增删操作时间时间复杂度是logn，注意我这里没有说unordered_map、unordered_set，unordered_map、unordered_set底层实现是哈希表。

**二叉树的存储方式：**
+ 顺序存储：用一个数组，节点i的左孩子 `2 * i + 1`，右节点：`2 * i + 2`
+ 链式： 一个节点，有左指针和右指针
```cpp
struct TreeNode {
    int val;
    TreeNode *left;
    TreeNode *right;
    TreeNode(int x) : val(x), left(NULL), right(NULL) {}
};
```

**二叉树的遍历**
+ 深度优先遍历
	+ 前序遍历：中左右
	+ 中序遍历：左中右
	+ 后序遍历：左右中
+ 广度优先遍历
	+ 层次遍历

[[7.1 递归遍历]]
[[7.2 迭代遍历]]
[[7.3 层序遍历]]
[[7.4 翻转二叉树]]
[[7.5 对称二叉树]]
[[7.6 二叉树的最大深度]]
[[7.7 二叉树的最小深度]]
[[7.8 完全二叉树的节点个数]]
[[7.9 平衡二叉树]]
[[7.10 二叉树的所有路径]]
[[7.11 左孩子之和]]
[[7.12 找树左下角的值]]
[[7.13 路径总和]]
[[7.14 中序和后序遍历构造二叉树]]
[[7.15 最大二叉树]]
[[7.16 合并二叉树]]
[[7.17 二叉树搜索树]]
[[7.18 二叉搜索树中的众数]]
[[7.19 二叉树的最近公共祖先]]
[[7.20 二叉搜索树的插入]]
[[7.21 删除二叉搜索树中的节点]]
[[7.22 修剪二叉搜索树]]
[[7.23 构建二叉搜索树]]
[[7.24 把二叉搜索树转换为累加树]]

---
# 8 回溯算法

回溯是递归的副产品，只要有递归就会有回溯。

**回溯的本质是穷举，穷举所有可能，然后选出我们想要的答案**，如果想让回溯法高效一些，可以加一些剪枝的操作，但也改不了回溯法就是穷举的本质。

回溯法，一般可以解决如下几种问题：

- 组合问题：N个数里面按一定规则找出k个数的集合
- 切割问题：一个字符串按一定规则有几种切割方式
- 子集问题：一个N个数的集合里有多少符合条件的子集
- 排列问题：N个数按一定规则全排列，有几种排列方式
- 棋盘问题：N皇后，解数独等等


[[8.1 组合]]
[[8.2 分割]]
[[8.3 子集]]
[[8.4 排列]]
[[8.5 棋盘]]
[[8.6 其他]]

---
# 9 贪心

[[9.1 分发饼干]]
[[9.2 摆动序列]]
[[9.3 最大子序和]]
[[9.4 买股票的最佳时机]]
[[9.5 跳跃游戏]]
[[9.6 K次取反后最大化数组和]]
[[9.7 加油站]]
[[9.8 分发糖果]]
[[9.9 柠檬水找零]]
[[9.10 根据身高重建队列]]
[[9.11 用最少数量的箭引爆气球]]
[[9.12 单调递增的数字]]
[[9.13 监控二叉树]]

---
# 10 动态规划

动态规划，英文：Dynamic Programming，简称DP，如果某一问题有很多重叠子问题，使用动态规划是最有效的。

所以动态规划中每一个状态一定是由上一个状态推导出来的，**这一点就区分于贪心**，贪心没有状态推导，而是从局部直接选最优的

**对于动态规划问题，我将拆解为如下五步曲，这五步都搞清楚了，才能说把动态规划真的掌握了！**

1. 确定dp数组（dp table）以及下标的含义
2. 确定递推公式
3. dp数组如何初始化
4. 确定遍历顺序
5. 举例推导dp数组


[[10.1 斐波那契数列]]
[[10.2 使用最小花费爬楼梯]]
[[10.3 不同路径]]
[[10.4 整数拆分]]
[[10.5 不同二叉搜索树]]
[[10.6 0-1背包问题]]
[[10.7 完全背包]]
[[10.8 单词拆分]]
[[10.9 多重背包]]
[[10.10 打家劫舍]]
[[10.11 买股票的最佳时机]]
[[10.12 子序列问题]]
[[10.13 编辑距离]]
[[10.14 回文子串]]

---
# 11 单调栈

[[11.1 每日温度]]
[[11.2 下一个更大元素]]
[[11.3 接雨水]]

---
# 12 图论

[12.1 图论理论基础](https://programmercarl.com/kamacoder/%E5%9B%BE%E8%AE%BA%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html)
[[12.2 深度优先搜索]]
[[12.3 广度优先搜索]]
[[12.4 有向图的完全可达性]]
[[12.5 岛屿的周长]]
[[12.6 并查集]]
[[12.7 最小生成树prim]]
[[12.8 最小生成树 kruskal]]
[[12.9 拓扑排序]]
# 12.10 最短路

## dijkstra (朴素版)

**dijkstra算法**：在有权图（权值非负数）中求从起点到其他节点的最短路径算法。

1. 第一步，选源点到哪个节点近且该节点未被访问过
2. 第二步，该最近节点被标记访问过
3. 第三步，更新非访问节点到源点的距离（即更新minDist数组）

**minDist数组 用来记录 每一个节点距离源点的最小距离**。

这里看起来和prim算法很像，但注意，prim算法是最小生成树，是说把图中所有节点连起来的权值最小，而dijkstra算法是说源点到图中任意一个节点的距离最小，两个是有区别的。

时间复杂度是O(n^2) 对于节点少的稠密图比较适合

[47. 参加科学大会（第六期模拟笔试）](https://kamacoder.com/problempage.php?pid=1047)

[题解](https://programmercarl.com/kamacoder/0047.%E5%8F%82%E4%BC%9Adijkstra%E6%9C%B4%E7%B4%A0.html#%E6%80%9D%E8%B7%AF)

```cpp
#include<iostream>
#include<vector>
#include <climits>

using namespace std;
int n,m;
int main(){
    int s,t,v;
    cin>>n>>m;
    vector<int> minDist(n+1,INT_MAX);
    vector<bool> isvisit(n+1,false);
    vector<vector<int>> graph(n+1,vector<int>(n+1,INT_MAX));
    while(m--){
        cin>>s>>t>>v;
        graph[s][t] = v;
    }
    minDist[1] = 0;
    for(int i =1;i<=n;i++){
        int minv = INT_MAX;
        int curr = 1;;
        for(int j=1;j<=n;j++)
            if(!isvisit[j]&&minDist[j]<minv){
                minv = minDist[j];
                curr = j;
            }
        
        isvisit[curr] = true;
        
        for(int j = 1;j<=n;j++){
            if(!isvisit[j]&&graph[curr][j] != INT_MAX&&minDist[j]>graph[curr][j]+minDist[curr]){
                minDist[j] = graph[curr][j]+minDist[curr];
            }
        }
    }
    if (minDist[n] == INT_MAX) cout << -1 << endl; // 不能到达终点
    else cout << minDist[n] << endl; // 到达终点最短路径
}
```

## dijkstra(堆优化版)

朴素版的对于节点少的图比较合适，但是如果节点多，边少的图，我们可以优化解法。

对于节点多边少的稀疏图，我们一般使用邻接表来存储

邻接表的优点：
- 对于稀疏图的存储，只需要存储边，空间利用率高
- 遍历节点链接情况相对容易
缺点：
- 检查任意两个节点间是否存在边，效率相对低，需要 O(V)时间，V表示某节点链接其他节点的数量。
- 实现相对复杂，不易理解


[47. 参加科学大会（第六期模拟笔试）](https://kamacoder.com/problempage.php?pid=1047)

[题解](https://programmercarl.com/kamacoder/0047.%E5%8F%82%E4%BC%9Adijkstra%E5%A0%86.html#%E6%80%9D%E8%B7%AF)

 时间复杂度：O(ElogE) E 为边的数量

```cpp
#include<iostream>
#include<vector>
#include <climits>
#include<list>
#include <queue>
using namespace std;
int n,m;
struct Edge{
    int target;
    int val;
    Edge(int t,int v):target(t),val(v){}
};
class mycomparision{
    public:
    bool operator()(const pair<int,int>& l,const pair<int,int>& r){
        return l.second>r.second;
    }
};
priority_queue<pair<int,int>,vector<pair<int,int>>,mycomparision> pq;
int main(){
    int s,t,v;
    cin>>n>>m;
    vector<int> minDist(n+1,INT_MAX);
    vector<bool> isvisit(n+1,false);
    vector<list<Edge>> graph(n+1);
    while(m--){
        cin>>s>>t>>v;
        graph[s].push_back(Edge(t,v));
    }
    pq.push(pair<int,int>(1,0));
    minDist[1]=0;
    while(!pq.empty()){
        pair<int,int> cur = pq.top();
        pq.pop();
        if(isvisit[cur.first]) continue;
        for(Edge edge:graph[cur.first]){
            if(!isvisit[edge.target]&&cur.second+edge.val<minDist[edge.target]){
                minDist[edge.target] = cur.second+edge.val;
                pq.push(pair<int,int>(edge.target,minDist[edge.target]));
            }
        }
    }
    if(minDist[n]==INT_MAX) cout<<-1<<endl;
    else cout<<minDist[n];
}
```

## Bellman_ford算法

[94. 城市间货物运输 I](https://kamacoder.com/problempage.php?pid=1152)

[题解](https://programmercarl.com/kamacoder/0094.%E5%9F%8E%E5%B8%82%E9%97%B4%E8%B4%A7%E7%89%A9%E8%BF%90%E8%BE%93I.html#%E6%80%9D%E8%B7%AF)

本题中存在负的权值，不可以使用dijkstra算法去求解。

存在负权值需要注意负权回路，负权回路是指一系列道路的总权值为负，这样的回路使得通过反复经过回路中的道路，理论上可以无限地减少总成本或无限地增加总收益。

```cpp
#include<iostream>
#include<vector>
#include <list>
#include <climits>
using namespace std;

struct Edge{
    int s,t,v;
    Edge(int s,int t,int val):s(s),t(t),v(val){}
};

int main(){
    int n,m;
    cin>>n>>m;
    vector<int> mindist(n+1,INT_MAX);
    vector<Edge> edge;
    int s,t,v;
    while(m--){
        cin>>s>>t>>v;
        edge.push_back(Edge(s,t,v));
    }
    mindist[1] = 0;
    for(int i = 1;i<n;i++){
        for(Edge e:edge){
            if(mindist[e.s]==INT_MAX) continue;
            if(mindist[e.t]>mindist[e.s]+e.v){
                mindist[e.t] = mindist[e.s]+e.v;
            }
        }
    }
    if(mindist[n]==INT_MAX) cout<<"unconnected"<<endl;
    else cout<<mindist[n];
    
}
```

## Bellman_ford 队列优化算法（SPFA）

所以如果图越稠密，则 SPFA的效率越接近与 Bellman_ford。

反之，图越稀疏，SPFA的效率就越高。

[94. 城市间货物运输 I](https://kamacoder.com/problempage.php?pid=1152)

[题解](https://programmercarl.com/kamacoder/0094.%E5%9F%8E%E5%B8%82%E9%97%B4%E8%B4%A7%E7%89%A9%E8%BF%90%E8%BE%93I-SPFA.html#%E8%83%8C%E6%99%AF)

```cpp
#include<iostream>
#include<vector>
#include <list>
#include <climits>
#include<queue>
using namespace std;

struct Edge{
    int t,v;
    Edge(int t,int val):t(t),v(val){}
};

int main(){
    int n,m;
    cin>>n>>m;
    vector<int> mindist(n+1,INT_MAX);
    vector<list<Edge>> edge(n+1);
    vector<bool> isvisit(n+1,false);
    queue<int> q;
    int s,t,v;
    while(m--){
        cin>>s>>t>>v;
        edge[s].push_back(Edge(t,v));
    }
    mindist[1] = 0;
    q.push(1);
    isvisit[1] = true;
    while(!q.empty()){
        int curr = q.front();
        q.pop();
        isvisit[curr]=false;
        for(Edge e:edge[curr]){
            if(mindist[e.t]>mindist[curr]+e.v){ //图中存在正权回路，会因为mindist数组的值不再改变，而不再加入队列，所以不会死循环
                mindist[e.t] = mindist[curr]+e.v;
                if(!isvisit[e.t]){
                    q.push(e.t);
                    isvisit[e.t] = true;
                }
            }
        }
    }
    if(mindist[n]==INT_MAX) cout<<"unconnected"<<endl;
    else cout<<mindist[n];
    
}
```
