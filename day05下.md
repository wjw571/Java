```java
package day05;
//for()循环结构演示----与次数相关的
public class ForDemo {
    public static void main(String[] args) {
        int a=1;
        System.out.println("9的乘法表:");
        for(;a<10;a++){
            System.out.println(a+"*9="+a*9);
        }
        int b=1;
        System.out.println("9的乘法表:");
        for(;b<10;){
            b++;
            System.out.println(b+"*9="+b*9);
        }



        for(int times=0;times<5;times++){
            System.out.println("行动是成功的阶梯");
        }
        System.out.println("继续执行......");
        /*
        执行过程：
            times=0   true  输出  times++
            times=1   true  输出  times++
            times=2   true  输出  times++
            times=3   true  输出  times++
            times=4   true  输出  times++
            times=5   false  退出for循环，继续执行
        */

        /*
        执行过程：
            num=1    true   输出    num++
            num=2    true   输出    num++
            num=3    true   输出    num++
            num=4    true   输出    num++
            num=5    true   输出    num++
            num=6    true   输出    num++
            num=7    true   输出    num++
            num=8    true   输出    num++
            num=9    true   输出    num++
            num=10   false   退出循环
        * */
        System.out.println("倒过来的9的乘法表：");
        for(int num=9;num>=1;num--){
            System.out.println(num+"*9="+num*9);
        }
        System.out.println("输出13579的9乘法表：");
        for (int num=1;num<10;num+=2){
            System.out.println(num+"*9="+num*9);
        }

        //break:跳出循环，循环结束，配着if使用，在某种特定条件下结束循环

        System.out.println("倒过来的且只要前六个9的乘法表：");
        for(int num=9;num>=1;num--){
            if(num==3){
                break;
            }
            System.out.println(num+"*9="+num*9);
        }

        //continue:跳过循环体中剩余语句进入下一个循环
        System.out.println("倒过来的且跳过3的9的乘法表：");
        for(int num=9;num>=1;num--){
            if(num%3==0){
                continue;//跳过循环体中剩余语句进入下一个循环
            }
            System.out.println(num+"*9="+num*9);
        }
        /*
        num=1  1*9=9
        num=2  2*9=9
        num=3 if true  使其跳过3的循环，进入下一个
        num=4  4*9=36
        num=5  5*9=45
        num=6 if true  使其跳过3的循环，进入下一个
        num=7  7*9=63
        num=8  8*9=72
        num=9 if true  使其跳过3的循环，进入下一个
        */



    }
        /*

}
```

```java
    变量的重名作用域：作用域重叠时，变量不能同名
    */
//如何选三种循环结构
/*
先看循环是否与次数相关：
    若相关，直接选择for
    若无关，看要素一和要素三是否相同
        若相同则，do while
        若不相同，while

* */
```

```java
//出题算题测试
//随机加法运算器
```

```java
Scanner scan = new Scanner(System.in);
int sum = 0;
for (int i = 1; i <= 10; i++) {
    int num1 = (int) (Math.random() * 100 + 1);
    int num2 = (int) (Math.random() * 100 + 1);
    int add = num1 + num2;
    System.out.println("这里是随机加法运算器");
    System.out.println("欢迎进行测试，题目一共10题");
    System.out.println("(" + i + ")" + num1 + "+" + num2 + "=" + "?");
    System.out.println("开始算吧！");
    int usernum = scan.nextInt();

    if (usernum == -1) {
        System.out.println("提前结束啦！");
        break;
    } else if (usernum != add) {
        System.out.println("算错啦！");
    } else {
        System.out.println("算对啦");
        sum += 10;
    }
}
System.out.println("总分为"+sum);
```

循环嵌套

```java
 System.out.println("九九算术乘法表如下：");
        for (int i=1;i<10;i++){
            for(int j=1;j<=i;j++){
                System.out.print(i+"*"+j+"="+i*j+"\t");
            }
            System.out.println();
        }

      /*  for(int a=1;a<=10;a++){//10
            for(int b=1;b<=20;b++){//200
                for (int c=1;c<=30;c++){//600000
                    System.out.print(a+"*"+b+"*"+c+"="+a*b*c+"\t"+"\t");
                }
                System.out.println();
            }
            System.out.println();
        }
*/        //break跳出一层循环
    }

        /*
         执行过程：
            i=1
            j=1  1*4=1
            j=2
            换行
            i=2
            j=1  1*2=2
            j=2  2*2=4
            j=3
            换行
            i=3
            j=1  3*1=3
            j=2  3*2=6
            j=3  3*3=9
            j=4
            换行
            i=4
            ......
        */
    /*
    外面走一次里面要走完
    时针走一次，里面要走一圈
    */
```

数组：

```java
{

   /*
    数组：
        相同数据类型元素的集合
        是一种数据类型（引用类型）
        定义：
            在一个数据类型后面加个[]则就是数组
                列子：
                数据类型   变量名
                int[]     a;
        int[] a;//声明整型数组变量a
        double[] a;//声明浮点型数组变量a
        boolean[] a;//声明布尔型数组变量a
        int 和int[]是两种完全不同的数据类型
        int[] a=new int[num];//num表示a可以装多少数据
        int[] a=new int[5];//声明整型数组a，包含5个元素，每个元素都是int类型，默认值为0
        double[] b=new double[10];//声明浮点型数组b，包含10个元素，每个元素都是double型，默认值为0.0
        boolean[] d=new boolean[26];//声明布尔型数组d，包含26个元素，每个元素都是boolean型，默认值为false
        书[] 书柜=new 书[20];
        衣服[] 衣柜=new 衣服[30];


       初始化：
        int[] arr=new int[3];//0,0,0
        int[] arr={2,5,8}//2,5,8
        int[] arr=new int[]{2,5,8};//2,5,8

        int[] arr;
        arr={2,5,8}//编译错误

        int[] arr;
        arr=new int[]{2,5,8};//可以


        访问：访问的数组中的元素
            通过数组名.length可以获取数组的长度（元素个数）
            int[] arr=new int[10];
            System.out.println(arr.length)

            通过下表/索引来访问数组中的元素
            下标从0开始，最大到（数组的长度-1）
            int[] arr=new int[3];//0,0,0
            //给第一个元素赋值为100
            //给第二个元素赋值为200
            //给第三个元素赋值为300

            arr[0]=200;//标号
            arr[1]=200;//标号
            arr[2]=200;//标号
            System.out.println(arr[arr.length-1]);//输出最后一个元素

            int a=0;
            int b=0;
            int c=0;
            //给第二个数赋值100
        遍历/迭代：从头到尾挨个走一遍
            for(int i=0;i<arr.length;i++){//遍历所有元素
            //arr[i]------代表每个元素
            arr[i]=100;
                System.out.println(arr[i]);
            }
     */
    int[] arr=new int[3];
    arr[0]=100;//arr的第一个元素为100
    arr[1]=200;//
    arr[2]=300;//
    System.out.println(arr.length);
    System.out.println(arr[arr.length-1]);
    int[] arr1=new int[10];
    for(int i=0;i<arr1.length;i++){
        arr1[i]=(int)(Math.random()*100);//0-99的随机数
        System.out.println(arr1[i]);
    }

}
```