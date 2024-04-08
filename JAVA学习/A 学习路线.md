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

#### 两种提升规则

* 取值范围小的，和取值范围大的进行运算，小的会先提升为大的，再进行运算。
* `byte`、`short`、`char`三种类型的数据在运算的时候，都会直接先提升为int，然后再进行运算。

取值范围从小到大的关系：

> `byte` `short` `int` `long` `float` `double`

char字符变量可以实现加减运算
    
> char字符变量是可以进行加减运算的，在运算的时候，我们通过查找对应字符变量值的ASCII值，利用其在ASCII里的对应值进行加减运算。

```java
char a = '1';
char b = '2'
System.out.println("a+b= "+(a+b));
```

### 数据类型的强制转换

如果要把一个取值范围大的数据或者变量赋值给另一个取值范围小的变量。是不允许直接操作，会报错，编译不通过。如果一定要这么干，就需要加入强制转换。

```java
public class OperatorDemo2 {
    public static void main(String[] args) {
        double a = 12.3;
        int b = (int) a;
        System.out.println(b);//12
    }
}
```

注意：强制转换会带来精度的丢失

### 自增自减运算符

``` java
++  // 自增运算符
--  // 自减运算符
```

 **使用方式：**
* 放在变量的前面，我们叫做先++。 比如：++a
* 放在变量的后面，我们叫做后++。 比如：a++

> 注意点：	不管是先++，还是后++。单独写在一行的时候，运算结果是一模一样的。

```java
int a = 10;
a++;//就是让变量a里面的值 + 1
System.out.println(a);//11
++a;//就是让变量a里面的值 + 1
System.out.println(a);//12
```





















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



