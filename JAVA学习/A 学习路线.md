[Java 学习路线 by 程序员鱼皮](https://github.com/liyupi/codefather/blob/main/%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF/Java%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF%20by%20%E7%A8%8B%E5%BA%8F%E5%91%98%E9%B1%BC%E7%9A%AE.md)
[java工程师之路](https://hollischuang.gitee.io/tobetopjavaer/#/menu?id=%E7%9B%AE%E5%BD%95)
[Java后端学习路线](https://zhuanlan.zhihu.com/p/652601404)
[Java学习路线](https://www.zhihu.com/tardis/bd/art/377897661?source_id=1001)
[Java学习路线](https://www.bilibili.com/read/cv27536199/?jump_opus=1)
[Java的数据结构和算法](https://blog.csdn.net/qq_43422402/article/details/136663325)
[github刷题指导](https://github.com/labuladong/fucking-algorithm)
# java SE

[[1 java 快速入门]]
[[2 基础语法]]
[[3 运算符和流程控制]]
[[4 面向对象]]
[[5 类和对象]]
[[6 抽象类和接口]]
[[7 数组和字符串]]
[[8 常用API]]

# 9 查找和排序

## 查找

### 顺序查找

说明：顺序查找适合于存储结构为数组或者链表。

**基本思想**：顺序查找也称为线形查找，属于无序查找算法。从数据结构线的一端开始，顺序扫描，依次将遍历到的结点与要查找的值相比较，若相等则表示查找成功；若遍历结束仍没有找到相同的，表示查找失败。

示例代码：
```java
public class A01_BasicSearchDemo1 {
    public static void main(String[] args) {

        int[] arr = {131, 127, 147, 81, 103, 23, 7, 79};
        int number = 82;
        System.out.println(basicSearch(arr, number));
    }

    //参数：
    //一：数组
    //二：要查找的元素
    //返回值：
    //元素是否存在
    public static boolean basicSearch(int[] arr, int number){
        //利用基本查找来查找number在数组中是否存在
        for (int i = 0; i < arr.length; i++) {
            if(arr[i] == number){
                return true;
            }
        }
        return false;
    }
}
```

### 二分查找

也叫做折半查找

说明：元素必须是有序的，从小到大，或者从大到小都是可以的。

如果是无序的，也可以先进行排序。但是排序之后，会改变原有数据的顺序，查找出来元素位置跟原来的元素可能是不一样的，所以排序之后再查找只能判断当前数据是否在容器当中，返回的索引无实际的意义。

　　**基本思想**：也称为是折半查找，属于有序查找算法。用给定值先与中间结点比较。比较完之后有三种情况：

- 相等
    
    说明找到了
    
- 要查找的数据比中间节点小
    
    说明要查找的数字在中间节点左边
    
- 要查找的数据比中间节点大
    
    说明要查找的数字在中间节点右边
    

代码示例：

```java
public class HelloWorld {  
    public static void main(String[] args){  
        int[] arr = {7, 23, 79, 81, 103, 127, 131};  
        System.out.println(binarySearch(arr, 127));  
    }  
  
    public static int binarySearch(int[] arr,int target){  
        int l = 0;  
        int r = arr.length-1;  // 区间是左闭右闭的
        while (l<=r){  // l==r 是有意义的
            int mid = l+(r-l)/2;  
            if(arr[mid]>target){  
                r = mid-1;  
            }  
            else if(arr[mid]<target){  
                l = mid+1;  
            }  
            else{  
                return mid;  
            }  
        }  
        return -1;  
    }  
  
}
```


# java EE



