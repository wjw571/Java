

```Java
if(boolean){//只判断一次
    
	语句块;//只执行一次

}
while(boolean){//判断多次
    
	语句块；//判断几次，执行几次

}
```

```java
案例一：
输出五次“行动是成功的阶梯”
		行动是成功的阶梯
		行动是成功的阶梯
		行动是成功的阶梯
		行动是成功的阶梯
    循环变量：输出几次
    1）int times=0;
    2）当times<5;
	3)times++;
	  times=1/2/3/4/5
      当times=5时候结束
案例二：
输出9的乘法表：
	1*9=
	2*9=
	3*9=
	....
  循环变量：乘数的变化
          1）int num=1;
		  2) 当num<=9;
          3）num++;
             num=1/2/3/4/5/6/7/8/9/10
             当num为10的时候结束
			 
    
```

案例一的代码

```Java
int times=0;//1）循环变量的初始化
while(times<5){//2)循环的条件
    System.out.println("行动是成功的阶梯");//----语句块得看情况放在  3）的之前还是之后
    //放在3）之前绝对没错
    times++;//3）循环变量的改变
}
System.out.println("继续执行.....");//while结束还是会执行之后语句
/*
            执行过程（带数）：
                            times=0
                true    输出 times=1
                true    输出 times=2
                true    输出 times=3
                true    输出 times=4
                true    输出 times=5
                false while循环结束
                输出继续执行.....
        */
```

案例二的代码



```Java
  int num=1;
        System.out.println("9的乘法表:");
        while(num<=9){
            System.out.println(num+"*9="+num*9);
            num++;
        }
        System.out.println("结束");
        /*
            执行过程：
                1）int num=1  循环变量初始化
                2）num<=9     循环变量的判断条件
                3）                 num=1
                    true   1*9=9    num=2
                    ture   2*9=18   num=3
                    ture   3*9=27   num=4
                    ture   4*9=36   num=5
                    ture   5*9=45   num=6
                    ture   6*9=54   num=7
                    ture   7*9=63   num=8
                    ture   8*9=72   num=9
                    ture   9*9=81   num=10
                    false  while循环结束
、
        */
```







- **变量的作用域/范围：从变量的声明开始，到包含它最近的大括号结束**





1. 循环结构：

   - while结构

     > 先判断后执行，有可能一次都不执行

   - do while结构

     > 先执行后判断，最少执行一次

   当要素1和要素3相同的时候，首选do .....while

   > 例如Guessing中，初始化是键盘输入，最后改变变量还是从键盘输入

2. 循环的三要素：

   - 循环变量的初始化

   - 循环的条件（以循环变量为基础）

   - 循环变量的改变（向着循环的结束变量）

     >循环变量：在整个循环过程中所反复改变的那个数

```Java
循环变量：所跑的圈数count
    1）int count=0;
    2）不够三才需要跑  count<3;
	3）够三圈了就不用跑了 
        count++;
		count=0/1/2/3 
        当：count=3;结束



跑三圈：
                         圈数为0
够三圈吗？   不够  跑一圈   圈数为1
够三圈吗？   不够  跑一圈   圈数为2
够三圈吗？   不够  跑一圈   圈数为3
够三圈吗？   够了
```



```Java
随机数：
/*
        随机数
        Math.random()------0.0到0.9999999999999.....不包括1
        *1000--------------0.0到999.99999999999.....
        +1-----------------1.0到1000.9999999999......
        (int)强转-----------1到1000

         Math.random()------0.0到0.9999999999999.....不包括1
        *1000--------------0.0到999.99999999999.....
        (int)强转-----------1到1000
        +1-----------------1.0到1000.9999999999......

        */

```





```Java
猜数字游戏 需求：
    循环三要素
    	循环变量：用户猜的数guess
    	1）guess =scan。nextInt();
		2）guess！=num;
		3)重新赋值（循环变量的改变）
            直到guess==num才会退出while
    
	int num=250//手里藏得数
	猜吧！
	1）300
	  太大了
	  猜吧！
	2）200
	  太小了
	  猜吧！
	3）251
	  太大了
	  猜吧
	4）250
	  恭喜你猜对了
	
```

代码解释---while版

```Java
package day04;
//猜数字小游戏
//循环三要素1.2.3.
import java.util.Scanner;
public class Guessing {
    public static void main(String[] args) {
        int num =(int)(Math.random()*1000+1);//系统随机生成
        System.out.println("作弊数字为："+num);
        //int num=250;
        /*
        随机数
        Math.random()------0.0到0.9999999999999.....不包括1
        *1000--------------0.0到999.99999999999.....
        +1-----------------1.0到1000.9999999999......
        (int)强转-----------1到1000

         Math.random()------0.0到0.9999999999999.....不包括1
        *1000--------------0.0到999.99999999999.....
        (int)强转-----------1到1000
        +1-----------------1.0到1000.9999999999......

        */


        System.out.println("开始猜数字吧！");
        Scanner scan=new Scanner(System.in);
        //在外面是三路，几路情况看有几种可能，外面是等于小于大于
        int guess=scan.nextInt();//1.
        while(guess!=num){//2.
        //在里面是两路，因为他在进入while的时候已经判断一次是否等于，所以只剩下两种：小于、大于
            if (guess>num) {
                System.out.println("太大了！");//300太大了
            }else{
                System.out.println("太小了！");//200太小了
            }
            System.out.println("重新猜吧！");
            guess=scan.nextInt();//3.
        }
        System.out.println("恭喜你猜对了");
    }
}
            /*
            执行过程:
                先初始化藏起来的数
                初始化循环变量guess
                进行判断guess和num
                    （带数）
                        1)300！=250   true
                          300>250太大了
                          重新猜吧！
                          guess重新从键盘输入200
                        2)200！=250   true
                          200<250太小了
                          重新猜吧！
                            guess重新从键盘输入250
                        3)250=250 false
                          恭喜你猜对了！

            */
```

do.....while版本

```Java
package day04;
//do..while结构的演示
//Guessing游戏的改造
import java.util.Scanner;
public class DoWhileDemo {
    public static void main(String[] args) {
        /*
        2.do...while结构：
            1）语法:
                do{
                    语法快;
                }while(boolean);
            2）执行过程：
                先执行语句块，再去判断Boolean的值，若为true则
                再执行语句块，再判断Boolean的值，若为true则
                再执行语句块，再判断Boolean的值，直到false则，while循环结构结束
        */
        Scanner scan=new Scanner(System.in);
        int num =(int)(Math.random()*1000+1);//系统随机生成
        System.out.println("作弊数字为："+num);
        int guess;
        System.out.println("开始猜吧！");
        do{
            guess=scan.nextInt();//1+3
            if(guess>num){
                System.out.println("猜大了，重新猜吧！");
            }else if(guess<num){
                System.out.println("猜小了，重新猜吧！");
            }else{
                System.out.println("恭喜你猜对了！");
            }
        }while(guess!=num);//2
            /*
            执行过程：
                定义一个num随机数进行猜测
                进行输出随机数进行作弊
                定义一个guess变量先不做初始化
                输出开头提示开始猜吧
                进入do先执行guess赋值
                然后进行比对大小---带数（1000，900，925）
                1000>925猜大来，重新猜    1000！=925 true
                继续执行，重新从键盘输入一个数字900
                900<925猜小了，重新猜     900！=925  true
                继续执行，重新从键盘输入一个数字925
                925==925，恭喜你猜对了     925==925  false
                退出do....whlie循环  结束



            */
    }
}
```