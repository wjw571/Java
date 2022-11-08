#### Java的运算符表达式

##### **算术运算符**

```Java
1.算术运算符：+，-，*，/，%，++，--；
    1）：*注意溢出
    2）：/去除余数
    3）；++/--：自增/自减1，可在变量前也可再变量后
        3.1）：单独使用时，在前在后都一样
        3.2）：被使用时，在前在后不一样
            a++的值为a(a--)
            ++a的值为a+1(--a)
```

> 代码解释：

```java
int a=5,b=5,e=4,r=4,h=3,k=3,t=2,m=2;
e++;
++r;
h--;
--k;
System.out.println(e);//只做一件事情，单独使用---5
System.out.println(r);//---5
System.out.println(h);//只做一件事情，单独使用---2
System.out.println(k);//---2
int c=a++;//被使用干了两件事，1）将a++的值5赋值给c 2）a自增变为6
int d=++b;//1)将++b的值6赋值给d 2）b自增1变为6
int q=t--;//被使用干了两件事，1）将t--的值2赋值给了q 2）t自减变为1
int y=--m;//被使用干了两件事，1）将--m的值1赋值给了y 2）m自减变为1
System.out.println(a);//---6
System.out.println(b);//---6

System.out.println(c);//---5
System.out.println(d);//---6

System.out.println(t);//---1
System.out.println(m);//---1

System.out.println(q);//---2
System.out.println(y);//---1
```

##### **关系运算符**

```Java
2.关系运算符：
   1）>(大于)，<(小于)
   >=(大于或等于)，<=(小于或等于)
   ！=(不等于),==(等于)
   2）关系运算的结果为Boolean型
   关系成立则为true，不成立则为false
```

> 代码解释

```Java
int u=5,i=10,o=5;
boolean u1=u>i;
System.out.println(u1);//false
System.out.println(u==o);//true
System.out.println(u>=o);//ture
System.out.println(u<=o);//ture
System.out.println(u!=o);//false
System.out.println(u+o>i);//先算术后关系比较---false
System.out.println(u%2==0);//false
System.out.println(o++>5);//false---o++的值为5,同时o自增1为6
System.out.println(o++>5);//true，因为这时候o为6，同时自增1为7
System.out.println(++i>10);//true,因为他是先自增1为11
```

##### **逻辑运算符**

```Java
3.逻辑运算符：
                                    补充解释---短路：某一个位置发生短路，后面的不走了
1）&&：逻辑(短路)与（同时满足才能为真）
   ---当第一个数为false，则直接为false
   ||：逻辑（短路）或（或者，满足一个则为真）
   ---当第一个数为true，则直接为true
   ！：逻辑非（非真则假，非假则为真）
2）逻辑运算是建立在关系运算的基础之上的
   逻辑运算结果也是boolean
```

> 代码解释

```Java
int a1=5,a2=10,a3=5;
boolean b2=a2>=a1&&a2<a3;//先做关系在做逻辑最后赋值
System.out.println(b2);//true&&false=false
System.out.println(a2<=a3&&a2>a1);//false&&true=false
System.out.println(a1==a2&&a3>a2);//false&&false=false
System.out.println(a2!=a3&&a1<a2);//true&&ture=ture

int c1=5,c2=10,c3=5;
System.out.println(c2>c1||c2<c3);//true||false=true
System.out.println(c2<=c3||c2>c1);//false||true=true
System.out.println(c2!=c3||c1<c2);//true||true=true
System.out.println(c1==c2||c3>c2);//false||false=false

//boolean b3=!c1<c2;//!的优先级最高，现在在！a
boolean b3=!(c1<c2);//!true=false
System.out.println(b3);
boolean b4=!(c1>c2);//!false=true
System.out.println(b4);

//短路
int e1=5,e2=10,e3=5;
boolean e4=e1>e2&&e3++>2;
System.out.println(e4);//false&&true=false
System.out.println(e3);//由于短路，前面已经停止运行，则不存在e3++----5
Boolean e5=e1<e2||e1++>2;
System.out.println(e5);//true||false=true
System.out.println(e1);//由于短路，前面已经停止运行，则不存在e1++----5
```