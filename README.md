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
      System.out.println("请输入你的性别(男\\女)");
      char gander = scanner.next().charAt(0);
      System.out.println("name = " + name + " age = " + age + " weight = "
      + weight + " isSingle = " + isSingle + " gander = " + gander);
      scanner.close();
   }
}
```





### 4. Random：

如何获取一个随机数？

* 可以使用Java提供的API：Math类的**random()**

> random() 会返回一个double类型的**0.0~1.0**之间的随机数

```JAVA
// 取一个0.0~1.0之间的随机数
double num1 = Math.random();
System.out.println(d1);
```

```java
// 取一个0~100之间的随机整数
int num2 = (int)(Math.random() * 101);
System.out.println(num2);
```

```java
// 取一个1~100之间的随机整数
int num3 = (int)(Math.random() * 100) + 1;
System.out.println(num3);
```

```java
// 取一个[a,b]之间的随机整数
int num4 = (int)(Math.random() * (b - a + 1)) + a;
System.out.println(num4);
```





### 5. Java中的流程控制：

Java 程序的结构分为：

- **顺序结构** 
- **分支结构** 
- **循环结构**


### 分支结构

#### ① if-else 条件判断结构

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



#### ② switch-case选择结构

1. 执行过程：

> 根据表达式中的值，依次匹配case语句，一旦与某个case的**常量**相等，那么就执行这个case中的执行语句。执行完执行语句后 1.**遇到break**会跳出当前switch-case结构 2.**没有遇到break**，则继续执行其后的case中的执行语句，直到遇到break或者完成所有的case以及default中的语句，退出当前switch-case结构(case穿透)

2. 语法格式：

```java
int num1 = 1;
switch(num1) {
    case 0:
        //执行语句1
        System.out.println(0);
        break;
    case 1:
        //执行语句2
        System.out.println(1);
        break;
    case 2:
        System.out.println(2);
        //执行语句n
        break;
    default:
        //执行语句n+1
        break;
}
```

3. switch中的表达式只能是特定的数据类型，如下：

   * byte
   * short
   * int
   * char
   * 枚举(JDK5.0新增)
   * String(JDK7.0新增)

4. case后面必须是**常量**不能是变量，也不能是一个范围

   

### 循环结构

凡是循环结构，就一定会有以下四个要素：

① 初始化条件
② 循环条件
③ 循环体
④ 迭代部分



#### ① for循环

for循环的格式：

```java
for(①;②;④) {
    ③
}
```

for循环的执行过程：① - ② - ③ - ④ - ② - ③ - ④ - ..... - 



#### ② while循环





#### ③ do-while循环






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

```java
// 案例6：遍历1-100以内的偶数，获取偶数的个数以及所有的偶数和
public static void main(String[] args) {
    int count = 0; //记录偶数的个数
    int sum = 0; //记录偶数的合

    for(int i = 1; i <= 100; i++) {
        if (i % 2 == 0) {
            count++;
            sum = sum + i;
            System.out.println(i);
        }
    }
    System.out.println("偶数的个数为：" + count);
    System.out.println("偶数合为：" + sum);
}
```

```java
/*
    案例7：输出所有的水仙花数，水仙花数是指一个3位数其各个位上的数字的立方和等于本身
    例如：153 = 1*1*1 + 3*3*3 + 5*5*5
     */
public static void main(String[] args) {
    int unitDigit; //个位
    int tensDigit; //十位
    int hundredsDigit; //百位
    int sum;
    for (int i = 100; i <= 999; i++) {
        unitDigit = i % 10;
        tensDigit = i / 10 % 10;
        hundredsDigit = i / 100;
        sum = unitDigit * unitDigit * unitDigit + tensDigit * tensDigit * tensDigit + hundredsDigit * hundredsDigit * hundredsDigit;
        if (sum == i) {
            System.out.println(i);
        }
    }
}
```

