# Python

## 基础

### 入门

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
    
	#r''表示''内部的字符串默认不转义
    print(r'\n')  # \n
    
	#'''''' 表示多行注释
	#单个#表示一行注释
    
	#布尔值 Ture False 开头大写
	#逻辑运算符 and or not
    #成员运算符 in  not in
    
    #del 删除
    #type() 查看数据类型
    
	# / 除法结果为浮点数
    # // 除法结果为整数
    # % 求余数
    # ** 幂运算
    print(2**3)  # 8
```

### Number (数字)

```python
	#int(x)将x转换为一个整数
    #float(x)将x转换到一个浮点数
    #complex(x)将x转换到一个复数，实数部分为 x，虚数部分为 0
    #complex(x,y)将 x 和 y 转换到一个复数，实数部分为 x，虚数部分为 y。x 和 y 是数字表达式
    #math库
     #数学常数
    	pi  3.1415
        e  自然对数
        inf  正无穷大
        nan  非浮点数标记
     #数值函数
    	fabs(x) 绝对值
        fmod(x,y)  取余数
        fsum([x,y,...])  求和
        gcd(x,y)  求最大公约数
        turnc(x)  求整数部分
        modf(x)   求小数部分和整数部分
        ceil(x)   向上取整
        floor(x)  向下取整
        factorial(x)  求阶乘
```

### String (字符串)

```python
	#字符串类型为str()
 	str1 = 'Hello World!'
    print(str1[0:5])  = Hello
	#ord()函数获取字符的整数表示
    	ord('A') = 65
    #chr()函数将编码转换为对应的字符
    	chr(66)  = 'B'
    #encode()将str()型编码为指定的bytes型
    	print('ABC'.encode('ascii')) = b'ABC'
    #decode()将bytes型变为str()型
    	print(b'ABC'.decode('ascii')) = ABC
    #len()函数计算字节数
    #Python格式化方式与c语言一致
    	# %d  整数
        # %f  浮点数
        # %s  字符串
        # %x  十六进制整数
        print('%.2f' % 3.1415926)
    #利用format()函数格式化，用传入的参数依次替换字符串内的占位符{0}、{1}
    	print('Hello, {0}, 成绩提升了 {1:.1f}%'.format('小明', 17.125)) = Hello, 小明, 成绩提升了 17.1%
```

### List (列表)

```python
	a= ['a','b','c']
    len(a) = 3
    print(a[2]) = c
    print(a[1:3]) = ['b','c']
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

### Tuple (元组)

```python
	#初始化后不能修改
	#定义tuple时元素必须确定下来
    	t=(1,2)
    #空的tuple
    	t=()
    #只有一个元素定义tuple时必须加一个,
    	t=(1,)
```

### Dict (字典)

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

### Set (集合)

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
    #两个set可作交集,并集
    	s1 = set([1, 2, 3])
	 	s2 = set([2, 3, 4])
        s1 - s2  = {1}  # 集合s1中包含而集合s2中不包含的元素
		s1 & s2  = {2, 3}  # 集合s1或s2中包含的所有元素
		s1 | s2  = {1, 2, 3, 4}  # 集合s1和s2中都包含了的元素
        s1 ^ s2  = {1, 4}  # 不同时包含于s1和s2的元素 
```

### 条件判断

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

### 循环语句

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

### 可变与不可变对象

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
