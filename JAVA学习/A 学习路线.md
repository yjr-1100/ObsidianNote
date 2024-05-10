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

# 10 List集合

## Collection集合

### 数组和集合的区别【理解】

- 相同点
    
    都是容器,可以存储多个数据
    
- 不同点
    
    - 数组的长度是不可变的,集合的长度是可变的
        
    - 数组可以存基本数据类型和引用数据类型
        
        集合只能存引用数据类型,如果要存基本数据类型,需要存对应的包装类

### 集合类体系结构【理解】

![[01_集合类体系结构图.png]]

### Collection 集合概述和使用【应用】

- Collection集合概述
    
    - 是单例集合的顶层接口,它表示一组对象,这些对象也称为Collection的元素
        
    - JDK 不提供此接口的任何直接实现.它提供更具体的子接口(如Set和List)实现
        
- 创建Collection集合的对象
    
    - 多态的方式
        
    - 具体的实现类ArrayList
        
- Collection集合常用方法
	      
| 方法名                        | 说明                |
| -------------------------- | ----------------- |
| boolean add(E e)           | 添加元素              |
| boolean remove(Object o)   | 从集合中移除指定的元素       |
| boolean removeIf(Object o) | 根据条件进行移除          |
| void clear()               | 清空集合中的元素          |
| boolean contains(Object o) | 判断集合中是否存在指定的元素    |
| boolean isEmpty()          | 判断集合是否为空          |
| int size()                 | 集合的长度，也就是集合中元素的个数 |

# java EE









