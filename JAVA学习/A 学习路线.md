[Java 学习路线 by 程序员鱼皮](https://github.com/liyupi/codefather/blob/main/%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF/Java%E5%AD%A6%E4%B9%A0%E8%B7%AF%E7%BA%BF%20by%20%E7%A8%8B%E5%BA%8F%E5%91%98%E9%B1%BC%E7%9A%AE.md)
[java工程师之路](https://hollischuang.gitee.io/tobetopjavaer/#/menu?id=%E7%9B%AE%E5%BD%95)
[Java后端学习路线](https://zhuanlan.zhihu.com/p/652601404)
[Java学习路线](https://www.zhihu.com/tardis/bd/art/377897661?source_id=1001)
[Java学习路线](https://www.bilibili.com/read/cv27536199/?jump_opus=1)
[Java的数据结构和算法](https://blog.csdn.net/qq_43422402/article/details/136663325)
[github刷题指导](https://github.com/labuladong/fucking-algorithm)
# java SE

[[1 java 快速入门]]

## 2 基础语法

### 注释

Java中的注释分为三种：

* 单行注释：


```java
// 这是单行注释文字
```


* 多行注释：

~~~java
/*
这是多行注释文字
这是多行注释文字
这是多行注释文字
*/
注意：多行注释不能嵌套使用。
~~~

* 文档注释（暂时用不到）：

```java
/**
参数：
返回值：
功能：
*/
```


### 关键字

被Java赋予了特定含义的英文单词。

​当我们在代码中写了关键字之后，程序在运行的时候，就知道要做什么事情了。

| **abstract**   | **assert**       | **boolean**   | **break**      | **byte**   |
| -------------- | ---------------- | ------------- | -------------- | ---------- |
| **case**       | **catch**        | **char**      | **class**      | **const**  |
| **continue**   | **default**      | **do**        | **double**     | **else**   |
| **enum**       | **extends**      | **final**     | **finally**    | **float**  |
| **for**        | **goto**         | **if**        | **implements** | **import** |
| **instanceof** | **int**          | **interface** | **long**       | **native** |
| **new**        | **package**      | **private**   | **protected**  | **public** |
| **return**     | **strictfp**     | **short**     | **static**     | **super**  |
| **switch**     | **synchronized** | **this**      | **throw**      | **throws** |
| **transient**  | **try**          | **void**      | **volatile**   | **while**  |

#### class关键字

表示定义一个类。创建一个类。

类：Java项目最基本的组成单元，一个完整的Java项目有可能会有成千上万个类来组成的。

class后面跟随的就是这个类的名字，简称：类名。

在类名后面会有一对大括号，表示这个类的内容。

举例：

```java
public class HelloWorld{
    
   
}
```

解释：class表示定义类。

​类名：HelloWorld

​HelloWorld后面的大括号表示这个类的范围。


### 字面量

作用：告诉程序员，数据在程序中的书写格式。

| **字面量类型** | **说明**                                  | **程序中的写法**           |
| -------------- | ----------------------------------------- | -------------------------- |
| 整数           | 不带小数的数字                            | 666，-88                   |
| 小数           | 带小数的数字                              | 13.14，-5.21               |
| 字符           | 必须使用单引号，有且仅能一个字符          | ‘A’，‘0’，   ‘我’          |
| 字符串         | 必须使用双引号，内容可有可无              | “HelloWorld”，“黑马程序员” |
| 布尔值         | 布尔值，表示真假，只有两个值：true，false | true 、false               |
| 空值           | 一个特殊的值，空值                        | 值是：null                 |

~~~java
public class Demo {
    public static void main(String[] args) {
        System.out.println(10); // 输出一个整数
        System.out.println(5.5); // 输出一个小数
        System.out.println('a'); // 输出一个字符
        System.out.println(true); // 输出boolean值true
        System.out.println("欢迎来到黑马程序员"); // 输出字符串
    }
}
~~~

> 区分技巧
> 1. 不带小数点的数字都是整数类型的字面量。
> 2. 只要带了小数点，那么就是小数类型的字面量。
> 3. 只要用双引号引起来的，不管里面的内容是什么，不管里面有没有内容，都是字符串类型的字面量。
> 4. 字符类型的字面量必须用单引号引起来，不管内容是什么，但是个数有且只能有一个。
> 5. 字符类型的字面量只有两个值，true、false。
> 6. 空类型的字面量只有一个值，null。

### 命名规则

#### 硬性要求：

- 必须由数字、字母、下划线_、美元符号$组成。
- 数字不能开头
- 不能是关键字
- 区分大小写的。

#### 小驼峰命名法

适用于**变量名**和**方法名**

* 如果是一个单词，那么全部小写，比如：name

* 如果是多个单词，那么从第二个单词开始，首字母大写，比如：firstName、maxAge

#### 大驼峰命名法

适用于**类名**

* 如果是一个单词，那么首字母大写。比如：Demo、Test。

* 如果是多个单词，那么每一个单词首字母都需要大写。比如：HelloWorld

不管起什么名字，都要做到见名知意。

### 变量

#### 什么是变量？

​	变量就在程序中临时存储数据的容器。但是这个容器中只能存一个值。

#### 变量的定义格式

​`数据类型 变量名 = 数据值；
##### 格式详解

​	数据类型：限定了变量当中能存储什么类型的数据。

​			   如果要存10，那么数据类型就需要写整数类型。

​			   如果要存10.0，那么数据类型就需要写小数类型。

​	变量名：其实就是这个容器的名字。

​			当以后想要使用变量里面的数据时，直接使用变量名就可以了。

​	数据值：真正存储在容器中的数据。

​	分号：表示语句的结束，就跟以前写作文时候的句号是一样的。
#### 变量的注意事项

- 变量名不能重复
- 在一条语句中，可以定义多个变量。但是这种方式影响代码的阅读，所以了解一下即可。
- 变量在使用之前必须要赋值。

### 数据类型与自动拆装箱

#### Java语言数据类型的分类

- 基本数据类型
- 引用数据类型（面向对象的时候再深入学习）

#### 基本数据类型的四类八种

| 数据类型 | 关键字  | 内存占用 |                 取值范围                  |
| :------: | :-----: | :------: | :---------------------------------------: |
|   整数   |  byte   |    1     |    负的2的7次方 ~ 2的7次方-1(-128~127)    |
|          |  short  |    2     | 负的2的15次方 ~ 2的15次方-1(-32768~32767) |
|          |   int   |    4     |        负的2的31次方 ~ 2的31次方-1        |
|          |  long   |    8     |        负的2的63次方 ~ 2的63次方-1        |
|  浮点数  |  float  |    4     |        1.401298e-45 ~ 3.402823e+38        |
|          | double  |    8     |      4.9000000e-324 ~ 1.797693e+308       |
|   字符   |  char   |    2     |                  0-65535                  |
|   布尔   | boolean |    1     |                true，false                |
> String不是基本数据类型，是引用类型。

每个类型都有一定的表示范围，但是，在程序中有些计算会导致超出表示范围，即溢出。溢出的时候并不会抛异常，也没有任何提示。所以，在程序中，使用同类型的数据进行运算的时候，一定要注意数据溢出的问题。

由于计算机中保存的小数其实是十进制的小数的近似值，并不是准确值，所以，千万不要在代码中使用浮点数来表示金额等重要的指标。建议使用BigDecimal或者Long（单位为分）来表示金额。

#### 定义8种基本数据类型变量

```java
public class VariableDemo3{
    public static void main(String[] args){
        //1.定义byte类型的变量
        //数据类型 变量名 = 数据值;
        byte a = 10;
        System.out.println(a);

        //2.定义short类型的变量
        short b = 20;
        System.out.println(b);

        //3.定义int类型的变量
        int c = 30;
        System.out.println(c);

        //4.定义long类型的变量
        long d = 123456789123456789L;
        System.out.println(d);

        //5.定义float类型的变量
        float e = 10.1F;
        System.out.println(e);

        //6.定义double类型的变量
        double f = 20.3;
        System.out.println(f);

        //7.定义char类型的变量
        char g = 'a';
        System.out.println(g);

        //8.定义boolean类型的变量
        boolean h = true;
        System.out.println(h);

    }
}
```


#### 自动拆装箱

##### 基本数据类型有什么好处

我们都知道在 Java 语言中，`new` 一个对象是存储在**堆**里的，我们通过**栈**中的**引用**来使用这些对象；所以，对象本身来说是比较**消耗资源**的。

对于经常用到的类型，如 int 等，如果我们每次使用这种变量的时候都需要 `new` 一个 Java 对象的话，就会比较笨重。所以，和 C++ 一样，Java 提供了基本数据类型，这种数据的变量不需要使用 new 创建，他们不会在堆上创建，而是直接在栈内存中存储，因此会更加高效。

##### 包装类型

Java 语言是一个面向对象的语言，但是 Java 中的**基本数据类型却是不面向对象**的，由于很多地方都需要使用对象而不是基本数据类型。比如，在集合类中，我们是无法将 int 、double 等类型放进去的。因为集合的容器要求元素是 Object 类型。为了让基本类型也具有对象的特征，就出现了包装类型，它相当于将基本类型“包装起来”，使得它具有了对象的性质，并且为其添加了属性和方法，丰富了基本类型的操作。这在实际使用时存在很多的不便，为了解决这个不足，在设计类时为**每个基本数据类型设计了一个对应的类**进行代表，这样八个和基本数据类型对应的类统称为包装类(Wrapper Class)。

包装类均位于 `java.lang` 包，包装类和基本数据类型的对应关系如下表所示

| 基本数据类型  | 包装类       |
| ------- | --------- |
| byte    | Byte      |
| boolean | Boolean   |
| short   | Short     |
| char    | Character |
| int     | Integer   |
| long    | Long      |
| float   | Float     |
| double  | Double    |

在这八个类名中，除了 Integer 和 Character 类以后，其它六个类的类名和基本数据类型一致，只是类名的第一个字母大写即可。

##### 拆箱与装箱

有了基本数据类型和包装类，肯定有些时候要在他们之间进行转换。比如把一个基本数据类型的 `int` 转换成一个包装类型的` Integer `对象。

我们认为包装类是对基本类型的包装，所以，把**基本数据类型转换成包装类的过程就是打包装**，英文对应于 boxing，中文翻译为**装箱**。

反之，把**包装类转换成基本数据类型的过程就是拆包装**，英文对应于 unboxing，中文翻译为**拆箱**。

在 Java SE5 之前，要进行装箱，可以通过以下代码：

```
    Integer i = new Integer(10);
```

##### 自动拆箱与自动装箱

在 Java SE5 中，为了减少开发人员的工作，Java 提供了自动拆箱与自动装箱功能。

自动装箱: 就是将基本数据类型自动转换成对应的包装类。

自动拆箱：就是将包装类自动转换成对应的基本数据类型。

```
    Integer i = 10;  //自动装箱
    int b = i;     //自动拆箱
```

`Integer i=10` 可以替代 `Integer i = new Integer(10);`，这就是因为 Java 帮我们提供了自动装箱的功能，不需要开发者手动去 new 一个 Integer 对象。

> 自动装箱都是通过包装类的 `valueOf()` 方法来实现的.自动拆箱都是通过包装类对象的 `xxxValue()` 来实现的。

```java
public static void main(String[]args){ 
	Integer integer=Integer.valueOf(1); 
	int i=integer.intValue(); 
}
```

##### 哪些地方会自动拆装箱

我们了解过原理之后，在来看一下，什么情况下，Java 会帮我们进行自动拆装箱。前面提到的变量的初始化和赋值的场景就不介绍了，那是最简单的也最容易理解的。

我们主要来看一下，那些可能被忽略的场景。

###### 场景一、将基本数据类型放入集合类

我们知道，Java 中的集合类只能接收对象类型，那么以下代码为什么会不报错呢，因为当我们把基本数据类型放入集合类中的时候，会进行自动装箱

```
    List<Integer> li = new ArrayList<>();
    for (int i = 1; i < 50; i ++){
        li.add(i);
    }
```

###### 场景二、包装类型和基本类型的大小比较

有没有人想过，当我们对 Integer 对象与基本类型进行大小比较的时候，实际上比较的是什么内容呢？看以下代码：

```
    Integer a = 1;
    System.out.println(a == 1 ? "等于" : "不等于");
    Boolean bool = false;
    System.out.println(bool ? "真" : "假");
```

包装类与基本数据类型进行比较运算，是先将包装类进行拆箱成基本数据类型，然后进行比较的。
###### 场景三、包装类型的运算

有没有人想过，当我们对 Integer 对象进行四则运算的时候，是如何进行的呢？看以下代码：

```
    Integer i = 10;
    Integer j = 20;

    System.out.println(i+j);
```

反编译后代码如下：

```
    Integer i = Integer.valueOf(10);
    Integer j = Integer.valueOf(20);
    System.out.println(i.intValue() + j.intValue());
```

我们发现，两个包装类型之间的运算，会被自动拆箱成基本类型进行。

###### 场景四、三目运算符的使用

这是很多人不知道的一个场景，作者也是一次线上的血淋淋的 Bug 发生后才了解到的一种案例。看一个简单的三目运算符的代码：

```
    boolean flag = true;
    Integer i = 0;
    int j = 1;
    int k = flag ? i : j;
```

很多人不知道，其实在 `int k = flag ? i : j;` 这一行，会发生自动拆箱（ JDK1.8 之前，详见：[《阿里巴巴Java开发手册-泰山版》提到的三目运算符的空指针问题到底是个怎么回事？](https://www.hollischuang.com/archives/4749) ）。

反编译后代码如下：

```
    boolean flag = true;
    Integer i = Integer.valueOf(0);
    int j = 1;
    int k = flag ? i.intValue() : j;
    System.out.println(k);
```

这其实是三目运算符的语法规范。当第二，第三位操作数分别为基本类型和对象时，其中的对象就会拆箱为基本类型进行操作。

因为例子中，`flag ? i : j;` 片段中，第二段的 i 是一个包装类型的对象，而第三段的 j 是一个基本类型，所以会对包装类进行自动拆箱。如果这个时候 i 的值为 `null`，那么就会发生 NPE。（[自动拆箱导致空指针异常](http://www.hollischuang.com/archives/435)）

###### 场景五、函数参数与返回值

这个比较容易理解，直接上代码了：

```
    //自动拆箱
    public int getNum1(Integer num) {
     return num;
    }
    //自动装箱
    public Integer getNum2(int num) {
     return num;
    }
```

##### 自动拆装箱与缓存

Java SE 的自动拆装箱还提供了一个和缓存有关的功能，我们先来看以下代码，猜测一下输出结果：

```java
    public static void main(String... strings) {

        Integer integer1 = 3;
        Integer integer2 = 3;

        if (integer1 == integer2)
            System.out.println("integer1 == integer2");
        else
            System.out.println("integer1 != integer2");

        Integer integer3 = 300;
        Integer integer4 = 300;

        if (integer3 == integer4)
            System.out.println("integer3 == integer4");
        else
            System.out.println("integer3 != integer4");
    }
```

我们普遍认为上面的两个判断的结果都是 false。虽然比较的值是相等的，但是由于比较的是对象，而对象的引用不一样，所以会认为两个 if 判断都是 false 的。在 Java 中，**`==` 比较的是对象引用，而 `equals` 比较的是值**。所以，在这个例子中，不同的对象有不同的引用，所以在进行比较的时候都将返回 false。奇怪的是，这里两个类似的 if 条件判断返回不同的布尔值。

上面这段代码真正的输出结果：

```
integer1 == integer2
integer3 != integer4
```

原因就和 Integer 中的缓存机制有关。在 Java 5 中，在 Integer 的操作上引入了一个新功能来节省内存和提高性能。**整型对象通过使用相同的对象引用实现了缓存和重用**。

> 适用于整数值区间 -128 至 +127。
> 
> 只适用于自动装箱。使用构造函数创建对象不适用。

具体的代码实现可以阅读[Java中整型的缓存机制](http://www.hollischuang.com/archives/1174)一文，这里不再阐述。

我们只需要知道，当需要进行自动装箱时，如果数字在 -128 至 127 之间时，会直接使用缓存中的对象，而不是重新创建一个对象。

其中的 Javadoc 详细的说明了缓存支持 -128 到 127 之间的自动装箱过程。最大值 127 可以通过 `-XX:AutoBoxCacheMax=size` 修改。

实际上这个功能在 Java 5 中引入的时候,范围是固定的 -128 至 +127。后来在 Java 6 中，可以通过 `java.lang.Integer.IntegerCache.high` 设置最大值。

这使我们可以根据应用程序的实际情况灵活地调整来提高性能。到底是什么原因选择这个 -128 到 127 范围呢？因为这个范围的数字是最被广泛使用的。 在程序中，第一次使用 Integer 的时候也需要一定的额外时间来初始化这个缓存。

在 Boxing Conversion 部分的 Java 语言规范(JLS)规定如下：

如果一个变量 p 的值是：

- -128 至 127 之间的整数 (§3.10.1)
- true 和 false 的布尔值 (§3.10.3)
- `\u0000` 至 `\u007f` 之间的字符 (§3.10.4)

范围内的时，将 p 包装成 a 和 b 两个对象时，可以直接使用 a == b 判断 a 和 b 的值是否相等。







# java EE



