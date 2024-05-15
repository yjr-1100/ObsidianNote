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
# java EE









