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
