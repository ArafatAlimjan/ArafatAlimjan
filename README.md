## Java 学习笔记


### 1. Java中的数据类型

**Java 中的数据类型分为两类：**

- 基本数据类型
- 引用数据类型

#### 1.1 基本数据类型

Java 语言提供了 `8 种基本数据类型`，大致分为 4 类：

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

#### 1.2 引用数据类型

- 类 (class)
- 数组 (array)
- 接口 (interface)
- 枚举 (enum)
- 注解 (annotation)
- 记录 (record)





### 2. 标识符命名规则

- **包名**：多单词组成时，所有字母都小写。例如：`java.lang`，`com.aarafat`

- **类名、接口名**：多单词组成时，每个单词的首字母都大写。例如：`HelloWorld`，`String`，`System`

- **变量名、方法名**：多单词组成时，第一个单词首字母小写，从第二个单词开始首字母大写。例如：`age`，`name`，`bookName`，`main`，`binarySearch`，`getName`

- **常量名**：所有字母都大写，多单词之间使用下划线分隔。例如：`MAX_VALUE`，`PI`，`DEFAULT_CAPACITY`

- **见名知意**：确保命名有意义，易于理解。





### 3. Scanner

**使用Scanner获取不同类型数据的步骤：**

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





### 4. Random

**如何获取一个随机数？**

* 可以使用Java提供的API：Math类的`random()`

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





### 5. Java中的流程控制

Java 程序的结构分为：

- **顺序结构** 
- **分支结构** 
- **循环结构**


#### 5.1 分支结构

#### ① if-else 条件判断结构

**基本格式：**

```java
if(条件表达式) {
    语句块;
}
```

**带 `else` 的格式：**

```java
if(条件表达式) {
    语句块1;
} else {
    语句块2;
}
```

**多条件的格式：**

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

1. **执行过程：**

> 根据表达式中的值，依次匹配case语句，一旦与某个case的`常量`相等，那么就执行这个case中的执行语句。执行完执行语句后 1.`遇到break`会跳出当前switch-case结构 2.`没有遇到break`，则继续执行其后的case中的执行语句，直到遇到break或者完成所有的case以及default中的语句，退出当前switch-case结构(case穿透)

2. **语法格式：**

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

4. case后面必须是`常量`不能是变量，也不能是一个范围

   

#### 5.2 循环结构

凡是循环结构，就一定会有以下`四个要素`：

① 初始化条件
② 循环条件 ---> 一定是boolean类型的变量或表达式
③ 循环体
④ 迭代部分



#### ① for循环

**for循环的格式：**

```java
for(①;②;④) {
    ③
}
```

for循环的执行过程：① - ② - ③ - ④ - ② - ③ - ④ - ..... - ②



#### ② while循环

```java
①;
while(②) {
    ③
    ④
}
```

while循环的执行过程：① - ② - ③ - ④ - ② - ③ - ④ - ..... - ②



#### ③ do-while循环

```java
①;
do{
    ③
	④
} while(②);
```

do-while循环的执行过程：① - ③ - ④ - ② - ③ - ④ - ..... - ②



#### ④ 嵌套循环

内层循环充当了外层循环的`循环体`

```java
/*
打印：
        ******
        ******
        ******
*/
public static void main(String[] args) {
    for (int j = 1; j <= 3; j++) {
        for (int i = 1; i <= 5; i++) {
            System.out.print("*");
        }
        System.out.println();
    }
}
```



#### ④ break和continue

* break：在循环体内结束整个循环过程

* continue ：结束本次的循环，直接进行下一次的循环

``break和continue后面都不能申明语句``





### 7. 工程与模块管理

#### 7.1 IDEA项目结构

**层级关系：**

```
project(工程) - module(模块) - package(包) - class(类) 
```

* 一个project中可以创建多个module
* 一个module中可以创建多个package
* 一个package中可以创建多个class





### 8. 数组(Array)

**概念：**是多个`相同类型`数据按照一定`顺序`排列组合，并使用`一个名字`匿名，并通过`编号`的方式对这些数据进行`统一管理`

**要素：**

* 数组名
* 元素
* 索引
* 长度

**特点：**

* 数组本身是`引用数据类型`，而数组中的元素可以是`任意数据类型`，包括基本数据类型和引用数据类型
* 创建数组对象会在内存中开辟一整块`连续的空间`。占据的空间的大小取决于数组的长度和数组中元素的类型
* 数组中的元素在内存中是依次紧密排列且有序的
* 数组一旦初始化完成，其长度是固定的`不能修改长度`
* 可以使用索引的方式调用指定位置的元素，速度很快
* 数组名中引用的是这块连续空间的首地址

**分类：**

* 按照元素类型：基本数据类型元素的数组、引用数据类型元素的数组
* 按照数组的维数：一维数组、二维数组 ......

**一维数组的使用：**

* 数组的声明和初始化
* 调用数组的指定元素
* 数组的长度属性：length
* 数组的遍历
* 数组元素的默认初始化值
* 一维数组的内存解析



#### 8.1 数组的声明和初始化

数组的声明：

```java
int[] list1;
```

数组的初始化一(定义元素)：

```java
list1 = new int[]{10, 20, 30};
```

数组的初始化二(定义数组的长度)：

数组长度一旦确定`改变不了长度`

```java
list1 = new int[3];
```

类型推断：

```java
//动态
int list1[] = new int[3];
//静态
int list1[] = {1, 2, 3, 4};
```



#### 8.2 数组元素的调用

* 通过索引的方式获取数组元素
* 索引范围从0开始，到数组长度-1结束

```java
int list1[] = {1, 2, 3, 4};
System.out.println(list1[0]);
```



#### 8.4 数组元素的赋值

```java
int list1[] = {1, 2, 3, 4};
list1[0] = 10;
System.out.println(list1[0]);
```



#### 8.5 数组的长度

用来描述数组容器的大小

使用`length`属性表示

```java
System.out.println(list1.length);
```



#### 8.6 数组的遍历

使用for循环遍历，idea中可以输入`fori`快捷输入遍历代码

```java
int list1[] = {1, 2, 3, 4};
for (int i = 0; i < list1.length; i++) {
    System.out.println(list1[i]);
}
```



#### 8.7 数默认初始化值

整型元素的默认初始化值：`0`

浮点型元素的默认初始化值：`0.0`

字符型元素的默认初始化值：`0` or `\u0000` (这两是一回事)

boolean型元素的默认初始化值：`false`

引用数据类型元素的默认初始化值：`null`



#### 8.8 一维数组的内存解析

**Java中的内存结构的划分（主要关心JVM运行时的内存环境）**

为了提高运行效率，JVM虚拟机对内存空间进行了不同区域的划分，每一片区域都有特定的`处理数据方式`和`内存管理方式`

![JVM Memory](https://arafat-1313316262.cos.ap-guangzhou.myqcloud.com/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202023-08-26%20005440.png?q-sign-algorithm=sha1&q-ak=AKIDawZgvz5qGmxIxaWAqzjngo2YLzyzB0rqxhDrQ0tTGP8B5Qeow3mdEbG2wzhf92Ub&q-sign-time=1692982549;1692986149&q-key-time=1692982549;1692986149&q-header-list=host&q-url-param-list=ci-process&q-signature=121e1acb9f95dcf23d7026c861ba5db860264489&x-cos-security-token=i89ju0qaBs6EWwOcD3YU7SOrfXaNRF6a082b6b10ae9b7d64f443bbe160813c03eHU26xPcVfT6ARzpB8VRX1LAxzRo7BAyYq1HCHWpPB8Ftyfv3iLwyQneNWXTRIrOODZuKGZpakjk9ilNCuE3eeaxkD0CqXkZyiRQSVA7vyfj5DBRh4qk_K5tp0r0Vq2qFI2MKWZjZJDnSNtQ3PMM9HWFWv5YT_iNnOet9kDoz1d6JFbUloP4RtsNFRvL2L-p&ci-process=originImage)

举例：具体一维数组代码的内存解析




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

```java
/*
    案例8：随机生成一个1到100之间的数，让用户猜这个随机数是多少。
    从键盘输入数，如果大了，提示"大了"；如果小了，提示"小了"，直到猜到正确的数字。
     */
public static void main(String[] args) {
    // 初始化 Scanner 对象和随机数
    Scanner scanner = new Scanner(System.in);
    int randomNumber = (int) (Math.random() * 100) + 1;

    System.out.println("随机数已生成，范围在1到100之间。请开始猜测：");

    // 循环直到用户猜中为止
    while (true) {
        int inputNumber = scanner.nextInt();

        if (inputNumber == randomNumber) {
            System.out.println("恭喜你猜中了！");
            break;
        } else if (inputNumber < randomNumber) {
            System.out.println("你猜的数小了。");
        } else {
            System.out.println("你猜的数大了。");
        }
    }

    // 关闭 Scanner 对象
    scanner.close();
}
```

