# Python

## 基础

```python
	input()  #输入 默认数据类型为str  int(input())整型输入
	print()  #输出 默认输出换行 end=''输出不换行
    #格式化输出
    	print('%.2f, %d'%(12,34)   # 12.00, 34  类似于c语言的输出
    	print('abc {} xyz'.format('mn'))  # abc mn xyz
    	print('abc {0} xyz {1}'.format('mn','tg'))  # abc mn xyz tg
    	print('abc {name} xyz'.format(name='mn'))  # abc mn xyz
    	print('{:.2f}'.format(12))  # 12.00
    	print('{0:.2f}'.format(12))  # 12.00
    	print('{num:.2f}'.format(num=12))  # 12.00
    
	#r' '表示内部的字符串默认不转义
    	print(r'\n')  # \n
    
	#'''''' 表示多行注释,也可是字符串跨多行
	#单个#表示一行注释
    
	#布尔值 Ture False 开头大写
	#逻辑运算符 and or not
    #成员运算符 in  not in
    #身份运算符 is is not
    #位运算符 & | ^ ~ << >>
        a = 0011 1100(60); b = 0000 1101(13)
    	# & 参与运算的两个值,如果两个相应位都为1,则该位的结果为1,否则为0。 a&b = 0000 1100
        # | 只要对应的二个二进位有一个为1时，结果位就为1。 a|b = 0011 1101
        # ^ 当两对应的二进位相异时，结果为1。 a^b = 0011 0001
        # ~ 对数据的每个二进制位取反,即把1变为0,把0变为1。 ~a  = 1100 0011
    	# << 运算数的各二进位全部左移若干位，由"<<"右边的数指定移动的位数，高位丢弃，低位补0。
       `# >> 把">>"左边的运算数的各二进位全部右移若干位，">>"右边的数指定移动的位数。
              
	# / 除法结果为浮点数
    # // 除法结果为整数
    # % 求余数
    # ** 幂运算
    print(2**3)  # 8            
    # c += a 等效于 c = c + a 其他同理
    
    # 多个变量赋值
    	a = b = c =1
        a, b, c = 1, 2, 'str'
              
    hex(x)  转换为十六进制字符串
    oct(x)  转换为八进制字符串
    
    import keyword
    keyword.kwlist  # python的保留关键字
          
    # 多行语句
    	total = item_one + \
        		item_two + \
        		item_three
    # 在 [], {}, 或 () 中的多行语句，不需要使用反斜杠(\)
          
    # Python可以在同一行中使用多条语句，语句之间使用分号(;)分割。
     	import sys; x = 'runoob'; sys.stdout.write(x + '\n')
    
	# python用import或者from...import来导入相应的模块
          import somemodule  # 导入整个模块
          import somemodule as module  # 将模块重命名，此程序使用此名
          from somemodule import somefunction  # 从某个模块中导入某个函数
          from somemodule import firstfunc, secondfunc, thirdfunc  # 从某个模块中导入多个函数
          form somemoudle import *  # 导入某个模块的全部函数
    
    del # 删除
    	del var
		del var_a, var_b
    
    type() # 查询变量所指的对象类型。
    isinstance()  #也可判断数据类型
    	a = 111
        isinstance(a, int)  # True
    # type() 与 isinstance() 不同在于：
    	#type()不会认为子类是一种父类类型。
    	#isinstance()会认为子类是一种父类类型。
         class A:
			pass
         class B(A):
           	pass
        isinstance(A(), A)  # True
		type(A()) == A  # True 
        isinstance(B(), A)  # True
		type(B()) == A  # False
```

## Number (数字)

Python 支持三种不同的数值类型：

- **整型(Int)** - 通常被称为是整型或整数，是正或负整数，不带小数点。Python3 整型是没有限制大小的，可以当作 Long 类型使用，所以 Python3 没有 Python2 的 Long 类型。
- **浮点型(float)** - 浮点型由整数部分与小数部分组成，浮点型也可以使用科学计数法表示（2.5e2 = 2.5 x 102 = 250）
- **复数( (complex))** - 复数由实数部分和虚数部分构成，可以用a + bj,或者complex(a,b)表示， 复数的实部a和虚部b都是浮点型。

**int(x)**将x转换为一个整数

**float(x)**将x转换到一个浮点数

**complex(x)**将x转换到一个复数，实数部分为 x，虚数部分为 0

**complex(x,y)**将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y。x 和 y 是数字表达式

### 数学函数（math库）

#### 数学常量

- **pi**  3.1415
- **e**  自然对数
- **inf**  正无穷大
- **nan**  非浮点数标记

#### 数值函数

```python
import math

math.fabs(x)

from math import *

fabs(x)  # 绝对值
fmod(x,y)  # 取余数
fsum([x,y,...])  # 求和
sqrt() # 求x的平方根
gcd(x,y)  # 求最大公约数
turnc(x)  # 求整数部分
modf(x)   # 求小数部分和整数部分
ceil(x)   # 向上取整
floor(x)  # 向下取整
factorial(x)  # 求阶乘
pow(x,y)  # 求x的y次方
exp(x)  # 求e的x次幂
log(x,base)  # log(100,10) = 2.9 log(math.e) = 1.0
log10(x)  # 求以10为基数的x的对数
#python自带
abs()  # 求绝对值
max(x1,x2,……)  # 求最大值
min(x1,x2,……)  # 求最小值
round(x[,n])  # 求浮点数x四舍五入的值 n：表示从小数点位数开始四舍五入
```

#### 三角函数

```python
from math import *

acos(x)  # 求x的反余弦弧度值 x[-1,1]
asin(x)  # 求x的反正弦弧度值 x[-1,1]
atan(x)  # 求x的反正切弧度值
atan2(y,x)  # 给定的X及Y坐标值的反正切值、
cos(x)  # 求x的弧度的余弦值
sin(x)  # 求x的弧度的正弦值
tan(x)  # 求x的弧度的正切值
hypot(x,y)  # 返回欧几里得范数 sqrt(x*x + y*y)
degrees(x)  # 将弧度转换为角度
radians()  # 将角度转换为弧度  radians(180/pi) = 1
```

### 随机数函数（random库）

```python
import random
import string

print(random.random())  # 随机生成0-1的浮点数
print(random.randint(1, 10))  # 随机生成1-10的整数
print(random.uniform(1.1, 5.4))  # 随机生成1.1-5.4的浮点数，区间可以不是整数
print(random.choice('tomorrow'))  # 从序列中随机选取一个元素,序列可以是列表、元组、字符串
print(random.randrange(1, 100, 2))  # 随机生成1-100间隔为2的随机奇数，0-100间隔为2的偶数

a = [1,2,3,4,5]
random.shuffle(a)  # 将列表a的元素顺序打乱

# 从a-zA-Z0-9生成指定数量的随机字符
random_str = ''.join(random.sample(string.ascii_letters + string.digits, 8))
```

## String (字符串)

```python
	#字符串类型为str()
 	str1 = 'Hello World!'
    # [:] 遵循左闭右开原则
    print(str1[0:-1]) = Hello World # 输出第一个到倒数第二个的所有字符
	print(str1[0]) = H              # 输出字符串第一个字符
	print(str1[2:5]) = llo          # 输出从第三个开始到第五个的字符
	print(str1[2:]) = llo World!    # 输出从第三个开始后的所有字符
	print(str1[1:5:2]) = el         # 输出从第二个开始到第五个且每隔两个的字符
	print(str1 * 2) = Hello World!Hello World! # 输出字符串两次
    
	#ord()函数获取字符的整数表示
    	ord('A') = 65
    #chr()函数将编码转换为对应的字符
    	chr(66)  = 'B'
    
    #Python格式化方式与c语言一致
    	# %c  字符及其ASCII码
    	# %d  整数
        # %f  浮点数
        # %s  字符串
        # %o  八进制整数
        # %x  十六进制整数
        # %u  无符号整型
        # %e  科学计数法格式化浮点数
        # %p  十六进制格式化变量的地址
        print('%.2f' % 3.1415926) = 3.14
    #格式化操作符辅助指令
    	# *  定义宽度或者小数点精度
        print('%*d'% (4,12)) =   12
        # -  左对齐
        # +  正数前面显示加号(+)
        # #  在八进制前面显示零('0')，在十六进制前面显示'0x'或者'0X'
        # 0  显示数字前面填充'0'而不是默认的空格
        # m.n  m是显示的最小总宽度,n是小数点后的位数
        
    #利用format()函数格式化，用传入的参数依次替换字符串内的占位符{0}、{1}
    	print('Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)) = Hello, 小明, 成绩提升了 17.1%
        
    #f-string 字面量格式化字符串python3.6后,f开头，表达式用{}包起来
    	name = 'World!'
        f'Hello {name}'  = 'Hello World!'
        f'{1+2}' = '3'
```

**转义字符**

| 转义字符     | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| \\(在行尾时) | 续行符                                                       |
| \\\          | 反斜杠符号                                                   |
| \\'          | 单引号                                                       |
| \\"          | 双引号                                                       |
| \a           | 响铃                                                         |
| \b           | 退格(Backspace)                                              |
| \000         | 空                                                           |
| \n           | 换行                                                         |
| \v           | 纵向制表符                                                   |
| \t           | 横向制表符                                                   |
| \r           | 回车，将 **\r** 后面的内容移到字符串开头，并逐一替换开头部分的字符，直至将 **\r** 后面的内容完全替换完成。 |
| \f           | 换页                                                         |

**内建函数**

```python
count(sub, start, end)  # 统计字符串某个字符出现的次数

decode()  # 将bytes型变为str()型  print(b'ABC'.decode('ascii')) = ABC
encode()  # 将str()型编码为指定的bytes型  print('ABC'.encode('ascii')) = b'ABC'

startswith(substr[, start[, end]])  # 判断字符串是否是以指定子字符串开头
endswith(substr[, start[, end]])  # 判断字符串是否以指定后缀结尾

expandtabs(tabsize)  # 指定转换字符串中的 tab 符号 \t 转为空格的字符数

find(str, start, end)  # 检测字符窜中是否包含子字符串str  返回包含子串开始的位置，否则返回-1
rfind(str, start, end)  # 返回子字符串最后出现的位置，否则返回-1

index(str, start, end)  # 作用同find()  包含返回子串开始的位置，否则抛出异常
rindex(str, start, end)  # 返回子字符串最后出现的位置，否则抛出异常

isalnum()  # 判断是否由字母和数字组成
isalpha()  # 判断是否只由字母或文字组成
isdigit()  # 判断是否只由数字组成
islower()  # 判断是否由小写字母组成
isnumeric()  # 判断是否只由数字组成，数字可以是： Unicode 数字，全角数字（双字节），罗马数字，汉字数字  一、①、Ⅰ
isspace()  # 判断是否只由空白字符组成
istitle()  # 判断所有的单词拼写首字母是否为大写，且其他字母为小写
isupper()  # 判断所有的字母是否都为大写
isdecimal()  # 判断字符串是否只包含十进制字符，只存在于unicode对象

join(sequence)  # 将序列中的元素以指定的字符连接生成一个新的字符串 sequence：要连接底元素序列
	s1 = '-'
    sequence = ("r", "u", "n", "o", "o", "b")
    s1.join(sequence) = r-u-n-o-o-b

len(s)  # 返回对象（字符、列表、元组等）长度或项目个数

center(width[,fillchar])  # 返回一个指定宽度width居中的字符串，fillchar为填充的字符，默认空格
ljust(width[, fillchar])  # 返回一个原字符串左对齐,并使用空格填充至指定长度的新字符串。如果指定的长度小于原字符串的长度则返回原字符串
rjust(width[, fillchar])  # 返回一个原字符串右对齐,并使用空格填充至长度 width 的新字符串。如果指定的长度小于字符串的长度则返回原字符串
zfill(width)  # 返回指定长度的字符串，原字符串右对齐，前面填充0

upper()  # 将所有小写字母转为大写
lower()  # 将所有大写字母转为小写
swapcase()  # 对字符串的大小写字母进行转换,大写变小写，小写变大写
title()  # 返回"标题化"的字符串  非字母后的第一个字母将转换为大写字母
	txt = "hello b2b2b2 and 3g3g3g"
	x = txt.title() = "Hello B2B2B2 And 3G3G3G"
capitalize()  # 将字符串的第一个字母变为大写，其他字母变为小写

strip()  # 用于移除字符串 头尾 指定的字符或字符序列
lstrip([chars])  # 用于截掉字符串左边的空格或指定字符
rstrip([chars])  # 删除字符串末尾的空格或指定字符

tranlate(table[, deletechars])  # 根据参数table给出的表转换字符串的字符,要过滤掉的字符放到deletechars中；table由maketrans生成
maketrans(intab, outtab)  # 用于创建字符映射的转换表，一个参数必须是字典，两个参数时长度要相等
	s1 = 'aeiou'; s2 = '12345'; str1 = 'google'
    trantab = str.maketrans(s1, s2); print(str.tranlate(trantab)) = g44l2

max(s)  # 返回字符窜最大的字母
min(s)  # 返回字符窜最小的字母

replace(old, new[, max])  # 替换字符串,max：替换不超过max次

split(str, num)  # 通过指定分隔符对字符串进行切片 num:分割次数，默认-1
splitlines([keepends])  # 按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表,如果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行符。
```

## List (列表)

```python
	a = ['a','b','c']
    b = [1, 2, 3]
    len(a) = 3
    print(a[2]) = c
    print(a[1:3]) = ['b', 'c']
    print(a[1:]) = ['b', 'c']  # 从第二个元素到最后
    print(a[0:3:2]) = ['a', 'c']  # 从第一个元素到第三个元素，间隔2
    list[-1::-1]
    #第一个参数 -1 表示最后一个元素
    # 第二个参数为空，表示移动到列表末尾
    # 第三个参数为步长，-1 表示逆向
    print(a + b) = ['a', 'b', 'c', 1, 2, 3]  # 连接两个链表
    
    #用-1做索引，直接获取最后一个元素 
    	a[-1] = c 
        a[-2] = b 
        a[-3] = a
    #append()追加元素到末尾
    	a.append('d')
    #insert()插入到指定位置
    	a.insert(1,'ab')
    #pop()删除末尾元素 
    	a.pop()
    #pop(i)删除指定位置元素
    	a.pop(i)
    #reverse()反向列表元素
    	a.reverse()
    #sort()进行排序
    	a.sort()
    #extend()在末尾追加另一个序列的值
    #clear()清空列表
    #copy()复制列表
    #list里元素类型可以不同
    #list元素也可以是另一个list
    	s = ['a','b','c',['ab','ac'],'d']
        len(s) = 4
     	#'ab'位置表示为s[3][0]
```

## Tuple (元组)

```python
	#初始化后不能修改
	#定义tuple时元素必须确定下来
    	t=(1,2)
    #空的tuple
    	t=()
    #只有一个元素定义tuple时必须加一个,
    	t=(1,)
```

## Dict (字典)

```python
	#具有极快的查找速度
    d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
    print(d['Michael']) = 95
    #可以通过key值放入dict中
    	d['Jack']=90
        print(d) = {'Michael': 95, 'Bob': 75, 'Tracy': 85, 'Jack': 90}
    #多次对一个key放入value，后面的值会把前面的值冲掉
    '''
    检测key是否存在
    	①print('Thomas' in d) = false
    	②print(d.get('Thomas')) = None
    	 print(d.get('Michael')) = 95
    '''
    #pop()删除一个key
    	d.pop('Bob')
        print(d) = {'Michael': 95, 'Tracy': 85, 'Jack': 90}
    #dict.clear() 清空字典
    #list可变，不可作为key
```

## Set (集合)

```python
	s=set([1,2,3])  #传入参数
    print(s) = {1, 2, 3}
    #set中重复元素会自动过滤
    #add(key)添加元素到set
    	s.add(4)
    #update(key)参数可以是列表，元组，字典
    	s.update({5,6})
        s.update([7,8])
    #remove(key)移除元素
    	s.remove(4)
    #discard(key)也是移除元素，若不存在，不报错
    	s.discard(9)
    #pop()随机删除一个元素
    	s.pop()
    #frozenset()冻结集合，不能添加删除元素，可以冻结列表、字典、元组等
    	frozenset(['b', 'r', 'u', 'o', 'n'])
    #两个set可作交集,并集
    	s1 = set([1, 2, 3])
	 	s2 = set([2, 3, 4])
        s1 - s2  = {1}  # 集合s1中包含而集合s2中不包含的元素
		s1 & s2  = {2, 3}  # 集合s1或s2中包含的所有元素
		s1 | s2  = {1, 2, 3, 4}  # 集合s1和s2中都包含了的元素
        s1 ^ s2  = {1, 4}  # 不同时包含于s1和s2的元素 
```

## 条件判断

```python
	'''
	if <条件判断1>:
    	<执行1>
	elif <条件判断2>:
    	<执行2>
	elif <条件判断3>:
   	 	<执行3>
	else:
    	<执行4>
    '''
```

## 循环语句

```python
	range(起始位置,最终位置,步长) #生成一个整数序列
    print(list(range(5))) = [0, 1, 2, 3, 4]
	#for循环
    	sum=0
    	for x in range(10):
        	sum+=x
        print(sum) = 45
    #while循环
		L = ['Bart', 'Lisa', 'Adam']
		n = 0
		while n < 3:
    		print('hello', L[n])
    		n +=1
        #hello Bart
		#hello Lisa
		#hello Adam
    #while循环使用 else 语句
    	while var1 :
            ......
        else :
            ......
    #break语句
    	#提前结束循环
        n = 1
		while n <= 100:
    		if n > 10: # 当n = 11时，条件满足，执行break语句
        		break # break语句会结束当前循环
    		print(n)
   			n = n + 1
    #continue
    	#跳过这次循环，进入下一次循环
        n = 0
		while n < 10:
   	 		n = n + 1
    		if n % 2 == 0: # 如果n是偶数，执行continue语句
        		continue # continue语句会直接继续下一轮循环，后续的print()语句不会执行
    		print(n)
```

## 可变与不可变对象

```python
#list、dict、int是可变对象  
    s =['c','b','a']
    s.sort()
    print(s)  = ['a','b','c']
#str、tuple、Number(int float bool complex)是不可变对象 
    a='abc'
    a.replace('a','A')  = 'Abc'
    print(a)  = 'abc'
```

## 函数

### 	调用函数

```python
#调用函数
	abs()  #绝对值
    max()  #最大值
    #数据类型转化函数
    	int()
        float()
        str()
        bool()
    #可以把函数名赋给一个变量
    	a=abs
    	print(a(-1)) = 1  
```

### 定义函数

```python
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x
#空函数
	def nop():
    	pass
```
