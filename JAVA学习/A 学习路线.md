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

# 8 常用API

## Math类

Math类所在包为java.lang包，因此在使用的时候不需要进行导包

```java
public class MathDemo01 {
    public static void main(String[] args) {

        // public static int abs(int a)         返回参数的绝对值
        System.out.println("-2的绝对值为：" + Math.abs(-2));
        System.out.println("2的绝对值为：" + Math.abs(2));

        // public static double ceil(double a)  返回大于或等于参数的最小整数
        System.out.println("大于或等于23.45的最小整数位：" + Math.ceil(23.45));
        System.out.println("大于或等于-23.45的最小整数位：" + Math.ceil(-23.45));

        // public static double floor(double a) 返回小于或等于参数的最大整数
        System.out.println("小于或等于23.45的最大整数位：" + Math.floor(23.45));
        System.out.println("小于或等于-23.45的最大整数位：" + Math.floor(-23.45));

        // public static int round(float a)     按照四舍五入返回最接近参数的int
        System.out.println("23.45四舍五入的结果为：" + Math.round(23.45));
        System.out.println("23.55四舍五入的结果为：" + Math.round(23.55));

        // public static int max(int a,int b)   返回两个int值中的较大值
        System.out.println("23和45的最大值为: " + Math.max(23, 45));

        // public static int min(int a,int b)   返回两个int值中的较小值
        System.out.println("12和34的最小值为: " + Math.min(12 , 34));

        // public static double pow (double a,double b)返回a的b次幂的值
        System.out.println("2的3次幂计算结果为: " + Math.pow(2,3));

        // public static double random()返回值为double的正值，[0.0,1.0)
        System.out.println("获取到的0-1之间的随机数为: " + Math.random());
    }

}
```


## System

System类所在包为java.lang包，因此在使用的时候不需要进行导包

```java
public class SystemDemo01 {

    public static void main(String[] args) {

        // 获取当前时间所对应的毫秒值
        long millis = System.currentTimeMillis();
		// 定义源数组
        int[] srcArray = {23 , 45 , 67 , 89 , 14 , 56 } ;

        // 定义目标数组
        int[] desArray = new int[10] ;

        // 进行数组元素的copy: 把srcArray数组中从0索引开始的3个元素，从desArray数组中的1索引开始复制过去
        System.arraycopy(srcArray , 0 , desArray , 1 , 3);

        // 输出结果
        System.out.println("当前时间所对应的毫秒值为：" + millis);
		// 终止JVM
        System.exit(0);
    }

}
```

**arraycopy方法底层细节：**

1.如果数据源数组和目的地数组都是基本数据类型，那么两者的类型必须保持一致，否则会报错

2.在拷贝的时候需要考虑数组的长度，如果超出范围也会报错

3.如果数据源数组和目的地数组都是引用数据类型，那么子类类型可以赋值给父类类型

```java
public class SystemDemo3 {
    public static void main(String[] args) {

        Student s1 = new Student("zhangsan", 23);
        Student s2 = new Student("lisi", 24);
        Student s3 = new Student("wangwu", 25);

        Student[] arr1 = {s1, s2, s3};
        Person[] arr2 = new Person[3];
        //把arr1中对象的地址值赋值给arr2中
        System.arraycopy(arr1, 0, arr2, 0, 3);

        //遍历数组arr2
        for (int i = 0; i < arr2.length; i++) {
            Student stu = (Student) arr2[i];
            System.out.println(stu.getName() + "," + stu.getAge());
        }
    }
}
```


## Runtime

```java
public class RunTimeDemo1 {
    public static void main(String[] args) throws IOException {
        /*
            public static Runtime getRuntime() 当前系统的运行环境对象
            public void exit(int status) 停止虚拟机
            public int availableProcessors() 获得CPU的线程数
            public long maxMemory() JVM能从系统中获取总内存大小(单位byte)
            public long totalMemory() JVM已经从系统中获取总内存大小(单位byte)
            public long freeMemory() JVM剩余内存大小(单位byte)
            public Process exec(string command) 运行cmd命令
        */

        //1.获取Runtime的对象
        //Runtime r1 =Runtime.getRuntime();

        //2.exit 停止虚拟机
        //Runtime.getRuntime().exit(0);
        //System.out.println("看看我执行了吗?");


        //3.获得CPU的线程数
        System.out.println(Runtime.getRuntime().availableProcessors());//8
        //4.总内存大小,单位byte字节
        System.out.println(Runtime.getRuntime().maxMemory() / 1024 / 1024);//4064
        //5.已经获取的总内存大小,单位byte字节
        System.out.println(Runtime.getRuntime().totalMemory() / 1024 / 1024);//254
        //6.剩余内存大小
        System.out.println(Runtime.getRuntime().freeMemory() / 1024 / 1024);//251

        //7.运行cmd命令
        //shutdown :关机
        //加上参数才能执行
        //-s :默认在1分钟之后关机
        //-s -t 指定时间 : 指定关机时间
        //-a :取消关机操作
        //-r: 关机并重启
        Runtime.getRuntime().exec("shutdown -s -t 3600");


    }
}
```



## Object类

>  public String toString()				//返回该对象的字符串表示形式(可以看做是对象的内存地址值)
>  public boolean equals(Object obj)		//比较两个对象地址值是否相等；true表示相同，false表示不相同

```java
class P{  
    int a;  
    P(int a){  this.a = a;  }  
  
    @Override  
    public String toString() {  
        return ""+a;  
    }  
}  
class PP{  
    int a;  
    PP(int a){ this.a = a;  }  
  
    @Override  
    public boolean equals(Object obj) {  
        if(obj==null) return false;  
        if (this==obj) return true;  
        PP o = (PP)obj;  
        return a==o.a;  
    }  
}  
public class HelloWorld {  
    public static void main(String[] args) {  
        // 使用匿名内部类  
        P p1 = new P(1);  
        P p2 = new P(1);  
        PP pp1 = new PP(1);  
        PP pp2 = new PP(1);  
        P p3 = p2;  
        p3.a = 3;  
        System.out.println(p2);//2  
        System.out.println(p1==p2);//false  
        System.out.println(p2==p3);// true  
        System.out.println(pp1==pp2);// false  
        System.out.println(p1.equals(p2));//false  
        System.out.println(p2.equals(p3));//true  
        System.out.println(pp1.equals(pp2));//true  
    }  
}
```

> protected Object clone()    			//对象克隆

浅拷贝

不管对象内部的属性是基本数据类型还是引用数据类型，都完全拷贝过来
基本数据类型拷贝过来的是具体的数据，引用数据类型拷贝过来的是地址值。
Object类默认的是浅克隆
![[浅克隆.png]]

深拷贝

基本数据类型拷贝过来，字符串复用，引用数据类型会重新创建新的

![[深克隆.png]]

```java
class User implements Cloneable{  
    private int id;  
    private String username;  
    private int[] data;  
    public User() {  
    }  
    public User(int id, String username, int[] data) {  
        this.id = id;  
        this.username = username;  
        this.data = data;  
    }  
    public int getId() {  
        return id;  
    }  
    public void setId(int id) {  
        this.id = id;  
    }  
    public String getUsername() {  
        return username;  
    }  
    public void setUsername(String username) {  
        this.username = username;  
    }  
    public int[] getData() {  
        return data;  
    }  
    public void setData(int[] data) {  
        this.data = data;  
    }  
  
    public String toString() {  
        return "角色编号为：" + id + "，用户名为：" + username + ", 进度:" + arrToString();  
    }  
  
    public String arrToString() {  
        StringJoiner sj = new StringJoiner(", ", "[", "]");  
        for (int i = 0; i < data.length; i++) {  
            sj.add(data[i] + "");  
        }  
        return sj.toString();  
    }  
//    默认的拷贝方式  
//    @Override  
//    protected Object clone() throws CloneNotSupportedException {  
//        return super.clone();  
//    }  
  
// 自己写深拷贝  
    @Override  
    protected Object clone() throws CloneNotSupportedException {  
        //调用父类中的clone方法  
        //相当于让Java帮我们克隆一个对象，并把克隆之后的对象返回出去。  
        //先把被克隆对象中的数组获取出来  
        int[] data = this.data;  
        //创建新的数组  
        int[] newData =new int[data.length];  
        //拷贝数组中的数据  
        for (int i = 0; i < data.length; i++) {  
            newData[i] = data[i];  
        }  
        //调用父类中的方法克隆对象  
        User u=(User)super.clone();  
        //因为父类中的克隆方法是浅克隆，替换克隆出来对象中的数组地址值  
        u.data =newData;  
        return u;  
    }  
}  
public class HelloWorld {  
    public static void main(String[] args) throws CloneNotSupportedException {  
        // 使用匿名内部类  
        //1.先创建一个对象  
        int[] data = {1, 2, 3, 4};  
        User u1 = new User(1, "zhangsan", data);  
        System.out.println(u1);  
  
        //2.克隆对象  
        //细节:  
        //方法在底层会帮我们创建一个对象,并把原对象中的数据拷贝过去。  
        //书写细节:  
        //1.重写Object中的clone方法  
        //2.让javabean类实现Cloneable接口  
        //3.创建原对象并调用clone就可以了  
        User u2 =(User)u1.clone();  
  
        //验证一件事情：Object中的克隆是浅克隆  
        //想要进行深克隆，就需要重写clone方法并修改里面的方法体  
        int[] arr = u1.getData();  
        arr[0] = 100;// 这个arr改了，u1 u2的都改了  
        System.out.println(u1);  
        System.out.println(u2);  
  
  
        //以后一般会用第三方工具进行克隆  
        //1.第三方写的代码导入到项目中  
        //2.编写代码  
        Gson gson =new Gson();  
//        把对象变成一个字符串  
        String s=gson.toJson(u1);  
//        再把字符串变回对象就可以了  
        User user =gson.fromJson(s, User.class);  
  
        int[] arr1=u1.getData();  
        arr1[0] = 100;  
  
//        打印对象  
        System.out.println(user);  
    }  
  
  
}
```


## Objects类

```java
public static String toString(Object o) 					// 获取对象的字符串表现形式
public static boolean equals(Object a, Object b)			// 比较两个对象是否相等
public static boolean isNull(Object obj)					// 判断对象是否为null
public static boolean nonNull(Object obj)					// 判断对象是否不为null
```

```java
public class ObjectsDemo01 {
    public static void main(String[] args) {
        // 调用方法
        method_04() ;

    }
    // 测试nonNull方法
    public static void method_04() {
        // 创建一个学生对象
        Student s1 = new Student("itheima" , "14") ;
        // 调用Objects类中的nonNull方法
        boolean result = Objects.nonNull(s1);
        // 输出结果
        System.out.println(result);
    }
    // 测试isNull方法
    public static void method_03() {
        // 创建一个学生对象
        Student s1 = new Student("itheima" , "14") ;
        // 调用Objects类中的isNull方法
        boolean result = Objects.isNull(s1);
        // 输出结果
        System.out.println(result);
    }
    // 测试equals方法
    public static void method_02() {
        // 创建两个学生对象
        Student s1 = new Student("itheima" , "14") ;
        Student s2 = new Student("itheima" , "14") ;
        // 调用Objects类中的equals方法，比较两个对象是否相等
        boolean result = Objects.equals(s1, s2);     // 如果Student没有重写Object类中的equals方法，此处比较的还是对象的地址值
        // 输出结果
        System.out.println(result);
    }
    // 测试toString方法
    public static void method_01() {
        // 创建一个学生对象
        Student s1 = new Student("itheima" , "14") ;
        // 调用Objects中的toString方法,获取s1对象的字符串表现形式
        String result = Objects.toString(s1);       // 如果Student没有重写Object类中的toString方法，此处还是返回的对象的地址值
        // 输出结果
        System.out.println(result);
    }
}
```

## BigDecimal类

### 引入

首先我们来分析一下如下程序的执行结果：

public class BigDecimalDemo01 {  
​  
    public static void main(String[] args) {  
        System.out.println(0.09 + 0.01);  
    }  
​  
}

这段代码比较简单，就是计算0.09和0.01之和，并且将其结果在控制台进行输出。那么按照我们的想法在控制台输出的结果应该为0.1。那么实际的运行结果是什么呢？我们来运行一下程序，控制台的输出

结果如下所示：

0.09999999999999999

这样的结果其实就是一个丢失精度的结果。为什么会产生精度丢失呢？

在使用float或者double类型的数据在进行数学运算的时候，很有可能会产生精度丢失问题。我们都知道计算机底层在进行运算的时候，使用的都是二进制数据； 当我们在程序中写了一个十进制数据 ，在

进行运算的时候，计算机会将这个十进制数据转换成二进制数据，然后再进行运算，计算完毕以后计算机会把运算的结果再转换成十进制数据给我们展示； 如果我们使用的是整数类型的数据进行计算，那

么在把十进制数据转换成二进制数据的时候不会存在精度问题； 如果我们的数据是一个浮点类型的数据，有的时候计算机并不会将这个数据完全转换成一个二进制数据，而是将这个将其转换成一个无限的

趋近于这个十进数的二进制数据； 这样使用一个不太准确的数据进行运算的时候， 最终就会造成精度丢失；为了提高精度，Java就给我们提供了BigDecimal供我们进行数据运算。

### 概述

查看API文档，我们可以看到API文档中关于BigDecimal类的定义如下：

![1576132679789](file://E:\BaiduSyncdisk\Java基础-资料\day18-API（常见API，对象克隆）\笔记\assets\1576132679789.png?lastModify=1712922080)

BigDecimal所在包是在java.math包下，因此在使用的时候就需要进行导包。我们可以使用BigDecimal类进行更加精准的数据计算。

###  常见方法

**构造方法**

要用BigDecimal类，那么就需要首先学习一下如何去创建BigDecimal的对象。通过查看API文档，我们可以发现Jdk中针对BigDecimal类提供了很多的构造方法，但是最常用的构造方法是：

![1576134383441](file://E:\BaiduSyncdisk\Java基础-资料\day18-API（常见API，对象克隆）\笔记\assets\1576134383441.png?lastModify=1712922080)

了解完常见的构造方法以后，我们接下来就重点介绍一下常见的成员方法。

**常见成员方法**

BigDecimal类中使用最多的还是提供的进行四则运算的方法，如下：

```java
public BigDecimal add(BigDecimal value) // 加法运算  
public BigDecimal subtract(BigDecimal value)    // 减法运算  
public BigDecimal multiply(BigDecimal value)    // 乘法运算  
public BigDecimal divide(BigDecimal value)  // 触发运算
```

接下来我们就来通过一些案例演示一下这些成员方法的使用。

**案例1**：演示基本的四则运算

代码如下所示：

```java
public class BigDecimalDemo01 {  
	public static void main(String[] args) {
        // 创建两个BigDecimal对象  
	     BigDecimal b1 = new BigDecimal("0.3") ;  
	     BigDecimal b2 = new BigDecimal("4") ;  

	     System.out.println(b1.add(b2));         // 进行加法运算 
	     System.out.println(b1.subtract(b2));    // 进行减法运算 
	     System.out.println(b1.multiply(b2));    // 进行乘法运算 
	     System.out.println(b1.divide(b2));      // 进行除法运算  
​  
   }  
​  
}
```

运行程序进行测试，控制台输出结果如下：

```java
4.3  
-3.7  
1.2  
0.075
```

此时我们可以看到使用BigDecimal类来完成浮点数的计算不会存在损失精度的问题。

**案例2**：演示除法的特殊情况

如果使用BigDecimal类型的数据进行除法运算的时候，得到的结果是一个无限循环小数，那么就会报错：ArithmeticException。 如下代码所示：

```java
public class BigDecimalDemo02 {  
    public static void main(String[] args) {  
        // 创建两个BigDecimal对象  
        BigDecimal b1 = new BigDecimal("1") ;  
        BigDecimal b2 = new BigDecimal("3") ;  
        System.out.println(b1.divide(b2));  
    }  
​  
}
```

运行程序进行测试，控制台输出结果如下所示：

```
Exception in thread "main" java.lang.ArithmeticException: Non-terminating decimal expansion; no exact representable decimal result.  
    at java.base/java.math.BigDecimal.divide(BigDecimal.java:1716)  
    at com.itheima.api.bigdecimal.demo02.BigDecimalDemo02.main(BigDecimalDemo02.java:14)
```

针对这个问题怎么解决，此时我们就需要使用到BigDecimal类中另外一个divide方法，如下所示：

> BigDecimal divide(BigDecimal divisor, int scale, int roundingMode)

上述divide方法参数说明：

divisor:    除数对应的BigDecimal对象；  
scale:  精确的位数；  
roundingMode:   取舍模式；  

取舍模式被封装到了RoundingMode这个枚举类中（关于枚举我们后期再做重点讲解），在这个枚举类中定义了很多种取舍方式。最常见的取舍方式有如下几个：  
UP(直接进1) ， FLOOR(直接删除) ， HALF_UP(4舍五入),我们可以通过如下格式直接访问这些取舍模式：枚举类名.变量名

接下来我们就来演示一下这些取舍模式，代码如下所示：

```java
public class BigDecimalDemo02 {  
    public static void main(String[] args) {  
        // 调用方法  
        method_03() ;  
    }  
    // 演示取舍模式HALF_UP  
    public static void method_03() {  
        // 创建两个BigDecimal对象  
        BigDecimal b1 = new BigDecimal("0.3") ;  
        BigDecimal b2 = new BigDecimal("4") ;  
        System.out.println(b1.divide(b2 , 2 , RoundingMode.HALF_UP));  
    }  
    // 演示取舍模式FLOOR  
    public static void method_02() {  
        // 创建两个BigDecimal对象  
        BigDecimal b1 = new BigDecimal("1") ;  
        BigDecimal b2 = new BigDecimal("3") ;  
        System.out.println(b1.divide(b2 , 2 , RoundingMode.FLOOR));  
    }  
    // 演示取舍模式UP  
    public static void method_01() {  
        // 创建两个BigDecimal对象  
        BigDecimal b1 = new BigDecimal("1") ;  
        BigDecimal b2 = new BigDecimal("3") ;  
        System.out.println(b1.divide(b2 , 2 , RoundingMode.UP));  
    }  
}
```

小结：后期在进行两个数的除法运算的时候，我们常常使用的是可以设置取舍模式的divide方法。

### 底层存储方式：

把数据看成字符串，遍历得到里面的每一个字符，把这些字符在ASCII码表上的值，都存储到数组中。

![[bigdecimal存储原理.png]]

## 正则表达式

### 正则表达式-字符类

- 语法示例：

1. `[abc]`：代表a或者b，或者c字符中的一个。
2. `[^abc]`：代表除a,b,c以外的任何字符。
3. `[a-z]`：代表a-z的所有小写字符中的一个。
4. `[A-Z]`：代表A-Z的所有大写字符中的一个。
5. `[0-9]`：代表0-9之间的某一个数字字符。
6. `[a-zA-Z0-9]`：代表a-z或者A-Z或者0-9之间的任意一个字符。
7. `[a-dm-p]`：a 到 d 或 m 到 p之间的任意一个字符。 

```java
package com.itheima.a08regexdemo;

public class RegexDemo2 {
    public static void main(String[] args) {
        //public boolean matches(String regex):判断是否与正则表达式匹配，匹配返回true
        // 只能是a b c
        System.out.println("-----------1-------------");
        System.out.println("a".matches("[abc]")); // true
        System.out.println("z".matches("[abc]")); // false

        // 不能出现a b c
        System.out.println("-----------2-------------");
        System.out.println("a".matches("[^abc]")); // false
        System.out.println("z".matches("[^abc]")); // true
        System.out.println("zz".matches("[^abc]")); //false
        System.out.println("zz".matches("[^abc][^abc]")); //true

        // a到zA到Z(包括头尾的范围)
        System.out.println("-----------3-------------");
        System.out.println("a".matches("[a-zA-z]")); // true
        System.out.println("z".matches("[a-zA-z]")); // true
        System.out.println("aa".matches("[a-zA-z]"));//false
        System.out.println("zz".matches("[a-zA-Z]")); //false
        System.out.println("zz".matches("[a-zA-Z][a-zA-Z]")); //true
        System.out.println("0".matches("[a-zA-Z]"));//false
        System.out.println("0".matches("[a-zA-Z0-9]"));//true


        // [a-d[m-p]] a到d，或m到p
        System.out.println("-----------4-------------");
        System.out.println("a".matches("[a-d[m-p]]"));//true
        System.out.println("d".matches("[a-d[m-p]]")); //true
        System.out.println("m".matches("[a-d[m-p]]")); //true
        System.out.println("p".matches("[a-d[m-p]]")); //true
        System.out.println("e".matches("[a-d[m-p]]")); //false
        System.out.println("0".matches("[a-d[m-p]]")); //false

        // [a-z&&[def]] a-z和def的交集。为:d，e，f
        System.out.println("----------5------------");
        System.out.println("a".matches("[a-z&[def]]")); //false
        System.out.println("d".matches("[a-z&&[def]]")); //true
        System.out.println("0".matches("[a-z&&[def]]")); //false

        // [a-z&&[^bc]] a-z和非bc的交集。(等同于[ad-z])
        System.out.println("-----------6------------_");
        System.out.println("a".matches("[a-z&&[^bc]]"));//true
        System.out.println("b".matches("[a-z&&[^bc]]")); //false
        System.out.println("0".matches("[a-z&&[^bc]]")); //false

        // [a-z&&[^m-p]] a到z和除了m到p的交集。(等同于[a-1q-z])
        System.out.println("-----------7-------------");
        System.out.println("a".matches("[a-z&&[^m-p]]")); //true
        System.out.println("m".matches("[a-z&&[^m-p]]")); //false
        System.out.println("0".matches("[a-z&&[^m-p]]")); //false

    }
}
```

### 正则表达式-逻辑运算符

- 语法示例：

  1. &&：并且
  2. |    ：或者
  3. \  ：转义字符

- 代码示例：

```java
public class Demo {
	public static void main(String[] args) {
		String str = "had";
		
		//1.要求字符串是小写辅音字符开头，后跟ad
		String regex = "[a-z&&[^aeiou]]ad";
		System.out.println("1." + str.matches(regex));
		
		//2.要求字符串是aeiou中的某个字符开头，后跟ad
		regex = "[a|e|i|o|u]ad";//这种写法相当于：regex = "[aeiou]ad";
		System.out.println("2." + str.matches(regex));
	}
}
```

### 正则表达式-预定义字符

- 语法示例：
    
    1. "." ： 匹配任何字符。
        
    2. "\d"：任何数字`[0-9]`的简写；
        
    3. "\D"：任何非数字`[^0-9]`的简写；
        
    4. "\s"： 空白字符：`[ \t\n\x0B\f\r]` 的简写
        
    5. "\S"： 非空白字符：`[^\s] `的简写
        
    6. "\w"：单词字符：`[a-zA-Z_0-9]`的简写
        
    7. "\W"：非单词字符：`[^\w]`

```java
public class Demo {
	public static void main(String[] args) {
        //.表示任意一个字符
        System.out.println("你".matches("..")); //false
        System.out.println("你".matches(".")); //true
        System.out.println("你a".matches(".."));//true

        // \\d 表示任意的一个数字
        // \\d只能是任意的一位数字
        // 简单来记:两个\表示一个\
        System.out.println("a".matches("\\d")); // false
        System.out.println("3".matches("\\d")); // true
        System.out.println("333".matches("\\d")); // false

        //\\w只能是一位单词字符[a-zA-Z_0-9]
        System.out.println("z".matches("\\w")); // true
        System.out.println("2".matches("\\w")); // true
        System.out.println("21".matches("\\w")); // false
        System.out.println("你".matches("\\w"));//false

        // 非单词字符
        System.out.println("你".matches("\\W")); // true
        System.out.println("---------------------------------------------");
        // 以上正则匹配只能校验单个字符。


        // 必须是数字 字母 下划线 至少 6位
        System.out.println("2442fsfsf".matches("\\w{6,}"));//true
        System.out.println("244f".matches("\\w{6,}"));//false

        // 必须是数字和字符 必须是4位
        System.out.println("23dF".matches("[a-zA-Z0-9]{4}"));//true
        System.out.println("23 F".matches("[a-zA-Z0-9]{4}"));//false
        System.out.println("23dF".matches("[\\w&&[^_]]{4}"));//true
        System.out.println("23_F".matches("[\\w&&[^_]]{4}"));//false
		
	}
}
```

### 正则表达式-数量词

- 语法示例：
  1. X? : 0次或1次
  2. X* : 0次到多次
  3. X+ : 1次或多次
  4. X{n} : 恰好n次
  5. X{n,} : 至少n次
  6. X{n,m}: n到m次(n和m都是包含的)

```java
public class Demo {
	public static void main(String[] args) {
		 // 必须是数字 字母 下划线 至少 6位
        System.out.println("2442fsfsf".matches("\\w{6,}"));//true
        System.out.println("244f".matches("\\w{6,}"));//false

        // 必须是数字和字符 必须是4位
        System.out.println("23dF".matches("[a-zA-Z0-9]{4}"));//true
        System.out.println("23 F".matches("[a-zA-Z0-9]{4}"));//false
        System.out.println("23dF".matches("[\\w&&[^_]]{4}"));//true
        System.out.println("23_F".matches("[\\w&&[^_]]{4}"));//false
	}
}
```

### 贪婪爬取和非贪婪爬取

只写+和表示贪婪匹配，如果在+和后面加问号表示非贪婪爬取  
+? 非贪婪匹配  
\*? 非贪婪匹配  
贪婪爬取:在爬取数据的时候尽可能的多获取数据  
非贪婪爬取:在爬取数据的时候尽可能的少获取数据  
​  
举例：  
如果获取数据：ab+  
贪婪爬取获取结果:abbbbbbbbbbbb  
非贪婪爬取获取结果:ab

```java
public class RegexDemo10 {
    public static void main(String[] args) {
        /*
            只写+和*表示贪婪匹配

            +? 非贪婪匹配
            *? 非贪婪匹配

            贪婪爬取:在爬取数据的时候尽可能的多获取数据
            非贪婪爬取:在爬取数据的时候尽可能的少获取数据

            ab+:
            贪婪爬取:abbbbbbbbbbbb
            非贪婪爬取:ab
        */
        String s = "Java自从95年问世以来，abbbbbbbbbbbbaaaaaaaaaaaaaaaaaa" +
                "经历了很多版木，目前企业中用的最多的是]ava8和]ava11，因为这两个是长期支持版木。" +
                "下一个长期支持版本是Java17，相信在未来不久Java17也会逐渐登上历史舞台";

        String regex = "ab+";
        Pattern p = Pattern.compile(regex);
        Matcher m = p.matcher(s);

        while (m.find()) {
            System.out.println(m.group());
        }


    }
}
```

### String的split方法中使用正则表达式

- String类的split()方法原型：
    
```java
    public String[] split(String regex)  
    //参数regex表示正则表达式。可以将当前字符串中匹配regex正则表达式的符号作为"分隔符"来切割字符串。
```
    
- 代码示例：

```java
/*
            有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
            要求2:把字符串中的三个姓名切割出来*/

String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";
//细节:
//方法在底层跟之前一样也会创建文本解析器的对象
//然后从头开始去读取字符串中的内容，只要有满足的，那么就切割。
String[] arr = s.split("[\\w&&[^_]]+");
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

### String类的replaceAll方法中使用正则表达式

- String类的replaceAll()方法原型：

```java
public String replaceAll(String regex,String newStr)
//参数regex表示一个正则表达式。可以将当前字符串中匹配regex正则表达式的字符串替换为newStr。
```

- 代码示例：

```java
/*
            有一段字符串:小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠
            要求1:把字符串中三个姓名之间的字母替换为vs
            要求2:把字符串中的三个姓名切割出来*/

String s = "小诗诗dqwefqwfqwfwq12312小丹丹dqwefqwfqwfwq12312小惠惠";
//细节:
//方法在底层跟之前一样也会创建文本解析器的对象
//然后从头开始去读取字符串中的内容，只要有满足的，那么就用第一个参数去替换。
String result1 = s.replaceAll("[\\w&&[^_]]+", "vs");
System.out.println(result1);
```

### 忽略大小写的写法

```java
//(?i) ：表示忽略后面数据的大小写
//忽略abc的大小写
String regex = "(?i)abc";
//a需要一模一样，忽略bc的大小写
String regex = "a(?i)bc";
//ac需要一模一样，忽略b的大小写
String regex = "a((?i)b)c";
```

### 正则表达式-分组括号( )

```java
//需求1:判断一个字符串的开始字符和结束字符是否一致?只考虑一个字符
//举例: a123a b456b 17891 &abc& a123b(false)
// \\组号:表示把第X组的内容再出来用一次
String regex1 = "(.).+\\1";
System.out.println("a123a".matches(regex1));
System.out.println("&abc&".matches(regex1));
System.out.println("a123b".matches(regex1));
System.out.println("--------------------------");

String str = "我要学学编编编编程程程程程程";

//需求:把重复的内容 替换为 单个的
//学学                学
//编编编编            编
//程程程程程程        程
//  (.)表示把重复内容的第一个字符看做一组
//  \\1表示第一字符再次出现
//  + 至少一次
//  $1 表示把正则表达式中第一组的内容，再拿出来用
String result = str.replaceAll("(.)\\1+", "$1");
System.out.println(result);
```

### 非捕获分组

非捕获分组：分组之后不需要再用本组数据，仅仅是把数据括起来。

```java
//身份证号码的简易正则表达式
//非捕获分组:仅仅是把数据括起来
//特点:不占用组号
//这里\\1报错原因:(?:)就是非捕获分组，此时是不占用组号的。


//(?:) (?=) (?!)都是非捕获分组//更多的使用第一个
//String regex1 ="[1-9]\\d{16}(?:\\d|x|x)\\1";
String regex2 ="[1-9]\\d{16}(\\d Xx)\\1";
//^([01]\d|2[0-3]):[0-5]\d:[@-5]\d$

System.out.println("41080119930228457x".matches(regex2));
```
# java EE



