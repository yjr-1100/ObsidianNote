## 1 java 快速入门

### Java概述
#### 为什么Java应用最广泛？

从互联网到企业平台，Java是应用最广泛的编程语言，原因在于：

- Java是基于JVM虚拟机的跨平台语言，一次编写，到处运行；
    
- Java程序易于编写，而且有内置垃圾收集，不必考虑内存管理；
    
- Java虚拟机拥有工业级的稳定性和高度优化的性能，且经过了长时期的考验；
    
- Java拥有最广泛的开源社区支持，各种高质量组件随时可用。
    

Java语言常年霸占着三大市场：

- 互联网和企业应用，这是Java EE的长期优势和市场地位；
    
- 大数据平台，主要有Hadoop、Spark、Flink等，他们都是Java或Scala（一种运行于JVM的编程语言）开发的；
    
- Android移动平台。
#### Java简介

Java介于编译型语言和解释型语言之间。
> 1. 编译型语言如C、C++，代码是直接编译成机器码执行，但是不同的平台（x86、ARM等）CPU的指令集不同，因此，需要编译出每一种平台的对应机器码。
> 2. 解释型语言如Python、Ruby没有这个问题，可以由解释器直接加载源码然后运行，代价是运行效率太低。

![[image-20210923091350952.png]]

Java是将代码编译成一种“字节码”，它类似于抽象的CPU指令，然后，针对不同平台编写虚拟机，不同平台的虚拟机负责加载字节码并执行，这样就实现了“一次编写，到处运行”的效果。当然，这是针对Java开发者而言。对于虚拟机，需要为每个平台分别开发。为了保证不同平台、不同公司开发的虚拟机都能正确执行Java字节码，SUN公司制定了一系列的Java虚拟机规范。从实践的角度看，JVM的兼容性做得非常好，低版本的Java字节码完全可以正常运行在高版本的JVM上。

#### Java的三大平台

- Java SE：Standard Edition 标准版，包含标准的JVM和标准库
	
- Java EE：Enterprise Edition 企业版，它只是在Java SE的基础上加上了大量的API和库，以便方便开发Web应用、数据库、消息服务等，Java EE的应用使用的虚拟机和Java SE完全相同。
	
- Java ME：Micro Edition 小型版，用于嵌入式消费类电子设备或者小型移动设备的开发。其中最为主要的还是小型移动设备的开发（手机）。渐渐的没落了，已经被安卓和IOS给替代了。

![[Pasted image 20240408090534.png]]

#### Java的主要特性

- 面向对象
- 安全性
- 多线程
- 简单易用
- 开源
- 跨平台


### java下载安装

#### JVM、JDK 与 JRE

初学者学Java，经常听到JVM、JDK、JRE这些名词，它们到底是啥？

- JDK：Java Development Kit
- JRE：Java Runtime Environment
- JVM：Java Virtual Machine

简单地说，**JRE**就是Java的运行环境。
但是，如果只有Java源码，要编译成Java字节码，就需要**JDK**，因为**JDK**除了包含**JRE**，还提供了编译器、调试器等开发工具。

![[Pasted image 20240408091002.png]]

####  JDK的安装目录介绍

本次学习使用 `JDK 22`

| 目录名称 | 说明                                                         |
| -------- | ------------------------------------------------------------ |
| bin      | 该路径下存放了JDK的各种工具命令。javac和java就放在这个目录。 |
| conf     | 该路径下存放了JDK的相关配置文件。                            |
| include  | 该路径下存放了一些平台特定的头文件。                         |
| jmods    | 该路径下存放了JDK的各种模块。                                |
| legal    | 该路径下存放了JDK各模块的授权文档。                          |
| lib      | 该路径下存放了JDK工具的一些补充JAR包。                       |

### 原始的开发方式

1. 编写后缀为 `.java` 的源代码文件
```java
public class HelloWorld {
	public static void main(String[] args) {
		System.out.println("HelloWorld");
	}
}
```
2. 使用 ` javac + 文件名 + .java ` 来进行编译 编译后生成 `.class` 文件
3. 使用 ` java + 文件名` 来运行

为什么要用main方法要public static：首先，由于java虚拟机需要在类外调用main方法，所以该方法的访问权限必须是public的，又因为Java虚拟机运行时系统在开始执行一个程序前并没有创建main（）方法所在类的一个实例对象 ，static 关键字告诉编译器，这个函数是静态函数，不需要创建对象，可以直接访问，并且static方法在静态数据区，可以直接调用，不用每次都生成。
### IDEA的使用

#### IDEA概述

IDEA全称IntelliJ IDEA，是用于Java语言开发的集成环境，它是业界公认的目前用于Java程序开发最好的工具。

**集成环境：** 把代码编写，编译，执行，调试等多种功能综合到一起的开发工具。

#### IDEA中项目的结构

##### 结构分类

- project（项目、工程）
- module（模块）
- package（包）
- class（类）

##### 结构介绍

​	为了让大家更好的吸收，package这一层级，我们后面再学习，先学习最基础的project、module、class。

project（项目、工程）

> 淘宝、京东、黑马程序员网站都属于一个个项目，IDEA中就是一个个的Project。

 module（模块）

> 在一个项目中，可以存放多个模块，不同的模块可以存放项目中不同的业务功能代码。在黑马程序员的官方网站中，至少包含了以下模块：
> 	- 论坛模块
> 	- 报名、咨询模块
> 为了更好的管理代码，我们会把代码分别放在两个模块中存放。

package（包）

> 一个模块中又有很多的业务，以黑马程序员官方网站的论坛模块为例，至少包含了以下不同的业务。
> 	- 发帖
> 	- 评论
 > 为了把这些业务区分的更加清楚，就会用包来管理这些不同的业务。

 class（类）

> 就是真正写代码的地方。

一个Java源码只能定义一个`public`类型的class，并且class名称和文件名要完全一致；