****

### java的变量

#### 变量种类（8种）

```
//八种基本数据类型
//byte、short
//int、long：整型
//float、double：浮点型，八个字节
//boolean：布尔型，一个字节
//char：字符型，两个字节
```

#### 整型（int）

```Java
//int：整型，-21个多亿到21多亿，四个字节
//两个整数相除，小数位无条件舍弃
int a=250;
System.out.println(5/2);//结果为2
//但变量超出范围，不会报错，但是会溢出
int c=2147483647;//这是a最大的值
c=c+1;
System.out.println(c);//结果为-2147483648
//溢出要避免
//int b=10000000000000000;//系统默认为int类型，但是超出范围
```

#### 长整型（long）

```java
 //long：长整型，很大很大很大，八个字节3
long d=10000000000000l;//长整型直接量需在数字后加L或l
long h=1000000000*2*10l;//20亿（int）从左到右
long e=1000000000*3*10l;//30亿（int）溢出
long r=1000000000l*3*10;//30亿（long）不会溢出；所以在前面需要在前面加l
System.out.println(d);
System.out.println(h);
System.out.println(e);
System.out.println(r);
```

#### 浮点型（double）

```java
//double（浮点型）很大很大很大
// 浮点数量默认为double
//3.14-----为double
//3.14F-----为float
double t=3.25;//3.25为浮点数直接量
//double和float进行运算时有可能发生舍入误差，在做精算度高的不能用这个
double y=6.0,u=5.9;
System.out.println(y-u);//0.10000000000000009,有可能发生舍入误差
                        //0.09999999999999964
```

#### 布尔型（Boolean）

```java
//Boolean（布尔型），只能装true或false只占一个字节
boolean l=true;//true 为布尔型直接量
boolean j=false;//false为布尔型直接量
//boolean i=25;//编译错误，布尔型只能存储true或false
```

#### 字符型（char）

```Java
// char：字符型，两个字节
//采用Unicode字符集编码格式（万国码、统一码、通用码）-----是世界级通用的定长（16位）字符集
//------因为符号太多了，所以Unicode又分划分为了很多个子集
//java中的char采用的是其中最最通用的一个子集，一个字符对应一个码
//‘女‘----对应一次码
char m='女';
System.out.println(m);
//ASCII码：’a‘----97、‘A’-----65、’0‘----48（0-----0）必须在单引号里面并且只能保存一个
//特殊符合可以通过\来转义
char n='\'';//通过\进行转义
char q='\\';
System.out.println(q);
System.out.println(n);
char o=65;//'A'=65范围是0---65535
System.out.println(o);//输出的时候会依据o的类型来决定
```

### 变量的转化

#### 两个方式

```java
-------自动（隐式）转化
-------强制转化
```

```java
byte k=5;//整数直接量赋值
byte k1=50;
//byte k1=500;//超出范围不可以
```

#### 两个规则

```java
byte k2= (byte) (k+k1);//再byet类型运算时（k）和（k1）系统默认为int，则int给byte需要强转
System.out.println('2'+'2');//'2'的编码50+'2'的编码50=100
System.out.println(2+2);//2+2=4
System.out.println('2');//因为没有运算，是什么类型输出什么类型----2
System.out.println(2+'2');//2+'2'的编码50=52
System.out.println(k2);
```

#### 字节

```java
 /*
   ----字节
  1G=1024M（兆）
  1M=1024KB（千字节）
  1KB=1024B（字节）
  1B=8Bit（位）
  1G=1024*1024*1024-----1073741824字节
  所以在选择类型的时候，选择够用就行
*/
//所有的变量/数据------都会存储在内存中，内存是有大小的
//变量到底占用多大的内容，是看变量的类型
```