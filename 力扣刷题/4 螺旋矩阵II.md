# 4 螺旋矩阵II

[59. 螺旋矩阵 II](https://leetcode.cn/problems/spiral-matrix-ii/)

```cpp
class Solution {
public:
    vector<vector<int>> generateMatrix(int n) {
        int loopnum = n/2;
        int cont = 1;
        vector<vector<int>> ans(n,vector<int>(n));
        int row = 0,col = 0;
        int len = n-1;
        while(loopnum>0){
            int i = row;
            int j = col;
            for(;j<len;j++){
                ans[i][j]=cont++;
            }
            for(;i<len;i++){
                ans[i][j]=cont++;
            }
            for(;j>col;j--){
                ans[i][j] = cont++;
            }
            for(;i>row;i--){
                ans[i][j] = cont++;
            }
            len--;
            row++;
            col++;
            loopnum--;
        }
        if(n%2)ans[n/2][n/2] = cont++;
        return ans;
    }
};
```

还是循环不变量原则，[思路讲解](https://programmercarl.com/0059.%E8%9E%BA%E6%97%8B%E7%9F%A9%E9%98%B5II.html#%E6%80%9D%E8%B7%AF)

# 相关题目

## [54.螺旋矩阵](https://leetcode.cn/problems/spiral-matrix/)



## [剑指Offer 29.顺时针打印矩阵](https://leetcode.cn/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

