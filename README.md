## Java 学习笔记

##### 2023-08-23 day


### 1. Java中的数据类型：

Java 中的数据类型分为两类：

- 基本数据类型
- 引用数据类型

#### 基本数据类型

Java 语言提供了 8 种基本数据类型，大致分为 4 类：

| 基本数据类型 | 分类   | 比特数 | 默认值     | 取值范围                          |
| ------------ | ------ | ------ | ---------- | --------------------------------- |
| `boolean`    | 布尔型 | 8 位   | `false`    | {false, true}                     |
| `char`       | 字符型 | 16 位  | `'\u0000'` | [0, \(2^{16} - 1\)]               |
| `byte`       | 整数型 | 8 位   | `0`        | [-\(2^7\), \(2^7 - 1\)]           |
| `short`      | 整数型 | 16 位  | `0`        | [-\(2^{15}\), \(2^{15} - 1\)]     |
| `int`        | 整数型 | 32 位  | `0`        | [-\(2^{31}\), \(2^{31} - 1\)]     |
| `long`       | 整数型 | 64 位  | `0L`       | [-\(2^{63}\), \(2^{63} - 1\)]     |
| `float`      | 浮点型 | 32 位  | `0.0F`     | [\(2^{-149}\), \(2^{128} - 1\)]   |
| `double`     | 浮点型 | 64 位  | `0.0D`     | [\(2^{-1074}\), \(2^{1024} - 1\)] |

注意：虽然各种数据类型的默认值看起来不一样，但在内存中都是 0。`boolean` 和 `char` 是唯二的无符号类型。

#### 引用数据类型

- 类 (class)
- 数组 (array)
- 接口 (interface)
- 枚举 (enum)
- 注解 (annotation)
- 记录 (record)





### 2. 标识符命名规则：

- **包名**：多单词组成时，所有字母都小写。例如：`java.lang`，`com.aarafat`

- **类名、接口名**：多单词组成时，每个单词的首字母都大写。例如：`HelloWorld`，`String`，`System`

- **变量名、方法名**：多单词组成时，第一个单词首字母小写，从第二个单词开始首字母大写。例如：`age`，`name`，`bookName`，`main`，`binarySearch`，`getName`

- **常量名**：所有字母都大写，多单词之间使用下划线分隔。例如：`MAX_VALUE`，`PI`，`DEFAULT_CAPACITY`

- **见名知意**：确保命名有意义，易于理解。





### 3. Scanner：

使用Scanner获取不同类型数据的步骤：

1. 导包 import java.util.Scanner
2. 提供(或创建)一个Scanner实例对象
3. 调用Scanner类中的方法，获取指定类型数据
4. 关闭资源，调用scanner类的close()

```java
import java.util.Scanner;

public class Main {
   /*
   小明要注册某交友网站，要求录入以下个人信息
   1.网名 2.年龄 3.体重 4.是否单身 4.性别
   */
   public static void main(String[] args) {
      Scanner scanner = new Scanner(System.in);
      System.out.println("请输入你的网名");
      String name = scanner.next();
      System.out.println("请输入你的年龄");
      int age = scanner.nextInt();
      System.out.println("请输入你的体重");
      double weight = scanner.nextDouble();
      System.out.println("是否单身");
      boolean isSingle = scanner.nextBoolean();
      System.out.println("请输入你的性别(男/女)");
      char gander = scanner.next().charAt(0);
      System.out.println("name = " + name + " age = " + age + " weight = "
      + weight + " isSingle = " + isSingle + " gander = " + gander);
   }
}

```



### 4. Java中的流程控制：

Java 程序的结构分为：

- **顺序结构** 
- **分支结构** 
- **循环结构**

#### if-else 条件判断结构

基本格式：

```java
if(条件表达式) {
    语句块;
}
```

带 `else` 的格式：

```java
if(条件表达式) {
    语句块1;
} else {
    语句块2;
}
```

多条件的格式：

```java
if(条件表达式1) {
    语句块1;
} else if (条件表达式2) {
    语句块2;
} else {
    语句块n;
}
```





## 案例练习：

```java
// 案例1：交换m和n的值
public static void main(String[] args) {
    int m = 10;
    int n = 20;
    int temp = m;
    m = n;
    n = temp;
    System.out.println("m=" + m + ", n=" + n);
}
```

```java
// 案例2：使用三目运算符求两个数的最大值
public static void main(String[] args) {
    int m = 20;
    int n = 20;
    int max = (m > n) ? m : n;
    System.out.println("最大值：" + max);
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

```java
/*
   案例4：
   法特参加Java考试，他和父亲岳不群达成承诺:
   如果:
   成绩为100分时，奖励一辆跑车
   成绩为(80，99]时，奖励一辆山地自行车
   当成绩为[60,80]时，奖励环球影城一日游
   其它时，胖揍一顿
   说明:默认成绩是在[0,100]范围内
*/
public static void main(String[] args) {
    int score = 100;
    if (score == 100) {
        System.out.println("奖励一辆跑车");
    } else if (score > 80 && score <= 99) {
        System.out.println("奖励一辆山地自行车");
    } else if (score >= 60 && score <= 80) {
        System.out.println("环球影城一日游");
    } else {
        System.out.println("胖揍一顿");
    }
}
```

```java
// 案例5：对num1, num2, num3进行排序(使用if-else嵌套)
// damn 怎么会有这么烂的代码
public static void main(String[] args) {
    int num1 = 10;
    int num2 = 20;
    int num3 = 7;
    if (num1 > num2) {
        if (num1 > num3) {
            if (num2 > num3) {
                System.out.println("num1 > num2 > num3");
            } else {
                System.out.println("num1 > num3 > num2");
            }
        } else {
            System.out.println("num3 > num1 > num2");
        }
    } else {
        if (num2 > num3) {
            if (num1 > num3) {
                System.out.println("num2 > num1 > num3");
            } else {
                System.out.println("num2 > num3 > num1");
            }
        } else {
            System.out.println("num3 > num2 > num1");
        }
    }
}
```
