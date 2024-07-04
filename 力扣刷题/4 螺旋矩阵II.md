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

首先利用和上一题同样的循环不变量的方法进行求解

```cpp
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int m = matrix.size(); // 行
        int n = matrix[0].size(); // 列
        vector<int> ans;
        int row_start = 0,row_end = m-1;
        int col_start = 0,col_end = n-1;
        int short_line = m<n?m:n;
        int loop = m<n?m/2:n/2;
        int i = 0;
        int j = 0;
        while(loop--){
            i = row_start;
            j = col_start;
            for(;j<col_end;j++){
                ans.push_back(matrix[i][j]);
            }
            for(;i<row_end;i++){
                ans.push_back(matrix[i][j]);
            }
            for(;j>col_start;j--){
                ans.push_back(matrix[i][j]);
            }
            for(;i>row_start;i--){
                ans.push_back(matrix[i][j]);
            }
            row_start++;
            col_start++;
            row_end--;
            col_end--;
        }
        i = row_start;j = col_start;
        if(short_line%2==1)
        {
          if(m<n){
	        for(;j<=col_end;j++) ans.push_back(matrix[i][j]);
	      }
	      else{
	        for(;i<=row_end;i++) ans.push_back(matrix[i][j]);
	      }
        }
        return ans;
    }
};
```

这个题和上面的题不一样，这个题的行和列不相同，循环的次数是短的边决定的，并且当短边是奇数时，会空一行或列没有添加到答案中，需要针对最后的那一行或列进行单独的添加。

当只剩下一行的时候，打破了循环不变量，循环不变量必须是四个过程都参加才可以，如果有过程无法参加则会出错，出现重复的情况。

下面介绍另一种循环控制方法：

```

```

## [剑指Offer 29.顺时针打印矩阵](https://leetcode.cn/problems/shun-shi-zhen-da-yin-ju-zhen-lcof/)

