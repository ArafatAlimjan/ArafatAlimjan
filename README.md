// 对num1, num2, num3进行排序(使用if-else嵌套)
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
