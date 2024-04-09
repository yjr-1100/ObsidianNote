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


# 5 类和对象

## 类和对象的理解

客观存在的事物皆为**对象** ，所以我们也常常说万物皆对象。

- 类
    
    - 类的理解
        
        - 类是对现实生活中一类具有共同属性和行为的事物的抽象
            
        - 类是对象的数据类型，类是具有相同属性和行为的一组对象的集合
            
        - 简单理解：类就是对现实事物的一种描述
            
    - 类的组成
        
        - **属性：**指事物的特征，例如：手机事物（品牌，价格，尺寸）
            
        - **行为：**指事物能执行的操作，例如：手机事物（打电话，发短信）
            
- 类和对象的关系
    
    - 类：类是对现实生活中一类具有共同属性和行为的事物的抽象
        
    - 对象：是能够看得到摸的着的真实存在的实体
        
    - 简单理解：**类是对事物的一种描述，对象则为具体存在的事物**
        

## 类的定义

类的组成是由属性和行为两部分组成

- **属性：** 在类中通过成员变量来体现（类中方法外的变量）
    
- **行为：** 在类中通过成员方法来体现（和前面的方法相比去掉static关键字即可）
    

类的定义步骤：

①定义类

②编写类的成员变量

③编写类的成员方法

```java
class Phone {
    //成员变量
    String brand;
    int price;

    //成员方法
    public void call() {
        System.out.println("打电话");
    }

    public void sendMessage() {
        System.out.println("发短信");
    }
}
```

## 对象的使用

* 创建对象的格式：
  * 类名 对象名 = new 类名();
* 调用成员的格式：
  * 对象名.成员变量
  * 对象名.成员方法();

```java
public class PhoneDemo {
    public static void main(String[] args) {
        //创建对象
        Phone p = new Phone();
        //使用成员变量
        System.out.println(p.brand);
        System.out.println(p.price);
        p.brand = "小米";
        p.price = 2999;
        System.out.println(p.brand);
        System.out.println(p.price);
        //使用成员方法
        p.call();
        p.sendMessage();
    }
}
```

## 对象内存图

### 单个对象内存图

* 成员变量使用过程
	![[1 1.png]]

- 成员方法调用过程
	![[2.png]]

### 多个对象内存图

- 成员变量使用过程
	![[3.png]]
	

- 成员方法调用过程
	![[4.png]]

> 多个对象在堆内存中，都有不同的内存划分，成员变量存储在各自的内存区域中，成员方法多个对象共用的一份


### 成员变量和局部变量的区别

* 类中位置不同：成员变量（类中方法外）局部变量（方法内部或方法声明上）
* 内存中位置不同：成员变量（堆内存）局部变量（栈内存）
* 生命周期不同：成员变量（随着对象的存在而存在，随着对象的消失而消失）局部变量（随着方法的调用而存在，方法的调用完毕而消失）
* 初始化值不同：成员变量（有默认初始化值）局部变量（没有默认初始化值，必须先定义，赋值才能使用）

## 封装

### 封装思想

1. 封装概述
   是面向对象三大特征之一（封装，继承，多态）

   **对象代表什么，就得封装对应的数据，并提供数据对应的行为** 

2. 封装代码实现
   将类的某些信息隐藏在类内部，不允许外部程序直接访问，而是通过该类提供的方法来实现对隐藏信息的操作和访问
   成员变量private，提供对应的getXxx()/setXxx()方法

### private关键字

private是一个修饰符，可以用来修饰成员（成员变量，成员方法）

* 被private修饰的成员，只能在本类进行访问，针对private修饰的成员变量，如果需要被其他类使用，提供相应的操作
- 提供“get变量名()”方法，用于获取成员变量的值，方法用public修饰
- 提供“set变量名(参数)”方法，用于设置成员变量的值，方法用public修饰

```java
/*
    学生类
 */
class Student {
    //成员变量
    private String name;
    private int age;

    //get/set方法
    public void setName(String n) {
        name = n;
    }
    public String getName() {
        return name;
    }
    public void setAge(int a) {
        age = a;
    }
    public int getAge() {
        return age;
    }
    public void show() {
        System.out.println(name + "," + age);
    }
}
/*
    学生测试类
 */
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s = new Student();
        //使用set方法给成员变量赋值
        s.setName("林青霞");
        s.setAge(30);
        s.show();
        //使用get方法获取成员变量的值
        System.out.println(s.getName() + "---" + s.getAge());
        System.out.println(s.getName() + "," + s.getAge());
    }
}
```

### this关键字

- this修饰的变量用于指代成员变量，其主要作用是（区分局部变量和成员变量的重名问题）
- 方法的形参如果与成员变量同名，不带this修饰的变量指的是形参，而不是成员变量
- 方法的形参没有与成员变量同名，不带this修饰的变量指的是成员变量


## 构造方法

### 构造方法概述

构造方法是一种特殊的方法

* 作用：创建对象   Student stu = **new Student();**

* 格式：

  public class 类名{
  ​        修饰符 类名( 参数 ) {

  ​        }
  }

* 功能：主要是完成对象数据的初始化

* 示例代码：
```java
class Student {
    private String name;
    private int age;

    //构造方法
    public Student() {
        System.out.println("无参构造方法");
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*
    测试类
 */
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s = new Student();
        s.show();
    }
}
```

### 构造方法的注意事项

* 构造方法的创建
	如果没有定义构造方法，系统将给出一个默认的无参数构造方法
	如果定义了构造方法，系统将不再提供默认的构造方法

* 构造方法的重载
	如果自定义了带参构造方法，还要使用无参数构造方法，就必须再写一个无参数构造方法

* 推荐的使用方式
	无论是否使用，都手工书写无参数构造方法

* 重要功能！
	可以使用带参构造，为成员变量进行初始化

```java
/*
    学生类
 */
class Student {
    private String name;
    private int age;
    public Student() {}
    public Student(String name) {
        this.name = name;
    }
    public Student(int age) {
        this.age = age;
    }
    public Student(String name,int age) {
        this.name = name;
        this.age = age;
    }

    public void show() {
        System.out.println(name + "," + age);
    }
}
/*
    测试类
 */
public class StudentDemo {
    public static void main(String[] args) {
        //创建对象
        Student s1 = new Student();
        s1.show();
        //public Student(String name)
        Student s2 = new Student("林青霞");
        s2.show();
        //public Student(int age)
        Student s3 = new Student(30);
        s3.show();
        //public Student(String name,int age)
        Student s4 = new Student("林青霞",30);
        s4.show();
    }
}
```
# 5 数组和字符串



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



