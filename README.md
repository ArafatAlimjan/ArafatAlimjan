## 学习笔记区：

#### 2023-08-23 Java Stady

##### 1. 标识符匿名规则：

1. **包名**：多单词组成时所有字母都小写：xxxyyyzzz
   例如：java.lang，com.aarafat

2. **类名、接口名**：多单词组成时，所有单词的首字母大写：XxxYyyZzz
   例如：HelloWorld，String，System

3. **变量名、方法名**：多单词组成时，第一个单词首字母小写，第二个单词开始每个单词首字母大写:xxxYyyZzz
   例如：age，name，bookName，main，binarySearch，getName

4. **常量名**：所有字母都大写，多单词时每个单词用下划线连接：XXX_YYY_ZZZ
   例如：MAX_VALUE，PI，DEFAULT_CAPACITY

5. **见名知意**

   


##### 2. Java中的数据类型：

Java 中的数据类型有两类：

* 基本数据类型

* 引用数据类型

  

###### 基本数据类型

Java 语言提供了 **8** 种基本类型，大致分为 **4** 类

| 基本数据类型 | 分类       | 比特数 | 默认值     | 取值范围                      | 说明                              |
| ------------ | ---------- | ------ | ---------- | ----------------------------- | --------------------------------- |
| `boolean`    | **布尔型** | 8 位   | `false`    | {false, true}                 |                                   |
| `char`       | **字符型** | 16 位  | `'\u0000'` | [0, $2^{16} - 1$]             | 存储 Unicode 码，用单引号赋值     |
| `byte`       | **整数型** | 8 位   | `0`        | [-$2^7$, $2^7 - 1$]           |                                   |
| `short`      | **整数型** | 16 位  | `0`        | [-$2^{15}$, $2^{15} - 1$]     |                                   |
| `int`        | **整数型** | 32 位  | `0`        | [-$2^{31}$, $2^{31} - 1$]     |                                   |
| `long`       | **整数型** | 64 位  | `0L`       | [-$2^{63}$, $2^{63} - 1$]     | 赋值时一般在数字后加上 `l` 或 `L` |
| `float`      | **浮点型** | 32 位  | `+0.0F`    | [$2^{-149}$, $2^{128} - 1$]   | 赋值时必须在数字后加上 `f` 或 `F` |
| `double`     | **浮点型** | 64 位  | `+0.0D`    | [$2^{-1074}$, $2^{1024} - 1$] | 赋值时一般在数字后加 `d` 或 `D`   |

尽管各种数据类型的默认值看起来不一样，但在内存中都是 0。

在这些基本类型中，`boolean` 和 `char` 是唯二的无符号类型。



###### 引用数据类型

* 类(class)

* 数组(array)

* 接口(interface)

* 枚举(enum)

* 注解(annotation)

* 记录(record)

  

##### 3. Java中的流程控制：

java程序设计中的结构有：

1. **顺序结构** 

2. **分支结构** 

3. **循环结构**

   

###### if-else条件判断结构

格式：

```java
if(条件表达式) {
    语句块;
}
```



## 案例练习区：

```java
// 案例1：交换m和n的值
   public static void main(String[] args) {
      int m = 10;
      int n = 20;
      int temp = m;
      m = n;
      n = temp;
      System.out.println("m=" + m + " n=" + n);
   }
```

```java
// 案例2：三目运算符求两个数的最大值
   public static void main(String[] args) {
      int m = 20;
      int n = 20;
      int max = (m > n) ? m : n;
      System.out.println(max);
   }
```

```java
// 案例3：今天是周2，10天以后是周几？
   public static void main(String[] args) {
      int week = 2;
      week += 10;
      week %= 7;
      System.out.println("今天是周2，10天以后是周" + ((week == 0) ? "日" : week));
   }
```
