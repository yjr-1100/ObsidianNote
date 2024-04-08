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

## 3 运算符和流程控制

### 运算符与表达式

运算符：就是对常量或者变量进行操作的符号。

表达式：用运算符把常量或者变量连接起来的，符合Java语法的式子就是表达式。

### 算术运算符

>  `+`  `-`  `*`  `/`  `%`

运算规则与小学数学没区别

注意：整数相除结果只能得到整除，如果结果想要是小数，必须要有小数参数
```java
int a = 19;  
System.out.println(a/3);  //6 
System.out.println(a/3.0);  //6.3333333333
System.out.println(a*1.0/3); //6.3333333333
```

### 数据类型的隐式转换

就是把一个取值范围小的数据或者变量，赋值给另一个取值范围大的变量。此时不需要我们额外写代码单独实现，是程序自动帮我们完成的。

#### 两种提升规则：

* 取值范围小的，和取值范围大的进行运算，小的会先提升为大的，再进行运算。
* byte、short、char三种类型的数据在运算的时候，都会直接先提升为int，然后再进行运算。

取值范围从小到大的关系：

> `byte` `short` `int` `long` `float` `double`



# java EE



