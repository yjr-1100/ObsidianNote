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























# java EE



