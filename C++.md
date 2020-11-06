# C++

##### 头文件及函数

```c++
#include <bits/stdc++.h>  //万能头文件

#include <stdio.h>
	scanf()  //C语言输入函数
    printf()  //C语言输出函数
    getchar()  //获得字符串
    %a   //读入一个浮点值（仅C99有效）
	%c   //读入一个字符
	%d   //读入十进制整数
	%i   //读入十进制，八进制，十六进制整数
	%o   //读入八进制整数
	%x   //读入十六进制整数
	%s   //读入一个字符串，遇空格，制表符或换行符结束
	%f,%e,%g  //用来输入实数，可以用小数形式或指数形式输入
	%p  //读入一个指针
	%u  //读入一个无符号十进制整数
	
#include <stdlib.h>
    void free (void *p)  //释放p所指的内存区
    void *malloc (unsigned size)  //分配size字节的存储区
    int rand (void)  //产生0到32767间的随机整数
    void exit (int state)  //程序中止执行，返回调用过程
        
#include <string.h>
    strcpy()  //连接
	strcmp()  //比较
	strlen()  //长度
	strcat()  //复制
        
#include <cmath>
    pow(2,3)=8  // 求幂函数 用double型，用int有误差
        		//原型 double pow(double x, int n)
    exp()  //指数函数  
	sqrt()  //平方根
	log;  //对数
	log10;  //对数
	sin,  //正弦
	cos,  //余弦
	tan， //正切
	floor;  //下取整
	ceil;  //上取整
	abs;  //整数绝对值
	fabs;  //实数绝对值
	fmod;  //求余
	abs;  //绝对值 

#include <algorithm>
	max()  //最大值
    min()  //最小值
	swap(x,y)  //交换x和y的值
    transform(s.begin(),s.end(),s.begin(),::tolower/::toupper)  //::tolower  字母转小写
                                                                //::toupper 字母转大写
    sort(a,a+n)  //默认递增排序
    /*若要递减排序，需要增加比较函数
       bool cmp (int a, int b){
             return a>b;
            }
        sort (a,a+n,cmp);
    */
    getline(字符,长度,"\0")  //字符    
    getline(cin, str1,'#')  //字符串

/* C++输入其他进制
dec 置基数为10 相当于"%d"
hex 置基数为16 相当于"%X"
oct 置基数为8 相当于"%o"
setiosflags(ios::uppercase) 16进制数大写输出
*/
        
/* 求数组最大最小值及下标 函数
在这之前，我们先定义一个a[6]数组={0,5,4,3,2,1},n=5;
*max_element(起点,执行长度);这个函数是用来求这个数组里最大的值,例：
K=*max_element(a+1,a+n+1);K的值也就等于5(注意：我是从下标1开始找的)；
二维的也就是：K=*max_element(a[i]+1,a[i]+n+1);
max_element(起点,执行长度)-数组名;这个函数求的是最大的数的下标，例:
k=max_element(a+1,a+n+1)-a;k的值就是1，
min_element也是一样的用法，只不过是求最小值。
*/
     
/*  函数:substr(start,length); 在<string>中
规定要返回其中一部分的字符串
正数 - 在字符串的指定位置开始
负数 - 在从字符串结尾的指定位置开始
0 - 在字符串中的第一个字符处开始
迭代器
s.begin()   获得指向开始位置的迭代器
s.end()      获得指向末尾的迭代器
容器
s.empty()  检查是否为空
s.size()等同于s.length()   返回数据的字符长度
修改器
s.clear()	清空内容
s.insert()	插入字符或字符串。目标 string 中的插入位置可用整数值或迭代器表示。如果参数仅为一个迭代器，则在其所指位置插入0值。
s.erase()	删除 1 个或 1 段字符
s.push_back()  追加 1 个字符
s.pop_back()   删除最后 1 个字符
*/
```