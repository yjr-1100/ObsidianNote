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

# java EE



