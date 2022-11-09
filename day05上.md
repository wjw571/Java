

```Java
//for()循环结构演示----与次数相关的
```

```java
/*
变量的重名作用域：作用域重叠时，变量不能同名
*/
```

```Java
//特殊点，for中的循环变量num，作用范围仅限当前for循环中
        /*
            3.for结构：
            1）语法：
                    1           2           3
                for(循环要素1;循环要素2;循环要素3){
                        语句块;------4
                }
            2）执行过程：
1243243243最后还是2
         */
```

代码例子

```Java
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
    System.out.println("9的乘法表:");
    for(int num=1;num<10;num++){
        System.out.println(num+"*9="+num*9);
    }
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
}
```

```java
//如何选三种循环结构
/*
先看循环是否与次数相关：
    若相关，直接选择for
    若无关，看要素一和要素三是否相同
        若相同则，do while
        若不相同，while

* */
```