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

# 3 运算符和流程控制

## 运算符
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

> 但是当存在其他操作时，结果不同

```java
int b;  
int a = 19;  
b = a++;  
System.out.println(b);  // 19,先赋值，后对a进行自加
System.out.println(a);  // 20,a自加结束后结果是20 
b = ++a;  
System.out.println(b);  // 21, 先对a自加，自加后的结果赋值
System.out.println(a);  // 21,a自加结束后结果是21
```

### 赋值运算符

把算术运算符和赋值运算符组合形成了**扩展赋值运算符**

```
=  +=  -=  *=  /=  %=
```

### 关系运算符

又叫比较运算符，其实就是拿着左边跟右边进行了判断

| 符号 | 解释                                                         |
| ---- | ------------------------------------------------------------ |
| ==   | 就是判断左边跟右边是否相等，如果成立就是true，如果不成立就是false |
| !=   | 就是判断左边跟右边是否不相等，如果成立就是true，如果不成立就是false |
| >    | 就是判断左边是否大于右边，如果成立就是true，如果不成立就是false |
| >=   | 就是判断左边是否大于等于右边，如果成立就是true，如果不成立就是false |
| <    | 就是判断左边是否小于右边，如果成立就是true，如果不成立就是false |
| <=   | 就是判断左边是否小于等于右边，如果成立就是true，如果不成立就是false |

> 注意：关系运算符最终的结果一定是布尔类型的。要么是true，要么是false

### 逻辑运算符

#### 与

`&` :  两边都为真，结果才是真，只要有一个为假，那么结果就是假。

``` java
System.out.println(true & true);//true
System.out.println(false & false);//false
System.out.println(true & false);//false
System.out.println(false & true);//false
```
#### 或

`|` : 两边都为假，结果才是假，只要有一个为真，那么结果就是真。

```java
System.out.println(true | true);//true
System.out.println(false | false);//false
System.out.println(true | false);//true
System.out.println(false | true);//true
```
#### 非

`!` : 取反操作，false取反就是true，true取反就是false

```java
System.out.println(!false);//true
System.out.println(!true);//false
```
#### 异或

`^` : 如果两边相同，结果为false，如果两边不同，结果为true

```java
System.out.println(true ^ true);//false
System.out.println(false ^ false);//false
System.out.println(true ^ false);//true
System.out.println(false ^ true);//true
```

#### 短路逻辑运算符&& 和 ||

> `&&`：运算结果跟`&`是一模一样的，只不过具有短路效果。
> `||`：运算结果跟`|`是一模一样的。只不过具有短路效果。

 **逻辑核心：**

​	当左边不能确定整个表达式的结果，右边才会执行。
​	当左边能确定整个表达式的结果，那么右边就不会执行了。从而提高了代码的运行效率。

### 三元运算符

又叫做：三元表达式或者问号冒号表达式。

格式：	关系表达式 ？ 表达式1 ：表达式2 ；

**计算规则：**

* 计算关系表达式的值。
* 如果关系表达式的值为真，那么执行表达式1。
* 如果关系表达式的值为假，那么执行表达式2。

> 注意：三元运算符的最终结果**一定要被使用**，要么赋值给一个变量，要么直接打印出来。

```java
public class OperatorDemo12 {
    public static void main(String[] args) {
        //需求：求两个数的较大值
        int a = 10;
        int b = 20;
        int max =  a > b ? a : b ;
        System.out.println(max);
        System.out.println(a > b ? a : b);
    }
}
```

## 流程控制

在一个程序执行的过程中，各条语句的执行顺序对程序的结果是有直接影响的。所以，我们必须清楚每条语句的执行流程。而且，很多时候要通过控制语句的执行顺序来实现我们想要的功能。

#### 顺序结构

顺序结构是程序中最简单最基本的流程控制，没有特定的语法结构，按照代码的先后顺序，依次执行，程序中大多数的代码都是这样执行的。

顺序结构执行流程图：
![[1545615769372.png]]


#### 判断和选择结构

##### if 语句

![[1545616039363.png]]


```java
public class IfDemo {
	public static void main(String[] args) {
		System.out.println("开始");	
		//定义两个变量
		int a = 10;
		int b = 20;	
		//需求：判断a和b的值是否相等，如果相等，就在控制台输出：a等于b
		if(a == b) {
			System.out.println("a等于b");
		}		
		//需求：判断a和c的值是否相等，如果相等，就在控制台输出：a等于c
		int c = 10;
		if(a == c) {
			System.out.println("a等于c");
		}		
		System.out.println("结束");
	}
}
```

##### if else 语句

![[1545616221283.png]]

```java
public class IfDemo02 {
	public static void main(String[] args) {
		System.out.println("开始");		
		//定义两个变量
		int a = 10;
		int b = 20;
		//需求：判断a是否大于b，如果是，在控制台输出：a的值大于b，否则，在控制台输出：a的值不大于b
		if(a > b) {
			System.out.println("a的值大于b");
		} else {
			System.out.println("a的值不大于b");
		}		
		System.out.println("结束");
	}
}
```

##### if else-if else 语句

![[1545616667104.png]]


##### switch case 语句

```java
switch (表达式) {
	case 1:
		语句体1;
		break;
	case 2:
		语句体2;
		break;
	...
	default:
		语句体n+1;
		break;
}
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



