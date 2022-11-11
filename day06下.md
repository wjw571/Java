方法的定义：五要素

> 修饰词：public static
>
> 返回值：

```java
方法可以有返回值，也可以没有返回值：
1）无返回值----返回值类型统一写成void
public static void say()
2）有返回值----返回值类型设计成特定的数据类型即可
pubic static int plus(int num1,int num2)

何时有返回值？何时无返回值？
---方法操作后：
1）若还需要用到方法中的某个数据-------有返回值
System.out.println("hello")走完以后，就不要使用什么数据
2）若不再需要用到方法中的某个数据------无返回值
int a=scan.nextInt();--还需要用到扫描到的数据
```

>方法名（小驼峰）say，plus
>
>参数列表（有参数更灵活）

```Java
System.out.println("hello")---有参数
int a=scan。nextInt();--------无参数

double c=Math.random();---无参数数据写死了（0-0.9..）
假设有参
double c=Math.random(0,99);---可自己设置数值
double d=Math.random(0,100);---可自己设置数值
double e=Math.random(0,1000);---可自己设置数值



public static void say()---无参

pubic static int plus(int num1,int num2)--有参
```

> 方法体

```java
public static void say(){

}
pubic static int plus(int num1,int num2){

}
```

方法的调用：

- 无返回值：方法名（有参数传参数）；
- 有返回值：数据类型 变量=方法名（有参数传参数）；

 return的作用：

- return 值；  1）结束方法的执行   2）返回结果给调用方

  -----用在有返回值的时候

- return;          1)结束方法的执行

  -----用在无返回值的时候

方法的嵌套：

```java
main(){

}
void 取款(){
	验证密码();//嵌套
}
void 存款(){

}
void 查询余额(){

}
void 验证密码(){

}



```

代码解释：

```java
 System.out.println("第一种复制方法：");
    int[] arr=new int[]{25,645,78,95,45};
    int[] brr=new int[10];
    System.arraycopy(arr,0,brr,0,1);
    for (int i=0;i<brr.length;i++){
        System.out.print(brr[i]+"\t");
    }
    System.out.println();
    System.out.println("第一种使用System.arraycopy,不需要import");
    System.out.println();
    System.out.println("第二种复制方法：");
    int[] a=new int[]{1,2,3,4,5,6,7};
    int[] b= Arrays.copyOf(a,5);
    for (int i=0;i<b.length;i++){
        System.out.print(b[i]+"\t");
    }
    System.out.println();
    System.out.println("第二种使用Array.copyOf,需要import");


    System.out.println("使用Arrays.copyOf可以扩容");
    int[] c=new int[]{1,2,3,4,5,6,7};
    c= Arrays.copyOf(c,10);
    for (int i=0;i<c.length;i++){
        System.out.print(c[i]+"\t");
    }
    System.out.println();
    System.out.println("扩容三位，自动补全");
    System.out.println();
    System.out.println("数组的排序");
    int[] d=new int[10];
    System.out.println("排序前");
    for(int i=0;i<d.length;i++){
        d [i]=(int)(Math.random()*100+1);
        System.out.print(d[i]+"  ");
    }
    System.out.println();
    Arrays.sort(d);
    System.out.println("排序后(升序)");
    for (int i=0;i<d.length;i++){
        System.out.print(d[i]+"  ");
    }
    System.out.println();
    System.out.println("降序（倒着输出）");
    for(int i=d.length-1;i>=0;i--){
        System.out.print(d[i]+"  ");
    }
    System.out.println();



    System.out.println("数组元素的最大值,并且放在末尾的下一个位置");
    int[] e=new int[10];
    for(int i=0;i<e.length;i++){
        e [i]=(int)(Math.random()*100+1);
        System.out.print(e[i]+"  ");
    }
    int max = e[0];
    for (int i=1;i< e.length;i++){
        if(e[i]>max){
            max=e[i];
        }
    }
    System.out.println();
    System.out.println("最大值为："+max);
    e= Arrays.copyOf(e,11);
    e[e.length-1]=max;
    for (int i=0;i<e.length;i++){
        System.out.print(e[i]+"  ");
    }
    System.out.println();
    System.out.println();


    System.out.println("无参无返回值的调用：");
    say();
    System.out.println("有参无返回值调用：");
    sayHi("zhangsan");
    System.out.println("有多个参无返回值调用：");
    sayHello("lisi",30);
    System.out.println("无参有返回值调用：");
    double a1=a();
    System.out.println("a1="+a1);
    System.out.println("有参多个有返回值调用：");
    int m=10,n=20;
    int sum=b(m,n);
    System.out.println("sum="+sum);
    System.out.println("数组无参有返回值调用：");
    int[] c1=c();
    System.out.println("数组的长度c1:"+c1.length);
    System.out.println("数组元素c1：");
    for (int i=0;i<c1.length;i++){
        System.out.print(c1[i]+"  ");
    }
    System.out.println();
    System.out.println("有参有返回值调用：");
    int f=max(100);
    System.out.println("max="+f);
    System.out.println("方法的嵌套：");
    System.out.println("我的饮食习惯：");
    like();
}
public static void say(){
    System.out.println("大家好，我叫wjw，今年我22岁了");
}
public static void sayHi(String name){
    System.out.println("大家好，我叫"+name+"，今年我22岁了");
}
public static void sayHello(String name,int age){
    System.out.println("大家好，我叫"+name+"，今年我"+age+"岁了");
}
public static double a(){
    return 6.66;
}
public static int b(int num1,int num2){
    int num=num1+num2;
    return num;
}
public static int[] c(){
    int[] arr=new int[]{20,60,50};
    return arr;
}
public static int max(int max){
    return max;
}
public static void like(){
    System.out.print("我喜欢：");
    food();
    System.out.println();
    System.out.print("我不喜欢:猪肉");
}
public static void food(){
    System.out.print("牛肉");
```