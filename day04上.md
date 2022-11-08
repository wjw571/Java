```java
if(){
	语句块;
}else if(){
	语句块;
}..........
```

代码解释--案例成绩等级

```Java

package day04;
import java.util.Scanner;
//成绩等级排名
/*
A:成绩大于等于90
B:成绩大于等于80小于90
C:成绩大于等于60小于80
D:成绩小于60
*/
public class ScoreLevel {
    public static void main(String[] args) {
        Scanner sacn=new Scanner(System.in);
        System.out.println("请输入成绩");
        double score=sacn.nextDouble();
        System.out.println("成绩是："+score);
        //带数（101，-1，99.999，89.9999，79.9999，59.9999）
        if(score<0||score>100){
            System.out.println("成绩不合法");
        } else if(score>=90){
            System.out.println("成绩等级为A");
        }else if (score>=80&&score<90){
            System.out.println("成绩等级为B");
        }else if(score>=60&&score<80){
            System.out.println("成绩等级为C");
        }else if(score<60){
            System.out.println("成绩等级为D");
        }
    }


}
```

switch .......case

```java
switch（）{
	case 1:
		语句块;
		break;	
	case 2:
		语句块;
		break;
	case 3:
		语句块;
		break;
	..........
	default:
	语句块；

}
```

代码解释--案例指令输入

```java
package day04;
import java.util.Scanner;
public class CommandBySwitch {
    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);
        System.out.println("请选择功能：1.存款 2.取款 3.查询余额 0.退卡");
        int command=scan.nextInt();
        //带数检测（1，2，3，0，55）
        switch(command){
            case 1:
                System.out.println("存款操作...");
                break;
            case 2:
                System.out.println("取款操作...");
                break;
            case 3:
                System.out.println("查询余额操作...");
                break;
            case 0:
                System.out.println("退卡操作...");
                break;
            default:
                System.out.println("输入错误");
        }
    }
}
```

键盘输入：

```java
package day04;
import java.util.Scanner;//1.
//Scanner的演示
public class ScannerDemo {
    public static void main(String[] args) {
        Scanner scan=new Scanner(System.in);//2.
        System.out.println("请输入年龄：");
        int age=scan.nextInt();//3.
        System.out.println("请输入商品的价格：");
        double prices=scan.nextDouble();//3.
        System.out.println("我的年龄是："+age+"，商品的价格是："+prices);
    }
}
```