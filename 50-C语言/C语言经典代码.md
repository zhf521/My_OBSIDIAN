---

banner: "https://api.dujin.org/bing/1920.php"

cssclass: noyaml,noscroll,myhome

obsidianUIMode: preview

---

#C语言 

# 生成两个数之间的随机整数
```c
int randBetweenMinMax(int min,int max)
{
	int a = rand() % (max-min+1) + min;
	return a;
}
```

# 两个整数的变量值交换
指针型
```c
void swap(int* x, int* y)
{
	int temp;
	temp = *x;
	*x = *y;
	*y = temp;
}
```

```c
#include<stdio.h>

void change(int *a, int *b)
{
    int temp;
    temp = *a;
    *a = *b;
    *b = temp;
}


int main()
{  
    int a = 0, b = 0;
    scanf("%d %d", &a, &b);
    change(&a, &b);
    printf("%d %d", a, b);
    return 0;
}
```
# 求阶乘
```c
#include <stdio.h>
#include <conio.h>

//递归法
int fac(int n)
{
	int f;
	if (n == 1)
		f = 1;
	else
		f = n * fac(n - 1);
	return f;
}

//for循环法
int fac(int n)
{
    int i;
    int item = 1;
    for (i = 1; i <= n; i++)
    {
        item *= i;
    }
    return item;
}

int main()
{
	int num = fac(5);
	printf("5!=%d\n", num);
	_getch();
	return 0;
}
```
# 乘法表
```c
#include <stdio.h>
int main()
{
    int i, j;
	for ( i = 1; i <= 9; i++)
	{
		for (j = 1; j <= i; j++)
		{
			printf("%d*%d=%-2d ", i, j, i * j);
		}
		printf("\n");
	}
    return 0;
}
```
# 最大公约数和最小公倍数
```c
#include <stdio.h>

int gcd(int m, int n)//最大公约数
{
    if (m % n == 0)
        return n;
    else
        return gcd(n, m % n);
}

int lcm(int m, int n)//最小公倍数
{
    return m * n / gcd(m, n);
}

int main()
{
    int m, n;
    scanf("%d%d", &m, &n);
    printf("%d\n", gcd(m, n));
    printf("%d", lcm(m, n));
    return 0;
}
```
# 素数 (质数) 的判断
```c
#include <stdio.h>
#include <math.h>
int a(int m)
{
    for (int i = 2; i <= sqrt(m); i++)
    {
        if (m % i == 0)
        {
            return 0;
        }
    }
    return m;
}
int main()
{
    int m = 0;
    scanf("%d", &m);
    if (a(m) == 0)
    {
        printf(" not prime");
    }
    else
    {
        printf("prime");
    }
    return 0;
}
```
# 宏定义，求三角形面积
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/C语言经典代码1.png)


```c
#include<stdio.h>
#include<math.h>
#define S(a,b,c) s=(a+b+c)/2
#define Area(a,b,c,s)  area=sqrt(s*(s-a)*(s-b)*(s-c))

int main()
{  
    int a, b, c, s = 0;
    float area = 0;
    scanf("%d %d %d", &a, &b, &c);
    S(a, b, c);
    Area(a, b, c, s);
    printf("%.3f", area);
    return 0;
}
```

# 宏定义，判断闰年
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/C语言经典代码2.png)

```c
#include<stdio.h>
#define LEAP_YEAR(y) if(y%400==0||y%4==0&&y%100!=0) printf("L"); else printf("N");
int main()
{  
    int y = 0;
    scanf("%d", &y);
    LEAP_YEAR(y);
    return 0;
}
```
# 宏定义，找最大数
![](https://obsidian-picture.oss-cn-qingdao.aliyuncs.com/my-img/C语言经典代码3.png)

```C
#include<stdio.h>
#define Max(a,b)  a>b?a:b

float MAX(float a, float b)
{
    return a > b ? a : b;
}

int main()
{  
    float x, y, z = 0;
    scanf("%f %f %f", &x, &y, &z);
    printf("%.3f\n", MAX(z, MAX(x, y)));
    printf("%.3f", Max(z, Max(x, y)));
    return 0;
}
```