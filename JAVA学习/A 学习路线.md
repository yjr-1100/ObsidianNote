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


# 6 数组和字符串

## 数组

### 概念

指的是一种容器，可以同来存储同种数据类型的多个值。但是数组容器在存储数据的时候，需要结合隐式转换考虑。

比如：定义了一个int类型的数组。那么boolean。double类型的数据是不能存到这个数组中的，但是byte类型，short类型，int类型的数据是可以存到这个数组里面的。一般我们容器的类和存储的数据类型保持一致

### 数组的定义和访问

> 数据类型[] 数组名
> 
> 数据类型 数组名 []

数组通过索引访问，直接打印数组名得到的是数组的地址值

```java
int[] b = {1,2,3};  // 静态初始化 
int[] a = new int[3]; //动态初始化
for(int i = 0;i<b.length;i++){  
    System.out.println(b[i]);  
}
System.out.println(b) // [I@10f87f48
```

\[ ：表示现在打印的是一个数组。
I：表示现在打印的数组是int类型的。
@：仅仅是一个间隔符号而已。
10f87f48：就是数组在内存中真正的地址值。（十六进制的）
















# 这些内容学字符串的时候再看
## 字符串的+操作

### 核心技巧：

- 当+操作中出现字符串时，此时就是字符串的连接符，会将前后的数据进行拼接，并产生一个新的字符串。
    
- 当连续进行+操作时，从左到右逐个执行的。
    

## 7.字符串相加的练习：

案例1：

1 + "abc" + 1

结果："1abc1"

解释：

第一步： 1 + "abc"。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"1abc"

第二步： "1abc" + 1。这个过程中，有字符串参与的，所以做的也是拼接操作，产生一个新的字符串"1abc1"

案例2：

1 + 2 + "abc" + 2 + 1

结果：“3abc21”

解释：

第一步：1 + 2 。在这个过程中，没有字符串参与的，所以做的是加法运算，结果为3。

第二步：3 + "abc"。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc"。

第三步："3abc" + 2。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串"3abc2"。

第四步："3abc2" + 1。在这个过程中，有字符串参与的，所以做的是拼接操作，产生一个新的字符串“3abc21”

案例3：

String name = "黑默丁格";  
System.out.println("我的名字是" + name);

结果： 我的名字是黑默丁格

解释：当字符串跟变量相加的时候，实际上是跟变量里面的值进行拼接。

## 8.字符的+操作

### 规则：

当+操作中出现了字符，会拿着字符到计算机内置的ASCII码表中去查对应的数字，然后再进行计算。

### 案例：

char c = 'a';  
int result = c + 0;  
System.out.println(result);//97

ASCII码表中：

'a' ----- 97

'A' ----- 65

























# java EE



