#### Java运算符表达式

##### 赋值运算符

```Java
4.赋值运算符：
1）简单赋值运算符
2）扩展赋值运算符：+=、-=、*=、/=、%=
```

> 代码解释

```Java
 int d1=5;
    d1+=5;//相当于d1=d1+5
    System.out.println(d1);//10
    d1*=2;//相当于d1=d1*2
    System.out.println(d1);//20
    d1/=5;//相当于d1=d1/5
    System.out.println(d1);//4
    d1%=3;//相当于d1=d1%3
    System.out.println(d1);//1
    //面试题：哪一句错了
      /*      short s=5;
            s+=10;//这个没错是因为，扩展运算自带强转 s=（short）（s+10）
            s=s+10;//short在运算时自动变成int，int再给short，则要强制
*/
```

##### 字符串连接运算符

```Java
 5.字符串连接运算符：
 1）+：
    1.1）若两边是数字，则是相加
    1.2）若两边要是字符串，则作为字符串连接
        char：字符型，必须放在''，1个
        string:字符串型，必须放在”“中，0个到多个
同化：只要跟字符串连在一起，都会变成字符串，后续在跟什么连接，把他当作字符串看带
```

> 代码解释

```Java
int age=22;
System.out.println("age=");//age=
System.out.println(age);//22
System.out.println("age="+age);//不同类型的，要用加号连接---age=22
System.out.println("我的年龄是"+age);
System.out.println("我的年龄是"+age+"了");
String name="WJW";
System.out.println("name:"+name);//name:WJW
System.out.println("大家好，我叫"+name);//大家好，我叫WJW
System.out.println("大家好，我叫"+name+"，今年我"+age+"岁了");//大家好，我叫WJW，今年我22岁了

System.out.println(10+20+""+30);//30---字符串+30，最后变成3030
System.out.println(""+10+20+30);//10---字符串+20+30，最后变成102030字符串
System.out.println(10+20+30+"");//60---字符串，最后是变成了60这个字符串
```

##### 条件（三目）运算符

```Java
6.条件（三目）运算符：
1）语法：
   Boolean？数1：数2
2）执行过程：
条件运算是有结果的，结果要么是？号后的数1，要么是：号后的数2
   若为true ，则是整个表达式的结果是？号后的数1
   若是false,则是整个表达式的结果是：号后的数2
```

> 代码解释

```Java
int num=5;
int flag=num>0?1:-1;//true---?号后的数1
System.out.println(flag);//1
int num1=-2;
int flag1=num1>0?1:-1;//false---:号后的数2
System.out.println(flag1);//-1

//小案例，比大小
int num2=8,num3=5;
int max=num2>num3?num2:num3;//不考虑相等，是因为如果相等，谁给赋值都可以
System.out.println("最大值为"+max);
```