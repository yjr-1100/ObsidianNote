[代码随想录](https://programmercarl.com/)
[labuladong的算法笔记](https://labuladong.online/algo/)
## 数组刷题

# 1 二分查找

## [704 二分查找](https://leetcode.cn/problems/binary-search/description/)

```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int l=0,r=nums.size();
        if(target<nums[l]||target>nums[r-1]) return -1;
        while(l<r){
            int mid = l+((r-l) >> 1);
            if(nums[mid]>target){
                r = mid;
            }
            else if(nums[mid]<target){
                l = mid+1;
            }
            else{
                return mid;
            }
        }
        return -1;
    }
};
```

