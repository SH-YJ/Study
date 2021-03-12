# **Python**

## 基础

```python
	input()  #输入 默认数据类型为str  int(input())整型输入
	print()  #输出 默认输出换行 end=''输出不换行
    
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
    # * 乘积
    # ** 幂运算
    print(2**3)  # 8            
    # c += a 等效于 c = c + a 其他同理
    
    # *与**的非运算用法
    	# * 用于参数前面(*args)表示接受多个参数并放在元组中
        def test(*p):
			print(p)
		test(1,2,3)  # (1, 2, 3)
        # ** 用于参数前面(**args)表示接受接收类似于关键参数一样赋值的形式的多个实参放入字典
        def func(**p):
            for i in p.items():
                print(i)
        func(x=1,y=2)  # ('x', 1) ('y', 2) 
    
    # 多个变量赋值
    	a = b = c =1
        a, b, c = 1, 2, 'str'
    
    bin(x)  # 转换为二进制字符串
    hex(x)  # 转换为十六进制字符串
    oct(x)  # 转换为八进制字符串
    
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

1. **int(x)**将x转换为一个整数
2. **float(x)**将x转换到一个浮点数
3. **complex(x)**将x转换到一个复数，实数部分为 x，虚数部分为 0
4. **complex(x,y)**将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y。x 和 y 是数字表达式

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
    	print('abc {} xyz'.format('mn'))  # abc mn xyz
    	print('abc {0} xyz {1}'.format('mn','tg'))  # abc mn xyz tg
    	print('abc {name} xyz'.format(name='mn'))  # abc mn xyz
    	print('{:.2f}'.format(12))  # 12.00
    	print('{0:.2f}'.format(12))  # 12.00
    	print('{num:.2f}'.format(num=12))  # 12.00
        # ^, <, > 分别是居中、左对齐、右对齐，后面带宽度
        print('{:^10d}'.format(13))
        # : 号后面带填充的字符，只能是一个字符，不指定则默认是用空格填充
        # + 表示在正数前显示 +，负数前显示 -；  （空格）表示在正数前加空格
        # 使用大括号 {} 来转义大括号
        # b、d、o、x 分别是二进制、十进制、八进制、十六进制
        print('{:x},{:#x}'.format(11,11))  # b,0xb
        
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

**内置函数**

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

replace(old, new[, max])  # 替换字符串,max：替换不超过max次，返回一个字符串，不影响本身

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
    append(obj)  # 追加元素到末尾
    insert(index, obj)  # 插入元素到指定位置
    pop([index])  # 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
    reverse()  # 反向列表元素
    extend()  # 在末尾追加另一个序列的值
    clear()  # 清空列表
    copy()  # 复制列表
    count(obj)  # 统计某个元素出现的次数
    index(x[, start[, end]])  # 从列表中找出某个值第一个匹配项的索引位置
    remove(obj)  # 移除列表中某个值的第一个匹配项
    sort(key, reverse)  # 进行排序,key:指定可迭代对象中的一个元素来进行排序,reverse:排序规则，reverse = True降序，reverse = False升序（默认）
    	def takeSecond(elem):  # 按照第二个元素排序
    		return elem[1]
        list = [(2, 2), (3, 4), (4, 1), (1, 3)]
        list.sort(key=takeSecond)
        print(list) = [(4, 1), (2, 2), (1, 3), (3, 4)]
    
    list(seq)  # 将元组或字符串转为列表
    max(list)  # 求列表最大元素
    min(list)  # 求列表最小元素
    #list里元素类型可以不同
    #list元素也可以是另一个list
    	s = ['a','b','c',['ab','ac'],'d']
        len(s) = 4
     	#'ab'位置表示为s[3][0]
```

### 将列表当做堆栈使用

列表方法使得列表可以很方便的作为一个堆栈来使用，堆栈作为特定的数据结构，最先进入的元素最后一个被释放（**后进先出**）。用 **append()** 方法可以把一个元素添加到堆栈顶。用不指定索引的 **pop()** 方法可以把一个元素从堆栈顶释放出来

**实例**

```python
stack = [3, 4, 5]
stack.append(6)
stack.append(7)
print(stack) = [3, 4, 5, 6, 7]

stack.pop() = 7
print(stack) = [3, 4, 5, 6]
```

### 将列表当作队列使用

把列表当做队列用，只是在队列里第一加入的元素，第一个取出来；但是拿列表用作这样的目的效率不高。在列表的最后添加或者弹出元素速度快，然而在列表里插入或者从头部弹出速度却不快

```python
from collections import deque
queue = deque(["Eric", "John", "Michael"])
queue.append("Terry")           # Terry 入队
queue.append("Graham")          # Graham 入队

queue.popleft() = 'Eric'        # 第一个元素出队
queue.popleft() ='John'         # 第二个元素出队

print(queue) = deque(['Michael', 'Terry', 'Graham'])
```

### 列表推导式

列表推导式提供了从序列创建列表的简单途径

```python
l1 = [x for x in range(10)]  # 这里不仅可以用for,也可以用if,while等循环或者判断语句
newlist = [(x, y) for x in a for y in b]
print(l1) = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### 嵌套列表解析

**实例**

```python
 matrix = [
   		[1, 2, 3, 4],
        [5, 6, 7, 8],
        [9, 10, 11, 12],
        ]
# 方法一
    [[row[i] for row in matrix] for i in range(4)]

# 方法二
	transposed = []
    for i in range(4):
 	     transposed.append([row[i] for row in matrix]
                          
# 方法三
  	transposed = []
 	for i in range(4):
 	     transposed_row = []
  	     for row in matrix:
 	        transposed_row.append(row[i])
 	     transposed.append(transposed_row)
```



## Tuple (元组)

```python
	#初始化后不能修改，是不可变的
	#定义tuple时元素必须确定下来
    	t=(1,2)
    #空的tuple
    	t=()
    #只有一个元素定义tuple时必须加一个,
    	t=(1,)
    
    tup2 = (1, 2, 3, 4, 5, 6, 7 )
	print(tup2[0]) = 1
	print(tup2[1:5]) = (2, 3, 4, 5)
    print(tup2[-1]) = 5
    # 元组中的元素不允许删除，但能用del删除整个元组
    
    # 元组内置函数
    tuple(iterable)  # 将可迭代元素转换为元组
    len(tuple)  # 计算元组元素个数
    max(tuple)  # 返回元组中元素最大值
    min(tuple)  # 返回元组中元素最小值
```

## Dict (字典)

```python
	#具有极快的查找速度
    d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
    print(d['Michael']) = 95
    #可以通过key值放入dict中
    	d['Jack']=90
        print(d) = {'Michael': 95, 'Bob': 75, 'Tracy': 85, 'Jack': 90}
    '''
    检测key是否存在
    	①print('Thomas' in d) = false
    	②print(d.get('Thomas')) = None
    	 print(d.get('Michael')) = 95
    '''
    
    # 字典键的特性
    	# 1) 不允许同一个键出现两次，创建时如果同一个键被赋值两次，后一个值被记住
        # 2) 键必须不可变，所以可以用数字(number)，字符串(str)或元组(tuple)，但是列表(list)不行
    
    # 字典内置函数
    	len(dict)  # 计算字典元素个数，即键的总数
        str(dict)  # 输出字典，以可打印的字符串表示
    
    # 字典内置方法
    	clear()  # 删除字典内所有元素
        copy()  # 返回一个字典的浅复制
        fromkeys(seq[, value])  # 用于创建一个新字典，用seq（键值列表）作字典的键，value作键所对应的初始值
        get(key, default=None)  # 返回指定键的值,default:指定的键不存在，返回默认值
        setdefault(key,default=None)  # 若键不存在，则添加键并将值设为默认值
    	items()  # 以列表返回可遍历的（键,值）元组数组
        keys()  # 返回一个可迭代对象，使用list()转换为列表
        values()  # 返回一个迭代器，可以使用list()转换为列表
        update(dict2)  # 把dict2的键值更新到dict1中
        pop(key[, default])  # 删除字典给定key所对应的值，返回被删除的值，key必须给出，否则返回default
        popitem()  # 返回并删除字典中的最后一对键和值
```

## Set (集合)

```python
	# 集合(set)是一个无序的不重复元素序列，set中重复元素会自动过滤
    # 可以使用大括号{}或者set()函数创建集合，创建一个空集合必须用set() 而不是{}
    
    s=set([1,2,3])  #传入参数
    print(s) = {1, 2, 3}
    
    #两个set可作交集,并集
    	s1 = set([1, 2, 3])
	 	s2 = set([2, 3, 4])
        s1 - s2  = {1}  # 集合s1中包含而集合s2中不包含的元素
		s1 & s2  = {2, 3}  # 集合s1或s2中包含的所有元素
		s1 | s2  = {1, 2, 3, 4}  # 集合s1和s2中都包含了的元素
        s1 ^ s2  = {1, 4}  # 不同时包含于s1和s2的元素 
    
    # set内置方法
    	add(x)  # 添加元素到set,
        update(x)  # 也是添加元素，参数可以是列表、元组、字典
        remove(x)  # 移除元素，若不存在，则报错
        discard(x)  # 也是移除元素，若不存在，不报错
        pop()  # 返回并随机删除集合中的一个元素
        len(s)  # 计算集合s元素个数
        clear()  # 清空集合s
        copy()  # 拷贝一个集合
        frozenset()  # 冻结集合，不能添加删除元素，可以冻结列表、字典、元组等
        
        difference(set)  # 返回两个集合的差集，即返回的集合元素包含在第一个集合中，但不包含在第二个集合中
        difference_update(set)  # 用于移除两个集合中都存在的元素，无返回值
        
        intersection(set1[,set2,……etc])  # 返回两个或更多集合中都包含的元素，即交集
        intersection_update(set1[,set2,……etc])  # 获取两个或更多集合中都包含的元素，无返回值
        
        isdisjoint(set)  # 用于判断是否包含相同元素，没有返回True,否则False
        issubset(set)  # 判断集合中的所有元素是否都包含在指定集合中，是则True,否则False
        issuperset(set)  # 判断指定集合的所有元素是否都包含在原始集合中，是则True,否则False
        
        symmetric_difference(set)  # 返回两个集合中不重复的元素集合,即会移除两个集合中都存在的元素
        symmetric_difference_update(set)  # 除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中
        
    	union()  # 方法返回两个集合的并集，即包含了所有集合的元素，重复的元素只会出现一次
```

## 条件控制

```python
if <条件判断1>:
    <执行1>
elif <条件判断2>:
    <执行2>
elif <条件判断3>:
   	<执行3>
else:
    <执行4>

# if语句用于表达式
str1 = "More" if a > b else "Less"
```

## 循环语句

### while循环

```python
L = ['Bart', 'Lisa', 'Adam']
n = 0
while n < 3:
    print('hello', L[n])
    n += 1
#hello Bart
#hello Lisa
#hello Adam

# while循环使用 else 语句
count = 0
while count < 5:
   print (count, " 小于 5")
   count = count + 1
else:
   print (count, " 大于或等于 5")
```

### for循环

```python
languages = ["C", "C++", "Perl", "Python"] 
for x in languages:
	print (x)
sum=0
for x in range(10):
	sum+=x
print(sum) = 45

# for循环也可以使用else语句
list = [1, 2, 3, 4, 5]
for i in list:
    print(i)
else:
    print('没有循环数据！')
```

### 遍历技巧

在**字典中遍历**时，关键字和对应的值可以使用 **items()** 方法同时解读出来

```python
dict = {1 : 'a', 2 : 'b'}
for k, v in dict.items():
	print(k, v)
'''
1 a
2 b
'''
```
在**序列中遍历**时，索引位置和对应值可以使用 **enumerate()** 函数同时得到：

```python
for i, v in enumerate(['tic', 'tac', 'toe']):
	print(i, v)
'''
0 tic
1 tac
2 toe
'''
```

同时**遍历两个或更多的序列**，可以使用 **zip()** 组合：

```python
list1 = [1,2,3,4]
list2 = ['a','b','c','d']
for each in zip(list1,list2):
    print(each)
'''
(1, 'a')
(2, 'b')
(3, 'c')
(4, 'd')
'''
for a,b in zip(list1,list2):
    print(a,b)
'''
1 a
2 b
3 c
4 d    
'''
```

**反向遍历**一个序列，首先指定这个序列，然后调用 **reversed()** 函数：

```python
for i in reversed(range(1, 10, 2)):
	print(i)
'''
9
7
5
3
1
'''
```

要按**顺序遍历**一个序列，使用 **sorted()** 函数返回一个已排序的序列，并不修改原值：

```python
basket = ['apple', 'orange', 'apple', 'pear', 'orange', 'banana']
for f in sorted(set(basket)):
	print(f)
'''
apple
banana
orange
pear
'''
```

### range()函数

```python
range(起始位置,最终位置,步长) #生成一个整数序列
print(list(range(5))) = [0, 1, 2, 3, 4]
```

### break和continue语句

```python
#break
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

### pass 语句

pass是**空语句**，是为了保持程序结构的完整性。

pass 不做任何事情，一般用做**占位语句**。

## 迭代器和生成器

### 迭代器

迭代器有两个基本的方法：**iter()** 和 **next()**。

```python
# 字符串，列表或元组对象都可用于创建迭代器
list=[1,2,3,4]
it = iter(list)    # 创建迭代器对象
print (next(it))   # 输出迭代器的下一个元素

# 迭代器对象可以使用常规for语句进行遍历
for x in it:
    print (x, end=" ") = 1 2 3 4
# 使用 next() 函数遍历
import sys
while True:
    try:
        print(next(it)) 
    except  StopIteration:
        sys.exit()
```

### 生成器

生成器是一个返回迭代器的函数，只能用于迭代操作

在调用生成器运行的过程中，每次遇到 yield 时函数会暂停并保存当前所有的运行信息，返回 yield 的值, 并在下一次执行 next() 方法时从当前位置继续运行。

```python
def fibonacci(n): # 生成器函数 - 斐波那契
    a, b, counter = 0, 1, 0
    while True:
        if (counter > n): 
            return
        yield a
        a, b = b, a + b
        counter += 1

f = fibonacci(10) # f 是一个迭代器，由生成器返回生成
 
while True:
    try:
        print (next(f), end=" ")
    except StopIteration:
        sys.exit()
```

## 函数

### **定义函数**

- 函数代码块以 **def** 关键词开头，后接函数标识符名称和圆括号 **()**。
- 任何传入参数和自变量必须放在圆括号中间，圆括号之间可以用于定义参数。
- 函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
- 函数内容以冒号 **:** 起始，并且缩进。
- **return [表达式]** 结束函数，选择性地返回一个值给调用方，不带表达式的 return 相当于返回 None。

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

### **可更改(mutable)与不可更改(immutable)对象**

在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

- **不可变类型：**变量赋值 **a=5** 后再赋值 **a=10**，这里实际是新生成一个 int 值对象 10，再让 a 指向它，而 5 被丢弃，不是改变 a 的值，相当于新生成了 a。
- **可变类型：**变量赋值 **la=[1,2,3,4]** 后再赋值 **la[2]=5** 则是将 list la 的第三个元素值更改，本身la没有动，只是其内部的一部分值被修改了。

python 函数的参数传递：

- **不可变类型：**类似 C++ 的值传递，如整数、字符串、元组。如 fun(a)，传递的只是 a 的值，没有影响 a 对象本身。如果在 fun(a) 内部修改 a 的值，则是新生成一个 a 的对象。
- **可变类型：**类似 C++ 的引用传递，如 列表，字典。如 fun(la)，则是将 la 真正的传过去，修改后 fun 外部的 la 也会受影响

### 匿名函数(lambda)

所谓匿名，意即不再使用 def 语句这样标准的形式定义一个函数。

- **lambda 只是一个表达式**，函数体比 def 简单很多。
- lambda的主体是一个表达式，而不是一个代码块。仅仅能在lambda表达式中封装有限的逻辑进去。
- lambda 函数拥有自己的命名空间，且不能访问自己参数列表之外或全局命名空间里的参数。
- 虽然lambda函数看起来只能写一行，却不等同于C或C++的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。

**语法**

```python
lambda [arg1 [,arg2,.....argn]]: expression
```

**实例**

```python
sum = lambda arg1, arg2: arg1 + arg2

# 调用sum函数
print ("相加后的值为 : ", sum( 10, 20 )) = 30
print ("相加后的值为 : ", sum( 20, 20 )) = 40
```

### 强制位置参数

Python3.8 新增了一个函数形参语法 **`/`** 用来指明函数形参必须使用指定位置参数，不能使用关键字参数的形式。

在以下的例子中，形参 **a 和 b** 必须使用**指定位置参数**，**c 或 d** 可以是**位置形参或关键字形参**，而 **e 或 f** 要求为**关键字形参**:

```python
def f(a, b, /, c, d, *, e, f):
    print(a, b, c, d, e, f)
    
# 正确写法 
f(10, 20, 30, d=40, e=50, f=60)
# 错误写法
f(10, b=20, c=30, d=40, e=50, f=60)   # b 不能使用关键字参数的形式
f(10, 20, 30, 40, 50, f=60)           # e 必须使用关键字参数的形式
```

## 面向对象

### 面向对象技术简介

- **类(Class):** 用来描述具有相同的属性和方法的对象的集合。它定义了该集合中每个对象所共有的属性和方法。对象是类的实例。
- **方法：**类中定义的函数。
- **类变量：**类变量在整个实例化的对象中是公用的。类变量定义在类中且在函数体之外。类变量通常不作为实例变量使用。
- **数据成员：**类变量或者实例变量用于处理类及其实例对象的相关的数据。
- **方法重写：**如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖（override），也称为方法的重写。
- **局部变量：**定义在方法中的变量，只作用于当前实例的类。
- **实例变量：**在类的声明中，属性是用变量来表示的，这种变量就称为实例变量，实例变量就是一个用 self 修饰的变量。
- **继承：**即一个派生类（derived class）继承基类（base class）的字段和方法。继承也允许把一个派生类的对象作为一个基类对象对待。例如，有这样一个设计：一个Dog类型的对象派生自Animal类，这是模拟"是一个（is-a）"关系（例图，Dog是一个Animal）。
- **实例化：**创建一个类的实例，类的具体对象。
- **对象：**通过类定义的数据结构实例。对象包括两个数据成员（类变量和实例变量）和方法。

### 类定义

```python
class ClassName:
    <statement-1>
    .
    .
    .
    <statement-N>
```

### 类对象

类对象支持两种操作：**属性引用和实例化**

类对象创建后，类命名空间中所有的命名都是有效属性名。

**实例**

```python
class MyClass:
    i = 12345
    def f(self):
        return 'hello world'
 
# 实例化类
x = MyClass()

# 属性引用
# 访问类的属性和方法
print("MyClass 类的属性 i 为：", x.i)
print("MyClass 类的方法 f 输出为：", x.f())
```

类有一个名为 **\__init__()** 的特殊方法（**构造方法**），该方法在类**实例化**时会自动调用，可以有参数

```python
def __init__(self):
    self.data = []
```

**实例**

```python
class Complex:
    def __init__(self, realpart, imagpart):
        self.r = realpart
        self.i = imagpart
x = Complex(3.0, -4.5)
print(x.r, x.i)   # 输出结果：3.0 -4.5
```

**self代表类的实例，而非类**

### 类的方法

类使用`def`关键字来定义一个方法，与一般函数定义不同，类方法必须包含参数 **self**, 且**为第一个参数**，**self 代表的是类的实例**。

**实例**

```python
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name, self.age))
 
# 实例化类
p = people('abc', 10, 30)
p.speak()
```

### 继承

派生类的定义如下所示:

```python
class DerivedClassName(BaseClassName1):
    <statement-1>
    .
    .
    .
    <statement-N>
```

**实例**

```python
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
#单继承示例
class student(people):
    grade = ''
    def __init__(self,n,a,w,g):
        #调用父类的构造函数
        people.__init__(self,n,a,w)
        self.grade = g
    #覆写父类的方法
    def speak(self):
        print("%s 说: 我 %d 岁了，我在读 %d 年级"%(self.name,self.age,self.grade))
 
 
 
s = student('ken',10,60,3)
s.speak()
```

### 多继承

多继承的类定义形如下例:

```python
class DerivedClassName(Base1, Base2, Base3):
    <statement-1>
    .
    .
    .
    <statement-N>
```

注意圆括号中**父类的顺序**，若是**父类中有相同的方法名**，而在**子类使用时未指定**，python从**左至右搜索** 即方法在子类中未找到时，从左到右**查找父类中是否包含方法**。

**实例**

```python
#类定义
class people:
    #定义基本属性
    name = ''
    age = 0
    #定义私有属性,私有属性在类外部无法直接进行访问
    __weight = 0
    #定义构造方法
    def __init__(self,n,a,w):
        self.name = n
        self.age = a
        self.__weight = w
    def speak(self):
        print("%s 说: 我 %d 岁。" %(self.name,self.age))
 
#另一个类，多重继承之前的准备
class speaker():
    topic = ''
    name = ''
    def __init__(self,n,t):
        self.name = n
        self.topic = t
    def speak(self):
        print("我叫 %s，我是一个演说家，我演讲的主题是 %s"%(self.name,self.topic))
 
#多重继承
class sample(speaker,student):
    a =''
    def __init__(self,n,a,w,g,t):
        student.__init__(self,n,a,w,g)
        speaker.__init__(self,n,t)
 
test = sample("Tim",25,80,4,"Python")
test.speak()   #方法名同，默认调用的是在括号中排前地父类的方法
```

### 方法重写

```python
class Parent:        # 定义父类
   def myMethod(self):
      print ('调用父类方法')
 
class Child(Parent): # 定义子类
   def myMethod(self):
      print ('调用子类方法')
 
c = Child()          # 子类实例
c.myMethod()         # 子类调用重写方法
super(Child,c).myMethod()  # 用子类对象调用父类已被覆盖的方法

super(type[, object-or-type]).xxx  # 函数用于调用父类(超类)的一个方法
```

### 类属性与方法

类的**私有属性**与**私有方法**：两个**下划线（_ _）**开头，声明该属性为私有，不能在类外使用，类内使用**self.__xxx**

**实例**

```python
class JustCounter:
    __secretCount = 0  # 私有变量
    publicCount = 0    # 公开变量
 
    def count(self):
        self.__secretCount += 1
        self.publicCount += 1
        print (self.__secretCount)
        
    def __foo(self):          # 私有方法
        print('这是私有方法')
 
counter = JustCounter()
counter.count()
counter.__foo()  # 报错
print (counter.publicCount)
print (counter.__secretCount)  # 报错，实例不能访问私有变量
```

**类的专有方法：**

- **\__init__ :** 构造函数，在生成对象时调用
- **\__del__ :** 析构函数，释放对象时使用
- **\__repr__ :** 打印，转换
- **\__setitem__ :** 按照索引赋值
- **\__getitem__:** 按照索引获取值
- **\__len__:** 获得长度
- **\__cmp__:** 比较运算
- **\__call__:** 函数调用
- **\__add__:** 加运算
- **\__sub__:** 减运算
- **\__mul__:** 乘运算
- **\__truediv__:** 除运算
- **\__mod__:** 求余运算
- **\__pow__:** 乘方

**运算符重载**

可以对**类的专有方法**进行重载

```python
class Vector:
   def __init__(self, a, b):
      self.a = a
      self.b = b
 
   def __str__(self):
      return 'Vector (%d, %d)' % (self.a, self.b)
   
   def __add__(self,other):
      return Vector(self.a + other.a, self.b + other.b)
 
v1 = Vector(2,10)
v2 = Vector(5,-2)
print (v1 + v2)
```

## 命名空间和作用域

### 命名空间

一般有三种命名空间：

- **内置名称（built-in names**）， Python 语言内置的名称，比如函数名 abs、char 和异常名称 BaseException、Exception 等等。
- **全局名称（global names）**，模块中定义的名称，记录了模块的变量，包括函数、类、其它导入的模块、模块级的变量和常量。
- **局部名称（local names）**，函数中定义的名称，记录了函数的变量，包括函数的参数和局部定义的变量。（类中定义的也是）

命名空间查找顺序:**局部的命名空间去 -> 全局命名空间 -> 内置命名空间**

**实例**

```python
# var1 是全局名称
var1 = 5
def some_func():
 
    # var2 是局部名称
    var2 = 6
    def some_inner_func():
 
        # var3 是内嵌的局部名称
        var3 = 7
```

### 作用域

四种作用域：

- **L（Local）**：最内层，包含局部变量，比如一个函数/方法内部。
- **E（Enclosing）**：包含了非局部(non-local)也非全局(non-global)的变量。比如两个嵌套函数，一个函数（或类） A 里面又包含了一个函数 B ，那么对于 B 中的名称来说 A 中的作用域就为 nonlocal。
- **G（Global）**：当前脚本的最外层，比如当前模块的全局变量。
- **B（Built-in）**： 包含了内建的变量/关键字等，最后被搜索。

规则顺序： **L –> E –> G –> B**。

![img](https://www.runoob.com/wp-content/uploads/2014/05/1418490-20180906153626089-1835444372.png)

**实例**

```python
g_count = 0  # 全局作用域
def outer():
    o_count = 1  # 闭包函数外的函数中
    def inner():
        i_count = 2  # 局部作用域
```

#### 全局变量和局部变量

**局部变量**只能在其**被声明的函数内部访问**，而**全局变量**可以在**整个程序范围内访问**。

```python
total = 0 # 这是一个全局变量
# 可写函数说明
def sum( arg1, arg2 ):
    #返回2个参数的和."
    total = arg1 + arg2 # total在这里是局部变量.
    print ("函数内是局部变量 : ", total)
    return total
 
#调用sum函数
sum( 10, 20 )
print ("函数外是全局变量 : ", total)
```

#### global 和 nonlocal关键字

当**内部作用域想修改外部作用域的变量**时，就要用到**global**和**nonlocal**关键字。

**实例1**

```python
# 修改全局变量 num
num = 1
def fun1():
    global num  # 需要使用 global 关键字声明
    print(num) 
    num = 123
    print(num)
fun1()
print(num)

'''
1
123
123
'''

a = 10
def test():
    global a
    a = a + 1
    print(a)
test()

'''
11
'''
```

**实例2**

```python
# 修改嵌套作用域（enclosing 作用域，外层非全局作用域）中的变量
def outer():
    num = 10
    def inner():
        nonlocal num   # nonlocal关键字声明
        num = 100
        print(num)
    inner()
    print(num)
outer()

'''
100
100
'''
```

## File 方法

### open()

**open()** 方法用于**打开一个文件**，并**返回文件对象**，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 **OSError**。

**语法**

```python
# 常用形式
open(file, mode='r')
# 完整形式
open(file, mode='r', buffering=-1, encoding=None, newfile=None, closefd=True, opener=None)
'''
file: 必需，文件路径（相对或者绝对路径）。
mode: 可选，文件打开模式
buffering: 设置缓冲
encoding: 一般使用utf8
errors: 报错级别
newline: 区分换行符
closefd: 传入的file参数类型
opener: 设置自定义开启器，开启器的返回值必须是一个打开的文件描述符。
'''
```

**mode参数**

| 模式    | 描述                                                         |
| :------ | :----------------------------------------------------------- |
| **t**   | **文本模式** (默认)。                                        |
| **x**   | **写模式，新建一个文件**，如果**该文件已存在则会报错**。     |
| **b**   | **二进制模式**。                                             |
| **+**   | 打开一个文件进行更新(**可读可写**)。                         |
| **r**   | 以**只读方式**打开文件。**文件的指针将会放在文件的开头**。这是默认模式。 |
| **rb**  | 以**二进制格式**打开一个文件用于**只读**。文件指针将会放在文件的**开头**。这是默认模式。一般用于非文本文件如图片等。 |
| **r+**  | 打开一个文件**用于读写**。文件指针将会放在文件的**开头**。   |
| **rb+** | 以**二进制格式**打开一个文件用于**读写**。文件指针将会放在文件的开头。一般用于非文本文件如图片等。 |
| **w**   | 打开一个文件**只用于写入**。如果**该文件已存在则打开文件，并从开头开始编辑**，即原有内容会被删除。如果**该文件不存在，创建新文件。** |
| **wb**  | 以**二进制格式**打开一个文件**只用于写入**。如果**该文件已存在则打开文件，并从开头开始编辑**，即原有内容会被删除。如果该**文件不存在，创建新文件**。一般用于非文本文件如图片等。 |
| **w+**  | 打开一个文件**用于读写**。如果**该文件已存在则打开文件，并从开头开始编辑**，即原有内容会被删除。如果**该文件不存在，创建新文件。** |
| **wb+** | 以**二进制格式**打开一个文件**用于读写**。如果**该文件已存在则打开文件，并从开头开始编辑**，即原有内容会被删除。如果**该文件不存在，创建新文件**。一般用于非文本文件如图片等。 |
| **a**   | 打开一个文件**用于追加**。如果**该文件已存在，文件指针将会放在文件的结尾**。也就是说，新的内容将会被写入到已有内容之后。如果**该文件不存在，创建新文件进行写入**。 |
| **ab**  | 以**二进制格式**打开一个文件**用于追加**。如果**该文件已存在，文件指针将会放在文件的结尾**。也就是说，新的内容将会被写入到已有内容之后。如果**该文件不存在，创建新文件进行写入**。 |
| **a+**  | 打开一个文件**用于读写**。如果**该文件已存在，文件指针将会放在文件的结尾**。文件打开时会是追加模式。如果**该文件不存在，创建新文件用于读写**。 |
| **ab+** | 以**二进制格式**打开一个文件用于**追加**。如果**该文件已存在，文件指针将会放在文件的结尾**。如果**该文件不存在，创建新文件用于读写**。 |

默认为**文本模式**，如果要以二进制模式打开，加上 `b`。

### file对象

#### close()

**close()** 方法用于**关闭一个已打开的文件**。**关闭后的文件不能再进行读写操作， 否则会触发 *ValueError* 错误**。

**实例**

```python
file = open('C:/path/1.txt', 'w')
print(file.name)  # 1.txt
file.close()  # 关闭文件
```

#### write()

**write()** 方法用于向文件中**写入指定字符串**，如果文件打开模式带 b，那写入文件内容时，str (参数)要用 encode 方法转为 bytes 形式，否则报错：TypeError: a bytes-like object is required, not 'str'。

**实例**

```python
file = open('1.txt', 'r', encoding='UTF-8')
file.write('12345')
file.close()
```

#### writelines()

**writelines()** 方法用于向文件中**写入一序列的字符串**

**实例**

```python
file = open('1.txt', 'r', encoding='UTF-8')
list = ['12\n', '23asd\n', 'asdzxc']
file.writelines(list)
file.close()
```

#### read()

**read()** 方法用于**从文件读取指定的字节数**，如果**未给定或为负则读取所有**。

**语法**

```python
read([size])
# size : 从文件中读取的字节数，默认为 -1，表示读取整个文件
```

**实例**

```python
file = open('1.txt', 'r', encoding='UTF-8')
text = file.read()
print(text)  # 12312
```

#### readline()

**readline()** 方法用于**从文件读取整行**，包括 **"\n"** 字符。如果**指定了一个非负数的参数，则返回指定大小的字节数，包括 "\n" 字符**

**语法**

```python
readline([size])
# size : 从文件中读取的字节数
```

**实例**

```python
file = open("runoob.txt", "r+")

line = file.readline()
print (line)  # 1:www.runoob.com

line = file.readline(5)
print (line)  # 2:www

file.close()
```

#### readlines()

**readlines()** 方法用于**读取所有行**(直到**结束符 EOF**)并**返回列表**，该列表可以由 Python 的 for... in ... 结构进行处理。 如果**碰到结束符 EOF 则返回空字符串**。

**实例**

```python
file = open("runoob.txt", "r")

for line in file.readlines():
    line = line.strip()                       #去掉每行头尾空白  
    print (line)
    
file.close()
'''
1:www.runoob.com
2:www.runoob.com
3:www.runoob.com
4:www.runoob.com
5:www.runoob.com
'''
```

#### tell()

**tell()** 方法返回**文件的当前位置**，即**文件指针当前位置**。

**实例**

```python
fo = open("runoob.txt", "r+")
 
line = fo.readline()
print ("读取的数据为: %s" % (line))

# 获取当前文件位置
pos = fo.tell()
print ("当前位置: %d" % (pos))  # 17
 
fo.close()
```

#### truncate()

**truncate()** 方法用于从**文件的首行首字节开始截断**，截断文件为 **size 个字节**，无 size 表示从当前位置截断；截断之后 V 后面的所有字节被删除，其中 Widnows 系统下的换行代表2个字节大小。

**语法**

```python
truncate([size])
# size : 可选，如果存在则文件截断为 size 字节
```

**实例**

```python
fo = open("runoob.txt", "r+")

line = fo.readline()
print ("读取行: %s" % (line))

fo.truncate()
line = fo.readlines()
print ("读取行: %s" % (line))

fo.close()

'''
读取行: 1:www.runoob.com

读取行: ['2:www.runoob.com\n', '3:www.runoob.com\n', '4:www.runoob.com\n', '5:www.runoob.com\n']
'''
```

#### flush()

**flush()** 方法是用来**刷新缓冲区**的，即将**缓冲区中的数据立刻写入文件，同时清空缓冲区**，不需要是被动的等待输出缓冲区写入。

**实例**

```python
file = open('C:/path/1.txt', 'w', encoding='UTF-8')
file.flush()  # 刷新缓冲区
file.close()  # 关闭文件
```

#### seek()

**seek()** 方法用于**移动文件读取指针到指定位置**。操作成功，则**返回新的文件位置**，如果操作失败，则函数** **。

**语法**

```python
seek(offset[, whence])
# offset : 开始的偏移量，也就是代表需要移动偏移的字节数，如果是负数表示从倒数第几位开始。
# whence : 可选，默认值为 0。给 offset 定义一个参数，表示要从哪个位置开始偏移；0 代表从文件开头开始算起，1 代表从当前位置开始算起，2 代表从文件末尾算起。
```

**实例**

```python
f = open('workfile', 'rb+')
f.write(b'0123456789abcdef')
# 16
f.seek(5)      # 移动到文件的第六个字节
# 5
f.read(1)
# b'5'
f.seek(-3, 2)  # 移动到文件倒数第三个字节
# 13
f.read(1)
# b'd'
```

#### fileno()

**fileno()** 方法**返回一个整型的文件描述符**(file descriptor FD 整型)，可用于底层操作系统的 I/O 操作。

**实例**

```python
file = open('1.txt', 'w')
print(file.fileno())  # 3
file.close()
```

#### isatty()

**isatty()** 方法**检测文件是否连接到一个终端设备**，如果**是返回 True**，**否则返回 False**。

**实例**

```python
file = open('1.txt', 'w')
print(file.isatty())  # False
file.close()
```

## OS 文件/目录方法

### os模块方法

#### getcwd()

**getcwd()**返回**当前的工作目录**。

**实例**

```python
import os

print(os.getcwd())  # C:/User/Desktop/Python
```

#### chdir()

**chdir()改变当前工作目录到指定的路径**，允许访问返回 **True** , 否则返回**False**

**实例**

```python
import os

os.chdir('C:/Desktop')
print(os.getcwd())  # C:/Desktop
```

#### listdir()

**listdir() 获取指定文件夹中的所有文件和文件夹组成的列表**，默认为当前路径。

**实例**

```python
import os

print(os.listdir())  # a list
print(os.listdir('C:/'))
```

#### mkdir()

**mkdir()**创建**一个目录/文件夹**。如果目录有多级，则**创建最后一级**，如果最后一级目录的**上级目录有不存在**的，则会抛出一个 **OSError**

**实例**

```python
import os

os.mkdir('C:/User/Appdata/newdirectory')
```

#### makedirs()

**makedirs()递归创建文件夹**，如果**子目录创建失败或者已经存在**，会抛出** OSError**

**实例**

```python
import os

os.makedirs('/newdir1/newdir2/newdir3')
```

#### remove()

**remove()删除指定路径的文件**

**实例**

```python
import os

os.remove('C:/User/1.txt')
```

#### rmdir()

**rmdir()移除一个目录/文件夹**（必须是**空目录**），否则, 抛出**OSError**

**实例**

```python
import os

os.rmdir('C:/User/Desktop/Emptydir')
```

#### removedirs()

**removedirs()递归删除文件夹**，必须是**空文件夹**。

**实例**

```python
import os

os.removedirs('C:/Windows/Media')
```

#### rename()

**rename(src, dst)**用于**重命名文件或目录**，如果**dst是一个存在的目录/文件**, 将**抛出OSError**。

**renames()**用于**递归重命名目录/文件**，**renames()**类似于**rename()**。

**实例**

```python
import os

print(os.listdir(os.getcwd()))  # ['old.txt']

os.rename('old.txt', 'new.txt')
print(os.listdir(os.getcwd()))  # ['new.txt']
```

#### stat()

**stat()获取文件的相关信息**

**返回值**

```python
# st_mode: inode 保护模式
# st_ino: inode 节点号。
# st_dev: inode 驻留的设备。
# st_nlink: inode 的链接数。
# st_uid: 所有者的用户ID。
# st_gid: 所有者的组ID。
# st_size: 普通文件以字节为单位的大小；包含等待某些特殊文件的数据。
# st_atime: 上次访问的时间。
# st_mtime: 最后一次修改的时间。
# st_ctime: 由操作系统报告的"ctime"。在某些系统上（如Unix）是最新的元数据更改的时间，在其它系统上（如Windows）是创建时间（详细信息参见平台的文档）。
```

**实例**

```python
import os

print(os.stat('1.txt'))
```

#### system()

**system()执行系统命令**

**实例**

```python
import os

os.system('cls')
```

#### popen()

**popen()执行系统命令**

**语法**

```python
os.popen(command[, mode[, bufsize]])
# command : 使用的命令。

# mode : 模式权限可以是 'r'(默认) 或 'w'。

# bufsize : 指明了文件需要的缓冲大小：0意味着无缓冲；1意味着行缓冲；其它正值表示使用参数大小的缓冲（大概值，以字节为单位）。负的bufsize意味着使用系统的默认值，一般来说，对于tty设备，它是行缓冲；对于其它文件，它是全缓冲。如果没有改参数，使用系统的默认值。
```

**实例**

```python
import os

a = 'mkdir nwdir'
b = os.popen(a,'r',1)

print(b)  # open file 'mkdir nwdir', mode 'r' at 0x81614d0
```



#### getenv()

**getenv()获得系统环境变量**

```python
import os

print(os.getenv('path'))
```

#### putenv()

**putenv('环境变量名'，'变量值')设置系统环境变量**

**实例**

```python
import os

os.putenv('envname', 'python ')
```

#### unlink()

**unlink()删除文件,如果文件是一个目录则返回一个错误。**

**实例**

```python
import os

os.unlink('dirname')
```

#### walk()

**walk()**用于通过在目录树中游走输出在**目录中的文件名**，**向上或者向下**。

**语法**

```python
walk(top[, topdown=True[, onerror=None[, followlinks=False]]])
# top : 根目录下的每一个文件夹(包含它自己), 产生3-元组 (dirpath, dirnames, filenames)【文件夹路径, 文件夹名字, 文件名】。

# topdown : 可选，为True或者没有指定, 一个目录的的3-元组将比它的任何子文件夹的3-元组先产生 (目录自上而下)。如果topdown为 False, 一个目录的3-元组将比它的任何子文件夹的3-元组后产生 (目录自下而上)。

# onerror : 可选，是一个函数; 它调用时有一个参数, 一个OSError实例。报告这错误后，继续walk,或者抛出exception终止walk。

# followlinks : 设置为 true，则通过软链接访问目录。
```

**实例**

```python
import os

for root, dirs, files in os.walk('C:/')
	print(root, dirs, files)
```

#### open()

**open()** 方法用于**打开一个文件**，并且**设置需要的打开选项**，模式参数mode参数是可选的，默认为 0777。

**语法**

```python
open(file, flags[, mode])
# flags : 该参数可以是以下选项，多个使用 "|" 隔开：
	# os.O_RDONLY: 以只读的方式打开
	# os.O_WRONLY: 以只写的方式打开
	# os.O_RDWR : 以读写的方式打开
	# os.O_NONBLOCK: 打开时不阻塞
	# os.O_APPEND: 以追加的方式打开
	# os.O_CREAT: 创建并打开一个新文件
	# os.O_TRUNC: 打开一个文件并截断它的长度为零（必须有写权限）
	# os.O_EXCL: 如果指定的文件存在，返回错误
	# os.O_SHLOCK: 自动获取共享锁
	# os.O_EXLOCK: 自动获取独立锁
	# os.O_DIRECT: 消除或减少缓存效果
	# os.O_FSYNC : 同步写入
	# os.O_NOFOLLOW: 不追踪软链接
```

**实例**

```python
import os

# 打开文件
fd = os.open( "foo.txt", os.O_RDWR|os.O_CREAT )

# 写入字符串
os.write(fd, str.encode("This is test"))

# 关闭文件
os.close( fd )
```

#### read()

**read()**用于从文件描述符 fd 中**读取最多 n 个字节**，返回包含读取字节的字符串，文件描述符 fd对应文件已达到结尾, 返回一个空字符串

**语法**

```python
read(fd, n)
# fd : 文件描述符
# n : 读取的字节
```

**实例**

```python
import os

fd = os.open("f1.txt",os.O_RDWR)
   
# 读取文本
ret = os.read(fd, 12)
print (ret)  # This is a test

# 关闭文件
os.close(fd)
```

#### write()

**write()**用于**写入字符串到文件描述符 fd** 中. **返回实际写入的字符串长度**

**语法**

```python
write(fd, str)
```

**实例**

```python
import os

fd = os.open("f1.txt",os.O_RDWR|os.O_CREAT)

# 写入字符串
str = "This is runoob.com site"
ret = os.write(fd,bytes(str, 'UTF-8'))

# 输出返回值
print (ret)  # 23

# 关闭文件
os.close(fd)
```

#### close()

**close(fd)**用于**关闭指定的文件描述符 fd**

### os模块的值

```python
import os

os.name  # 返回当前系统的内核名称 win->nt linux/unix->posix

os.curdir  # 获取当前路径

os.pardir  # 获取上层目录路径

os.sep  # 获取当前系统的路径分割符号 window -> \ linux/unix -> /

os.extsep  # 获取当前系统中文件名和后缀之间的分割符号，所有系统都是.

os.linesep  # 获取当前系统的换行符号 window -> \r\n linux/unix -> \n

os.environ  # 直接获取所有环境变量的信息组成的字典，如果希望更改环境变量，并且可以查询得到
```

### **os.path模块**

| 方法                            | 说明                                                       |
| :------------------------------ | :--------------------------------------------------------- |
| **abspath(path)**               | 返回**绝对路径**                                           |
| **basename(path)**              | 返回**文件名**                                             |
| **commonprefix(list)**          | 返回list(多个路径)中，**所有path共有的最长的路径**         |
| **dirname(path)**               | 返回**文件路径**                                           |
| **exists(path)**                | **路径存在**则返回**True**,**路径损坏**返回**False**       |
| **lexists**                     | **路径存在**则返回**True**,**路径损坏**也返回**True**      |
| **expanduser(path)**            | 把**path中包含的"~"和"~user"**转换成**用户目录**           |
| **expandvars(path)**            | 根据**环境变量的值**替换**path中包含的"$name"和"${name}"** |
| **getatime(path)**              | 返回**最近访问时间**（浮点型秒数）                         |
| **getmtime(path)**              | 返回**最近文件修改时间**                                   |
| **getctime(path)**              | 返回**文件 path 创建时间**                                 |
| **getsize(path)**               | 返回**文件大小**，如果文件不存在就返回错误                 |
| **isabs(path)**                 | 判断**是否为绝对路径**                                     |
| **isfile(path)**                | 判断**路径是否为文件**                                     |
| **isdir(path)**                 | 判断**路径是否为目录**                                     |
| **islink(path)**                | 判断**路径是否为链接**                                     |
| **ismount(path)**               | 判断**路径是否为挂载点**                                   |
| **join(path1[, path2[, ...]])** | 把**目录和文件名合成一个路径**                             |
| **normcase(path)**              | 转换**path的大小写和斜杠**                                 |
| **normpath(path)**              | 规范**path字符串形式**                                     |
| **realpath(path)**              | 返回**path的真实路径**                                     |
| **relpath(path[, start])**      | 从**start开始计算相对路径**                                |
| **samefile(path1, path2)**      | 判断**目录或文件是否相同**                                 |
| **sameopenfile(fp1, fp2)**      | 判断**fp1和fp2是否指向同一文件**                           |
| **samestat(stat1, stat2)**      | 判断**stat1和stat2是否指向同一个文件**                     |
| **split(path)**                 | 把路径分割成 **dirname** 和 **basename**，返回一个元组     |
| **splitdrive(path)**            | 一般用在 windows 下，返回**驱动器名**和**路径**组成的元组  |
| **splitext(path)**              | 分割路径中的**文件名**与**拓展名**                         |
| **splitunc(path)**              | 把路径分割为**加载点**与**文件**                           |
| **supports_unicode_filenames**  | 设置**是否支持unicode路径名**                              |

## 异常

### 异常处理

#### try/except

**语法**

```python
try:
	执行代码
except:
    发生异常时执行的代码
```

**try 语句**按照如下方式工作；

- 首先，**执行 try 子**句（在关键字 try 和关键字 except 之间的语句）。
- 如果**没有异常发生，忽略 except 子句**，try 子句执行后结束。
- 如果在执行 try 子句的过程中**发生了异常**，那么 **try 子句余下的部分将被忽略**。如果异常的类型和 except 之后的名称相符，那么对应的 except 子句将被执行。
- 如果**一个异常没有与任何的 except 匹配**，那么**这个异常将会传递给上层的 try 中**。

一个 try 语句可能包含多个except子句，一个except子句可以同时处理多个异常。

#### try/except...else

**语法**

```python
try:
    执行代码
except:
    发生异常时执行的代码
else:
    没有异常时执行的代码
```

#### try-finally 语句

**语法**

```python
try:
    执行代码
except:
    发生异常时执行的代码
else:
    没有异常时执行的代码
finally:
    不管有没有异常都会执行的代码
```

### 抛出异常

使用 `raise` 语句抛出一个指定的异常

raise 唯一的一个参数指定了要被抛出的异常。它必须是一个异常的实例或者是异常的类（也就是 Exception 的子类）

**语法**

```python
raise [Exception [, args [, traceback]]]
```

**实例**

```python
x = int(input())
if x > 5:
    raise Exception('x不能大于5!')
else:
    print(x)
```

### 自定义异常

创建一个新的异常类来自定义异常。异常类继承自 Exception 类，可以直接继承，或者间接继承

**实例**

```python
class MyError(Exception):
	def __init__(self, value):
  		self.value = value
   	def __str__(self):
       	return repr(self.value)

try:
   	raise MyError(2*2)
except MyError as e:
   	print('My exception occurred, value:', e.value)  # My exception occurred, value: 4

raise MyError('oops!')
'''
Traceback (most recent call last):
  File "<stdin>", line 1, in ?
__main__.MyError: 'oops!'
'''
```

### 预定义的清理行为

一些对象定义了标准的清理行为，无论系统是否成功的使用了它，一旦不需要它了，那么这个标准的清理行为就会执行。

关键词 `with` 语句就可以保证诸如文件之类的对象在使用完之后一定会正确的执行他的清理方法:

```python
with open("myfile.txt") as f:
    for line in f:
        print(line, end="")
# 代码执行完毕后，即使在处理过程中出问题了，文件 f 总是会关闭
```

### 断言（assert）

```python
assert  表达式
#  接下来的语句：如果为真就执行，反之会抛出AssertionError异常

assert expression
等价于
if not expression:
    raise AssertionError
    
x = '2'
assert type(x) is int
'''
Traceback (most recent call last):
  File "S:/Desktop/py文件/Normal/Study/List.py", line 8, in <module>
    assert type(x) is int
AssertionError
'''
```

## 日期与时间

Python 提供了一个 `time` 和 `calendar` 模块可以用于格式化日期和时间。

每个时间戳都以自从 **1970 年 1 月 1 日**午夜（历元）经过了多长时间来表示

### 时间元组

就是**struct_time元组**

| 属性         | 值                                                           |
| :----------- | :----------------------------------------------------------- |
| **tm_year**  | 2008                                                         |
| **tm_mon**   | 1 到 12                                                      |
| **tm_mday**  | 1 到 31                                                      |
| **tm_hour**  | 0 到 23                                                      |
| **tm_min**   | 0 到 59                                                      |
| **tm_sec**   | 0 到 61 (60或61 是闰秒)                                      |
| **tm_wday**  | 0到6 (0是周一)                                               |
| **tm_yday**  | 一年中的第几天，1 到 366                                     |
| **tm_isdst** | 是否为夏令时，值有：1(夏令时)、0(不是夏令时)、-1(未知)，默认 -1 |

### 日期格式化符号

python中**时间日期格式化符号**：

| 符号   | 说明                                      |
| :----- | ----------------------------------------- |
| **%y** | 两位数的年份表示（0~99）                  |
| **%Y** | 四位数的年份表示（000~9999）              |
| **%m** | 月份（01~12）                             |
| **%d** | 月内中的一天（0~31）                      |
| **%H** | 24小时制小时数（0~23）                    |
| **%I** | 12小时制小时数（01~12）                   |
| **%M** | 分钟数（00~59）                           |
| **%S** | 秒（00~59）                               |
| **%a** | 本地简化星期名称                          |
| **%A** | 本地完整星期名称                          |
| **%b** | 本地简化的月份名称                        |
| **%B** | 本地完整的月份名称                        |
| **%c** | 本地相应的日期表示和时间表示              |
| **%j** | 年内的一天（001~365）                     |
| **%p** | 本地A.M 或P.M 的等价符                    |
| **%U** | 一年中的星期数（00~53）星期天为星期的开始 |
| **%w** | 星期（0~6），星期天为星期的开始           |
| **%W** | 一年中的星期数（00~53）星期一为星期的开始 |
| **%x** | 本地相应的日期表示                        |
| **%X** | 本期相应的时间表示                        |
| **%Z** | 当前时区的名称                            |
| **%%** | %号本身                                   |

### Time模块

#### altzone()

返回格林威治西部的**夏令时地区的偏移秒数**。如果该地区在格林威治东部会返回负值（如西欧，包括英国）。对夏令时启用地区才能使用。

**实例**

```python
import time

print(time.altzone())  # -32400
```

#### asctime()

**asctime([tupletime])**接受时间元组并返回一个可读的形式为"Tue Dec 11 18:07:14 2008"（2008年12月11日 周二18时07分14秒）的24个字符的字符串。

**实例**

```python
import time

localtime = time.asctime(time.localtime())
print(localtime)  # Thu Feb 11 12:26:06 2021
```

####  ctime()

**ctime([secs])**作用相当于asctime(localtime(secs))，未给参数相当于asctime()

**实例**

```python
import time

print(time.ctime())  # Thu Feb 11 12:31:05 2021
```

#### gmtime()

**gmtime([secs])**接收时间戳（1970纪元后经过的浮点秒数）并返回格林威治天文时间下的时间元组t。注：t.tm_isdst始终为0

**实例**

```python
import time

print(time.gmtime(1455508609.34375))
# time.struct_time(tm_year=2016, tm_mon=2, tm_mday=15, tm_hour=3, tm_min=56, tm_sec=49, tm_wday=0, tm_yday=46, tm_isdst=0)
```

#### localtime()

**localtime([secs])**接收时间戳（1970纪元后经过的浮点秒数）并返回当地时间下的时间元组t（t.tm_isdst可取0或1，取决于当地当时是不是夏令时）

**实例**

```python
import time

localtime = time.localtime(time.time())
print(localtime)
# time.struct_time(tm_year=2021, tm_mon=2, tm_mday=11, tm_hour=10, tm_min=9, tm_sec=45, tm_wday=3, tm_yday=42, tm_isdst=0)
```

#### strftime()

**语法**

```python
time.strftime(format[, tupletime])  # 接收以时间元组，并返回以可读字符串表示的当地时间，格式由fmt决定。
strptime(str,fmt='%a %b %d %H:%M:%S %Y')  # 根据fmt的格式把一个时间字符串解析为时间元组。
```

**实例**

```python
import time

# 格式化成2021-02-11 10:14:56形式
print (time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))

# 格式化成Thu Feb 11 10:14:56 2021形式
print (time.strftime("%a %b %d %H:%M:%S %Y", time.localtime()))
 
# 将格式字符串转换为时间戳
a = "Thu Feb 11 10:14:56 2021"
print (time.mktime(time.strptime(a,"%a %b %d %H:%M:%S %Y")))
# 1613009696.0
```

#### mktime()

**mktime(tupletime)**接受时间元组并返回时间戳（1970纪元后经过的浮点秒数）。

**实例**

```python
import time

t = (2020, 2, 11, 12, 40, 38, 1, 48, 0)
secs = time.mktime( t )
print (secs)  # 1613018438.0
```

#### sleep()

**sleep(secs)**推迟调用线程的运行，secs指秒数。

实例

```python
import time

print ("Start : %s" % time.ctime())  # Start : Thu Feb 11 12:44:13 2021
time.sleep( 5 )
print ("End : %s" % time.ctime())  # End : Thu Feb 11 12:44:18 2021
```

#### time()

**time()**返回当前时间的时间戳（1970纪元后经过的浮点秒数）。

**实例**

```python
import time

print(time.time())  # 1613018886.8422368
```

#### perf_counter()

**perf_counter()**返回计时器的**精准时间**（系统的运行时间），**包含整个系统的睡眠时间**。

**实例**

```python
import time

scale = 50

print("执行开始".center(scale // 2, "-"))  # .center() 控制输出的样式，宽度为 25//2，即 22，汉字居中，两侧填充 -

start = time.perf_counter()
for i in range(scale + 1):
    a = '*' * i  # i 个长度的 * 符号
    b = '.' * (scale - i)  # scale-i） 个长度的 . 符号。符号 * 和 . 总长度为50
    c = (i / scale) * 100  # 显示当前进度，百分之多少
    dur = time.perf_counter() - start  # 计时，计算进度条走到某一百分比的用时
    print("\r{:^3.0f}%[{}->{}]{:.2f}s".format(c, a, b, dur), end='')  # \r用来在每次输出完成后，将光标移至行首，这样保证进度条始终在同一行输出，即在一行不断刷新的效果。
    time.sleep(0.1)  # 在输出下一个百分之几的进度前，停止0.1秒
print("\n" + "执行结果".center(scale // 2, '-'))
```

#### process_time()

**process_time()**返回当前进程执行 CPU 的时间总和，**不包含睡眠时间**,**与perf_counter()类似**。

### Datetime模块

#### date类

**datetime.date(year, month, day)**

**静态方法和字段**

```python
date.max、date.min  # date对象所能表示的最大、最小日期
date.resolution  # date对象表示日期的最小单位。这里是天
date.today()  # 返回一个表示当前本地日期的date对象

import datetime

print(datetime.date.min)  # 0001-01-01
print(datetime.date.max)  # 9999-12-31
print(datetime.date.resolution)  # 1 day, 0:00:00
print(datetime.date.today())  # 2021-02-13
```

**方法和属性**

```python
import datetime

d1 = date(2021, 2, 15)  # date对象

print(d1.year, d1.month, d1.day)  # 2021 2 15
d2 = d1.replace(year, month, day)  # 生成一个新的日期对象，用参数指定的年，月，日代替原有对象中的属性。（原有对象仍保持不变）

d1.timetuple()  # 返回日期对应的time.struct_time(时间元组)对象

d1.weekday()  # 返回weekday，如果是星期一，返回0；如果是星期2，返回1，以此类推

d1.isoweekday()  # 返回weekday，如果是星期一，返回1；如果是星期2，返回2，以此类推
d1.isocalendar()  # 返回格式如(year，month，day)的元组
d1.isoformat()  # 返回格式如'YYYY-MM-DD’的字符串

d1.strftime(fmt)  # 和time模块strftime()相同
```

#### time类

**datetime.time(hour[ , minute[ , second[ , microsecond[ , tzinfo] ] ] ] )** 

**静态方法和字符**

```python
time.min  # time类所能表示的最小时间。time.min = time(0, 0, 0, 0)
time.max  # time类所能表示的最大时间。time.max = time(23, 59, 59, 999999)；
time.resolution  # 时间的最小单位，这里是1微秒；
```

**方法和属性**

```python
import datetime

t1 = datetime.time(10, 23, 15, 456)  # time对象
print(t1.hour, t1.minute, t1.second, t1.microsecond)  # 10 23 14 456
t1.tzinfo  # 时区信息

t2 = t1.replace([hour[, minute[, second[, microsecond[, tzinfo]]]]])  # 创建一个新的时间对象，用参数指定的时、分、秒、微秒代替原有对象中的属性（原有对象仍保持不变）

t1.isoformat()  # 返回型如"HH:MM:SS"格式的字符串表示

t1.strftime(fmt)  # 同time模块中的strftime()
```

#### datetime类

datetime相当于date和time结合起来。
**datetime.datetime (year, month, day[ , hour[ , minute[ , second[ , microsecond[ , tzinfo] ] ] ] ] )**

**静态方法和字段**

```python
from datetime import *

datetime.today()  # 返回一个表示当前本地时间的datetime对象；
datetime.now([tz])  # 返回一个表示当前本地时间的datetime对象，如果提供了参数tz，则获取tz参数所指时区的本地时间

datetime.utcnow()  # 返回一个当前utc时间的datetime对象；#格林威治时间

datetime.fromtimestamp(timestamp[, tz])  # 根据时间戮创建一个datetime对象，参数tz指定时区信息
datetime.utcfromtimestamp(timestamp)  # 根据时间戮创建一个datetime对象

datetime.combine(date, time)  # 根据date和time，创建一个datetime对象

datetime.strptime(date_string, format)  # 将格式字符串转换为datetime对象
```

**方法和属性**

```python
import datetime

dt = datetime.datetime.now()  # datetime对象
dt.year, month, day, hour, minute, second, microsecond, tzinfo  # 
dt.date()  # 获取date对象；
dt.time()  # 获取time对象；
dt1 = dt.replace([year[, month[, day[, hour[, minute[, second[, microsecond[, tzinfo]]]]]]]])  # 创建一个新的datetime对象，用参数代替原有对象中的属性（原有对象仍保持不变）
dt.timetuple()  # 返回日期对应的time.struct_time(时间元组)对象
dt.utctimetuple()
dt.toordinal()
dt.weekday()  
dt.isocalendar()  # 返回格式如(year，month，day)的元组；
dt.isoformat([ sep] )
dt.ctime()  # 返回一个日期时间的C格式字符串，等效于time.ctime(time.mktime(dt.timetuple()))；
dt.strftime(format)  # 同上strftime()
```

#### timedelta类

使用timedelta可以很方便的在日期上做天days，小时hour，分钟，秒，毫秒，微妙的时间计算。

```python
import datetime

dt = datetime.datetime.now()

dt1 = dt + datetime.timedelta(days=-1)  # 昨天
dt2 = dt + datetime.timedelta(days=0)  # 今天
dt3 = dt + datetime.timedelta(days=1)  # 明天
print(dt1, dt2, dt3)
# 2021-02-14 19:58:10.528188 2021-02-15 19:58:10.528188 2021-02-16 19:58:10.528188
```

### Calendar模块

#### calendar()

**calendar(year, w=2, l=1, c=6)**返回一个多行字符串格式的**year年年历**，3个月一行，**间隔距离为c**。 每日**宽度间隔为w字符**。每行长度为21* W+18+2* C。**l是每星期行数**。

**实例**

```python
import calendar

print(calendar.calendar(2021))
'''
 2021

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
             1  2  3       1  2  3  4  5  6  7       1  2  3  4  5  6  7
 4  5  6  7  8  9 10       8  9 10 11 12 13 14       8  9 10 11 12 13 14
11 12 13 14 15 16 17      15 16 17 18 19 20 21      15 16 17 18 19 20 21
18 19 20 21 22 23 24      22 23 24 25 26 27 28      22 23 24 25 26 27 28
25 26 27 28 29 30 31                                29 30 31
………………
'''
```

#### firstweekday( )

**firstweekday( )**返回**当前每周起始日期的设置**。默认情况下，首次载入caendar模块时返回**0**，即**星期一**

**实例**

```python
import calendar

print(calendar.firstweekday())  # 0
```

#### isleap()

**isleap(year)**是**闰年返回 True**，**否则为 false**。

**实例**

```python
import calendar

print(calendar.isleap(2020))  # True
```

#### leapdays()

**leapdays(y1,y2)**返回在Y1，Y2**两年之间的闰年总数**。

**实例**

```python
import calendar

print(calendar.leapdays(1999, 2021))  # 6
```

#### month()

**month(year,month,w=2,l=1)**返回一个多行字符串格式的**year年month月日历**，两行标题，一周一行。每日宽度间隔为w字符。每行的长度为7* w+6。l是每星期的行数。

**实例**

```python
import calendar

print(calendar.month(2021,2))
'''
   February 2021
Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
'''
```

#### monthcalendar()

**monthcalendar(year,month)**返回一个**整数的单层嵌套列表**。每个子列表装载**代表一个星期的整数**。Year年month月外的日期都设为0;范围内的日子都由该月第几日表示，从1开始。

**实例**

```python
import calendar

print(calendar.monthcalendar(2021,2))
# [[1, 2, 3, 4, 5, 6, 7], [8, 9, 10, 11, 12, 13, 14], [15, 16, 17, 18, 19, 20, 21], [22, 23, 24, 25, 26, 27, 28]]
```

#### monthrange()

**monthrange(year,month)**返回**两个整数**。第一个是**该月的星期几**，第二个是**该月有几天**。星期几是从0（星期一）到 6（星期日）

**实例**

```python
import calendar

print(calendar.monthrange(2021,2))  # (0, 28)
```

#### prcal()

**prcal(year, w=0, l=0, c=6, m=3)**相当于 **print (calendar.calendar(year, w=0, l=0, c=6, m=3))**。

**实例**

```python
import calendar

print(calendar.prcal(2021))
'''
 2021

      January                   February                   March
Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su      Mo Tu We Th Fr Sa Su
             1  2  3       1  2  3  4  5  6  7       1  2  3  4  5  6  7
 4  5  6  7  8  9 10       8  9 10 11 12 13 14       8  9 10 11 12 13 14
11 12 13 14 15 16 17      15 16 17 18 19 20 21      15 16 17 18 19 20 21
18 19 20 21 22 23 24      22 23 24 25 26 27 28      22 23 24 25 26 27 28
25 26 27 28 29 30 31                                29 30 31
………………
'''
```

#### prmonth()

**prmonth(theyear, themonth, w=0, l=0)**相当于 **print(calendar.month(theyear, themonth, w=0, l=0))**

**实例**

```python
import calendar

print(calendar.prmonth(2021,2))
'''
   February 2021
Mo Tu We Th Fr Sa Su
 1  2  3  4  5  6  7
 8  9 10 11 12 13 14
15 16 17 18 19 20 21
22 23 24 25 26 27 28
'''
```

#### setfirstweekday()

**setfirstweekday(weekday)**设置每周的起始日期码。0（星期一）到6（星期日）

#### timegm()

**timegm(tupletime)**和time.gmtime相反：接受一个时间元组形式，返回该时刻的时间戳（1970纪元后经过的浮点秒数）。

#### weekday()

**weekday(year,month,day)**返回给定日期的日期码。0（星期一）到6（星期日）。月份为 1（一月） 到 12（12月）。

## 正则表达式

**re 模块**使 Python 语言拥有全部的正则表达式功能。

### re库的函数

#### match()

**re.match()** 尝试**从字符串的起始位置匹配一个模式**，返回一个**匹配的对象**，如果**不是起始位置匹配成功的话，match()就返回None**。

**语法**

```python
re.match(pattern, string, flags=0)
# pattern : 匹配的正则表达式 
# string : 要匹配的字符串
# flags : 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等（正则表达式修饰符）

# 可以使用group(num)或则groups()匹配对象函数来获取匹配表达式
# group(num=0)	匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。
# groups()	返回一个包含所有小组字符串的元组，从 1 到 所含的小组号
```

**实例**

```python
import re

print(re.match('www', 'www.baidu.com').span())  # 在起始位置匹配 (0, 3)
print(re.match('com', 'www.runoob.com'))  # 不在起始位置匹配 None

line = "Cats are smarter than dogs"
# .* 表示任意匹配除换行符（\n、\r）之外的任何单个或多个字符
# (.*?) 表示"非贪婪"模式，只保存第一个匹配到的子串
matchObj = re.match( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if matchObj:
   print(matchObj.group())  # Cats are smarter than dogs
   print(matchObj.group(1))  # Cats
   print(matchObj.group(2))  # smarter
else:
   print ("No match!!")
```

#### search()

**re.search()扫描整个字符串并返回第一个成功的匹配**。

**语法**

```python
re.search(pattern, string, flags=0)
# pattern : 匹配的正则表达式 
# string : 要匹配的字符串
# flags : 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等（正则表达式修饰符）

# 可以使用group(num)或则groups()匹配对象函数来获取匹配表达式
# group(num=0)	匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。
# groups()	返回一个包含所有小组字符串的元组，从 1 到 所含的小组号
```

**实例**

```python
import re
 
print(re.search('www', 'www.runoob.com').span())  # 在起始位置匹配 (0, 3)
print(re.search('com', 'www.runoob.com').span())  # 不在起始位置匹配 (11, 14)

line = "Cats are smarter than dogs"
searchObj = re.search( r'(.*) are (.*?) .*', line, re.M|re.I)
 
if searchObj:
   print ("searchObj.group() : ", searchObj.group())  # Cats are smarter than dogs
   print ("searchObj.group(1) : ", searchObj.group(1))  # Cats 
   print ("searchObj.group(2) : ", searchObj.group(2))  # smarter
else:
   print ("Nothing found!!")
```

#### sub()

**re.sub()**用于**替换字符串中的匹配项**

**语法**

```python
re.sub(pattern, repl, string, count=0, flags=0)
# pattern : 正则中的模式字符串。
# repl : 替换的字符串，也可为一个函数。
# string : 要被查找替换的原始字符串。
# count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。
# flags : 编译时用的匹配模式，数字形式。
# 前三个为必选参数，后两个为可选参数
```

**实例**

```python
import re
 
phone = "2004-959-559 # 这是一个电话号码"
 
# 删除注释
num = re.sub(r'#.*$', "", phone)
print ("电话号码 : ", num)  # 电话号码 :  2004-959-559
 
# 移除非数字的内容
num = re.sub(r'\D', "", phone)
print ("电话号码 : ", num)  # 电话号码 :  2004959559
```

**repl参数可以是函数**

```python
import re
 
# 将匹配的数字乘于 2
def double(matched):
    value = int(matched.group('value'))
    return str(value * 2)
 
s = 'A23G4HFD567'
print(re.sub('(?P<value>\d+)', double, s))  # A46G8HFD1134
```

#### compile()

**re.compile()**用于**编译正则表达式**，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用

**语法**

```python
re.compile(pattern[, flags])
# pattern : 一个字符串形式的正则表达式
# flags 可选，表示匹配模式，比如忽略大小写，多行模式等,具体见正则表达式修饰符
```

**实例**

```python
import re

pattern = re.compile('\\d+')  # 至少匹配一个数字

m = pattern.match('one12twothree34four', 3, 10) # 从'1'的位置开始匹配，正好匹配

m.group(0)   # '12'
m.start(0)   # 3
m.end(0)     # 5
m.span(0)    # (3, 5)

# group([group1, …]) 方法用于获得一个或多个分组匹配的字符串，当要获得整个匹配的子串时，可直接使用 group() 或 group(0)；
# start([group]) 方法用于获取分组匹配的子串在整个字符串中的起始位置（子串第一个字符的索引），参数默认值为 0；
# end([group]) 方法用于获取分组匹配的子串在整个字符串中的结束位置（子串最后一个字符的索引+1），参数默认值为 0；
# span([group]) 方法返回 (start(group), end(group))。
```

#### findall()

**re.findall()**字符串中**找到正则表达式所匹配的所有子串**，并返回一个列表，如果没有找到匹配的，则返回空列表

**语法**

```python
re.findall(pattern, string, flags=0)

pattern.findall(string[, pos[, endpos]])

# pattern 匹配模式。
# string 待匹配的字符串。
# pos 可选参数，指定字符串的起始位置，默认为 0。
# endpos 可选参数，指定字符串的结束位置，默认为字符串的长度。
```

**实例**

```python
import re
 
result1 = re.findall(r'\d+','runoob 123 google 456')
 
pattern = re.compile(r'\d+')   # 查找数字
result2 = pattern.findall('runoob 123 google 456')
result3 = pattern.findall('run88oob123google456', 0, 10)
 
print(result1)  # ['123', '456']
print(result2)  # ['123', '456']
print(result3)  # ['88', '12']
```

#### finditer()

和 findall 类似，在字符串中**找到正则表达式所匹配的所有子串**，并把它们作为一个**迭代器**返回

**语法**

```python
re.finditer(pattern, string, flags=0)
# pattern : 匹配的正则表达式 
# string : 要匹配的字符串
# flags : 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等（正则表达式修饰符）
```

**实例**

```python
import re
 
it = re.finditer(r"\d+","12a32bc43jf3") 
for match in it: 
    print (match.group())
'''
12 
32 
43 
3
'''
```

#### spilt()

**re.split()**方法**按照能够匹配的子串将字符串分割**后返回列表

**语法**

```python
re.split(pattern, string[, maxsplit=0, flags=0])
# pattern :  匹配的正则表达式
# string : 要匹配的字符串。
# maxsplit : 分隔次数，maxsplit=1 分隔一次，默认为 0，不限制次数。
# flags	: 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：正则表达式修饰符 - 可选标志
```

**实例**

```python
import re

list1 = re.split(r'\W+', 'runoob, runoob, runoob.')
print(list1)  # ['runoob', 'runoob', 'runoob', '']
```



### 正则表达式对象

#### re.RegexObject

re.compile() 返回 RegexObject 对象。

#### re.MatchObject

group() 返回被 RE 匹配的字符串。

- **start()** 返回匹配开始的位置
- **end()** 返回匹配结束的位置
- **span()** 返回一个元组包含匹配 (开始,结束) 的位置

### 正则表达式修饰符

正则表达式可以包含一些可选标志修饰符来控制匹配的模式。修饰符被指定为一个可选的标志。多个标志可以通过按位 OR(|) 它们来指定。

| 修饰符 | 描述                                                         |
| :----- | :----------------------------------------------------------- |
| re.I   | 使匹配对大小写不敏感                                         |
| re.L   | 做本地化识别（locale-aware）匹配                             |
| re.M   | 多行匹配，影响 ^ 和 $                                        |
| re.S   | 使 . 匹配包括换行在内的所有字符                              |
| re.U   | 根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.      |
| re.X   | 该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。 |

## JSON & XML

### JSON

**JSON(JavaScript Object Notation, JavaScript对象表示法)**

JSON 是存储和交换文本信息的语法

**JSON的两种数据结构类型**：**键值对的集合**、**值的有序列表**

**Python 编码为 JSON 类型转换对应表：**

| Python                                 | JSON   |
| :------------------------------------- | :----- |
| dict                                   | object |
| list, tuple                            | array  |
| str                                    | string |
| int, float, int- & float-derived Enums | number |
| True                                   | true   |
| False                                  | false  |
| None                                   | null   |

Python3 中可以使用 **json 模块**来对 JSON 数据进行编解码，它包含了两个函数：

- **json.dumps():** 对数据进行编码。
- **json.loads():** 对数据进行解码。

**实例**

```python
import json

# Python 字典类型转换为 JSON 对象
data1 = {
    'No' : 1,
    'name' : 'Test',
    'url' : 'Just Code It !'
}
 
json_str = json.dumps(data1)
print ("Python 原始数据：", repr(data1))
print ("JSON 对象：", json_str)
 
# 将 JSON 对象转换为 Python 字典
data2 = json.loads(json_str)
print ("data2['name']: ", data2['name'])
print ("data2['url']: ", data2['url'])
```

如果**处理的是文件而不是字符串**，可以使用 **json.dump()** 和 **json.load()** 来编码和解码JSON数据。

**实例**

```python
import json

# 写入 JSON 数据
with open('data.json', 'w') as f:
    json.dump(data, f)
 
# 读取数据
with open('data.json', 'r') as f:
    data = json.load(f)
```

### XML解析

XML 指可扩展标记语言(e**X**tensible **M**arkup **L**anguage)

XML 被设计用来传输和存储数据

**Python 对 XML 的解析**

常见的 XML 编程接口有 DOM 和 SAX，这两种接口处理 XML 文件的方式不同，当然使用场合也不同。

Python 有三种方法解析 XML，SAX，DOM，以及 ElementTree:

**1.SAX (simple API for XML )**

Python 标准库包含 SAX 解析器，SAX 用事件驱动模型，通过在解析 XML 的过程中触发一个个的事件并调用用户定义的回调函数来处理 XML 文件。

**2.DOM(Document Object Model)**

将 XML 数据在内存中解析成一个树，通过对树的操作来操作 XML。

#### 使用SAX解析xml

在 Python 中使用 sax 方式处理 xml 要先引入 xml.sax 中的 parse 函数，还有 xml.sax.handler 中的 ContentHandler

##### ContentHandler 类的方法

| 方法名                        | 功能                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| **characters(content)**       | 调用时机：**①**从行开始，遇到标签之前，存在字符，content 的值为这些字符串。**②**从一个标签，遇到下一个标签之前， 存在字符，content 的值为这些字符串。**③**从一个标签，遇到行结束符之前，存在字符，content 的值为这些字符串。标签可以是开始标签，也可以是结束标签。 |
| **startDocument()**           | SAX解析器在文档解析时启动调用                                |
| **endDocument()**             | SAX解析器在解析到文档结尾时调用                              |
| **startElement(name, attrs)** | 遇到XML开始标签时调用，name 是标签的名字，attrs 是标签的属性值字典 |
| **endElement(name)**          | 遇到XML结束标签时调用，name时标签的名字                      |

##### SAX相关函数 

**make_parser 方法**

以下方法创建一个新的解析器对象并返回。

```python
xml.sax.make_parser( [parser_list] )
# parser_list : 可选参数，解析器列表
```

------

**parser 方法**

以下方法创建一个 SAX 解析器并解析xml文档：

```python
xml.sax.parse( xmlfile, contenthandler[, errorhandler])
# xmlfile : xml文件名
# contenthandler : 必须是一个 ContentHandler 的对象
# errorhandler : 如果指定该参数，errorhandler 必须是一个 SAX ErrorHandler 对象
```

------

**parseString 方法**

parseString 方法创建一个 XML 解析器并解析 xml 字符串：

```python
xml.sax.parseString(xmlstring, contenthandler[, errorhandler])
# xmlstring : xml字符串
# contenthandler : 必须是一个 ContentHandler 的对象
# errorhandler : 如果指定该参数，errorhandler 必须是一个 SAX ErrorHandler对象
```

**实例**

```python
import xml.sax


class MovieHandler(xml.sax.ContentHandler):
    def __init__(self):
        self.CurrentDate = ""
        self.type = ""
        self.format = ""
        self.year = ""
        self.rating = ""
        self.stars = ""
        self.description = ""

    # 元素开始调用
    def startElement(self, tag, attributes):
        self.CurrentData = tag
        if tag == "movie":
            print("*****Movie*****")
            title = attributes["title"]
            print("Title:", title)

    # 元素结束调用
    def endElement(self, tag):
        if self.CurrentData == "type":
            print("Type:", self.type)
        elif self.CurrentData == "format":
            print("Format:", self.format)
        elif self.CurrentData == "year":
            print("Year:", self.year)
        elif self.CurrentData == "rating":
            print("Rating:", self.rating)
        elif self.CurrentData == "stars":
            print("Stars:", self.stars)
        elif self.CurrentData == "description":
            print("Description:", self.description)
        self.CurrentData = ""

    # 读取字符时调用
    def characters(self, content):
        if self.CurrentData == "type":
            self.type = content
        elif self.CurrentData == "format":
            self.format = content
        elif self.CurrentData == "year":
            self.year = content
        elif self.CurrentData == "rating":
            self.rating = content
        elif self.CurrentData == "stars":
            self.stars = content
        elif self.CurrentData == "description":
            self.description = content


if __name__ == '__main__':
    # 创建一个 XMLReader
    parser = xml.sax.make_parser()
    # 关闭命名空间
    parser.setFeature(xml.sax.handler.feature_namespaces, 0)

    # 重写 ContextHandler
    Handler = MovieHandler()
    parser.setContentHandler(Handler)

    parser.parse("movie.xml")
```

#### 使用DOM解析xml

**实例**

```python
from xml.dom.minidom import parse


if __name__ == '__main__':
    # 使用mindom解析器打开xml文档
    DOMTree = parse('movie.xml')
    collection = DOMTree.documentElement
    
    if collection.hasAttribute('shelf'):
        print("Root element : %s" % collection.getAttribute("shelf"))

    # 在集合照片获取所有电影
    movies = collection.getElementsByTagName('movie')

    for movie in movies:
        print("*****Movie*****")
        if movie.hasAttribute("title"):
            print("Title: %s" % movie.getAttribute("title"))

        type = movie.getElementsByTagName('type')[0]
        print( type.nodeName + ':'+type.childNodes[0].data)  # nodeName:节点名称

        format = movie.getElementsByTagName('format')[0]
        print("Format: %s" % format.childNodes[0].data)

        rating = movie.getElementsByTagName('rating')[0]
        print("Rating: %s" % rating.childNodes[0].data)

        description = movie.getElementsByTagName('description')[0]
        print("Description: %s" % description.childNodes[0].data)
```

## 多线程

多线程类似于同时执行多个不同程序，多线程运行有如下优点：

- 使用线程可以把占据长时间的程序中的任务放到后台去处理。
- 用户界面可以更加吸引人，比如用户点击了一个按钮去触发某些事件的处理，可以弹出一个进度条来显示处理的进度。
- 程序的运行速度可能加快。
- 在一些等待的任务实现上如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下我们可以释放一些珍贵的资源如内存占用等等。

线程可以分为:

- **内核线程：**由操作系统内核创建和撤销。
- **用户线程：**不需要内核支持而在用户程序中实现的线程。

Python3 线程中常用的两个模块为：

- **_thread**
- **threading**（推荐使用）

### threading模块

**threading相关函数**

| 函数                   | 功能                                                         |
| ---------------------- | ------------------------------------------------------------ |
| **active_count()**     | 返回**当前活动的线程对象的数量**                             |
| **current_thread()**   | 返回**当前线程对象**                                         |
| **get_ident()**        | 返回**当前线程的ID**,这是一个非零整数                        |
| **enumerate()**        | 枚举函数，返回**当前活动的所有线程对象**（列表形式）         |
| **main_thread()**      | 返回**主线程对象**。在正常情况下，主线程时python解释器启动的线程 |
| **settrace(func)**     | 为从线程模块启动的所有线程**设置跟踪功能**。func参数为自定义函数名 |
| **setprofile(func)**   | 为从线程模块启动的所有线程**设置配置文件功能**。func参数为自定义函数名 |
| **stack_size([size])** | 返回**创建新线程时使用的线程堆栈大小**。size可选参数可以设置0~32768(32kb)范围的数值，默认为0 |

threading提供**TIMEOUT_MAX**常量，当**Lock.acquire()、RLock.acquire()、Condition.wait()**等方法超过这个数值，会抛出**OverflowErro**r异常错误信息

#### Thread类（线程对象）

Thread类通过调用用户指定函数func，用于独立生成一个活动的线程。

**调用用户指定函数func**，有两种方法：

- 在**Thread创建实例对象**时，把**func以参数形式传递给构造函数**
- 通过**继承Thread类**，并**重写run()方法**，**调用func函数**，只能重写init()与run()方法

**Thread类以构造函数调用形式如下**：

```python
Thread(group=None, target=None, name=None, args=(), kwargs={}, *, daemon=None)
# group : 用于保留，作为将来可扩展的功能，可忽略
# target : 设置线程需要执行的自定义函数func，设置完成后，run()被调用；target=None线程不执行任何操作
# name : 指定需要执行的线程名称。
# args : 当自定义函数func带有参数时，把参数以元组形式通过args传递给func
# kwargs : 当自定义函数func带有参数时，把参数以字典形式通过kwargs传递给func
# daemon : 当daemon不是None，通过设置(True或False)确定是否守护线程；当daemon-None时，守护线程属性会继承父线程（主线程默认情况下为非守护线程）
```

**Thred类的主要方法**

| 方法                     | 功能                                                         |
| ------------------------ | ------------------------------------------------------------ |
| **start()**              | **线程启动状态**(一个线程对象只能调用一次该方法)，该方法必须在run()方法前调用 |
| **run()**                | **运行线程**，使线程处于活动状态；在run()方法里执行指定的用户自定义函数func |
| **join([timeout=None])** | **阻塞调用线程**。等待调用该方法的线程对象运行，一直到该线程执行终止，阻塞才释放。timeout为可选参数，可以设置阻塞时间，不存在时或为None，该操作阻塞，知道线程终止 |
| **is_alive()**           | 返回**线程是否活动的**                                       |
| **getName()**            | **返回线程名**                                               |
| **setName()**            | **设置线程名**                                               |
| **setDaemon()**          | **设置守护线程(True/False)**                                 |

**Thread类的属性**

| 属性       | 功能                                                         |
| ---------- | ------------------------------------------------------------ |
| **daemon** | 显示**此线程是否为守护线程**（True/False）。必须在start()之前设置 |
| **name**   | **线程名称**                                                 |
| **ident**  | **线程的ID号**，若线程未启动，则为None;启动后为非零整数      |

**实例**

```python
import threading
import time


exitFlag = 0

# 继承Thread类，重写init()与run()
class myThread(threading.Thread):
    def __init__(self, threadID, name, counter):
        threading.Thread.__init__(self)
        self.threadID = threadID
        self.name = name
        self.counter = counter

    def run(self):
        print("开始线程：" + self.name)
        print_time(self.name, self.counter, 5)
        print("退出线程：" + self.name)


def print_time(threadName, delay, counter):
    while counter:
        if exitFlag:
            threadName.exit()
        time.sleep(delay)
        print("%s: %s" % (threadName, time.ctime(time.time())))
        counter -= 1


# 创建新线程
thread1 = myThread(1, "Thread-1", 1)
thread2 = myThread(2, "Thread-2", 2)

# 开启新线程
thread1.start()
thread2.start()
thread1.join()
thread2.join()
print("退出主线程")
```

#### Lock类（锁对象）

当锁在被锁定时，它并不属于某一个特定的线程。

锁只有“**锁定**”和“**非锁定**”两种状态，**当锁被创建时，是处于“非锁定”状态的**。当**锁已经被锁定**时，**再次调用acquire()方法会被阻塞执行**，直到**锁被调用release()方法释放掉锁并将其状态改为“非锁定”**

**Lock类的方法：**

- **acquire(blocking=True, timeout=-1)** : 获取锁，并将**锁的状态改为“锁定”**，成功返回True，失败返回False。当**一个线程获得锁时，会阻塞其他尝试获取锁的线程，直到这个锁被释放掉**。timeout默认值为**-1**，即**将无限阻塞等待直到获得锁**，如果设为其他的值时（单位为秒的浮点数），将**最多阻塞等待timeout指定的秒数**。当**blocking为False**时，**timeout参数被忽略**，即没有获得锁也不进行阻塞。
- **release()** : **释放一个锁，并将其状态改为“非锁定**”，需要注意的是**任何线程都可以释放锁**，不只是获得锁的线程。**release()**方法只能在**锁处于“锁定”状态时调用**，如果**在“非锁定”状态时调用则会报RuntimeError错误**

**使用锁实现线程同步的实例：**

```python
import threading
import time

lock = threading.Lock()

global_resource = [None] * 5


def change_resource(para, sleep):
    lock.acquire()
    # 不加锁，会使后面的输出元素混乱
    global global_resource
    for i in range(len(global_resource)):
        global_resource[i] = para
        time.sleep(sleep)
    print('修改全局变量：', global_resource)

    lock.release()


if __name__ == '__main__':
    thread_hi = threading.Thread(target=change_resource, args=('hi', 2))
    thread_hello = threading.Thread(target=change_resource, args=('hello', 1))
    thread_hi.start()
    thread_hello.start()
'''
修改全局变量： ['hi', 'hi', 'hi', 'hi', 'hi']
修改全局变量： ['hello', 'hello', 'hello', 'hello', 'hello']
'''
```

#### RLock类（递归锁对象）

递归锁和普通锁的差别在于加入了**“所属线程”和“递归等级”**的概念，释放锁必须有获取锁的线程来进行释放，同时，同一个线程在释放锁之前再次获取锁将不会阻塞当前线程，只是在**锁的递归等级上加了1**（获得锁时的初始递归等级为1）。

使用普通锁时，对于一些可能**造成死锁的情况，可以考虑使用递归锁来解决。**

**Rlock类的方法:**

- **acquire(blocking=True, timeout=-1)：**与普通锁的不同之处在于：**当使用默认值时，如果这个线程已经拥有锁，那么锁的递归等级加1**。线程获得锁时，该锁的递归等级被**初始化为1**。当**多个线程被阻塞**时，只有**一个线程能在锁被解时获得锁**，这种情况下，**acquire()是没有返回值的**。
- **release()：**没有返回值，**调用一次则递归等级减1**，**递归等级为零时表示这个线程的锁已经被释放掉**，其他线程可以获取锁了。可能在一个线程中调用了多次acquire()，导致锁的递归等级大于了1，那么就需要调用对应次数的release()来完全释放锁，并将**它的递归等级减到零，其他的线程才能获取锁，不然就会一直被阻塞着**

**递归锁实例：**

```python
import threading
import time

# 使用成一个递归锁就可以解决当前这种死锁情况
rlock_hi = rlock_hello = threading.RLock()


def test_thread_hi():
    # 初始时锁内部的递归等级为1
    rlock_hi.acquire()
    print('线程test_thread_hi获得了锁rlock_hi')
    time.sleep(2)
    # 如果再次获取同样一把锁，则不会阻塞，只是内部的递归等级加1
    rlock_hello.acquire()
    print('线程test_thread_hi获得了锁rlock_hello')
    # 释放一次锁，内部递归等级减1
    rlock_hello.release()
    # 这里再次减，当递归等级为0时，其他线程才可获取到此锁
    rlock_hi.release()


def test_thread_hello():
    rlock_hello.acquire()
    print('线程test_thread_hello获得了锁rlock_hello')
    time.sleep(2)
    rlock_hi.acquire()
    print('线程test_thread_hello获得了锁rlock_hi')
    rlock_hi.release()
    rlock_hello.release()


if __name__ == '__main__':
    thread_hi = threading.Thread(target=test_thread_hi)
    thread_hello = threading.Thread(target=test_thread_hello)
    thread_hi.start()
    thread_hello.start()
'''
线程test_thread_hi获得了锁rlock_hi
线程test_thread_hi获得了锁rlock_hello
线程test_thread_hello获得了锁rlock_hello
线程test_thread_hello获得了锁rlock_hi
'''
```

#### Condition类(条件变量对象)

**Condition类的方法:**

- **acquire(\*args)**：**请求底层锁**。此方法调用底层锁对应的方法和返回对应方法的返回值。
- **release()**：**释放底层锁**。此方法调用底层所对应的方法，没有返回值。
- **wait(timeout=None)**：**释放锁**，**等待直到被通知（再获取锁）或者发生超时事件**。如果**线程在调用此方法时本身并没有锁**（即线程首先得有锁），则会报**RuntimeError错误**。这个方法**释放底层锁，然后阻塞线程**，直到另一个线程中的同一个条件变量**使用notify()或notify_all()唤醒**，**或者超时事件发生**，一旦被唤醒或者超时，则会重新去获取锁并返回（成功返回True，否则返回False）。timeout参数为浮点类型的秒数。在RLock中使用一次release方法，可能并不能释放锁，因为锁可能被acquire()了多次，但是在条件变量对象中，它调用了RLock类的内部方法，可以一次就完全释放锁，重新获取锁时也会重置锁的递归等级。
- **wait_for(predicate, timeout=None)：**与wait方法相似，**等待，直到条件计算为True，返回最后一次的predicate的返回值**。**predicate参数为一个返回值为布尔值的可调用对象**。调用此方法的时候会先调用predicate对象，如果返回的就是True，则不会释放锁，直接往后执行。另一个线程通知后，在它释放锁时，才会触发wait_for方法等待事件，这时如果predicate结果为True，则尝试获取锁，获取成功后则继续往后执行，如果为False，则会一直阻塞下去。此方法如果忽略timeout参数，就相当于：while not predicate(): condition_lock.wait()。
- **notify(n=1)**：**唤醒一个等待这个条件的线程**，如果调用这个方法的线程在没有获得锁的情况下调用这个方法，会报RuntimeError错误。默认唤醒一个线程，可以通过参数n设置唤醒n个正在等待这个条件变量的线程，如果没有线程在等待，调用这个方法不会发生任何事。如果等待的线程中正好有n个线程，那么这个方法可以准确的唤醒这n个线程，但是等待的线程超过指定的n个，有时候可能会唤醒超过n个的线程，所以依赖参数n是不安全的行为。
- **notify_all()**：**唤醒所有等待这个条件的线程**。这个方法与notify()不同之处在于它唤醒所有线程，而不是特定n个。

**条件变量实例：**

```python
import threading
import time

condition_lock = threading.Condition()
PRE = 0


def pre():
    print(PRE)
    return PRE


def test_thread_hi():
    # 在使用wait/wait_for之前必须线获得锁
    condition_lock.acquire()

    print('等待线程test_thread_hello的通知')
    # 先执行一次pre，返回False后释放掉锁，等另一个线程释放掉锁后再次执行pre，返回True后再次获取锁
    # wait_for的返回值不是True和False，而是predicate参数的返回值
    condition_lock.wait_for(pre)
    print('继续执行')

    # 使用wait/wait_for之后要释放锁
    condition_lock.release()


def test_thread_hello():
    time.sleep(1)
    condition_lock.acquire()
    global PRE
    PRE = 1
    print('修改PRE值为1')

    print('通知线程test_thread_hi可以准备获取锁了')
    condition_lock.notify()

    # 先notify/notify_all之后在释放锁
    condition_lock.release()
    print('你获取锁吧')


if __name__ == '__main__':
    thread_hi = threading.Thread(target=test_thread_hi)
    thread_hello = threading.Thread(target=test_thread_hello)
    thread_hi.start()
    thread_hello.start()
'''
等待线程test_thread_hello的通知
0
修改PRE值为1
通知线程test_thread_hi可以准备获取锁了
你获取锁吧
1
继续执行
'''
```

#### Event类(事件对象)

如果**一个或多个线程需要知道另一个线程的某个状态才能进行下一步的操作**，就可以使用线程的**event事件对象**来处理。

一个事件对象管理一个内部标志，初始状态默认为False。

**Event类的方法:**

- **is_set()**：当**内部标志为True时返回True**。
- **set()**：**设置内部标志为True**。此时**所有等待中的线程将被唤醒**，调用**wait()方法的线程将不会被阻塞**。
- **clear()**：将**内部标志设置为False**。所有**调用wait()方法的线程将被阻塞**，直到**调用set()方法将内部标志设置为True**。
- **wait(timeout=None)**：**阻塞线程直到内部标志为True**，或者**发生超时事件**。如果调用时内部标志就是True，那么不会被阻塞，否则将被阻塞。timeout为浮点类型的秒数。

**事件对象实例：**

```python
import threading
import time

event = threading.Event()


def student_exam(student_id):
    print('学生%s等待监考老师发卷。。。' % student_id)
    event.wait()
    print('开始考试了')


def invigilate_teacher():
    time.sleep(5)
    print('考试时间到，学生们可以开始考试了！')
    # 设置内部标志位True，并唤醒所有等待的线程
    event.set()


if __name__ == '__main__':
    for student_id in range(3):
        threading.Thread(target=student_exam, args=(student_id,)).start()
    threading.Thread(target=invigilate_teacher).start()
'''
学生0等待监考老师发卷。。。
学生1等待监考老师发卷。。。
学生2等待监考老师发卷。。。
考试时间到，学生们可以开始考试了！
开始考试了
开始考试了
开始考试了
'''
```

#### Timer类(定时器对象)

表示**一个操作需要在等待一定时间之后执行**，相当于一个定时器。Timer类是**threading.Thread的子类**，所以它可以像**一个自定义线程一样工作**。

和线程一样，可以通过**start()方法启动定时器**，在定时器计时结束之前（线程开启之前）可以使用**cancel()方法停止计时器**。计时器等待的时间可能与用户设置的时间不完全一样。

**Timer类以构造函数调用形式如下**

```python
threading.Timer(interval, function, args=None, kwargs=None)
# interval : 间隔时间，即定时器秒数。
# function : 执行的函数。
# args : 传入function的参数，如果为None，则会传入一个空列表。
# kwargs : 传入function的关键字参数，如果为None，则会传入一个空字典。

# 方法：cancel() 停止计时器，并取消对应函数的执行，这个方法只有在计时器还没有计时结束之前才会生效，如果已经开始执行函数，则不会生效。
```

#### Barrier类(栅栏对象)

栅栏对象**用于一个固定数量的线程**，而这些线程需要等待彼此的情况。这些线程中的每个线程都会尝试调用wait()方法，然后阻塞，直到所有线程都调用了wait()方法，然后所有线程会被同时释放。

**Barrier类以构造函数调用形式如下**

```python
threading.Barrier(parties, action=None, timeout=None)
# parties : 指定需要创建的栅栏对象的线程数。
# action : 一个可调用对象，当所有线程都被释放时，在释放前，其中一个线程（随机）会自动调用这个对象。
# timeout : 设置wait()方法的超时时间。
```

**Barrier类的方法:**

- **wait(timeout=None)：**通过栅栏。当**所有线程都调用了这个方法，则所有线程会被同时释放**。如果提供了timeout参数，那么此参数是优先于初始化方法中的timeout参数的。返回值为range(parties)中的一个整数，每个线程的返回值都不同。如果提供了action参数，那么在所有线程释放前，其中一个线程（随机）会调用这个action参数对象，并且如果这个action调用发生了异常，则栅栏对象将进入破损状态。如果wait()方法发生了超时事件，那么栅栏对象也将进入破损状态。如果栅栏对象进入破损状态或者重置栅栏对象时仍有线程在等待释放，则会报BrokenBarrierError异常。
- **reset()：**将**一个栅栏对象重置为默认的初始态**。如果此时有任何线程正在等待释放，那么将会报BrokenBarrierError异常。如果barrier中有线程的状态是未知的，那么可能需要外部的某种同步来确保线程已被释放。如果栅栏对象已经破损，那么最好是丢弃它并重新创建一个新的栅栏对象。
- **abort()：**使**栅栏对象进入破损状态**。这将导致所有已经调用和未调用的wait()方法引发BrokenBarrierError异常。比如，需要放弃一个线程，但又不想引发死锁的情况，就可以调用这个方法。一个更好的办法是提供一个合理的timeout参数值，来自动避免某个线程出错。
- **parties：**通过**栅栏的线程数量**。
- **n_waiting：**在**栅栏中正在等待的线程数量**。
- **broken：**如果**栅栏对象为破损状态则返回True**。

**栅栏对象实例：**

```python
import threading
import time


def test_action():
    print('所有栅栏线程释放前调用此函数！')


barrier = threading.Barrier(3, test_action)


def barrier_thread(sleep):
    time.sleep(sleep)
    print('barrier thread-%s wait...' % sleep)
    # 阻塞线程，直到阻塞线程数达到栅栏指定数量
    barrier.wait()
    print('barrier thread-%s end!' % sleep)


if __name__ == '__main__':
    for sleep in range(6):
        threading.Thread(target=barrier_thread, args=(sleep,)).start()
'''
barrier thread-0 wait...
barrier thread-1 wait...
barrier thread-2 wait...
所有栅栏线程释放前调用此函数！
barrier thread-2 end!
barrier thread-0 end!
barrier thread-1 end!
barrier thread-3 wait...
barrier thread-4 wait...
barrier thread-5 wait...
所有栅栏线程释放前调用此函数！
barrier thread-5 end!
barrier thread-3 end!
barrier thread-4 end!
'''
```

