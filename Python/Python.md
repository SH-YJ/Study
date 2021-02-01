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

### 断言（assert）

```python
assert  表达式
#  接下来的语句：如果为真就执行，反之会抛出AssertionError异常
```

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

```
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



## OS 文件/目录方法