---
banner: "https://api.dujin.org/bing/1920.php"
cssclass: noyaml,noscroll,myhome
obsidianUIMode: preview
---

#C语言 

# 绝对值函数

C 语言中求绝对值的函数有两种，分别为 abs ()、fabs ()

abs () 函数用来对整型变量求绝对值，fabs () 函数用来对浮点型变量求绝对值

abs () 函数在头文件“stdlib. h”中，fabs () 函数在头文件“math. h”中。必须先引用头文件才可以使用相应函数。

# 平方根函数

sqrt (x)
求 x 的平方根
计算一个非负实数的平方根，sqrt () 函数在头文件“math. h”中

# 幂函数

pow (x, n)
计算 x 的 n 次方, pow () 函数在头文件“math. h”中

#  rand () 函数
函数在“stdlib. h”这是一个伪随机函数，我们可以使用 time 来重新“播种”, 使用“time. h”文件。
> 如何产生一定范围的随机数呢？
我们可以利用取模的方法：
int a = rand () % 10;    //产生 0~9 的随机数，注意 10 会被整除
如果要规定上下限：
int a = rand () % 51 + 13;    //产生 13~63 的随机数
分析：取模即取余，rand ()%51+13 我们可以看成两部分：rand ()%51 是产生 0~50 的随机数，后面+13 保证 a 最小只能是 13，最大就是 50+13=63。

例如:
```c
//随机数的种子
	srand((unsigned int)time(NULL));
//生成0~9之间的随机数	
	rand() % 10；
```