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
### Collection集合的遍历

#### 迭代器遍历

- 迭代器介绍
    
    - 迭代器,集合的专用遍历方式
        
    - Iterator< E > iterator(): 返回此集合中元素的迭代器,通过集合对象的iterator()方法得到
        
- Iterator中的常用方法
    
    boolean hasNext(): 判断当前位置是否有元素可以被取出 E next(): 获取当前位置的元素,将迭代器对象移向下一个索引位置
    
- Collection集合的遍历
	``` java
	//创建集合对象
	 Collection<String> c = new ArrayList<>();
	 //添加元素
	 c.add("hello");
	 c.add("world");
	 c.add("java");
	 c.add("javaee");
	 //Iterator<E> iterator()：返回此集合中元素的迭代器，通过集合的iterator()方法得到
	 Iterator<String> it = c.iterator();
	 //用while循环改进元素的判断和获取
	 while (it.hasNext()) {
	     String s = it.next();
	     System.out.println(s);
	 }
	```

迭代器中删除的方法

void remove(): 删除迭代器对象当前指向的元素

```java
public class IteratorDemo2 {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("a");
        list.add("b");
        list.add("b");
        list.add("c");
        list.add("d");

        Iterator<String> it = list.iterator();
        while(it.hasNext()){
            String s = it.next();
            if("b".equals(s)){
                //指向谁,那么此时就删除谁.
                it.remove();
            }
        }
        System.out.println(list);
    }
}
```

注意：迭代器遍历完毕，指针不会复位，我们再次遍历的时候，要重新创建一个迭代器。迭代器遍历时，不能用集合的方法进行增加或者删除

#### lambda表达式遍历

利用forEach方法，再结合lambda表达式的方式进行遍历

```java
public static void main(String[] args) {
//1.创建集合并添加元素
    Collection<String> coll = new ArrayList<>();
    coll.add("zhangsan");
    coll.add("lisi");
    coll.add("wangwu");
    //2.利用匿名内部类的形式
    //底层原理：
    //其实也会自己遍历集合，依次得到每一个元素
    //把得到的每一个元素，传递给下面的accept方法
    //s依次表示集合中的每一个数据
    /* coll.forEach(new Consumer<String>() {
        @Override
        public void accept(String s) {
            System.out.println(s);
        }
        });*/

        //lambda表达式
        coll.forEach(s -> System.out.println(s));
}
```

#### 增强for循环

介绍

- 它是JDK5之后出现的,其内部原理是一个Iterator迭代器
    
- 实现Iterable接口的类才可以使用迭代器和增强for
    
- 简化数组和Collection集合的遍历

```java
public class MyCollectonDemo1 {
    public static void main(String[] args) {
        ArrayList<String> list =  new ArrayList<>();
        list.add("a");
        list.add("b");
        list.add("c");
        list.add("d");
        list.add("e");
        list.add("f");

        //1,数据类型一定是集合或者数组中元素的类型
        //2,str仅仅是一个变量名而已,在循环的过程中,依次表示集合或者数组中的每一个元素
        //3,list就是要遍历的集合或者数组
        for(String str : list){
            System.out.println(str);
        }
    }
}
```

## List集合

List集合的概述

- 有序集合,这里的有序指的是存取顺序
    
- 用户可以精确控制列表中每个元素的插入位置,用户可以通过整数索引访问元素,并搜索列表中的元素
    
- 与Set集合不同,列表通常允许重复的元素

### List集合的特有方法【应用】

- 方法介绍

|方法名|描述|
|---|---|
|void add(int index,E element)|在此集合中的指定位置插入指定的元素|
|E remove(int index)|删除指定索引处的元素，返回被删除的元素|
|E set(int index,E element)|修改指定索引处的元素，返回被修改的元素|
|E get(int index)|返回指定索引处的元素|

```java
public class MyListDemo {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("aaa");
        list.add("bbb");
        list.add("ccc");
        //method1(list);
        //method2(list);
        //method3(list);
        //method4(list);
    }

    private static void method4(List<String> list) {
        //返回指定索引处的元素
        String s = list.get(0);
        System.out.println(s);
    }

    private static void method3(List<String> list) {
        // 修改指定索引处的元素，返回被修改的元素
        //被替换的那个元素,在集合中就不存在了.
        String result = list.set(0, "qqq");
        System.out.println(result);
        System.out.println(list);
    }

    private static void method2(List<String> list) {
        // 删除指定索引处的元素，返回被删除的元素
        //在List集合中有两个删除的方法
        //第一个 删除指定的元素,返回值表示当前元素是否删除成功
        //第二个 删除指定索引的元素,返回值表示实际删除的元素
        String s = list.remove(0);
        System.out.println(s);
        System.out.println(list);
    }

    private static void method1(List<String> list) {
        //        void add(int index,E element)	在此集合中的指定位置插入指定的元素
        //原来位置上的元素往后挪一个索引.
        list.add(0,"qqq");
        System.out.println(list);
    }
}
```

### List的遍历

除了上面cllection的遍历方式，还添加了一种遍历方法

```java
//获取一个列表迭代器的对象，里面的指针默认也是指向0索引的

//额外添加了一个方法：在遍历的过程中，可以添加元素
ListIterator<String> it = list.listIterator();
while(it.hasNext()){
    String str = it.next();
    if("bbb".equals(str)){
        //qqq
        it.add("qqq");
    }
}
System.out.println(list);
```

### List的实现方式

- ArrayList集合
    
    底层是数组结构实现，查询快、增删慢
    
- LinkedList集合
    
    底层是链表结构实现，查询慢、增删快

#### LinkedList集合的特有功能

|方法名|说明|
|---|---|
|public void addFirst(E e)|在该列表开头插入指定的元素|
|public void addLast(E e)|将指定的元素追加到此列表的末尾|
|public E getFirst()|返回此列表中的第一个元素|
|public E getLast()|返回此列表中的最后一个元素|
|public E removeFirst()|从此列表中删除并返回第一个元素|
|public E removeLast()|从此列表中删除并返回最后一个元素|
```java
public class MyLinkedListDemo4 {
    public static void main(String[] args) {
        LinkedList<String> list = new LinkedList<>();
        list.add("aaa");
        list.add("bbb");
        list.add("ccc");
//        public void addFirst(E e)	在该列表开头插入指定的元素
        //method1(list);

//        public void addLast(E e)	将指定的元素追加到此列表的末尾
        //method2(list);

//        public E getFirst()		返回此列表中的第一个元素
//        public E getLast()		返回此列表中的最后一个元素
        //method3(list);

//        public E removeFirst()		从此列表中删除并返回第一个元素
//        public E removeLast()		从此列表中删除并返回最后一个元素
        //method4(list);
      
    }

    private static void method4(LinkedList<String> list) {
        String first = list.removeFirst();
        System.out.println(first);

        String last = list.removeLast();
        System.out.println(last);

        System.out.println(list);
    }

    private static void method3(LinkedList<String> list) {
        String first = list.getFirst();
        String last = list.getLast();
        System.out.println(first);
        System.out.println(last);
    }

    private static void method2(LinkedList<String> list) {
        list.addLast("www");
        System.out.println(list);
    }

    private static void method1(LinkedList<String> list) {
        list.addFirst("qqq");
        System.out.println(list);
    }
}
```


## Set集合

### Set集合概述和特点【应用】

- 不可以存储重复元素
    
- 没有索引,不能使用普通for循环遍历

### Set集合的遍历

```java
public class MySet1 {
    public static void main(String[] args) {
      	//创建集合对象
        Set<String> set = new TreeSet<>();
      	//添加元素
        set.add("ccc");
        set.add("aaa");
        set.add("aaa");
        set.add("bbb");      
      	//遍历集合
        Iterator<String> it = set.iterator();
        while (it.hasNext()){
            String s = it.next();
            System.out.println(s);
        }
        System.out.println("-----------------------------------");
        for (String s : set) {
            System.out.println(s);
        }
    }
}
```

## TreeSet集合

### TreeSet集合概述和特点【应用】

- 不可以存储重复元素
    
- 没有索引
    
- 可以将元素按照规则进行排序
    
    - TreeSet()：根据其元素的自然排序进行排序
        
    - TreeSet(Comparator comparator) ：根据指定的比较器进行排序


### TreeSet集合基本使用

```java
public class TreeSetDemo01 {
    public static void main(String[] args) {
        //创建集合对象
        TreeSet<Integer> ts = new TreeSet<Integer>();

        //添加元素
        ts.add(10);
        ts.add(40);
        ts.add(30);
        ts.add(50);
        ts.add(20);

        ts.add(30);

        //遍历集合
        for(Integer i : ts) {
            System.out.println(i);
        }
    }
}
```

### 自然排序Comparable的使用【应用】

- 案例需求
    
    - 存储学生对象并遍历，创建TreeSet集合使用无参构造方法
        
    - 要求：按照年龄从小到大排序，年龄相同时，按照姓名的字母顺序排序
        
- 实现步骤
    
    1. 使用空参构造创建TreeSet集合
        
        - 用TreeSet集合存储自定义对象，无参构造方法使用的是自然排序对元素进行排序的
            
    2. 自定义的Student类实现Comparable接口
        
        - 自然排序，就是让元素所属的类实现Comparable接口，重写compareTo(T o)方法
            
    3. 重写接口中的compareTo方法
        
        - 重写方法时，一定要注意排序规则必须按照要求的主要条件和次要条件来写

```java
public class Student implements Comparable<Student>{
    private String name;
    private int age;
    public Student() { }
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() { return name; }
    public void setName(String name) { this.name = name; }
    public int getAge() { return age;  }
    public void setAge(int age) { this.age = age;  }
    @Override
    public String toString() {
        return "Student{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
    @Override
    public int compareTo(Student o) {
        //按照对象的年龄进行排序
        //主要判断条件: 按照年龄从小到大排序
        int result = this.age - o.age;
        //次要判断条件: 年龄相同时，按照姓名的字母顺序排序
        result = result == 0 ? this.name.compareTo(o.getName()) : result;
        return result;
    }
}
 public static void main(String[] args) {
        //创建集合对象
        TreeSet<Student> ts = new TreeSet<>();
	    //创建学生对象
        Student s1 = new Student("zhangsan",28);
        Student s2 = new Student("lisi",27);
        Student s3 = new Student("wangwu",29);
        Student s4 = new Student("zhaoliu",28);
        Student s5 = new Student("qianqi",30);
		//把学生添加到集合
        ts.add(s1);
        ts.add(s2);
        ts.add(s3);
        ts.add(s4);
        ts.add(s5);
		//遍历集合
        for (Student student : ts) {
            System.out.println(student);
        }
    }
```

### 比较器排序Comparator的使用【应用】

- 案例需求
    
    - 存储老师对象并遍历，创建TreeSet集合使用带参构造方法
        
    - 要求：按照年龄从小到大排序，年龄相同时，按照姓名的字母顺序排序
        
- 实现步骤
    
    - 用TreeSet集合存储自定义对象，带参构造方法使用的是比较器排序对元素进行排序的
        
    - 比较器排序，就是让集合构造方法接收Comparator的实现类对象，重写compare(T o1,T o2)方法
        
    - 重写方法时，一定要注意排序规则必须按照要求的主要条件和次要条件来写

```java
public class Teacher {
    private String name;
    private int age;
    public Teacher() {  }
    public Teacher(String name, int age) {
        this.name = name;
        this.age = age;
    }
    public String getName() { return name;  }
    public void setName(String name) { this.name = name;}
    public int getAge() { return age; }
    public void setAge(int age) {  this.age = age;  }
    @Override
    public String toString() {
        return "Teacher{" +
                "name='" + name + '\'' +
                ", age=" + age +
                '}';
    }
}
public static void main(String[] args) {
      //创建集合对象
    TreeSet<Teacher> ts = new TreeSet<>(new Comparator<Teacher>() {
        @Override
        public int compare(Teacher o1, Teacher o2) {
            //o1表示现在要存入的那个元素
            //o2表示已经存入到集合中的元素
            //主要条件
            int result = o1.getAge() - o2.getAge();
            //次要条件
            result = result == 0 ? o1.getName().compareTo(o2.getName()) : result;
            return result;
        }
    });
	//创建老师对象
    Teacher t1 = new Teacher("zhangsan",23);
    Teacher t2 = new Teacher("lisi",22);
    Teacher t3 = new Teacher("wangwu",24);
    Teacher t4 = new Teacher("zhaoliu",24);
	//把老师添加到集合
    ts.add(t1);
    ts.add(t2);
    ts.add(t3);
    ts.add(t4);
	//遍历集合
    for (Teacher teacher : ts) {
        System.out.println(teacher);
    }
}
```

## HashSet集合
### HashSet集合概述和特点【应用】

- 底层数据结构是哈希表
    
- 存取无序
    
- 不可以存储重复元素
    
- 没有索引,不能使用普通for循环遍历

```java
public class HashSetDemo {
    public static void main(String[] args) {
        //创建集合对象
        HashSet<String> set = new HashSet<String>();

        //添加元素
        set.add("hello");
        set.add("world");
        set.add("java");
        //不包含重复元素的集合
        set.add("world");

        //遍历
        for(String s : set) {
            System.out.println(s);
        }
    }
}
```

### 哈希值【理解】

- 哈希值简介
    
    是JDK根据对象的地址或者字符串或者数字算出来的int类型的数值
    
- 如何获取哈希值
    
    Object类中的public int hashCode()：返回对象的哈希码值
    
- 哈希值的特点
    
    - 同一个对象多次调用hashCode()方法返回的哈希值是相同的
        
    - 默认情况下，不同对象的哈希值是不同的。而重写hashCode()方法，可以实现让不同对象的哈希值相同

- HashSet集合存储自定义类型元素,要想实现元素的唯一,要求必须重写hashCode方法和equals方法