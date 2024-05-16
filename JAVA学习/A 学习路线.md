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
[[9 查找和排序]]
[[10 List集合]]

# 11 枚举和注解

## 枚举

枚举对应英文(enumeration,简写 enum)

枚举是一组常量的集合。可以理解:枚举属于一种特殊的类，里面只包含一组有限的特定的对象

### 自定义枚举类

1. 构造函数私有，禁止在外部直接**new**
2. 不需要提供setXxx 方法，因为枚举对象值通常为只读,
3. 对枚举对象/属性使用 final + static 共同修饰，实现底层优化
4. 枚举对象名通常使用全部大写，常量的命名规范.
5. 枚举对象根据需要，也可以有多个属性 

```java
package top.jerry1100.demo1;  
  
public class Enumeration {  
    public static void main(String[] args) {  
        System.out.println(Seanon.AUTUMN);  
        System.out.println(Seanon.SPRINT);  
        System.out.println(Seanon.WINTER);  
        System.out.println(Seanon.SUMMER);  
    }  
  
}  
  
class Seanon{  
    private String name; // 名字  
    private String desc; // 描述  
//    定义四个对象  
    public static final Seanon SPRINT = new Seanon("春天","温暖");  
    public static final Seanon SUMMER = new Seanon("夏天","炎热");  
    public static final Seanon AUTUMN = new Seanon("秋天","凉爽");  
    public static final Seanon WINTER = new Seanon("冬天","寒冷");  
    private Seanon(String name,String desc){  
        this.name = name;  
        this.desc = desc;  
    }  
  
    public String getDesc() {  
        return desc;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    @Override  
    public String toString() {  
        return "Seanon{" +  
                "name='" + name + '\'' +  
                ", desc='" + desc + '\'' +  
                '}';  
    }  
}
```

### 使用enum关键字实现枚举

1. 使用关键字 enum 替代 class
2. public static final Season SPRING = new Season("春天"，"温暖")直接使用 SPRING("春天"，"温暖")解读 常量名(实参列表)
3. 如果有多个常量(对象)，使用号间隔即可
4. 如果使用enum 来实现枚举，要求将定义常量对象，写在前面
5. 使用了enum关键字以后就不能再继承它了，因为enum会隐式继承Enum，而java是单继承机制，但是还可以实现接口

```java
package top.jerry1100.demo1;  
  
public class Enumeration {  
    public static void main(String[] args) {  
        System.out.println(Seanon.AUTUMN);  
        System.out.println(Seanon.SPRINT);  
        System.out.println(Seanon.WINTER);  
        System.out.println(Seanon.SUMMER);  
    }  
}  
enum Seanon{  
//    定义四个对象  
    SPRINT("春天","温暖"),  
    SUMMER("夏天","炎热"),  
    AUTUMN("秋天","凉爽"),  
    WINTER("冬天","寒冷");  
    private String name; // 名字  
    private String desc; // 描述  
    private Seanon(String name,String desc){  
        this.name = name;  
        this.desc = desc;  
    }  
    public String getDesc() {  
        return desc;  
    }  
    public String getName() {  
        return name;  
    }  
    @Override  
    public String toString() {  
        return "Seanon{" +  
                "name='" + name + '\'' +  
                ", desc='" + desc + '\'' +  
                '}';  
    }  
}
```

### enum 关键字的一些常用方法

```java
//        输出枚举对象的顺序和名字  
        Seanon autumn = Seanon.AUTUMN;  
        System.out.println(autumn.ordinal()); //2  
        System.out.println(autumn.name()); //AUTUMN  
//        得到所有枚举对象  
        Seanon[] values = Seanon.values();  
        for(Seanon i :values){  
            System.out.println(i);  
        }  
//        根据输入的字符串，得到枚举对象，如果没有会报错  
        Seanon autumn2 = Seanon.valueOf("AUTUMN");  
        System.out.println(autumn2);  
//        比较两个常量，就是在比较他们的ordinal  
        System.out.println(Seanon.AUTUMN.compareTo(autumn2));//0  
        System.out.println(autumn.compareTo(autumn2));//0  
        System.out.println(Seanon.SPRINT.compareTo(autumn2));//-2
```

## 注解

注解的理解
1)注解(Annotation)也被称为元数据(Metadata),用于修饰解释 包、类、方法、属性、构造器、局部变量等数据信息。
2)和注释一样，注解不影响程序逻辑，但注解可以被编译或运行，相当于嵌入在代码中的补充信息。
3)在JavaSE中，注解的使用目的比较简单，例如标记过时的功能，忽略警告等。在JavaEE中注解占据了更重要的角色，例如用来配置应用程序的任何切面，代替java EE旧版中所遗留的繁冗代码和XML配置等。


使用 Annotation 时要在其前面增加 @ 符号, 并把该 Annotation 当成一个修饰符使用。用于修饰它支持的程序元素，三个基本的 Annotation:
@Override: 限定某个方法，是重写父类方法,该注解只能用于方法
@Deprecated: 用于表示某个程序元素(类,方法等)已过时
@SuppressWarnings: 抑制编译器警告

### @Override

**Override 使用说明**
1. @Override 表示指定重写父类的方法(从编译层面验证)，如果父类没有fly方法，则会报错
2. 如果不写@Override 注解,而父类仍有 public void fly(){}，仍然构成重写
3. @Override 只能修饰方法，不能修饰其它类，包，属性等等
4. 查看@Override注解源码为 @Target(ElementType.METHOD),说明只能修饰方法
5. @Target 是修饰注解的注解， 称为元注解

```java
class Father{//父类
	public void fly(){
		System.out.println("Father fly...");
	}
}
class Son extends Father {//子类
	@0verride
	//说明 写不写override都是重写，但是写了注解，编译器会去检查该方法是否真的重写，如果重写就编译通过，如果没重写则编译不通过
	public void fly(){
		System.out.println("Son fly...."),
	}
}
```

### @Deprecated

1. 用于表示某个程序元素(类,方法等)已过时
2. 可以修饰方法，类，字段,包,参数 等等
3. @Target(value={CONSTRUCTOR, FIELD, LOCAL VARIABLE, METHOD PACKAGE,PARAMETER, TYPE})
4. Deprecated 的作用可以做到新旧版本的兼容和过渡

```java
@Deprecated
class A {
	@Deprecated
	public int n1 = 10;
	@Deprecated
	public void hi(){
		System.out.println("hi");
	}
}
```


# java EE









