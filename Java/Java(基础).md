

# Java(基础)

## 入门

```java
//Java注释
//	1.单行注释   //
//	2.多行注释   /* */
//	3.文档注释	 /** 以* /结束

//Java标识符
//  可以由字母、数字、下划线和美元符组成，不能以数字开头，不能使Java中地关键字

//Java跨平台通用换行符 %n

/*
Java常量
  整型   有二进制、八进制、十进制、十六进制
		二进制:以0b开头
		八进制:以0开头，0~7
		十进制:0~9
		十六进制:以0x开头，0~9、A~F
  浮点型  float double
        单精度以f结尾
        双精度以d结尾
  字符  用单引号' '
        '\u0000'表示空白字符 
  字符串 用双引号" "
  布尔常量  ture和false
  null常量 表示应用对象为空
*/
    
/*
Java变量
基本数据类型
  整数类型(byte, short, int, long)
  浮点型数据(float, double) e表示以10为底的指数 +-正负指数
  字符类型(char)
  布尔类型(boolean)
*/
    
/*
Java类型转换
	1.自动类型转换
		byte b = 3;
		int  x = b;
		①整数类型之间可以实现转换
		②整数类型转换为float类型
		③其他类型转换为double类型
	2.强制类型转换
		byte b = (byte) num;
*/`
    
/*
Java运算符
  1.算数运算符(+, -, *, /, %, ++, --) 求余时，结果与左边数符号有关
  2.赋值运算符(=, +=, -=, *=, /=, %=, <<=, >>=, &=, ^=, |=)
  3.比较运算符(==, !=, <, >, <=, >=)  结果为布尔值
  4.逻辑运算符
	  与(&) 左边为false,右边依旧计算
      或(|) 一边为true为true
      非(!) 
      异或(^) 两边布尔值相同为false,不同为true 
      短路与(&&) 左边为false,右边不计算
      短路或(||) 左边为true,右边不计算
  5.位运算符
  	  ~  按位取反运算符翻转操作数的每一位，即0变成1，1变成0。a=60,~a=-61，二进制取反;
  	  << 按位左移运算符。左操作数按位左移右操作数指定的位数。
  	  >> 按位右移运算符。左操作数按位右移右操作数指定的位数。
  	  >>> 按位右移补零操作符。左操作数的值按右操作数指定的位数右移，移动得到的空位以零填充。
  6.条件运算符(?:)
  	  int a,b;
  	  a = 10;
  	  如果 a 等于 1 成立，则设置 b 为 20，否则为 30
  	  b = (a == 1) ? 20 : 30;
      输出:30
  7.instanceof 运算符
  	  该运算符用于操作对象实例，检查该对象是否是一个特定类型(类类型或接口类型)。
  	  格式:( Object reference variable ) instanceof  (class/interface type)
  	  boolean result = name instanceof String; 由于 name 是 String 类型，所以返回真
*/    
    
/*    
选择结构
 1.if条件语句
   (1)if语句
   (2)if...else语句
   (3)if...else if...else语句
 2.①switch条件语句(byte、short、int 或者 char)
 	switch(){
 		case 1:
 		default:
 	}
   ②switch对于字符串的支持(String)
    switch(){
    	case "string1":
    	case "string2":
    	default:
    }
*/

/*
循环结构
 1.while循环语句
 	while(循环条件){
 		执行语句
 		...
 	}
 2.do...while循环语句
 	do{
 		执行语句
 		...
 	}while(循环条件);
 3.for循环语句
 	for(初始表达式;循环条件;操作表达式){
 		执行语句
 		...
 	}
   数组的增强型for循环
   for(声明语句 : 表达式){
        执行语句
        ...
   }
   声明语句：声明新的局部变量，该变量的类型必须和数组元素的类型匹配。其作用域限定在循环语句块，其值与此时数组元素的值相等。
   表达式：表达式是要访问的数组名，或者是返回值为数组的方法。
 4.跳转语句(break,continue)
 	break 结束循环
 	continue  结束本次循环，进入下一次循环
*/
    
/*
Java方法(函数)
 1.方法的定义	
 	修饰符 返回值类型 方法名 ([参数类型 参数名1，参数名称 参数名2,...]){
 		执行语句
 		...
 		return 返回值;
 	}
 	static int Get (int a){
 		return a;
 	}
 2.方法的重载
 	public static int add(int x,int y){
 		return x + y;
 	}
 	public static int add(int x,int y,int z){
 		return x + y + z;
 	}
 	public static double add(double x,double y){
 		return x + y;
 	}
 3.构造方法
 	当一个对象被创建时候，构造方法用来初始化该对象。构造方法和它所在类的名字相同，但构造方法没有返回值。
 	通常会使用构造方法给一个类的实例变量赋初值，或者执行其它必要的步骤来创建一个完整的对象。
 4.可变参数
 	typeName... parameterName
 	一个方法中只能指定一个可变参数，它必须是方法的最后一个参数。任何普通的参数必须在它之前声明。
 	public static void printMax( double... numbers) {
 	}
 5.finalize() 方法
 	它在对象被垃圾收集器析构(回收)之前调用,用来清除回收对象。
 	使用 finalize() 来确保一个对象打开的文件被关闭了。
 	protected void finalize()
	{
   		// 在这里终结代码
	}
 	System.gc(); //调用Java垃圾收集器
*/
 
/*
Java数组
 1.数组定义
 	int[] x = new int[100];
 	初始化
 	int[] x = new int[]{1,2,3,4,5,......};
    int[] x = {1,2,3,4,5,......};
 2.多维数组
 	int[][] arr = new int[3][4];
 	int[][] arr = new int[3][];
 	int[][] arr = {{1,2},{3,4,5,6},{7,8,9}};
*/    
```

## Java语言支持的转义字符

| 符号   | 字符定义                 |
| ------ | ------------------------ |
| \n     | 换行 (0x0a)              |
| \r     | 回车 (0x0d)              |
| \f     | 换页符(0x0c)             |
| \b     | 退格 (0x08)              |
| \0     | 空字符 (0x0)             |
| \s     | 空格 (0x20)              |
| \t     | 制表符                   |
| \ddd   | 八进制字符 (ddd)         |
| \uxxxx | 16进制Unicode字符 (xxxx) |

## Java修饰符

### 访问控制修饰符

- **default** (即默认，什么也不写）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。

- **private** : 在同一类内可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**

- **public** : 对所有类可见。使用对象：类、接口、变量、方法

- **protected** : 对同一包内的类和所有子类可见。使用对象：变量、方法。 **注意：不能修饰类（外部类）**。

  **访问控制**

| 修饰符    | 当前类 | 同一包内 | 子孙类（同一包内） | 子孙类（不同包内） | 其他包 |
| --------- | ------ | -------- | ------------------ | ------------------ | ------ |
| public    | Y      | Y        | Y                  | Y                  | Y      |
| protected | Y      | Y        | Y                  | Y/N                | N      |
| default   | Y      | Y        | Y                  | N                  | N      |
| private   | Y      | N        | N                  | N                  | N      |

**protected**

- **子类与基类在同一包中**：被声明为 protected 的变量、方法和构造器能被同一个包中的任何其他类访问；

- **子类与基类不在同一包中**：那么在子类中，子类实例可以访问其从基类继承而来的 protected 方法，而不能访问基类实例的protected方法。

**方法继承的规则**

- 父类中声明为 public 的方法在子类中也必须为 public。
- 父类中声明为 protected 的方法在子类中要么声明为 protected，要么声明为 public，不能声明为 private。
- 父类中声明为 private 的方法，不能够被继承。

### 非访问修饰符

- **static 修饰符**：用来修饰类方法和类变量。
- **final 修饰符**：用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。
- **abstract 修饰符**：用来创建抽象类和抽象方法。
- **synchronized 和 volatile 修饰符**：主要用于线程的编程。

#### static 修饰符

- **静态变量：**

  static 关键字用来声明独立于对象的静态变量，**无论一个类实例化多少对象，它的静态变量只有一份拷贝**。 静态变量也被称为类变量。**局部变量不能被声明为 static 变量**。

  ```java
  class student {
      static String schoolname;
  }
  public class example12 {
      public static void main(String[] args){
          student s1 = new student();
          student s2 = new student();
          student.schoolname = "南阳师范学院";
          s1.schoolname  = "南阳理工学院";
          System.out.println(s1.schoolname);
          System.out.println(s2.schoolname); //由最后赋值的决定静态变量的值
      }
  }
  //输出:南阳理工学院
  //	  南阳理工学院
  ```

  

- **静态方法：**

  static 关键字用来声明独立于对象的静态方法。**静态方法不能使用类的非静态变量**。静态方法从参数列表得到数据，然后计算这些数据。

#### final 修饰符

- **final 变量：**

  final 表示"最后的、最终的"含义，变量一旦赋值后，**不能被重新赋值**。被 final 修饰的实例变量必须**显式指定初始值**。

  final 修饰符通常和 static 修饰符一起使用来创建类常量。

- **final 方法**

  父类中的 final 方法可以被子类继承，但是**不能被子类重写**。

- **final 类**

  final 类**不能被继承**，没有类能够继承 final 类的任何特性。

#### abstract 修饰符

- **抽象类**

  抽象类**不能用来实例化对象**，声明抽象类的唯一目的是为了**将来对该类进行扩充**。

  一个类**不能同时被 abstract 和 final 修饰**。如果一个类**包含抽象方法**，那么该类一定要**声明为抽象类**，否则将出现编译错误。

  抽象类可以包含**抽象方法**和**非抽象方法**。

  ```java
  abstract class Caravan{
     private double price;
     private String model;
     private String year;
     public abstract void goFast(); //抽象方法
     public abstract void changeColor();
  }
  ```

- **抽象方法**

  抽象方法是一种**没有任何实现**的方法，该**方法的的具体实现由子类提供**。

  抽象方法**不能**被声明成 **final** 和 **static**。

  任何继承抽象类的子类**必须实现父类的所有抽象方法**，除非该**子类也是抽象类**。

  如果一个类包含**若干个抽象方法**，那么该类必须**声明为抽象类**。抽象类**可以不包含抽象方法**。

  ```java
  public abstract class SuperClass{
      abstract void m(); //抽象方法
  }
   
  class SubClass extends SuperClass{
       //实现抽象方法
        void m(){
            .........
        }
  }
  ```

#### synchronized 修饰符

synchronized 关键字声明的方法同一时间只能被一个线程访问。synchronized 修饰符可以应用于四个访问修饰符。

```java
public synchronized void showDetails(){
.......
}
```

#### transient 修饰符

序列化的对象包含被 transient 修饰的实例变量时，java 虚拟机(JVM)跳过该特定的变量。

该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型。

```java
public transient int limit = 55;   // 不会持久化
public int b; // 持久化
```

#### volatile 修饰符

volatile 修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。而且，当成员变量发生变化时，会强		制线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值。

一个 volatile 对象引用可能是 **null**。

```java
public class MyRunnable implements Runnable
{
    private volatile boolean active;
    public void run()
    {
        active = true;
        while (active) // 第一行
        {
            // 代码
        }
    }
    public void stop()
    {
        active = false; // 第二行
    }
}
```

在一个线程调用 run() 方法（在 Runnable 开启的线程），在另一个线程调用 stop() 方法。 如果 ***第一行\*** 中缓冲区的 active 值被使用，那么在 ***第二行\*** 的 active 值为 false 时循环不会停止。

## Java Number & Math 类 & Random类

### Number

在实际开发过程中，我们经常会遇到需要**使用对象**，而**不是内置数据类型**的情形。为了解决这个问题，Java 语言为每一个内置数据类型提供了对应的包装类。

所有的包装类**（Integer、Long、Byte、Double、Float、Short）**都是抽象类 Number 的子类。

| 包装类    | 基本数据类型 |
| --------- | ------------ |
| Boolean   | boolean      |
| Byte      | byte         |
| Short     | short        |
| Integer   | int          |
| Long      | long         |
| Character | char         |
| Float     | float        |
| Double    | double       |

这种由编译器特别支持的包装称为装箱，所以当内置数据类型被当作对象使用的时候，编译器会把内置类型装箱为包装类。

编译器也可以把一个对象拆箱为内置类型。Number 类属于 java.lang 包。

**Integer类的常用方法：**

| 方法声明                                 | 方法描述                                             |
| ---------------------------------------- | ---------------------------------------------------- |
| **static String toBinaryString (int i)** | 以**二进制无符号整数**形式返回一个整数参数的字符串   |
| **static String toHexString (int i)**    | 以**十六进制无符号整数**形式返回一个整数参数的字符串 |
| **static String toOctalString (int i)**  | 以**八进制无符号整数**形式返回一个整型参数的字符串   |
| **static Integer valueOf (int i)**       | 返回一个表示**指定的int的 `Integer`实例**            |
| **static Integer valueOf (String s)**    | 返回保存**指定的String的值的 `Integer`对象**         |
| **static int parseInt (String s)**       | 将字符串参数作为**有符号的十进制整数进行解析**       |
| **IntValue ()**                          | 将`Integer`类型的值以  `int` 类型返回                |

### Math类

##### xxxValue()方法

| 类型            | 方法及描述                                       |
| --------------- | ------------------------------------------------ |
| byte            | **byteValue()**:以 byte 形式返回指定的数值。     |
| abstract double | **doubleValue()**:以 double 形式返回指定的数值。 |
| abstract float  | **floatValue()**:以 float 形式返回指定的数值。   |
| abstract int    | **intValue()**:以 int 形式返回指定的数值。       |
| abstract long   | **longValue()**:以 long 形式返回指定的数值。     |
| short           | **shortValue()**:以 short 形式返回指定的数值。   |

以上各函数不接受任何的参数。

```java
public class Test{ 
 
   public static void main(String args[]){
      Integer x = 5;
      // 返回 byte 原生数据类型
      System.out.println( x.byteValue() );
 
      // 返回 double 原生数据类型
      System.out.println(x.doubleValue());
 
      // 返回 long 原生数据类型
      System.out.println( x.longValue() );      
   }
}
/*输出:
5
5.0
5
*/
```

##### compareTo()方法

compareTo() 方法用于将 **Number 对象**与**方法的参数**进行比较。可用于比较**Byte**, **Double**, **Integer**, **Float**, **Long**或**Short**类型的参数。

该方法用于**两个相同数据类型**的比较，两个不同类型的数据不能用此方法来比较。

**返回值**

- 如果指定的数与参数**相等**返回**0**。
- 如果指定的数**小于**参数返回 **-1**。
- 如果指定的数**大于**参数返回 **1**。

```java
public class Test{ 
   public static void main(String args[]){
      Integer x = 5;
      System.out.println(x.compareTo(3));
      System.out.println(x.compareTo(5));
      System.out.println(x.compareTo(8));         
     }
}
/*输出:
1
0
-1
*/
```

##### epuals()方法

如 Number 对象**不为 Null**，且与方法的参数类型与数值都**相等**返回 **True**，否则返回 **False**。

```java
public class Test{
    public static void main(String args[]){
        Integer x = 5;
        Integer y = 10;
        Integer z =5;
        Short a = 5;
        
        System.out.println(x.equals(y));  
        System.out.println(x.equals(z)); 
        System.out.println(x.equals(a));
    }
}
/*输出:
false
true
false
*/
```

##### valueOf()方法

用于返回**给定参数的原生 Number 对象值**，参数可以是**原生数据类型**, **String**等。

该方法是**静态方法**。该方法可以接收两个参数一个是**字符串**，一个是**基数**。

**语法**

```java
static Integer valueOf(int i)
static Integer valueOf(String s)
static Integer valueOf(String s, int radix)
```

**参数**

- **i** -- Integer 对象的整数。
- **s** -- Integer 对象的字符串。
- **radix** --在解析字符串 s 时使用的进制数，用于指定使用的进制数。

**返回值**

- **Integer valueOf(int i)：**返回一个表示指定的 **int 值**的 **Integer 实例**。
- **Integer valueOf(String s):**返回保存指定的 **String** 的**值的 Integer 对象**。
- **Integer valueOf(String s, int radix):** 返回一个 **Integer 对象**，该对象中保存了用第二个参数提供的**基数**进行**解析**时从**指定的 String 中提取的值**。

```Java
public class Test{
public static void main(String args[]){
                Integer x =Integer.valueOf(9);
                Double c = Double.valueOf(5);
                Float a = Float.valueOf("80");              

                Integer b = Integer.valueOf("444",16);   // 使用 16 进制

                System.out.println(x);
                System.out.println(c);
                System.out.println(a);
                System.out.println(b);
        }
}
/*输出:
9
5.0
80.0
1092
*/
```

##### toString() 方法

用于返回以一个**字符串**表示的 **Number 对象值**。

如果方法使用了**原生的数据类型**作为参数，返回**原生数据类型的 String 对象值**。

如果方法有**两个参数**， 返回用**第二个参数**指定**基数**表示的第一个参数的**字符串表示形式**。

**语法**

```java
String toString()
static String toString(int i)
static String toString(int i,int radix)
```

**参数**

- **i** -- 要转换的整数。
- **radix** --用于指定使用的进制数。

**返回值**

- **toString():** 返回表示 Integer 值的 String 对象。
- **toString(int i):** 返回表示指定 int 的 String 对象。
- **toString(int i,int radix)**:返回一个String对象，返回用**第二个参数**指定**基数**表示的第一个参数的**字符串表示形式**。

```java
public class Test{
    public static void main(String args[]){
        Integer x = 5;

        System.out.println(x.toString());  
        System.out.println(Integer.toString(12)); 
        System.out.println(Integer.toString(8,2));
    }
}
/*输出:
5
12
1000
*/
```

##### parseInt() 方法

用于将**字符串参数**作为**有符号的十进制整数**进行解析。

如果方法有两个参数， 使用第二个参数指定的**基数**，将**字符串参数**解析为**有符号的整数**。

**语法**

```java
static int parseInt(String s)
static int parseInt(String s, int radix)
```

**参数**

- **s** -- 十进制表示的字符串。
- **radix** -- 指定的基数。

**返回值**

- **parseInt(String s):** 返回用**十进制参数**表示的**整数值**。
- **parseInt(String s,int radix):** 使用指定基数的字符串参数表示的整数 (基数可以是 10, 2, 8, 或 16 等进制数) 。

```java
public class Test{
    public static void main(String args[]){
        int x =Integer.parseInt("9");
        double c = Double.parseDouble("5");
        int b = Integer.parseInt("444",16);

        System.out.println(x);
        System.out.println(c);
        System.out.println(b);
    }
}
/*输出:
9
5.0
1092
*/
```

##### abs()方法

返回参数的绝对值。参数可以是 int, float, long, double, short, byte类型。

```java
public class Test{ 
    public static void main(String args[]){
        Integer a = -8;
        double d = -100;
        float f = -90;    
                        
        System.out.println(Math.abs(a));
        System.out.println(Math.abs(d));     
        System.out.println(Math.abs(f));    
    }
}
/*输出:
8
100.0
90.0
*/
```

##### ceil() 方法

可对一个数进行**上舍入**，返回值**大于或等于**给定的参数，类型为双精度浮点型。

```java
public class Test{
    public static void main(String args[]){
        double d = 100.675;
        float f = -90;    
 
        System.out.println(Math.ceil(d));
        System.out.println(Math.ceil(f));
    }
}
/*输出:
101.0
-90.0
*/
```

##### floor() 方法

可对一个数进行**下舍入**，返回给定参数最大的整数，该整数**小于或等于**给定的参数。

```java
public class Test{
    public static void main(String args[]){
        double d = 100.675;
        float f = -90;
 
        System.out.println(Math.floor(d));
        System.out.println(Math.floor(f));
    }
}
/*输出:
100.0
-90.0
*/
```

##### rint() 方法

返回**最接近参数的整数值**。

```java
public class Test{
    public static void main(String args[]){
        double d = 100.675;
        double e = 100.500;
        double f = 100.200;
 
        System.out.println(Math.rint(d));
        System.out.println(Math.rint(e)); 
        System.out.println(Math.rint(f)); 
        //同时存在下面按两个数，返回其值的偶数值
        System.out.println(Math.rint(100.5));
        System.out.println(Math.rint(101.5));
    }
}
/*输出:
101.0
100.0
100.0
100.0
102.0
*/
```

##### round() 方法

返回一个最接近的 **int、long 型值**，**四舍五入**

```java
public class Test{
    public static void main(String args[]){
        double d = 100.675;
        double e = 100.500;
        float f = 100;
        float g = 90f;
 
        System.out.println(Math.round(d));
        System.out.println(Math.round(e)); 
        System.out.println(Math.round(f)); 
        System.out.println(Math.round(g)); 
    }
}
/*输出:
101
101
100
90
*/
```

##### min() 方法

用于返回两个参数中的**最小值**。

```java
public class Test{
    public static void main(String args[]){
        System.out.println(Math.min(12.123, 12.456));      
        System.out.println(Math.min(23.12, 23.0));  
    }
}
/*输出:
12.123
23.0
*/
```

##### max() 方法

用于返回两个参数中的**最大值**。

```java
public class Test{
    public static void main(String args[]){
        System.out.println(Math.max(12.123, 18.456));      
        System.out.println(Math.max(23.12, 23.0));  
    }
}
/*输出:
18.456
23.12
*/
```

##### exp() 方法

用于返回自然数底数**e的参数次方**

```java
public class Test{ 
    public static void main(String args[]){
        double x = 11.635;
        double y = 2.76;

        System.out.printf("e 的值为 %.4f%n", Math.E);
        System.out.printf("exp(%.3f) 为 %.3f%n", x, Math.exp(x));  
    }
}
/*输出:
e 的值为 2.7183
exp(11.635) 为 112983.831
*/
```

##### log() 方法

用于返回参数的**自然数底数的对数值**。

```Java
public class Test{
    public static void main(String args[]){
        double x = 11.635;
        double y = 2.76;

        System.out.printf("e 的值为 %.4f%n", Math.E);
        System.out.printf("log(%.3f) 为 %.3f%n", x, Math.log(x));
    }
}
/*输出:
e 的值为 2.7183
log(11.635) 为 2.454
*/
```

##### pow() 方法

用于返回第一个参数的**第二个参数次方**。

```java
public class Test{
    public static void main(String args[]){
        double x = 11.635;
        double y = 2.76;

        System.out.printf("e 的值为 %.4f%n", Math.E);
        System.out.printf("pow(%.3f, %.3f) 为 %.3f%n", x, y, Math.pow(x, y));
    }
}
/*输出:
e 的值为 2.7183
pow(11.635, 2.760) 为 874.008
*/
```

##### sqrt() 方法

用于返回参数的**算术平方根**。

```java
public class Test{ 
    public static void main(String args[]){
        double x = 11.635;
        double y = 2.76;

        System.out.printf("e 的值为 %.4f%n", Math.E);
        System.out.printf("sqrt(%.3f) 为 %.3f%n", x, Math.sqrt(x));
    }
}
/*输出:
e 的值为 2.7183
sqrt(11.635) 为 3.411
*/
```

##### sin() 方法

用于返回指定double类型参数的**正弦值**。

```java
public class Test{
    public static void main(String args[]){
    
        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.1f 度的正弦值为 %.4f%n", degrees, Math.sin(radians));

    }
}
/*输出:
pi 的值为 3.1416
45.0 度的正弦值为 0.7071
*/
```

##### cos() 方法

用于返回指定double类型参数的**余弦值**。

```java
public class Test{ 
    public static void main(String args[]){
    
        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.1f 度的余弦值为 %.4f%n", degrees, Math.cos(radians));

    }
}
/*输出:
pi 的值为 3.1416
45.0 度的余弦值为 0.7071
*/
```

##### tan() 方法

用于返回指定double类型参数的**正切值**。

```java
public class Test{
    public static void main(String args[]){

        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.1f 度的正切值是 %.4f%n", degrees, Math.tan(radians));

    }
}
/*输出:
pi 的值为 3.1416
45.0 度的正切值是 1.0000
*/
```

##### asin() 方法

用于返回指定double类型参数的**反正弦值**。

```java
public class Test{ 
    public static void main(String args[]){

        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.4f 的反正弦值为 %.4f 度 %n", Math.sin(radians), Math.toDegrees(Math.asin(Math.sin(radians))));

    }
}
/*输出:
pi 的值为 3.1416
0.7071 的反正弦值为 45.0000 度 
*/
```

##### acos() 方法

用于返回指定double类型参数的**反余弦值**。

```java
public class Test{
    public static void main(String args[]){

        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.4f 的反余弦值为 %.4f 度 %n", Math.cos(radians), Math.toDegrees(Math.acos(Math.sin(radians))));

    }
}
/*输出:
pi 的值为 3.1416
0.7071 的反余弦值为 45.0000 度 
*/
```

##### atan() 方法

用于返回指定double类型参数的**反正切值**。

```java
public class Test{ 
    public static void main(String args[]){

        double degrees = 45.0;
        double radians = Math.toRadians(degrees);

        System.out.format("pi 的值为 %.4f%n", Math.PI);
        System.out.format("%.4f 的反正切值 %.4f 度 %n", Math.cos(radians), Math.toDegrees(Math.atan(Math.sin(radians))));

    }
}
/*输出:
pi 的值为 3.1416
0.7071 的反正切值 35.2644 度 
*/
```

##### atan2() 方法

用于将**矩形坐标** (x, y) 转换成**极坐标** (r, theta)，返回**所得角 theta**。该方法通过计算 **y/x** 的**反正切值**来计算**相角 theta**，范围为从 -pi 到 pi。

```java
public class Test{ 
    public static void main(String args[]){
        double x = 45.0;
        double y = 30.0;
 
        System.out.println( Math.atan2(x, y) );
    }
}
/*输出;
0.982793723247329
*/
```

##### toDegrees() 方法

用于将参数转化为**角度**。

```java
public class Test{
    public static void main(String args[]){
        double x = 45.0;
        double y = 30.0;

        System.out.println( Math.toDegrees(x) );
        System.out.println( Math.toDegrees(y) );
    }
}
/*输出:
2578.3100780887044
1718.8733853924698
*/
```

##### toRadians() 方法

用于将**角度**转换为**弧度**。

```java
public class Test{
    public static void main(String args[]){
        double x = 45.0;
        double y = 30.0;

        System.out.println( Math.toRadians(x) );
        System.out.println( Math.toRadians(y) );
    }
}
/*输出:
0.7853981633974483
0.5235987755982988
*/
```

##### random() 方法

用于返回一个随机数，随机数范围为 **0.0 =< Math.random < 1.0**，**不接受任何参数**。

```java
public class Test{
    public static void main(String args[]){
        System.out.println( Math.random() );
        System.out.println( Math.random() );
    }
}
/*输出:
0.5444085967267008
0.7960235983184115
*/
```

##### Math 的 floor,round 和 ceil 方法实例比较

| 参数 | Math.floor | Math.round | Math.ceil |
| :--- | :--------- | :--------- | :-------- |
| 1.4  | 1          | 1          | 2         |
| 1.5  | 1          | 2          | 2         |
| 1.6  | 1          | 2          | 2         |
| -1.4 | -2         | -1         | -1        |
| -1.5 | -2         | -1         | -1        |
| -1.6 | -2         | -2         | -1        |

```java
public class Main {   
  public static void main(String[] args) {   
    double[] nums = { 1.4, 1.5, 1.6, -1.4, -1.5, -1.6 };   
    for (double num : nums) {   
      test(num);   
    }   
  }   
  
  private static void test(double num) {   
    System.out.println("Math.floor(" + num + ")=" + Math.floor(num));   
    System.out.println("Math.round(" + num + ")=" + Math.round(num));   
    System.out.println("Math.ceil(" + num + ")=" + Math.ceil(num));   
  }   
}
/*输出:
Math.floor(1.4)=1.0
Math.round(1.4)=1
Math.ceil(1.4)=2.0
Math.floor(1.5)=1.0
Math.round(1.5)=2
Math.ceil(1.5)=2.0
Math.floor(1.6)=1.0
Math.round(1.6)=2
Math.ceil(1.6)=2.0
Math.floor(-1.4)=-2.0
Math.round(-1.4)=-1
Math.ceil(-1.4)=-1.0
Math.floor(-1.5)=-2.0
Math.round(-1.5)=-1
Math.ceil(-1.5)=-1.0
Math.floor(-1.6)=-2.0
Math.round(-1.6)=-2
Math.ceil(-1.6)=-1.0
*/
```

### Random类

Random可以在指定范围内**随机产生数字**。

**Random的构造函数：**

| 方法声明              | 方法描述                                             |
| --------------------- | ---------------------------------------------------- |
| **Random()**          | 构造方法，用于创建一个伪随机数生成器                 |
| **Random(long seed)** | 构造方法，使用一个long型的seed种子创建伪随机数生成器 |

**无参构造方法实例：**

```java
import java.util.Random;
public class random{
    public static void main(String[] args){
        Random r = new Random();//不传入种子
        //随机产生10个[0,100]之间的整数
        for (int i = 0;i < 10; i++){
            system.out.println(r.nextInt(100));
        }
    }
}
//两次输出结果不同。没有指定种子，系统会以当前时间戳作为种子，产生随机数。
```

**有参构造方法实例：**

```java
import java.util.Random;
public random(){
    public static void main(String[] args){
        Random r = new Random(13); //创建对象时传入种子
        //随机产生10个[0,100]之间的整数
        for (int i = 0;i < 10; i++){
            System.out.println(r.nextInt(100));
        }
    }
}
//两次输出结果都一样，指定了相同的种子，则每个实例对象产生的随机数具有相同的序列。
```

Random类的常用方法：

| 方法声明                    | 方法描述                                         |
| --------------------------- | ------------------------------------------------ |
| **boolean  nextBoolean ()** | 随机生成**boolean**类型的随机数                  |
| **double  nextDouble ()**   | 随机生成**double**类型的随机数                   |
| **float  nextFloat ()**     | 随机生成**float**类型的随机数                    |
| **int  nextInt ()**         | 随机生成**int**类型的随机数                      |
| **int  nextInt (int n)**    | 随机生成**[0,n]之间的int**类型的随机数           |
| **long  nextLong()**        | 随机生成**long**类型的随机数                     |
| **double  nextGaussian()**  | 平均值为0.0，标准差为1.0的伪随机高斯分布双精度数 |

## Java Character 类

使用**Character**的**构造方法**创建一个**Character类对象**

```java
Character ch = new Character('a');
```

将一个**char**类型的参数传递给需要一个**Character**类型参数的方法时，那么编译器会**自动**地将**char类型参数转换为Character对象**。 这种特征称为**装箱**，反过来称为**拆箱**。

```java
// 原始字符 'a' 装箱到 Character 对象 ch 中
Character ch = 'a';
 
// 原始字符 'x' 用 test 方法装箱
// 返回拆箱的值到 'c'
char c = test('x');
```

### Character方法

#### isLetter() 方法

用于判断指定字符是否为**字母**。

```java
//如果字符为字母，则返回 true；否则返回 false。
public class Test {

    public static void main(String args[]) {
        System.out.println(Character.isLetter('c'));
        System.out.println(Character.isLetter('5'));
    }
}
/*输出:
true
false
*/
```

#### isDigit() 方法

用于判断指定字符是否为**数字**。

```java
//如果字符为数字，则返回 true；否则返回 false。
public class Test {

    public static void main(String args[]) {
        System.out.println(Character.isDigit('c'));
        System.out.println(Character.isDigit('5'));
    }
}
/*输出:
false
true
*/
```

#### isWhitespace() 方法

用于判断指定字符是否为**空白字符**，空白符包含：**空格**、**tab 键**、**换行符**。

```java
//如果字符为空白字符，则返回 true；否则返回 false。
public class Test {
 
    public static void main(String args[]) {
        System.out.println(Character.isWhitespace('c'));
        System.out.println(Character.isWhitespace(' '));
        System.out.println(Character.isWhitespace('\n'));
        System.out.println(Character.isWhitespace('\t'));
    }
}
/*输出:
false
true
true
true
*/
```

#### isUpperCase() 方法

用于判断指定字符是否为**大写字母**。

```java
//如果字符为大写，则返回 true；否则返回 false。
public class Test {

    public static void main(String args[]) {
        System.out.println( Character.isUpperCase('c'));
        System.out.println( Character.isUpperCase('C'));
    }
}
/*输出:
false
true
*/
```

#### isLowerCase() 方法

用于判断指定字符是否为**小写字母**。

```java
//如果字符为小写，则返回 true；否则返回 false。
public class Test {

    public static void main(String args[]) {
        System.out.println( Character.isLowerCase('c'));
        System.out.println( Character.isLowerCase('C'));
    }
}
/*输出:
true
false
*/
```

#### toUpperCase() 方法

用于将**小写字符**转换为**大写**。

```java
public class Test {
    public static void main(String args[]) {
        System.out.println(Character.toUpperCase('a'));
        System.out.println(Character.toUpperCase('A'));
    }
}
/*输出:
A
A
*/
```

#### toLowerCase() 方法

用于将**大写字符**转换为**小写**。

```java
public class Test {
    public static void main(String args[]) {
        System.out.println(Character.toLowerCase('a'));
        System.out.println(Character.toLowerCase('A'));
    }
}
/*输出:
a
a
*/
```

#### toString() 方法

用于返回一个表示指定 **char 值**的 **String 对象**。结果是**长度为 1 的字符串**，**仅由指定的 char 组成**。

```java
public class Test {
    public static void main(String args[]) {
        System.out.println(Character.toString('a'));
        System.out.println(Character.toString('A'));
    }
}
/*输出:
a
A
*/
```

## Java String 类

### 创建字符串

创建字符串最简单的方式如下:

```java
String greeting = "菜鸟教程";
```

String 类有 **11 种构造方法**，这些方法提供不同的参数来初始化字符串，比如提供一个**字符数组参数**:

```java
public class StringDemo{
   public static void main(String args[]){
      char[] helloArray = { 'r', 'u', 'n', 'o', 'o', 'b'};
      String helloString = new String(helloArray);  
      System.out.println( helloString );
   }
}
/*输出:
runoob
*/
```

String 类是**不可改变**的，所以你一旦创建了 String 对象，那**它的值就无法改变**了

### 字符串长度

```java
public class StringDemo {
    public static void main(String args[]) {
        String site = "www.runoob.com";
        int len = site.length();
        System.out.println( "菜鸟教程网址长度 : " + len );
   }
}
/*输出:
菜鸟教程网址长度 : 14
*/
```

### 连接字符串

String 类提供了连接两个字符串的方法：

```java
//string1.concat(string2);
"我的名字是 ".concat("Runoob");

//常用的是使用'+'操作符来连接字符串
"Hello," + " runoob" + "!"
```

### 创建格式化字符串

输出格式化数字可以使用 **printf()** 和 **format()** 方法。

String 类**使用**静态方法 format() 返回一个**String 对象**而不是 **PrintStream 对象**。

**String 类的静态方法 format()** 能用来**创建可复用的格式化字符串**，而**不仅仅是用于一次打印输出**。

```java
System.out.printf("浮点型变量的值为 " +
                  "%f, 整型变量的值为 " +
                  " %d, 字符串变量的值为 " +
                  "is %s", floatVar, intVar, stringVar);
String fs;
fs = String.format("浮点型变量的值为 " +
                   "%f, 整型变量的值为 " +
                   " %d, 字符串变量的值为 " +
                   " %s", floatVar, intVar, stringVar);
```

### String 方法

#### charAt() 方法

用于返回**指定索引处的字符**。索引范围为从 **0 到 length() - 1**。

```java
public class Test {
    public static void main(String args[]) {
        String s = "www.runoob.com";
        char result = s.charAt(6);
        System.out.println(result);
    }
}
/*输出:
n
*/
```

#### compareTo() 方法

用于两种方式的比较：

- **字符串**与**对象**进行比较。
- 按**字典顺序**比较两个字符串。

**返回值**

- 如果参数字符串**等于**此字符串，则返回值 **0**；
- 如果此字符串**小于**字符串参数，则返回一个**小于 0 的值**；
- 如果此字符串**大于**字符串参数，则返回一个**大于 0 的值**。

```java
public class Test {
    public static void main(String args[]) {
        String str1 = "Strings";
        String str2 = "Strings";
        String str3 = "Strings123";
 
        int result = str1.compareTo( str2 );
        System.out.println(result);
      
        result = str2.compareTo( str3 );
        System.out.println(result);
     
        result = str3.compareTo( str1 );
        System.out.println(result);
    }
}
/*输出:
0
-3
3
*/
```

#### compareToIgnoreCase() 方法

用于按**字典顺序**比较两个字符串，**不考虑大小写**。

**返回值**

- 如果参数字符串**等于**此字符串，则返回值 **0**；
- 如果此字符串**小于**字符串参数，则返回一个**小于 0 的值**；
- 如果此字符串**大于**字符串参数，则返回一个**大于 0 的值**。

```java
public class Test {
    public static void main(String args[]) {
        String str1 = "STRINGS";
        String str2 = "Strings";
        String str3 = "Strings123";

        int result = str1.compareToIgnoreCase( str2 );
        System.out.println(result);
      
        result = str2.compareToIgnoreCase( str3 );
        System.out.println(result);
     
        result = str3.compareToIgnoreCase( str1 );
        System.out.println(result); 
    }
}
/*输出:
0
-3
3
*/
```

#### concat() 方法

用于将指定的**字符串**参数**连接**到字符串上。

```java
public class Test {
    public static void main(String args[]) {
        String s = "菜鸟教程：";
        s = s.concat("www.runoob.com");
        System.out.println(s);
    }
}
/*输出:
菜鸟教程：www.runoob.com
*/
```

#### contentEquals() 方法

用于将此**字符串**与**指定的 StringBuffer** 比较。

```java
//如字符串与指定 StringBuffer 表示相同的字符序列，则返回 true；否则返回 false。
public class Test {
    public static void main(String args[]) {
        String str1 = "String1";
        String str2 = "String2";
        StringBuffer str3 = new StringBuffer( "String1");

        boolean  result = str1.contentEquals( str3 );
        System.out.println(result);
          
        result = str2.contentEquals( str3 );
        System.out.println(result);
    }
}
/*输出:
true
false
*/
```

#### copyValueOf() 方法

**copyValueOf()** 方法有两种形式：

- **public static String copyValueOf(char[] data):** 返回指定数组中表示该字符序列的字符串。
- **public static String copyValueOf(char[] data, int offset, int count):** 返回指定数组中表示该字符序列的 字符串。

**参数**

- **data** -- 字符数组。
- **offset** -- 子数组的初始偏移量。。
- **count** -- 子数组的长度。

```java
public class Test {
    public static void main(String args[]) {
        char[] Str1 = {'h', 'e', 'l', 'l', 'o', ' ', 'r', 'u', 'n', 'o', 'o', 'b'};
        String Str2 = "";
 
        Str2 = Str2.copyValueOf( Str1 );
        System.out.println("返回结果：" + Str2);
 
        Str2 = Str2.copyValueOf( Str1, 2, 6 );
        System.out.println("返回结果：" + Str2);
    }
}
/*输出:
返回结果：hello runoob
返回结果：llo ru
*/
```

#### endsWith() 方法

用于测试字符串是否以指定的后缀结束。

```java
//如果参数表示的字符序列是此对象表示的字符序列的后缀，则返回 true；否则返回 false。注意，如果参数是空字符串，或者等于此 String 对象（用 equals(Object) 方法确定），则结果为 true。
public class Test {
    public static void main(String args[]) {
        String Str = new String("菜鸟教程：www.runoob.com");
        boolean retVal;
 
        retVal = Str.endsWith( "runoob" );
        System.out.println("返回值 = " + retVal );
 
        retVal = Str.endsWith( "com" );
        System.out.println("返回值 = " + retVal );
    }
}
/*输出;
返回值 = false
返回值 = true
*/
```

#### equals() 方法

用于将**字符串**与**指定的对象**比较。

```java
//如果给定对象与字符串相等，则返回 true；否则返回 false。
public class Test {
        public static void main(String args[]) {
                String Str1 = new String("runoob");
                String Str2 = Str1;
                String Str3 = new String("runoob");
                boolean retVal;

                retVal = Str1.equals( Str2 );
                System.out.println("返回值 = " + retVal );

                retVal = Str1.equals( Str3 );
                System.out.println("返回值 = " + retVal );
        }
}
/*输出:
返回值 = true
返回值 = true
*/
```

#### equalsIgnoreCase() 方法

用于将**字符串**与**指定的对象**比较，**不考虑大小写**。

```java
//如果给定对象与字符串相等，则返回 true；否则返回 false。
public class Test {
    public static void main(String args[]) {
        String Str1 = new String("runoob");
        String Str2 = Str1;
        String Str3 = new String("runoob");
        String Str4 = new String("RUNOOB");
        boolean retVal;

        retVal = Str1.equals( Str2 );
        System.out.println("返回值 = " + retVal );

        retVal = Str3.equals( Str4);
        System.out.println("返回值 = " + retVal );

        retVal = Str1.equalsIgnoreCase( Str4 );
        System.out.println("返回值 = " + retVal );
    }
}
/*输出:
返回值 = true
返回值 = false
返回值 = true
*/
```

#### getBytes() 方法

有两种形式：

- **getBytes(String charsetName):** 使用**指定的字符集**将**字符串编码为 byte 序列**，并将结果存储到一个新的 byte 数组中。
- **getBytes():** 使用平台的**默认字符集**将**字符串编码为 byte 序列**，并将结果存储到一个新的 byte 数组中。

```java
import java.io.*;
 
public class Test {
    public static void main(String args[]) {
        String Str1 = new String("runoob");
 
        try{
            byte[] Str2 = Str1.getBytes();
            System.out.println("返回值：" + Str2 );
            
            Str2 = Str1.getBytes( "UTF-8" );
            System.out.println("返回值：" + Str2 );
            
            Str2 = Str1.getBytes( "ISO-8859-1" );
            System.out.println("返回值：" + Str2 );
        } catch ( UnsupportedEncodingException e){
            System.out.println("不支持的字符集");
        }
    }
}
/*输出:
返回值：[B@7852e922
返回值：[B@4e25154f
返回值：[B@70dea4e
*/
```

#### getChars() 方法

将**字符**从**字符串**复制到**目标字符数组**。

**语法**

```java
public void getChars(int srcBegin, int srcEnd, char[] dst,  int dstBegin)
```

**参数**

- **srcBegin** -- 字符串中要复制的**第一个字符**的索引。
- **srcEnd** -- 字符串中要复制的**最后一个字符之后**的索引。
- **dst** -- **目标数组**。
- **dstBegin** -- 目标数组中的**起始偏移量**。

```java
public class Test {
    public static void main(String args[]) {
        String Str1 = new String("www.runoob.com");
        char[] Str2 = new char[6];

        try {
            Str1.getChars(4, 10, Str2, 0);
            System.out.print("拷贝的字符串为：" );
            System.out.println(Str2 );
        } catch( Exception ex) {
            System.out.println("触发异常...");
        }
    }
}
/*输出:
拷贝的字符串为：runoob
*/
```

#### hashCode() 方法

用于返回字符串的**哈希码**。

```java
public class Test {
        public static void main(String args[]) {
                String Str = new String("www.runoob.com");
                System.out.println("字符串的哈希码为 :" + Str.hashCode());
        }
}
/*输出:
字符串的哈希码为 :321005537
*/
```

#### indexOf() 方法

有以下四种形式：

- **public int indexOf(int ch):** 返回**指定字符**在字符串中**第一次出现**处的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **public int indexOf(int ch, int fromIndex):** 返回从 **fromIndex 位置**开始查找**指定字符**在字符串中**第一次出现**处的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **int indexOf(String str):** 返回**指定字符**在字符串中**第一次出现**处的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **int indexOf(String str, int fromIndex):** 返回从 **fromIndex 位置**开始查找**指定字符**在字符串中**第一次出现**处的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。

**第一个字符位置为0**

```java
public class Main {
    public static void main(String args[]) {
        String string = "aaa456ac";  
        //查找指定字符是在字符串中的下标。在则返回所在字符串下标；不在则返回-1.  
        System.out.println(string.indexOf("b")); // indexOf(String str); 返回结果：-1，"b"不存在  
 
        // 从第四个字符位置开始往后继续查找，包含当前位置  
        System.out.println(string.indexOf("a",3));//indexOf(String str, int fromIndex); 返回结果：6  
 
        //（与之前的差别：上面的参数是 String 类型，下面的参数是 int 类型）参考数据：a-97,b-98,c-99  
 
        // 从头开始查找是否存在指定的字符  
        System.out.println(string.indexOf(99));//indexOf(int ch)；返回结果：7  
        System.out.println(string.indexOf('c'));//indexOf(int ch)；返回结果：7  
 
        //从fromIndex查找ch，这个是字符型变量，不是字符串。字符a对应的数字就是97。  
        System.out.println(string.indexOf(97,3));//indexOf(int ch, int fromIndex); 返回结果：6  
        System.out.println(string.indexOf('a',3));//indexOf(int ch, int fromIndex); 返回结果：6  
    }
}
```

#### intern() 方法

返回字符串对象的**规范化表示形式**。

遵循以下规则：对于任意两个字符串 s 和 t，当且仅当 **s.equals(t) 为 true** 时，**s.intern() == t.intern() 才为 true**。

```java
//返回一个字符串，内容与此字符串相同，但一定取自具有唯一字符串的池。
public class Test {
    public static void main(String args[]) {
        String Str1 = new String("www.runoob.com");
        String Str2 = new String("WWW.RUNOOB.COM");

        System.out.print("规范表示:" );
        System.out.println(Str1.intern());

        System.out.print("规范表示:" );
        System.out.println(Str2.intern());
    }
}
/*输出:
规范表示:www.runoob.com
规范表示:WWW.RUNOOB.COM
*/
```

#### lastIndexOf() 方法

有以下四种形式：

- **public int lastIndexOf(int ch):** 返回**指定字符**在此字符串中**最后一次出现**处的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **public int lastIndexOf(int ch, int fromIndex):** 返回**指定字符**在此字符串中**最后一次出现**处的索引，从**指定的索引处**开始进行**反向搜索**，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **public int lastIndexOf(String str):** 返回**指定子字符串**在此字符串中**最右边出现处**的索引，如果此字符串中**没有这样的字符**，则返回 **-1**。
- **public int lastIndexOf(String str, int fromIndex):** 返回**指定子字符串**在此字符串中**最后一次出现**处的索引，从**指定的索引**开始**反向搜索**，如果此字符串中**没有这样的字符**，则返回 **-1**。

```Java
public class Test {
    public static void main(String args[]) {
        String Str = new String("菜鸟教程:www.runoob.com");
        String SubStr1 = new String("runoob");
        String SubStr2 = new String("com");

        System.out.print("查找字符 o 最后出现的位置 :" );
        System.out.println(Str.lastIndexOf( 'o' ));
        System.out.print("从第14个位置查找字符 o 最后出现的位置 :" );
        System.out.println(Str.lastIndexOf( 'o', 14 ));
        System.out.print("子字符串 SubStr1 最后出现的位置:" );
        System.out.println( Str.lastIndexOf( SubStr1 ));
        System.out.print("从第十五个位置开始搜索子字符串 SubStr1最后出现的位置 :" );
        System.out.println( Str.lastIndexOf( SubStr1, 15 ));
        System.out.print("子字符串 SubStr2 最后出现的位置 :" );
        System.out.println(Str.lastIndexOf( SubStr2 ));
    }
}
/*输出:
查找字符 o 最后出现的位置 :17
从第14个位置查找字符 o 最后出现的位置 :13
子字符串 SubStr1 最后出现的位置:9
从第十五个位置开始搜索子字符串 SubStr1最后出现的位置 :9
子字符串 SubStr2 最后出现的位置 :16
*/
```

#### length() 方法

用于返回字符串的**长度**。

**空字符串**的长度返回 **0**。

```java
public class Test {
        public static void main(String args[]) {
                String Str1 = new String("www.runoob.com");
                String Str2 = new String("runoob" );

                System.out.print("字符串 Str1 长度 :");
                System.out.println(Str1.length());
                System.out.print("字符串 Str2 长度 :");
                System.out.println(Str2.length());
        }
}
/*输出:
字符串 Str1 长度 :14
字符串 Str2 长度 :6
*/
```

#### matches() 方法

用于检测**字符串**是否**匹配**给定的**正则表达式**。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.runoob.com");

        System.out.print("返回值 :" );
        System.out.println(Str.matches("(.*)runoob(.*)"));
        
        System.out.print("返回值 :" );
        System.out.println(Str.matches("(.*)google(.*)"));

        System.out.print("返回值 :" );
        System.out.println(Str.matches("www(.*)"));
    }
}
/*输出:
返回值 :true
返回值 :false
返回值 :true
*/
```

#### regionMatches() 方法

用于检测**两个字符串**在**一个区域内**是否**相等**。

**语法**

```java
public boolean regionMatches(int toffset,String other,int ooffset,int len)

public boolean regionMatches(boolean ignoreCase,int toffset,String other,int ooffset,int len)
```

**参数**

- **ignoreCase** -- 如果为 **true**，则比较字符时**忽略大小写**。
- **toffset** -- 此**字符串**中**子区域**的**起始偏移量**。
- **other** -- **字符串参数**。
- **ooffset** -- **字符串参数**中**子区域**的**起始偏移量**。
- **len** -- 要比较的**字符数**。

```java
//如果字符串的指定子区域匹配字符串参数的指定子区域，则返回 true；否则返回 false。是否完全匹配或考虑大小写取决于 ignoreCase 参数。
public class Test {
    public static void main(String args[]) {
        String Str1 = new String("www.runoob.com");
        String Str2 = new String("runoob");
        String Str3 = new String("RUNOOB");

        System.out.print("返回值 :" );
        System.out.println(Str1.regionMatches(4, Str2, 0, 5));

        System.out.print("返回值 :" );
        System.out.println(Str1.regionMatches(4, Str3, 0, 5));

        System.out.print("返回值 :" );
        System.out.println(Str1.regionMatches(true, 4, Str3, 0, 5));
    }
}
/*输出:
返回值 :true
返回值 :false
返回值 :true
*/
```

#### replace() 方法

通过用 **newChar 字符替换**字符串中出现的所有 **searchChar 字符**，并返回替换后的**新字符串**。

```java
public class Main {
    public static void main(String args[]) {
        String Str = new String("Runoob");

        System.out.print("返回值 :" );
        System.out.println(Str.replace('o', 'T'));

        System.out.print("返回值 :" );
        System.out.println(Str.replace('u', 'D'));
    }
}
/*输出:
返回值 :RunTTb
返回值 :RDnoob
*/
```

#### replaceAll() 方法

使用给定的参数 **replacement** **替换**字符串所有**匹配**给定的**正则表达式**的**子字符串**。

```java
public String replaceAll(String regex, String replacement)
//成功则返回替换的字符串，失败则返回原始字符串。
    
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.google.com");

        System.out.print("匹配成功返回值 :" );
        System.out.println(Str.replaceAll("(.*)google(.*)", "runoob" ));
        System.out.print("匹配失败返回值 :" );
        System.out.println(Str.replaceAll("(.*)taobao(.*)", "runoob" ));
    }
}
/*输出:
匹配成功返回值 :runoob
匹配失败返回值 :www.google.com
*/
```

#### replaceFirst() 方法

使用给定的参数 **replacement** **替换**字符串**第一个匹配**给定的**正则表达式**的**子字符串**。

```java
//成功则返回替换的字符串，失败则返回原始字符串。
public class Test {
    public static void main(String args[]) {
        String Str = new String("hello runoob，I am from runoob。");

        System.out.print("返回值 :" );
        System.out.println(Str.replaceFirst("runoob", "google" ));
        System.out.print("返回值 :" );
        System.out.println(Str.replaceFirst("(.*)runoob(.*)", "google" ));
    }
}
/*输出:
返回值 :hello google，I am from runoob。
返回值 :google
*/
```

#### split() 方法

根据匹配给定的**正则表达式**来**拆分字符串**。

**注意：** **.** 、 **$**、 **|** 和 ***** 等转义字符，必须得加 \\。

**注意：**多个分隔符，可以用 **|** 作为连字符。

**语法**

```java
public String[] split(String regex)
public String[] split(String regex, int limit)
```

**参数**

- **regex** -- **正则表达式分隔符**。
- **limit** -- 分割的**份数**。

```java
public class Test {
    public static void main(String args[]) {
        String str = new String("Welcome-to-Runoob");
 
        System.out.println("- 分隔符返回值 :" );
        for (String retval: str.split("-")){
            System.out.println(retval);
        }
 
        System.out.println("");
        System.out.println("- 分隔符设置分割份数返回值 :" );
        for (String retval: str.split("-", 2)){
            System.out.println(retval);
        }
 
        System.out.println("");
        String str2 = new String("www.runoob.com");
        System.out.println("转义字符返回值 :" );
        for (String retval: str2.split("\\.", 3)){
            System.out.println(retval);
        }
 
        System.out.println("");
        String str3 = new String("acount=? and uu =? or n=?");
        System.out.println("多个分隔符返回值 :" );
        for (String retval: str3.split("and|or")){
            System.out.println(retval);
        }
    }
}
/*输出:
- 分隔符返回值 :
Welcome
to
Runoob

- 分隔符设置分割份数返回值 :
Welcome
to-Runoob

转义字符返回值 :
www
runoob
com

多个分隔符返回值 :
acount=? 
 uu =? 
 n=?
*/
```

#### startsWith() 方法

用于检测**字符串**是否以**指定的前缀**开始。

**语法**

```Java
public boolean startsWith(String prefix, int toffset)
public boolean startsWith(String prefix)
```

**参数**

- **prefix** -- **前缀**。
- **toffset** -- 字符串中**开始查找的位置**。

```Java
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.runoob.com");
 
        System.out.print("返回值 :" );
        System.out.println(Str.startsWith("www") );
 
        System.out.print("返回值 :" );
        System.out.println(Str.startsWith("runoob") );
 
        System.out.print("返回值 :" );
        System.out.println(Str.startsWith("runoob", 4) );
    }
}
/*输出:
返回值 :true
返回值 :false
返回值 :true
*/
```

#### subSequence() 方法

返回一个**新的字符序列**，它是此序列的一个**子序列**。

**语法**

```java
public CharSequence subSequence(int beginIndex, int endIndex)
```

**参数**

- **beginIndex** -- **起始索引**（**包括**）。
- **endIndex** -- **结束索引**（**不包括**）。

```java
public class Test {
    public static void main(String args[]) {
         String Str = new String("www.runoob.com");

         System.out.print("返回值 :" );
         System.out.println(Str.subSequence(4, 10) );
    }
}
/*输出:
返回值 :runoob
*/
```

#### substring() 方法

返回字符串的**子字符串**。

**语法**

```java
public String substring(int beginIndex)// 从beginIndex开始到末尾
public String substring(int beginIndex, int endIndex)
```

**参数**

- **beginIndex** -- **起始索引**（**包括**），索引从0开始。
- **endIndex** -- **结束索引**（**不包括**）。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.runoob.com");
 
        System.out.print("返回值 :" );
        System.out.println(Str.substring(4) );
 
        System.out.print("返回值 :" );
        System.out.println(Str.substring(4, 10) );
    }
}
/*输出:
返回值 :runoob.com
返回值 :runoob
*/
```

#### toCharArray() 方法

将**字符串**转换为**字符数组**。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.runoob.com");

        System.out.print("返回值 :" );
        char ch[] = Str.toCharArray();
        System.out.println(ch[1])
    }
}
/*输出:
返回值 :w
*/
```

#### toLowerCase() 方法

将字符串转换为**小写**。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("WWW.RUNOOB.COM");

        System.out.print("返回值 :" );
        System.out.println( Str.toLowerCase() );
    }
}
/*输出:
返回值 :www.runoob.com
*/
```

#### toUpperCase() 方法

将字符串小写字符转换为**大写**。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("www.runoob.com");

        System.out.print("返回值 :" );
        System.out.println( Str.toUpperCase() );
    }
}
/*输出:
返回值 :WWW.RUNOOB.COM
*/
```

#### toString() 方法

返回此**对象本身**（它已经是一个字符串）。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("WWW.RUNOOB.COM");

        System.out.print("返回值 :" );
        System.out.println( Str.toString() );
    }
}
/*输出:
返回值 :WWW.RUNOOB.COM
*/
```

#### trim() 方法

用于删除字符串的**头尾空白符**。

```java
public class Test {
    public static void main(String args[]) {
        String Str = new String("    www.runoob.com    ");
        System.out.print("原始值 :" );
        System.out.println( Str );

        System.out.print("删除头尾空白 :" );
        System.out.println( Str.trim() );
    }
}
/*输出:
原始值 :    www.runoob.com    
删除头尾空白 :www.runoob.com
*/
```

#### valueOf() 方法

返回该参数的**字符串表现形式**

**语法**

```Java
static String valueOf(boolean b) 
static String valueOf(char c) 
static String valueOf(char[] data) 
static String valueOf(char[] data, int offset, int count) 
static String valueOf(double d) 
static String valueOf(float f) 
static String valueOf(int i)
static String valueOf(long l)
static String valueOf(Object obj) 
```

**实例**

```java
public class Test {
    public static void main(String args[]) {
        double d = 1100.00;
        boolean b = true;
        long l = 1234567890;
        char[] arr = {'r', 'u', 'n', 'o', 'o', 'b' };

        System.out.println("返回值 : " + String.valueOf(d) );
        System.out.println("返回值 : " + String.valueOf(b) );
        System.out.println("返回值 : " + String.valueOf(l) );
        System.out.println("返回值 : " + String.valueOf(arr) );
    }
}
/*输出:
返回值 : 1100.0
返回值 : true
返回值 : 1234567890
返回值 : runoob
*/
```

#### contains() 方法

用于判断字符串中是否包含**指定的字符或字符串**。

```java
public class Main {
    public static void main(String[] args) {
        String myStr = "Runoob";
        System.out.println(myStr.contains("Run"));
        System.out.println(myStr.contains("o"));
        System.out.println(myStr.contains("s"));
    }
}
/*输出:
true
true
false
*/
```

#### isEmpty() 方法

用于判断字符串**是否为空**。

```java
public class Main {
    public static void main(String[] args) {
        String myStr1 = "Runoob";  
        String myStr2 = "";        // 空字符串
        String myStr3 = "    ";    // 多个空格，length() 不为 0 
        System.out.println("myStr1 是否为空：" + myStr1.isEmpty());
        System.out.println("myStr2 是否为空：" + myStr2.isEmpty());
        System.out.println("myStr3 长度：" + myStr3.length());
        System.out.println("myStr3 是否为空：" + myStr3.isEmpty());
    }
}
/*输出:
myStr1 是否为空：false
myStr2 是否为空：true
myStr3 长度：4
myStr3 是否为空：false
*/
```

## Java StringBuffer & StringBuilder 类

当对**字符串**进行**修改**的时候，需要使用 **StringBuffer** 和 **StringBuilder** 类。

和 String 类不同的是，**StringBuffer** 和 **StringBuilder** 类的对象能够被**多次的修改**，并且**不产生新的未使用对象**。

StringBuilder 类在 Java 5 中被提出，它和 StringBuffer 之间的最大不同在于 **StringBuilder** 的方法**不是线程安全**的（**不能同步访问**）。

由于 **StringBuilder** 相较于 **StringBuffer** 有**速度优势**，所以**多数情况下建议使用 StringBuilder 类**。然而在应用程序要求**线程安全**的情况下，则**必须使用 StringBuffer 类**。

### StringBuffer 方法

#### append()

将**指定的字符**串**追加**到此**字符序列**。

```java
StringBuffer str = new StringBuffer("a");
str.append("b");
System.out.println(str);
//输出:ab
```

#### reverse()

将此**字符序列**用其**反转**形式取代。

```java
StringBuffer str = new StringBuffer("abcd");
str.reverse();
System.out.println(str);
//输出:dcba
```

#### delete(int start, int end)

移除此序列的**子字符串**中的**字符**。

**参数**

- **start**——起始位置(**包括**)
- **end**——结束位置(**不包括**)

```java
StringBuffer str = new StringBuffer("abcd");
str.delete(0,2);
System.out.println(str);
//输出:acd
```

#### **insert(int offset, int i)**

将参数的**字符串**表示形式**插入此序列**中。

```java
StringBuffer str = new StringBuffer("abcd");
str.insert(0,2);
System.out.println(str);
//输出:2abcd
```

####  replace(int start, int end, String str)

使用给定 `String` 中的字符**替换**此序列的**子字符串中的字符**。

**参数**

- **start**——起始位置(**包括**)
- **end**——结束位置(**不包括**)
- **str**——替换字符串

```Java
StringBuffer str = new StringBuffer("abcd");
str.replace(0,2,"sd");
System.out.println(str);
```

#### 和 [String 类](#String 方法)的方法类似：

| 方法名                                                       | 方法描述                                                     |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| **int capacity()**                                           | 返回当前**容量**。                                           |
| **char charAt(int index)**                                   | 返回此序列中**指定索引处的 `char` 值**。                     |
| **void ensureCapacity(int minimumCapacity)**                 | **确保容量至少等于指定的最小值**。                           |
| **void getChars(int srcBegin, int srcEnd, char[] dst, int dstBegin)** | 将**字符**从此序列**复制**到目标**字符数组 `dst`**。         |
| **int indexOf(String str)**                                  | 返回**第一次出现的指定子字符串**在该字符串中的索引。         |
| **int indexOf(String str, int fromIndex)**                   | 从**指定的索引处开始**，返回**第一次出现的指定子字符串**在该字符串中的索引。 |
| **int lastIndexOf(String str)**                              | 返回**最右边出现的指定子字符串**在此字符串中的索引。         |
| **int lastIndexOf(String str, int fromIndex)**               | 返回 String 对象中**子字符串最后出现的位置**。               |
| **int length()**                                             | 返回**长度**（字符数）。                                     |
| **void setCharAt(int index, char ch)**                       | 将**给定索引处的字符设置为 `ch`**。                          |
| **void setLength(int newLength)**                            | **设置字符序列的长度**。                                     |
| **CharSequence subSequence(int start, int end)**             | 返回一个**新的字符序列**，该字符序列是此序列的子序列。       |
| **String substring(int start)**                              | 返回一个新的 `String`，它包含此字符序列当前所包含的**字符子序列**。 |
| **String substring(int start, int end)**                     | 返回一个新的 `String`，它包含此序列当前所包含的**字符子序列**。 |
| **String toString()**                                        | 返回此序列中**数据的字符串表示形式**。                       |

## Java System类 & Runtime类

### System类

System类定义了一些与系统相关的属性和方法，所提供的**属性和方法都是静态**的。

**System类的常用方法:**

| 方法声明                                                     | 方法描述                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **static void exit (int status)**                            | 该方法用于**终止正在运行的Java虚拟机**，其中，参数status表示状态码，若**状态码非0，则表示异常终止** |
| **static void gc ()**                                        | 运行垃圾回收器，并对**垃圾进行回收**                         |
| **static native long currentTimeMillis ()**                  | 返回以毫秒为单位的当前时间，**1970年1月1日至今的毫秒数**。   |
| **static void arraycopy (Object src, int secPos, Object dest, int destPos, int length)** | 从**`src`引用的指定源数组复制到dest引用的数组**，**复制从指定的位置开始，到目标数组的指定位置结束** |
| **static Properties getProperties ()**                       | **取得当前的系统属性**                                       |
| **static String getProperty (String key)**                   | 获取**指定键描述的系统属性**                                 |

#### getProperties ()

```java
import java.util.*;

public class system{
    public static void main(String[] args){
        //获取当前系统属性
        Properties properties = System.getProperties();
        System.out.println(properties);
        //获取所有系统属性的key(属性)，返回set对象
        Set<String> propertyNames = properties.stringPropertyNames();
        for (String key : propertyNames){
            //获取当前键key(属性名)所对应的值(属性值)
            String value = System.getProperty(key);
            System.out.println(key + "--->" + value);
        }
    }
}
```

#### currentTimeMillis()

```java
public class system{
    public static void main(String[] args){
        long startTime = System.currentTimeMillis();
        int sum = 0;
        for (int i = 0;i < 100000000; i++){
            sum += i; 
        }
        long endTime = System.currentTimeMillis();//循环结束后当前的时间
        System.out.println("程序运行的时间为:" + (endTime - startTime) + "毫秒");
    }
}
//程序运行的时间为:32毫秒
```

#### arraycopy (Object src, int secPos, Object dest, int destPos, int length)

用于将一个数组中的元素快速拷贝到另一个数组:

- src：表示源数组
- dest：表示目标数组
- srcPos：表示**源数组中拷贝元素的起始位置**。
- destPos：表示**拷贝到的目标数组的起始位置**。
- length：表示**拷贝元素的个数**。

```Java
public class system{
	public static void main(String[] args){
        int[] fromArray = {101, 102, 103, 104, 105, 106};//源数组
        int[] toArray = {201, 202, 203, 204, 205, 206};//目标数组
        System.arraycopy(fromArray, 2, toArray, 3, 2);//拷贝数组元素
        for (int i = 0; i < toArray.length; i++){
            System.out.println(i + "：" + toArray[i]);
        }
    }
}
/*输出:
0：201
1：202
2：203
3：103
4：104
5：206
*/
```

### runtime类

Runtime类用于表示**虚拟机运行时的状态**，用于**封装JVM虚拟机进程**。

每次使用Java命令启动虚拟机都对应一个Runtime实例，并且**只有一个实例**。

对象不可以直接实例化。获得一个Runtime实例，只能通过以下方式:

```java
Runtime run = Runtime.getRuntime();
```

#### 实例

```java
public class runtime{
    public static void main(String[] args){
        Runtime rt = Runtime.getRuntime(); //获取
        System.out.println("处理器的个数："+ rt.availableProcessors() +"个");
        System.out.println("空闲内存数量："+ rt.freeMemory()/1024/1024 +"M");
        System.out.println("最大可用内存数量："+ rt.maxMemory()/1024/1024 +"M");
    }
}
/*输出:
处理器的个数：8个
空闲内存数量：117M
最大可用内存数量：1787M
*/
```

#### exec()方法

```Java
public class runtime{
    public static void main(String[] args) throws IOException{
        Runtime rt = Runtime.getRuntime(); //获取
        rt.exec("notepad.exe");//打开记事本
    }
}
```

#### destory()方法

```Java
public class runtime{
    public static void main(String[] args) throws IOException, InterruptedException{
        Runtime rt = Runtime.getRuntime(); //创建一个Runtime实例对象
        Process process = rt.exec("notepad.exe");//得到表示进程的Process对象
        Thread.sleep(3000);  //休眠3秒
        process.destroy(); //杀掉进程
    }
}
```

## Java Arrays 类

能**方便地操作数组**，它提供的所有方法都是**静态**的。

具有以下功能：

- 给数组赋值：通过 **fill** 方法。
- 对数组排序：通过 **sort** 方法,按升序。
- 比较数组：通过 **equals** 方法比较数组中元素值是否相等。
- 查找数组元素：通过 **binarySearch** 方法能对排序好的数组进行二分查找法操作。

### toString()方法

```java
public static String toString(int[] a) 
```

返回指定数组内容的**字符串表示形式**，**方便输出**

```java
public static void main(String[] args) {
  // 定义int 数组
  int[] arr  =  {2,34,35,4,657,8,69,9};
  // 打印数组,输出地址值
  System.out.println(arr); // [I@2ac1fdc4
  // 数组内容转为字符串
  String s = Arrays.toString(arr);
  // 打印字符串,输出内容
  System.out.println(s); // [2, 34, 35, 4, 657, 8, 69, 9]
}
```

### sort方法

```java
public static void sort(int[]  a) 
```

对指定的 int 型数组按数字升序进行排序

```java
public static void main(String[] args) {
  	// 定义int 数组
	int[] arr  =  {24, 7, 5, 48, 4, 46, 35, 11, 6, 2};
  	System.out.println("排序前:"+ Arrays.toString(arr)); // 排序前:[24, 7, 5, 48, 4, 46, 35, 11, 6, 2]
  	// 升序排序
  	Arrays.sort(arr);
  	System.out.println("排序后:"+ Arrays.toString(arr));// 排序后:[2, 4, 5, 6, 7, 11, 24, 35, 46, 48]
}
```

### binarysearch()方法

```java
public static int binarySearch(int[] a,int key)
```

 使用**二分搜索法**来搜索**指定的 int 型数组**，以获得指定的值。必须在进行此**调用之前**对**数组进行排序**（通过 **sort(int[])** 方法）。如果没有对数组进行排序，则结果是不确定的。如果数组包含多个带有指定值的元素，则无法保证找到的是哪一个。

返回**排序后**的**所在位置**。

```java
public static void main(String[] args){
	System.out.println(arr);
    System.out.println(Arrays.binarySearch(arr,7));
    System.out.println("------------");
    for (int i : arr) {
    	System.out.println(i);
    }
    System.out.println("----------------");
    //先排序
    Arrays.sort(arr);
    for (int i : arr) {
    	System.out.println(i);
    }
    System.out.println("-----------");
    //二分查找法
    int i = Arrays.binarySearch(arr,7);
    System.out.println(i);
}    
```

### fill()方法

```java
public static void fill(int[] a,int val)
```

 将指定的 int 值分配给指定 int 型数组的**每个元素**。

```java
int[] arr = {1,2,45,56,67,6,7,8};
Arrays.fill(arr,9);
//输出:[9, 9, 9, 9, 9, 9, 9, 9]
```

### equals()方法

```java
public static boolean equals(byte[] a, byte[] a2)
```

如果两个指定的 **byte 型数组**彼此相等，则返回 **true**。如果两个数组包含**相同数量**的元素，并且两个数组中的**所有相应元素对都是相等**的，则认为这两个数组是**相等**的。此外，如果两个数组引用都为 **null**，则认为它们是**相等**的。

## Java 日期 & 时间

java.util 包提供了 **Date 类**来封装当前的日期和时间。 

第一个构造函数使用**当前日期和时间**来初始化对象。

```java
Date( )
```

第二个构造函数**接收一个参数**，该参数是从**1970年1月1日起的毫秒数**。

```Java
Date(long millisec)
```

### Date对象的方法:

| 方法                            | 描述                                                         |
| :------------------------------ | :----------------------------------------------------------- |
| **boolean after(Date date)**    | 若当调用此方法的Date对象在指定日期之后返回true,否则返回false。 |
| **boolean before(Date date)**   | 若当调用此方法的Date对象在指定日期之前返回true,否则返回false。 |
| **Object clone( )**             | 返回此对象的副本。                                           |
| **int compareTo(Date date)**    | 比较当调用此方法的Date对象和指定日期。两者相等时候返回0。调用对象在指定日期之前则返回负数。调用对象在指定日期之后则返回正数。 |
| **int compareTo(Object obj)**   | 若obj是Date类型则操作等同于compareTo(Date) 。否则它抛出ClassCastException。 |
| **boolean equals(Object date)** | 当调用此方法的Date对象和指定日期相等时候返回true,否则返回false。 |
| **long getTime( )**             | 返回自 1970 年 1 月 1 日 00:00:00 GMT 以来此 Date 对象表示的毫秒数。 |
| **int hashCode( )**             | 返回此对象的哈希码值。                                       |
| **void setTime(long time)**     | 用自1970年1月1日00:00:00 GMT以后time毫秒数设置时间和日期。   |
| **String toString( )**          | 把此 Date 对象转换为以下形式的 String： dow mon dd hh:mm:ss zzz yyyy 其中： dow 是一周中的某一天 (Sun, Mon, Tue, Wed, Thu, Fri, Sat)。 |

**获取当前时间**

```Java
import java.util.Date;
  
public class DateDemo {
   public static void main(String args[]) {
       // 初始化 Date 对象
       Date date = new Date();
        
       // 使用 toString() 函数显示日期时间
       System.out.println(date.toString());
   }
}
//Sat Oct 17 20:03:24 CST 2020
```

### 日期比较

Java使用以下三种方法来比较两个日期：

- 使用 **getTime()** 方法获取两个日期（**自1970年1月1日经历的毫秒数值**），然后比较这两个值。
- 使用方法 **before()**，**after()** 和 **equals()**。例如，一个月的12号比18号早，则 new Date(99, 2, 12).before(new Date (99, 2, 18)) 返回true。
- 使用 **compareTo()** 方法，它是由 **Comparable 接口**定义的，**Date 类实现了这个接口**。

### SimpleDateFormat 格式化日期

**SimpleDateFormat** 是一个以**语言环境敏感**的方式来格式化和分析日期的类。**SimpleDateFormat** 允许你选择**任何用户自定义日期时间**格式来运行

```java
import java.util.*;
import java.text.*;
 
public class DateDemo {
   public static void main(String args[]) {
      Date dNow = new Date( );
      SimpleDateFormat ft = new SimpleDateFormat ("yyyy-MM-dd hh:mm:ss");//字符可随意交换
      System.out.println("当前时间为: " + ft.format(dNow));
   }
}
//输出:2020-10-20 19:25:08
```

#### 日期和时间的格式化编码

| **字母** | **描述**                 | **示例**                |
| -------- | :----------------------- | :---------------------- |
| **G**    | 纪元标记                 | AD                      |
| **y**    | 四位年份                 | 2001                    |
| **M**    | 月份                     | July or 07              |
| **d**    | 一个月的日期             | 10                      |
| **h**    | A.M./P.M. (1~12)格式小时 | 12                      |
| **H**    | 一天中的小时 (0~23)      | 22                      |
| **m**    | 分钟数                   | 30                      |
| **s**    | 秒数                     | 55                      |
| **S**    | 毫秒数                   | 234                     |
| **E**    | 星期几                   | Tuesday                 |
| **D**    | 一年中的日子             | 360                     |
| **F**    | 一个月中第几周的周几     | 2 (second Wed. in July) |
| **w**    | 一年中第几周             | 40                      |
| **W**    | 一个月中第几周           | 1                       |
| **a**    | A.M./P.M. 标记           | PM                      |
| **k**    | 一天中的小时(1~24)       | 24                      |
| **K**    | A.M./P.M. (0~11)格式小时 | 10                      |
| **z**    | 时区                     | Eastern Standard Time   |
| **'**    | 文字定界符               | Delimiter               |
| **"**    | 单引号                   | `                       |

### printf格式化日期

使用**两个字母格式**，它以 **%t** 开头并且以下面表格中的**一个字母**结尾。

```Java
import java.util.Date;
 
public class DateDemo {
  public static void main(String args[]) {
     // 初始化 Date 对象
     Date date = new Date();
 
     //c的使用  
    System.out.printf("全部日期和时间信息：%tc%n",date);          
    //f的使用  
    System.out.printf("年-月-日格式：%tF%n",date);  
    //d的使用  
    System.out.printf("月/日/年格式：%tD%n",date);  
    //r的使用  
    System.out.printf("HH:MM:SS PM格式（12时制）：%tr%n",date);  
    //t的使用  
    System.out.printf("HH:MM:SS格式（24时制）：%tT%n",date);  
    //R的使用  
    System.out.printf("HH:MM格式（24时制）：%tR",date);  
  }
}
/*输出:
全部日期和时间信息：星期一 九月 10 10:43:36 CST 2012  
年-月-日格式：2012-09-10  
月/日/年格式：09/10/12  
HH:MM:SS PM格式（12时制）：10:43:36 上午  
HH:MM:SS格式（24时制）：10:43:36  
HH:MM格式（24时制）：10:43
*/
```

如果**提供日期多次格式化**是一种不好的做法。一个**格式字符串**可以指示要**格式化的参数的索引**。

**索引**必须**紧跟**在**％**之后，并必须由**$**终止

```java
import java.util.Date;

public class DateDemo {

   public static void main(String args[]) {
       // Instantiate a Date object
       Date date = new Date();

       // display time and date using toString()
       System.out.printf("%1$s %2$tB %2$td, %2$tY", 
                         "Due date:", date);
   }
}
//输出:Due date: 五月 31, 2017
```

也可以使用**<**标志。则表示**相同的参数**，根据前述格式规范，应再次使用。

```java
import java.util.Date;

public class DateDemo {

   public static void main(String args[]) {
       // Instantiate a Date object
       Date date = new Date();

       // display formatted date
       System.out.printf("%s %tB %<te, %<tY", 
                         "Due date:", date);
   }
}
//这将产生以下结果:
Due date: 五月 31, 2017
```

定义**日期格式的转换符**可以使日期通过**指定的转换符**生成**新字符串**。

```Java
import java.util.*;
  
public class DateDemo {
   public static void main(String args[]) {
       Date date=new Date();                                      
        //b的使用，月份简称  
        String str=String.format(Locale.US,"英文月份简称：%tb",date);       
        System.out.println(str);                                                                              
        System.out.printf("本地月份简称：%tb%n",date);  
        //B的使用，月份全称  
        str=String.format(Locale.US,"英文月份全称：%tB",date);  
        System.out.println(str);  
        System.out.printf("本地月份全称：%tB%n",date);  
        //a的使用，星期简称  
        str=String.format(Locale.US,"英文星期的简称：%ta",date);  
        System.out.println(str);  
        //A的使用，星期全称  
        System.out.printf("本地星期的简称：%tA%n",date);  
        //C的使用，年前两位  
        System.out.printf("年的前两位数字（不足两位前面补0）：%tC%n",date);  
        //y的使用，年后两位  
        System.out.printf("年的后两位数字（不足两位前面补0）：%ty%n",date);  
        //j的使用，一年的天数  
        System.out.printf("一年中的天数（即年的第几天）：%tj%n",date);  
        //m的使用，月份  
        System.out.printf("两位数字的月份（不足两位前面补0）：%tm%n",date);  
        //d的使用，日（二位，不够补零）  
        System.out.printf("两位数字的日（不足两位前面补0）：%td%n",date);  
        //e的使用，日（一位不补零）  
        System.out.printf("月份的日（前面不补0）：%te",date);  
   }
}
/*输出:
英文月份简称：May
本地月份简称：五月
英文月份全称：May
本地月份全称：五月
英文星期的简称：Thu
本地星期的简称：星期四
年的前两位数字（不足两位前面补0）：20
年的后两位数字（不足两位前面补0）：17
一年中的天数（即年的第几天）：124
两位数字的月份（不足两位前面补0）：05
两位数字的日（不足两位前面补0）：04
月份的日（前面不补0）：4
*/
```

#### **日期和时间转换字符**

| 字符  | 描述                                 | 例子                         |
| ----- | ------------------------------------ | ---------------------------- |
| **c** | 完整的日期和时间                     | Mon May 04 09:51:52 CDT 2009 |
| **F** | ISO 8601 日期                        | 2004-02-09                   |
| **D** | U.S. 格式时间 (月/日/年)             | 02/09/2004                   |
| **T** | 24-时制                              | 18:05:19                     |
| **r** | 12-时制                              | 06:05:19 pm                  |
| **R** | 24-时制，无秒                        | 18:05                        |
| **Y** | 四位数年份 (用前行零列)              | 2004                         |
| **y** | 年份的后两位数(用前行零列)           | 04                           |
| **C** | 年份的前两位(用前行零列)             | 20                           |
| **B** | 完整月份名称                         | February                     |
| **b** | 缩写月份名称                         | Feb                          |
| **m** | 两位数月份 (用前行零列)              | 02                           |
| **d** | 两位数日期 (用前行零列)              | 03                           |
| **e** | 两位数日期(无前行零列)               | 9                            |
| **A** | 完整星期名称                         | Monday                       |
| **a** | 缩写星期名称                         | Mon                          |
| **j** | 年中的三位数天数(用前行零列)         | 069                          |
| **H** | 两位数小时(用前行零列), 00 和 23之间 | 18                           |
| **k** | 两位数小时(无前行零列), 0 和 23 之间 | 18                           |
| **I** | 两位数小时 (用前行零列), 01和12之间  | 06                           |
| **l** | 两位数小时 (无前行零列), 1 和12之间  | 6                            |
| **M** | 两位数分钟 (用前行零列)              | 05                           |
| **S** | 两位数秒钟(用前行零列)               | 19                           |
| **L** | 三位数毫秒（用前行零列)              | 047                          |
| **N** | 九位数纳秒 (用前行零列)              | 047000000                    |
| **P** | 大写上下午标记                       | PM                           |
| **p** | 小写上下午标记                       | pm                           |
| **z** | RFC 822 从GMT数字抵消                | -0800                        |
| **Z** | 时区                                 | PST                          |
| **s** | 从 1970-01-01 00:00:00 的秒数GMT     | 1078884319                   |
| **Q** | 从 1970-01-01 00:00:00 的毫秒数GMT   | 1078884319047                |

### 字符串转换日期

**SimpleDateFormat** 类有一些**附加的方法**，特别是**parse()**，它试图按照给定的**SimpleDateFormat** 对象的**格式化存储**来**解析字符串**。

```java
import java.util.*;
import java.text.*;

public class DateDemo {
   public static void main(String args[]) {
      SimpleDateFormat ft = new SimpleDateFormat ("yyyy-MM-dd"); 

      String input = args.length == 0 ? "1818-11-11" : args[0]; 

      System.out.print(input + " Parses as "); 

      Date t; 

      try { 
          t = ft.parse(input); 
          System.out.println(t); 
      } catch (ParseException e) { 
          System.out.println("Unparseable using " + ft); 
      }
   }
}
/*输出:
$ java DateDemo
1818-11-11 Parses as Wed Nov 11 00:00:00 GMT 1818
$ java DateDemo 2007-12-01
2007-12-01 Parses as Sat Dec 01 00:00:00 GMT 2007
*/
```

Java 休眠(sleep)

**sleep()**使**当前线程**进入**停滞**状态（**阻塞当前线程**），**让出CPU的使用**、目的是**不让当前线程独自霸占**该进程所获的**CPU资源**，以**留一定时间**给**其他线程**执行的机会。

```java
import java.util.*;

public class SleepDemo {
   public static void main(String args[]) {
      try { 
         System.out.println(new Date( ) + "\n"); 
         Thread.sleep(1000*3); //休眠3秒钟 
         System.out.println(new Date( ) + "\n"); 
      } catch (Exception e) { 
          System.out.println("Got an exception!"); 
      }
   }
}
/*输出:
Wed May 31 15:37:56 CST 2017
Wed May 31 15:37:59 CST 2017
*/
```

### 测量时间间隔

以**毫秒**为单位

```Java
import java.util.*;
  
public class DiffDemo {
 
   public static void main(String args[]) {
      try {
         long start = System.currentTimeMillis( );
         System.out.println(new Date( ) + "\n");
         Thread.sleep(5*60*10);
         System.out.println(new Date( ) + "\n");
         long end = System.currentTimeMillis( );
         long diff = end - start;
         System.out.println("Difference is : " + diff);
      } catch (Exception e) {
         System.out.println("Got an exception!");
      }
   }
}
/*输出:
Mon Oct 19 09:09:41 CST 2020

Mon Oct 19 09:09:44 CST 2020

Difference is : 3019
*/
```

### Calendar类

| 常量                  | 描述                           |
| :-------------------- | :----------------------------- |
| Calendar.YEAR         | 年份                           |
| Calendar.MONTH        | 月份                           |
| Calendar.DATE         | 日期                           |
| Calendar.DAY_OF_MONTH | 日期，和上面的字段意义完全相同 |
| Calendar.HOUR         | 12小时制的小时                 |
| Calendar.HOUR_OF_DAY  | 24小时制的小时                 |
| Calendar.MINUTE       | 分钟                           |
| Calendar.SECOND       | 秒                             |
| Calendar.DAY_OF_WEEK  | 星期几                         |

#### set设置

```java
Calendar c1 = Calendar.getInstance();
c1.set(2009, 6, 12);//把Calendar对象c1的年月日分别设这为：2009、6、12
//public void set(int field,int value)
//把 c1对象代表的日期设置为10号，其它所有的数值会被重新计算
c1.set(Calendar.DATE,10);
c1.set(Calendar.YEAR,2008);
```

#### **add设置**

```Java
Calendar c1 = Calendar.getInstance();
//把c1对象的日期加上10，也就是c1也就表示为10天后的日期，其它所有的数值会被重新计算
c1.add(Calendar.DATE, 10);
c1.add(Calendar.DATE, -10);
```

#### Calendar类对象信息的获得

```Java
Calendar c1 = Calendar.getInstance();
// 获得年份
int year = c1.get(Calendar.YEAR);
// 获得月份
int month = c1.get(Calendar.MONTH) + 1;
// 获得日期
int date = c1.get(Calendar.DATE);
// 获得小时
int hour = c1.get(Calendar.HOUR_OF_DAY);
// 获得分钟
int minute = c1.get(Calendar.MINUTE);
// 获得秒
int second = c1.get(Calendar.SECOND);
// 获得星期几（注意（这个与Date类是不同的）：1代表星期日、2代表星期一、3代表星期二，以此类推）
int day = c1.get(Calendar.DAY_OF_WEEK);
```

### GregorianCalendar类

**Calendar**类实现了**公历日历**，**GregorianCalendar**是Calendar类的一个**具体实现**。

#### **GregorianCalendar**对象的构造方法

| 构造函数                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| GregorianCalendar()                                          | 在默认时区与默认语言环境使用当前时间构造默认的GregorianCalendar。 |
| GregorianCalendar(int year, int month, int date)             | 在默认时区设置默认的语言环境用给定的日期构造一个GregorianCalendar |
| GregorianCalendar(int year, int month, int date, int hour, int minute) | 用给定的日期和时间设置为与默认语言环境的默认时区构造一个GregorianCalendar。 |
| GregorianCalendar(int year, int month, int date, int hour, int minute, int second) | 用给定的日期和时间设置为与默认语言环境的默认时区构造一个 GregorianCalendar |
| GregorianCalendar(Locale aLocale)                            | 基于当前时间与给定语言环境的默认时区构建一个GregorianCalendar。 |
| GregorianCalendar(TimeZone zone)                             | 基于当前时间，使用默认的语言环境在给定的时区构建一个GregorianCalendar。 |
| GregorianCalendar(TimeZone zone, Locale aLocale)             | 基于当前时间与给定语言环境的给定时区构建一个GregorianCalendar。 |

#### GregorianCalendar类的方法

| 方法                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| void add(int field, int amount)                              | 基于日历的规则，以给定的时间字段添加指定（有符号的）时间量。 |
| protected void computeFields()                               | 将UTC转换为毫秒时间字段值.                                   |
| protected void computeTime()                                 | 覆盖日历转换时间域值为UTC的毫秒.                             |
| boolean equals(Object obj)                                   | 这个GregorianCalendar与一个对象引用比较.                     |
| int get(int field)                                           | 获取给定时间域的值.                                          |
| int getActualMaximum(int field)                              | 返回该字段可能的最大值，给定到当前的日期.                    |
| int getActualMinimum(int field)                              | 返回该字段可能具有的最小值，给定当前的日期.                  |
| int getGreatestMinimum(int field)                            | 对于给定的字段中返回高最低值（如果有变化）.                  |
| Date getGregorianChange()                                    | 获取公历更改日期.                                            |
| int getLeastMaximum(int field)                               | 对于给定的字段返回最低的最大值，如果有变化.                  |
| int getMaximum(int field)                                    | 返回给定字段中的最大值.                                      |
| Date getTime()                                               | 获取日历的当前时间.                                          |
| long getTimeInMillis()                                       | 获取日历的当前时间长.                                        |
| TimeZone getTimeZone()                                       | 获取时区.                                                    |
| int getMinimum(int field)                                    | 返回给定字段中的最小值.                                      |
| int hashCode()                                               | 重写hashCode.                                                |
| boolean isLeapYear(int year)                                 | 确定给定年份是闰年.                                          |
| void roll(int field, boolean up)                             | 加上或减去（上/下）的时间在给定的时间字段一个单元，不更改更大的字段. |
| void set(int field, int value)                               | 设置时间字段与给定值.                                        |
| void set(int year, int month, int date)                      | 设置为年，月，日的值.                                        |
| void set(int year, int month, int date, int hour, int minute) | 设置为年，月，日，小时和分钟值.                              |
| void set(int year, int month, int date, int hour, int minute, int second) | 设置为字段的年，月，日，小时，分钟和秒的值.                  |
| void setGregorianChange(Date date)                           | 设置GregorianCalendar更改日期.                               |
| void setTime(Date date)                                      | 设置日历的当前时间与给定日期.                                |
| void setTimeInMillis(long millis)                            | 从给定long值设置日历的当前时间.                              |
| void setTimeZone(TimeZone value)                             | 将时区设置与给定的时区值.                                    |
| String toString()                                            | 返回此日历的字符串表示形式.                                  |

```Java
import java.util.*;
  
public class GregorianCalendarDemo {
 
   public static void main(String args[]) {
      String months[] = {
      "Jan", "Feb", "Mar", "Apr",
      "May", "Jun", "Jul", "Aug",
      "Sep", "Oct", "Nov", "Dec"};
      
      int year;
      // 初始化 Gregorian 日历
      // 使用当前时间和日期
      // 默认为本地时间和时区
      GregorianCalendar gcalendar = new GregorianCalendar();
      // 显示当前时间和日期的信息
      System.out.print("Date: ");
      System.out.print(months[gcalendar.get(Calendar.MONTH)]);
      System.out.print(" " + gcalendar.get(Calendar.DATE) + " ");
      System.out.println(year = gcalendar.get(Calendar.YEAR));
      System.out.print("Time: ");
      System.out.print(gcalendar.get(Calendar.HOUR) + ":");
      System.out.print(gcalendar.get(Calendar.MINUTE) + ":");
      System.out.println(gcalendar.get(Calendar.SECOND));
      
      // 测试当前年份是否为闰年
      if(gcalendar.isLeapYear(year)) {
         System.out.println("当前年份是闰年");
      }
      else {
         System.out.println("当前年份不是闰年");
      }
   }
}
/*输出:
Date: Apr 22 2009
Time: 11:25:27
当前年份不是闰年
*/
```

## Java 正则表达式

正则表达式定义了**字符串**的模式。

正则表达式可以用来搜索、编辑或处理**文本**。

**java.util.regex** 包主要包括以下三个类：

- **Pattern 类**：

  pattern 对象是一个正则表达式的编译表示。Pattern 类**没有公共构造方法**。要创建一个 Pattern 对象，你必须首先**调用其公共静态编译方法**，它返回一个 Pattern 对象。该方法**接受一个正则表达式**作为它的**第一个参数**。

- **Matcher 类**：

  Matcher 对象是对输入字符串进行**解释**和**匹配**操作的**引擎**。与Pattern 类一样，Matcher 也**没有公共构造方法**。你需要**调用 Pattern 对象的 matcher 方法**来获得一个 Matcher 对象。

- **PatternSyntaxException**：

  PatternSyntaxException 是一个非强制异常类，它表示一个**正则表达式模式中的语法错误**。

```java
import java.util.regex.*;
 
class RegexExample1{
   public static void main(String args[]){
      String content = "I am noob from runoob.com.";
 
      String pattern = ".*runoob.*";
 
      boolean isMatch = Pattern.matches(pattern, content);
      System.out.println("字符串中是否包含了 'runoob' 子字符串? " + isMatch);
   }
}
//输出:字符串中是否包含了 'runoob' 子字符串? true
```

#### 捕获组

捕获组是把**多个字符**当**一个单独单元**进行处理的方法，它通过对**括号内**的字符**分组**来创建。

捕获组是通过**从左至右**计算其开括号来编号。例如，在表达式（（A）（B（C））），有四个这样的组：

- ((A)(B(C)))
- (A)
- (B(C))
- (C)

可以通过调用 **matcher** 对象的 **groupCount** 方法来查看表达式有**多少个分组**。**groupCount** 方法返回一个 **int 值**，表示matcher对象当前有**多个捕获组**。

还有一个特殊的组**（group(0)）**，它总是代表**整个表达式**。该组**不包括**在 **groupCount** 的**返回值**中。

以 **(?)** 开头的组是纯的**非捕获组**，它**不捕获文本**，也**不针对组合计进行计数**。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
 
public class RegexMatches
{
    public static void main( String args[] ){
 
      // 按指定模式在字符串查找
      String line = "This order was placed for QT3000! OK?";
      String pattern = "(\\D*)(\\d+)(.*)";
 
      // 创建 Pattern 对象
      Pattern r = Pattern.compile(pattern);
 
      // 现在创建 matcher 对象
      Matcher m = r.matcher(line);
        
      System.out.println(m.groupCount());//捕获组数量
      if (m.find( )) {
         System.out.println("Found value: " + m.group(0) );
         System.out.println("Found value: " + m.group(1) );
         System.out.println("Found value: " + m.group(2) );
         System.out.println("Found value: " + m.group(3) ); 
      } else {
         System.out.println("NO MATCH");
      }
   }
}
/*输出:
3
Found value: This order was placed for QT3000! OK?
Found value: This order was placed for QT
Found value: 3000
Found value: ! OK?
*/
```

#### 正则表达式语法

在其他语言中，**`\\`** 表示：**我想要在正则表达式中插入一个普通的（字面上的）反斜杠，请不要给它任何特殊的意义。**

在 Java 中，**`\\`** 表示：**我要插入一个正则表达式的反斜线，所以其后的字符具有特殊的意义。**

在其他的语言中，一个反斜杠 **`\`** 就足以具有转义的作用，而在 Java 中正则表达式中则需要有**两个反斜杠**才能被解析为其他语言中的**转义作用**。也可以简单的理解在 Java 的正则表达式中，两个 **`\\`** 代表其他语言中的一个 **`\`**，这也就是为什么表示一位数字的正则表达式是 **`\\d`**，而表示一个普通的反斜杠是 **`\\\\`**。

| 字符          | 说明                                                         |
| :------------ | :----------------------------------------------------------- |
| \             | 将**下一字符**标记为**特殊字符**、**文本**、**反向引用**或**八进制转义符**。例如，**"n"匹配字符"n"。"\n"匹配换行符。序列"`\\`"匹配"`\`"，"\("匹配"("。** |
| ^             | 匹配**输入字符串开始**的位置。如果设置了 **RegExp** 对象的 **Multiline** 属性，**^** 还会与"\n"或"\r"之**后**的位置匹配。 |
| $             | 匹配**输入字符串结尾**的位置。如果设置了 **RegExp** 对象的 **Multiline** 属性，**$** 还会与"\n"或"\r"之**前**的位置匹配。 |
| *             | **零次或多次匹配**前面的**字符**或**子表达式**。例如，**zo* 匹配"z"和"zoo"**。***** 等效于 **{0,}**。 |
| +             | **一次或多次匹配**前面的**字符**或**子表达式**。例如，**"zo+"与"zo"和"zoo"匹配，但与"z"不匹配**。**+** 等效于 **{1,}**。 |
| ?             | **零次或一次匹配**前面的**字符**或**子表达式**。例如，"do(es)?"匹配"do"或"does"中的"do"。**?** 等效于 **{0,1}**。 |
| {*n*}         | ***n*** 是**非负整数**。**正好**匹配 *n* 次。例如，**"o{2}"与"Bob"中的"o"不匹配，但与"food"中的两个"o"匹配**。 |
| {*n*,}        | ***n*** 是**非负整数**。**至少**匹配 *n* 次。例如，"o{2,}"不匹配"Bob"中的"o"，而匹配"foooood"中的所有 o。"o{1,}"等效于"o+"。"o{0,}"等效于"o*"。 |
| {*n*,*m*}     | ***m*** 和 ***n*** 是**非负整数**，其中 ***n* <= *m***。匹配**至少 *n* 次**，**至多 *m* 次**。例如，**"o{1,3}"匹配"fooooood"中的头三个 o**。'**o{0,1}**' 等效于 '**o?**'。注意：**不能将空格插入逗号和数字之间**。 |
| ？            | 当**此字符紧随任何其他限定符（*，+，?，{n}，{n,}，{n,m}）之后**时，匹配模式是"**非贪心的**"。"**非贪心的"模式**匹配搜索到的、**尽可能短**的**字符串**，而**默认的"贪心的"模式**匹配搜索到的、**尽可能长的字符串**。例如，在**字符串"oooo"中，"o+?"只匹配单个"o"，而"o+"匹配所有"o"。** |
| **.**         | 匹配**除"\r\n"之外**的**任何单个字符**。若要**匹配包括"\r\n"在内的任意字符，请使用诸如"[\s\S]"之类的模式。** |
| (*pattern*)   | 匹配 ***pattern*** 并**捕获**该匹配的**子表达式**。可以使用 **$0…$9** 属性从结果"匹配"集合中检索捕获的匹配。若要匹配括号字符 ( )，请使用"`\(`"或者"`\)`"。 |
| (?:*pattern*) | 匹配 ***pattern*** 但**不捕获**该匹配的**子表达式**，即它是一个**非捕获匹配**，**不存储供以后使用的匹配**。这对于用"**or"字符 (\|) 组合**模式部件的情况很有用。例如，'**industr(?:y\|ies) 是比 'industry\|industries' 更经济的表达式**。 |
| (?=*pattern*) | 执行**正向预测先行搜索**的**子表达式**，该表达式匹配**处于匹配 *pattern* 的字符串的起始点的字符串**。它是一个**非捕获匹配**，即**不能捕获供以后使用的匹配**。例如，'**Windows (?=95\|98\|NT\|2000)' 匹配"Windows 2000"中的"Windows"，但不匹配"Windows 3.1"中的"Windows**"。预测先行不占用字符，即发生匹配后，**下一匹配的搜索紧随上一匹配之后**，而不是在组成预测先行的字符后。 |
| (?!*pattern*) | 执行**反向预测先行搜索**的**子表达式**，该表达式匹配**不处于匹配 *pattern* 的字符串的起始点的搜索字符串**。它是一个**非捕获匹配**，即**不能捕获供以后使用的匹配**。例如，'**Windows (?!95\|98\|NT\|2000)' 匹配"Windows 3.1"中的 "Windows"，但不匹配"Windows 2000"中的"Windows"**。预测先行不占用字符，即发生匹配后，**下一匹配的搜索紧随上一匹配之后**，而不是在组成预测先行的字符后。 |
| *x*\|*y*      | **匹配 *x* 或 *y***。例如，'**z\|food' 匹配"z"或"food"**。**'(z\|f)ood' 匹配"zood"或"food"**。 |
| [*xyz*]       | **字符集**。匹配**包含的任一字符**。例如，"**[abc]"匹配"plain"中的"a"**。 |
| [^*xyz*]      | **反向字符集**。匹配**未包含的任何字符**。例如，"**[^abc]"匹配"plain"中"p"，"l"，"i"，"n"**。 |
| [*a-z*]       | **字符范围**。匹配**指定范围内的任何字符**。例如，"**[a-z]"匹配"a"到"z"范围内的任何小写字母**。 |
| [^*a-z*]      | **反向范围字符**。匹配**不在指定的范围内的任何字符**。例如，"**[^a-z]"匹配任何不在"a"到"z"范围内的任何字符**。 |
| \b            | 匹配一个**字边界**，即**字与空格间的位置**。例如，"**er\b"匹配"never"中的"er"，但不匹配"verb"中的"er"**。 |
| \B            | **非字边界匹配**。"**er\B"匹配"verb"中的"er"，但不匹配"never"中的"er"**。 |
| \c*x*         | 匹配 ***x* 指示的控制字符**。例如，**\cM 匹配 Control-M 或回车符**。***x* 的值必须在 A-Z 或 a-z 之间**。如果**不是这样，则假定 c 就是"c"字符本身**。 |
| \d            | **数字字符匹配**。等效于 **[0-9]**。                         |
| \D            | **非数字字符匹配**。等效于 **[^0-9]**。                      |
| \f            | **换页符匹配**。等效于 **\x0c** 和 **\cL**。                 |
| \n            | **换行符匹配**。等效于 **\x0a** 和 **\cJ**。                 |
| \r            | 匹配一个**回车符**。等效于 **\x0d** 和 **\cM**。             |
| \s            | 匹配**任何空白字符**，包括**空格**、**制表符**、**换页符**等。与 **[ \f\n\r\t\v]** 等效。 |
| \S            | 匹配**任何非空白字符**。与 **[^ \f\n\r\t\v]** 等效。         |
| \t            | **制表符匹配**。与 **\x09** 和 **\cI** 等效。                |
| \v            | **垂直制表符匹配**。与 **\x0b** 和 **\cK** 等效。            |
| \w            | 匹配**任何字类字符**，**包括下划线**。与"**[A-Za-z0-9_]**"等效。 |
| \W            | 与**任何非单词字符**匹配。与"**[^A-Za-z0-9_]**"等效。        |
| \x*n*         | **匹配 *n***，此处的 ***n*** 是一个**十六进制转义码**。十六进制转义码**必须正好是两位数长**。例如，"**\x41"匹配"A"**。**"\x041"与"\x04"&"1"等效**。**允许在正则表达式中使用 ASCII 代码**。 |
| \num          | **匹配 *num***，此处的 ***num*** 是一个**正整数**。到**捕获匹配的反向引用**。例如，**"(.)\1"匹配两个连续的相同字符**。 |
| \n            | 标识一个**八进制转义码**或**反向引用**。如果 ***\n*** 前面**至少有 *n* 个捕获子表达式**，那么 ***n* 是反向引用**。否则，如果 ***n* 是八进制数 (0-7)**，那么 ***n* 是八进制转义码**。 |
| \nm           | 标识一个**八进制转义码**或**反向引用**。如果 ***\nm*** 前面**至少有 *nm* 个捕获子表达式**，那么 ***nm* 是反向引用**。如果 ***\nm*** 前面**至少有 *n* 个捕获**，则 ***n* 是反向引用**，**后面跟有字符 *m***。如果**两种前面的情况都不存在**，则 ***\nm*** 匹配**八进制值 *nm***，其中 ***n* 和 *m* 是八进制数字 (0-7)**。 |
| \nml          | 当 ***n*** 是**八进制数 (0-3)**，***m*** 和 ***l*** 是**八进制数 (0-7)** 时，匹配**八进制转义码 *nml***。 |
| \u*n*         | 匹配 ***n***，其中 ***n*** 是以**四位十六进制**数表示的 **Unicode 字符**。例如，**\u00A9 匹配版权符号 (©)**。 |

#### Pattern类的方法

**Pattern**类用于创建一个**正则表达式**,也可以说创建一个匹配模式,它的**构造方法是私有的,不可以直接创建**,但可以通过**Pattern.complie(String regex)**简单工厂方法创建一个正则表达式。

```Java
Pattern p=Pattern.compile("\\w+"); 
System.out.println(p.pattern());//返回 \w+
```

**pattern()** 返回**正则表达式的字符串形式**,其实就是返回Pattern.complile(String regex)的**regex参数**。

##### **split() 方法**

Pattern有一个**split(CharSequence input)**方法,用于**分隔字符串**,并返回一个**String**。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class test(){
	public static void main(){
        Pattern p=Pattern.compile("\\d+"); 
		String[] str=p.split("我的QQ是:456456我的电话是:0532214我的邮箱是:aaa@aaa.com");
        for (String Str:str){
            System.out.println(Str);
        }
    }
}
/*输出:
我的QQ是:
我的电话是:
我的邮箱是:aaa@aaa.com
*/
```

##### **matcher() 方法**

- **matcher(String regex,CharSequence input):**静态方法,用于**快速匹配字符串**,该方法适合用于**只匹配一次**,且匹配**全部字符串**。
- **matcher(CharSequence input):**返回一个**Matcher对象**。

```Java
Pattern.matches("\\d+","2223");//返回true 
Pattern.matches("\\d+","2223aa");//返回false,需要匹配到所有字符串才能返回true,这里aa不能匹配到 
Pattern.matches("\\d+","22bb23");//返回false,需要匹配到所有字符串才能返回true,这里bb不能匹配到
```

#### Matcher 类的方法

**Matcher类**的**构造方法**也是**私有的**,不能随意创建,只能通过**Pattern.matcher(CharSequence input)方法**得到该类的实例. 

```Java
Pattern p=Pattern.compile("\\d+"); 
Matcher m=p.matcher("22bb23"); 
m.pattern();//返回p 也就是返回该Matcher对象是由哪个Pattern对象的创建的
```

##### matches() , lookingAt() & find() 方法

**Matcher**类提供三个匹配操作方法,三个方法均返回**boolean类型**,当**匹配到时返回true**,**没匹配到则返回false** 。

**matches()**对**整个字符串**进行匹配,只有**整个字符串都匹配了才返回true** 

```Java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class test1 {
    public static void main(String[] args){
        Pattern p=Pattern.compile("\\d+"); 
		Matcher m=p.matcher("22bb23"); 
		m.matches();//返回false,因为bb不能被\d+匹配,导致整个字符串匹配未成功.
        //上面代码等价于Pattern.compile(regex).matcher(input).matches(); 
		Matcher m2=p.matcher("2223"); 
		m2.matches();//返回true,因为\d+匹配到了整个字符串
    }
}
```

**lookingAt()**对**前面的字符串**进行匹配,只有**匹配到的字符串**在**最前面**才返回**true** 

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class test1 {
    public static void main(String[] args){
        Pattern p=Pattern.compile("\\d+"); 
		Matcher m=p.matcher("22bb23"); 
		m.lookingAt();//返回true,因为\d+匹配到了前面的22 
		Matcher m2=p.matcher("aa2223"); 
		m2.lookingAt();//返回false,因为\d+不能匹配前面的aa 
    }
}
```

**find()**对**字符串**进行匹配,匹配到的**字符串可以在任何位置**. 

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class test1 {
    public static void main(String[] args){
        Pattern p=Pattern.compile("\\d+"); 
		Matcher m=p.matcher("22bb23"); 
		m.find();//返回true 
		Matcher m2=p.matcher("aa2223"); 
		m2.find();//返回true 
		Matcher m3=p.matcher("aa2223bb"); 
		m3.find();//返回true 
		Matcher m4=p.matcher("aabb"); 
		m4.find();//返回false 
    }
}
```

##### start() , end() & group() 方法

当使用**matches(),lookingAt(),find()**执行**匹配操作**后,就可以利用以上三个方法**得到更详细的信息：**

- **start()**返回匹配到的**子字符串在字符串中的初始索引位置**. 
- **end()**返回匹配到的**子字符串的最后一个字符**在**字符串中的索引位置**.
- **group()**返回匹配到的**子字符串** 

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class test1 {
    public static void main(String[] args){
        Pattern p=Pattern.compile("\\d+"); 
		Matcher m=p.matcher("aaa2223bb"); 
		m.find();//匹配2223 
		m.start();//返回3 
		m.end();//返回7,返回的是2223后的索引号 
		m.group();//返回2223 
 
		Mathcer m2=m.matcher("2223bb"); 
		m.lookingAt();   //匹配2223 
		m.start();   //返回0,由于lookingAt()只能匹配前面的字符串,所以当使用lookingAt()匹配时,start()方法总是返回0 
		m.end();   //返回4 
		m.group();   //返回2223 
 
		Matcher m3=m.matcher("2223bb"); 
		m.matches();   //匹配整个字符串 
		m.start();   //返回0,
		m.end();   //返回6,matches()匹配所有字符串 
		m.group();   //返回2223bb 
    }
}
```

**start()**,**end()**,**group()**均有一个**重载方法**它们是**start(int i),end(int i),group(int i)**专用于**分组操作**。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
public class test1 {
    public static void main(String[] args){
		Pattern p=Pattern.compile("([a-z]+)(\\d+)"); 
		Matcher m=p.matcher("aaa2223bb"); 
		m.find();   //匹配aaa2223 
		m.groupCount();   //返回2,因为有2组 
		m.start(1);   //返回0 返回第一组匹配到的子字符串在字符串中的索引号 
		m.start(2);   //返回3 
		m.end(1);   //返回3 返回第一组匹配到的子字符串的最后一个字符在字符串中的索引位置. 
		m.end(2);   //返回7 
		m.group(1);   //返回aaa,返回第一组匹配到的子字符串 
		m.group(2);   //返回2223,返回第二组匹配到的子字符串
    }
}
```

**综合**

```java
import java.util.regex.Pattern;
 
public class RegexMatches
{
    private static final String REGEX = "\\bcat\\b";
    private static final String INPUT =
                                    "cat cat cat cattie cat";
 
    public static void main( String args[] ){
       Pattern p = Pattern.compile(REGEX);
       Matcher m = p.matcher(INPUT); // 获取 matcher 对象
       int count = 0;
 
       while(m.find()) {
         count++;
         System.out.println("Match number "+count);
         System.out.println("start(): "+m.start());
         System.out.println("end(): "+m.end());
      }
   }
}
/*输出:
Match number 1
start(): 0
end(): 3
Match number 2
start(): 4
end(): 7
Match number 3
start(): 8
end(): 11
Match number 4
start(): 19
end(): 22
Start 方法返回在以前的匹配操作期间，由给定组所捕获的子序列的初始索引，end 方法最后一个匹配字符的索引加 1。
*/
```

```java
Pattern p=Pattern.compile("\\d+"); 
Matcher m=p.matcher("我的QQ是:456456 我的电话是:0532214 我的邮箱是:aaa123@aaa.com"); 
while(m.find()) { 
     System.out.println(m.group()); 
} 
 
/*输出: 
 
456456 
0532214 
123
*/ 
 
//如将以上while()循环替换成 
 
while(m.find()) { 
     System.out.println(m.group()); 
     System.out.print("start:"+m.start()); 
     System.out.println(" end:"+m.end()); 
} 
 
/*则输出: 
 
456456 
start:6 end:12 
0532214 
start:19 end:26 
123 
start:36 end:39 
*/
```

只有当匹配操作成功,才可以使用**start(),end(),group()**三个方法,否则会抛出**java.lang.IllegalStateException**,也就是当**matches(),lookingAt(),find()**其中任意一个方法返回**true**时,才可以使用。

##### replaceFirst() & replaceAll() 方法

**replaceFirst** 和 **replaceAll** 方法用来替换匹配正则表达式的文本。不同的是，**replaceFirst** 替换**首次匹配**，**replaceAll** 替换**所有匹配**。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
 
public class RegexMatches
{
    private static String REGEX = "dog";
    private static String INPUT = "The dog says meow. " +
                                    "All dogs say meow.";
    private static String REPLACE = "cat";
 
    public static void main(String[] args) {
       Pattern p = Pattern.compile(REGEX);
       // get a matcher object
       Matcher m = p.matcher(INPUT); 
       INPUT = m.replaceAll(REPLACE);
       System.out.println(INPUT);
   }
}
//输出:The cat says meow. All cats say meow.
```

##### appendReplacement() & appendTail() 方法

- **appendReplacement(StringBuffer sb, String replacement):**实现**非终端**添加和替换步骤。
- **appendTail(StringBuffer sb):**实现**终端**添加和替换步骤。

```java
import java.util.regex.Matcher;
import java.util.regex.Pattern;
 
public class RegexMatches
{
   private static String REGEX = "a*b";
   private static String INPUT = "aabfooaabfooabfoobkkk";
   private static String REPLACE = "-";
   public static void main(String[] args) {
      Pattern p = Pattern.compile(REGEX);
      // 获取 matcher 对象
      Matcher m = p.matcher(INPUT);
      StringBuffer sb = new StringBuffer();
      while(m.find()){
         m.appendReplacement(sb,REPLACE);
      }
      m.appendTail(sb);
      System.out.println(sb.toString());
   }
}
//输出:-foo-foo-foo-kkk
```

##### quoteReplacement(String s) 方法

返回**指定字符串的字面替换字符串**。这个方法返回一个字符串，就像传递给Matcher类的appendReplacement 方法一个字面字符串一样。

```java
import java.util.regex.*; 
  
public class GFG { 
    public static void main(String[] args) { 
		String regex = "FGF"; 
   
        Pattern pattern = Pattern.compile(regex); 

        String stringToBeMatched = "GFGFGFGFGFGFGFGFGFG FGF GFG GFG FGF"; 
  
        Matcher matcher = pattern.matcher(stringToBeMatched); 
  
        // Get the String to be replaced 
        String stringToBeReplaced = "GFG"; 

        System.out.println(matcher.quoteReplacement(stringToBeReplaced)); 
        System.out.println(matcher.replaceAll( matcher.quoteReplacement(stringToBeReplaced))); 
    } 
}
/*输出:
GFG
GGFGGGFGGGFGGGFGGFG GFG GFG GFG GFG
*/
```

##### PatternSyntaxException 类的方法

**PatternSyntaxException** 是一个**非强制异常类**，它指示一个**正则表达式模式中的语法错误**。

| **序号**                           | **方法及说明**                                               |
| :--------------------------------- | :----------------------------------------------------------- |
| **public String getDescription()** | 获取错误的**描述**。                                         |
| **public int getIndex()**          | 获取错误的**索引**。                                         |
| **public String getPattern()**     | 获取**错误的正则表达式模式**。                               |
| **public String getMessage()**     | 返回**多行字符串**，包含**语法错误及其索引的描述、错误的正则表达式模式**和**模式中错误索引的可视化指示。** |

#### 常用正则表达式([在线查询](https://any86.github.io/any-rule/))

##### 匹配

- `^\d+$` ：非负整数（正整数 + 0）
- `^[0-9]*[1-9][0-9]*$` ：正整数
- `^((-\d+)|(0+))$` ：非正整数（负整数 + 0）
- `^-[0-9]*[1-9][0-9]*$` ：负整数
- `^-?\d+$` ：整数
- `^\d+(\.\d+)?$` ：非负浮点数（正浮点数 + 0）
- `^(([0-9]+\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\.[0-9]+)|([0-9]*[1-9][0-9]*))$` ：正浮点数
- `^((-\d+(\.\d+)?)|(0+(\.0+)?))$` ：非正浮点数（负浮点数 + 0）
- `^(-(([0-9]+\.[0-9]*[1-9][0-9]*)|([0-9]*[1-9][0-9]*\.[0-9]+)|([0-9]*[1-9][0-9]*)))$` ：负浮点数
- `^(-?\d+)(\.\d+)?$` ：浮点数
- `^[A-Za-z]+$` ：由26个英文字母组成的字符串
- `^[A-Z]+$` ：由26个英文字母的大写组成的字符串
- `^[a-z]+$` ：由26个英文字母的小写组成的字符串
- `^[A-Za-z0-9]+$` ：由数字和26个英文字母组成的字符串
- `^\w+$` ：由数字、26个英文字母或者下划线组成的字符串
- `^[\w-]+(\.[\w-]+)*@[\w-]+(\.[\w-]+)+$` ：email地址
- `^[a-zA-z]+://(\w+(-\w+)*)(\.(\w+(-\w+)*))*(\?\S*)?$` ：url
- `/^(d{2}|d{4})-((0([1-9]{1}))|(1[1|2]))-(([0-2]([1-9]{1}))|(3[0|1]))$/` ：年-月-日
- `/^((0([1-9]{1}))|(1[1|2]))/(([0-2]([1-9]{1}))|(3[0|1]))/(d{2}|d{4})$/` ：月/日/年
- `^([w-.]+)@(([[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}.)|(([w-]+.)+))([a-zA-Z]{2,4}|[0-9]{1,3})(]?)$` ：Emil
- `/^((\+?[0-9]{2,4}\-[0-9]{3,4}\-)|([0-9]{3,4}\-))?([0-9]{7,8})(\-[0-9]+)?$/` ：电话号码
- `^(d{1,2}|1dd|2[0-4]d|25[0-5]).(d{1,2}|1dd|2[0-4]d|25[0-5]).(d{1,2}|1dd|2[0-4]d|25[0-5]).(d{1,2}|1dd|2[0-4]d|25[0-5])$` ：IP地址
- 匹配中文字符的正则表达式： `[\u4e00-\u9fa5]`
- 匹配双字节字符(包括汉字在内)：`[^\x00-\xff]`
- 匹配空行的正则表达式：`\n[\s| ]*\r`
- 匹配HTML标记的正则表达式：`/<(.*)>.*<\/\1>|<(.*) \/>/`
- 匹配首尾空格的正则表达式：`(^\s*)|(\s*$)`
- 匹配Email地址的正则表达式：`\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*`
- 匹配网址URL的正则表达式：`^[a-zA-z]+://(\\w+(-\\w+)*)(\\.(\\w+(-\\w+)*))*(\\?\\S*)?$`或者`^http:\/\/[A-Za-z0-9]+\.[A-Za-z0-9]+[\/=\?%\-&_~@[\]\':+!]*([^<>\"\"])*$`
- 匹配帐号是否合法(字母开头，允许5-16字节，允许字母数字下划线)：`^[a-zA-Z][a-zA-Z0-9_]{4,15}$`
- 匹配国内电话号码：`(\d{3}-|\d{4}-)?(\d{8}|\d{7})?`
- 匹配腾讯QQ号：`^[1-9]*[1-9][0-9]*$`

##### 捕获

- 提取信息中的网络链接：`(h|H)(r|R)(e|E)(f|F) *= *('|")?(\w|\\|\/|\.)+('|"| *|>)?`
- 提取信息中的邮件地址：`\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*`
- 提取信息中的图片链接：`(s|S)(r|R)(c|C) *= *('|")?(\w|\\|\/|\.)+('|"| *|>)?`
- 提取信息中的IP地址：`^(?:(?:25[0-5]|2[0-4]\\d|[01]?\\d{1,2}\\.)){3}(?:(?:25[0-5]|2[0-4]\\d|[01]?\\d{1,2}))&`
- 提取信息中的中国手机号码：`(86)*0*13\d{9}`
- 提取信息中的中国固定电话号码：`(\(\d{3,4}\)|\d{3,4}-|\s)?\d{8}`
- 提取信息中的中国电话号码（包括移动和固定电话）：`(\(\d{3,4}\)|\d{3,4}-|\s)?\d{7,14}`
- 提取信息中的中国邮政编码：`/^(0[1-7]|1[0-356]|2[0-7]|3[0-6]|4[0-7]|5[1-7]|6[1-7]|7[0-5]|8[013-6])\d{4}$/`
- 提取信息中的浮点数（即小数）：`(-?\d*)\.?\d+`
- 提取信息中的任何数字 ：`(-?\d*)(\.\d+)?`

## Java Stream(流)、File(文件)、IO

**Java.io**包几乎包含了所有**操作输入、输出需要的类**。所有这些流类代表了输入源和输出目标。

**Java.io**包中的流支持很多种格式，比如：**基本类型**、**对象**、**本地化字符集**等等。

### 控制台输入输出

#### 读取控制台输入

Java 的**控制台输入**由 **System.in** 完成。

为了获得一个绑定到控制台的字符流，你可以把 **System.in 包装在一个 BufferedReader** 对象中来创建一个字符流。

```Java
BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
```

#### 从控制台读取多字符输入

从 **BufferedReader** 对象**读取一个字符**要使用 **read() **方法。

每次调用 **read()** 方法，它从**输入流读取一个字符**并把该字符作为**整数值返回**。当流结束的时候返回 **-1**。该方法抛出 **IOException**。

```java
//使用 BufferedReader 在控制台读取字符
 
import java.io.*;
 
public class BRRead {
    public static void main(String args[]) throws IOException {
        char c;
        // 使用 System.in 创建 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        System.out.println("输入字符, 按下 'q' 键退出。");
        // 读取字符
        do {
            c = (char) br.read();
            System.out.println(c);
        } while (c != 'q');
    }
}
/*输出:
输入字符, 按下 'q' 键退出。
runoob
r
u
n
o
o
b

q
q
*/
```

#### 从控制台读取字符串

从标准输入**读取一个字符串**需要使用 **BufferedReader** 的 **readLine()** 方法。

```java
//使用 BufferedReader 在控制台读取字符
import java.io.*;
 
public class BRReadLines {
    public static void main(String args[]) throws IOException {
        // 使用 System.in 创建 BufferedReader
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        String str;
        System.out.println("Enter lines of text.");
        System.out.println("Enter 'end' to quit.");
        do {
            str = br.readLine();
            System.out.println(str);
        } while (!str.equals("end"));
    }
}
/*输出:
Enter lines of text.
Enter 'end' to quit.
This is line one
This is line one
This is line two
This is line two
end
end
*/
```

*JDK 5 后的版本我们也可以使用* [Java Scanner](#Java Scanner 类) *类来获取控制台的输入。*

#### 控制台输出

控制台的输出由 **print()** 和 **println()** 完成。这些方法都由**类 PrintStream 定义**，System.out 是该类对象的一个引用。

**PrintStream 继承了 OutputStream类**，并且实现了方法 **write()**。这样，write() 也可以用来往**控制台写操作**。

```java
import java.io.*;
 
//演示 System.out.write().
public class WriteDemo {
    public static void main(String args[]) {
        int b;
        b = 'A';
        System.out.write(b);
        System.out.write('\n');
    }
}
//输出:A
```

### 读写文件

下图是一个描述输入流和输出流的类层次图。

![Snipaste_2020-10-24_12-50-08](S:\Desktop\图片\Snipaste_2020-10-24_12-50-08.png)

#### FileInputStream 类

该流用于从文件**读取数据**，它的对象可以用**关键字 new 来创建**。

1.可以使用字符串类型的文件名来创建一个输入流对象来读取文件：

```java
InputStream f = new FileInputStream("C:/java/hello");
```

2.也可以使用一个**文件对象**来创建一个**输入流对象**来读取文件。我们首先得使用 **File()** 方法来创建一个文件对象：

```java
File f = new File("C:/java/hello");
InputStream out = new FileInputStream(f);
```

创建了**InputStream**对象，就可以使用下面的方法来读取流或者进行其他的流操作。

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| **public void close() throws IOException{}**                 | **关闭此文件输入流**并**释放与此流有关的所有系统资源**。抛出IOException异常。 |
| **protected void finalize()throws IOException {}**           | 这个方法**清除与该文件的连接**。**确保在不再引用文件输入流时调用其 close 方法**。抛出IOException异常。 |
| **public int read(int r)throws IOException{}**               | 这个方法从 InputStream 对象**读取指定字节的数据**。返回为**整数值**。返回下一字节数据，如果已经到**结尾则返回-1**。 |
| **public int read(byte[] r) throws IOException{}**           | 这个方法从输入流**读取r.length长度的字节**。返回**读取的字节数**。如果是文件**结尾则返回-1**。 |
| **public int read(byte[] r,int off,int len) throws IOException{}** | **off**表示指定字节数组开始保存数据的**起始下标**，**len**表示**读取的字节数目**. |
| **public int available() throws IOException{}**              | 返回**下一次对此输入流调用的方法**可以**不受阻塞地从此输入流读取的字节数**。返回一个**整数值**。 |
#### FileOutputStream 类

该类用来创建一个文件并向文件中**写数据**。

如果该流在打开文件进行输出前，**目标文件不存在**，那么该流会**创建该文件**。

1.使用字符串类型的文件名来创建一个输出流对象：

```java
OutputStream f = new FileOutputStream("C:/java/hello")
```

2.也可以使用一个**文件对象**来创建一个**输出流**来写文件。我们首先得使用**File()**方法来创建一个文件对象：

```java
File f = new File("C:/java/hello");
OutputStream f = new FileOutputStream(f);
```

创建**OutputStream** 对象完成后，就可以使用下面的方法来写入流或者进行其他的流操作。

| 方法                                               | 描述                                                         |
| :------------------------------------------------- | :----------------------------------------------------------- |
| **public void close() throws IOException{}**       | **关闭此文件输入流**并**释放与此流有关的所有系统资源**。抛出IOException异常。 |
| **protected void finalize()throws IOException {}** | 这个方法**清除与该文件的连接**。**确保在不再引用文件输入流时调用其 close 方法**。抛出IOException异常。 |
| void flush()                                       | **刷新此输出流**并**强制写出所有缓冲的输出的字节**。         |
| **public void write(int w)throws IOException{}**   | 这个方法把**指定的字节**写到**输出流**中。                   |
| **public void write(byte[] w)**                    | 把指定数组中**w.length长度的字节**写到**OutputStream**中。   |
| **public void write(byte[] w,int off,int len)**    | **off**表示指定字节数组开始保存数据的**起始下标**，**len**表示**读取的字节数目**. |

#### FIle实例

 **InputStream** 和 **OutputStream** 用法的例子

```Java
//文件名 :fileStreamTest2.java
import java.io.*;
 
public class fileStreamTest2 {
    public static void main(String[] args) throws IOException {
 
        File f = new File("a.txt");
        FileOutputStream fop = new FileOutputStream(f);
        // 构建FileOutputStream对象,文件不存在会自动新建
 
        OutputStreamWriter writer = new OutputStreamWriter(fop, "UTF-8");
        // 构建OutputStreamWriter对象,参数可以指定编码,默认为操作系统默认编码,windows上是gbk
 
        writer.append("中文输入");
        // 写入到缓冲区
 
        writer.append("\r\n");
        // 换行
 
        writer.append("English");
        // 刷新缓存冲,写入到文件,如果下面已经没有写入的内容了,直接close也会写入
 
        writer.close();
        // 关闭写入流,同时会把缓冲区内容写入文件,所以上面的注释掉
 
        fop.close();
        // 关闭输出流,释放系统资源
 
        FileInputStream fip = new FileInputStream(f);
        // 构建FileInputStream对象
 
        InputStreamReader reader = new InputStreamReader(fip, "UTF-8");
        // 构建InputStreamReader对象,编码与写入相同
 
        StringBuffer sb = new StringBuffer();
        while (reader.ready()) {
            sb.append((char) reader.read());
            // 转成char加到StringBuffer对象中
        }
        System.out.println(sb.toString());
        reader.close();
        // 关闭读取流
 
        fip.close();
        // 关闭输入流,释放系统资源
 
    }
}
/*文件内:
中文输入
English
*/
```

#### ByteArrayInputStream类

**字节数组输入流**在内存中创建一个**字节数组缓冲区**，从**输入流读取的数据保存在该字节数组缓冲区**中。

创建字节数组输入流对象有以下几种方式。

1.**接收字节数组作为参数**创建：.

```Java
ByteArrayInputStream bArray = new ByteArrayInputStream(byte [] a);
```

2.接收一个**字节数组**，和两个**整型变量 off、len**，**off**表示**第一个读取的字节**，**len**表示**读取字节的长度**。

```Java
ByteArrayInputStream bArray = new ByteArrayInputStream(byte[] a,int off,int len)
```

成功创建字节数组输入流对象后，可以参见以下列表中的方法，对流进行读操作或其他操作。

| 方法                                            | 描述                                                |
| :---------------------------------------------- | :-------------------------------------------------- |
| **public int read()**                           | 从此输入流中**读取下一个数据字节**。                |
| **public int read(byte[] r, int off, int len)** | 将**最多 `len` 个数据字节**从此输入流读入字节数组。 |
| **public int available()**                      | 返回**可不发生阻塞地从此输入流读取的字节数**。      |
| **public void mark(int read)**                  | **设置**流中的**当前标记位置**。                    |
| **public long skip(long n)**                    | 从此输入流中**跳过 `n` 个输入字节**。               |

#### ByteArrayOutputStream类

字节数组**输出流**在内存中创建一个**字节数组缓冲区**，**所有发送到输出流的数据保存在该字节数组缓冲区**中。

创建字节数组输出流对象有以下几种方式。

1.下面的构造方法创建一个**32字节（默认大小）**的缓冲区。

```java
ByteArrayOutputStream bOut = new ByteArrayOutputStream();
```

2.另一个构造方法创建一个大小为**n字节**的缓冲区。

```Java
ByteArrayOutputStream bOut = new ByteArrayOutputStream(int a);
```

成功创建字节数组输出流对象后，可以参见以下列表中的方法，对流进行写操作或其他操作。

| 方法                                              | 描述                                                         |
| :------------------------------------------------ | :----------------------------------------------------------- |
| **public void reset()**                           | 将此字节数组**输出流的 `count` 字段重置为零**，从而**丢弃输出流中目前已累积的所有数据输出**。 |
| **public byte[] toByteArray()**                   | **创建一个新分配的字节数组**。**数组的大小**和**当前输出流的大小**，内容是**当前输出流的拷贝**。 |
| **public String toString()**                      | 将**缓冲区的内容**转换为**字符串**，根据**平台的默认字符编码将字节转换成字符**。 |
| **public void write(int w)**                      | 将**指定的字节**写入此字节数组输出流。                       |
| **public void write(byte []b, int off, int len)** | 将**指定字节数组**中从**偏移量 `off` 开始的 `len` 个字节写入此字节数组**输出流。 |
| **public void writeTo(OutputStream outSt)**       | 将此字节数组输出流的**全部内容**写入到指定的输出流参数中。   |

#### ByteArray实例

**ByteArrayInputStream** 和 **ByteArrayOutputStream**的使用：

```Java
import java.io.*;

public class ByteStreamTest {
   public static void main(String[] args) throws IOException {
      ByteArrayOutputStream bOutput = new ByteArrayOutputStream(12);
      while( bOutput.size()!= 10 ) {
         // 获取用户输入
         bOutput.write(System.in.read()); 
      }
      byte b [] = bOutput.toByteArray();
      System.out.println("Print the content");
      for(int x= 0 ; x < b.length; x++) {
         // 打印字符
         System.out.print((char)b[x]  + "   "); 
      }
      System.out.println("   ");
      int c;
      ByteArrayInputStream bInput = new ByteArrayInputStream(b);
      System.out.println("Converting characters to Upper case " );
      for(int y = 0 ; y < 1; y++ ) {
         while(( c= bInput.read())!= -1) {
            System.out.println(Character.toUpperCase((char)c));
         }
         bInput.reset(); 
      }
   }
}
/*输出:
asdfghjkly
Print the content
a   s   d   f   g   h   j   k   l   y
Converting characters to Upper case
A
S
D
F
G
H
J
K
L
Y
*/
```

#### DataInputStream 类

数据输入流允许应用程序以与**机器无关方式**从**底层输入流中读取**基本 Java 数据类型。

1.下面的构造方法用来创建数据输入流对象。

```java
DataInputStream dis = new DataInputStream(InputStream in);
```

创建对象成功后，可以参照以下列表给出的方法，对流进行写操作或者其他操作。

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| **public final int read(byte[] r, int off, int len)throws IOException** | 从所包含的输入流中将 **`len` 个字节**读入一个字节数组中。如果**len为-1**，则返回**已读字节数**。 |
| **Public final int read(byte [] b)throws IOException**       | 从**所包含的输入流中读取一定数量的字节**，并将它们**存储到缓冲区数组 `b` 中。** |
| **public final Boolean readBooolean() throws IOException**   | 从输入流中读取字节，返回输入流中**两个字节**作为`Boolean`类型返回值。 |
| **public final byte readByte() throws IOException**          | 从输入流中读取字节，返回输入流中**两个字节**作为`byte`类型返回值。 |
| **public final short readShort() throws IOException**        | 从输入流中读取字节，返回输入流中**两个字节**作为`short`类型返回值。 |
| **public final Int readInt() throws IOException**            | 从输入流中读取字节，返回输入流中**两个字节**作为`int`类型返回值。 |
| **public String readLine() throws IOException**              | 从输入流中**读取下一文本行**。                               |

#### DataOutputStream类

数据输出流允许应用程序以与**机器无关方式**将Java基本数据类型**写到底层输出流**。

1.下面的构造方法用来创建数据输出流对象。

```java
DataOutputStream out = new DataOutputStream(OutputStream  out);
```

创建对象成功后，可以参照以下列表给出的方法，对流进行写操作或者其他操作。

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| **public final void write(byte[] w, int off, int len)throws IOException** | 将指定字节数组中从**偏移量 `off` 开始的 `len` 个字节**写入此字节数组输出流。 |
| **Public final int write(byte [] b) throws IOException**     | 将**指定的字节**写入**此字节数组输出流**。                   |
| **public final void writeBooolean() throws IOException**     | 将`Boolean`类型以字节的方式写入到输出流。                    |
| **public final void writeByte() throws IOException**         | 将`byte`类型以字节的方式写入到输出流。                       |
| **public final void writeShort() throws IOException**        | 将`short`类型以字节的方式写入到输出流。                      |
| **public final void writeInt() throws IOException**          | 将`int`类型以字节的方式写入到输出流。                        |
| **Public void flush() throws IOException**                   | **刷新此输出流**并**强制写出所有缓冲的输出字节**。           |
| **public final void writeBytes(String s) throws IOException** | 将**字符串以字节序列写入到底层的输出流**，字符串中每个字符都**按顺序写入**，并**丢弃其高八位**。 |

#### Data实例

**DataInputStream**和**DataOutputStream**的使用

```java
//文本文件test.txt中读取5行，并转换成大写字母，最后保存在另一个文件test1.txt中
/*test.txt文件内容如下:
runoob1
runoob2
runoob3
runoob4
runoob5
*/
import java.io.*;
 
public class Test{
   	public static void main(String args[])throws IOException{
 		// BufferedInputStream与DataInputStream读写方法类似
      	DataInputStream in = new DataInputStream(new FileInputStream("test.txt"));
      	DataOutputStream out = new DataOutputStream(new  FileOutputStream("test1.txt"));
      	BufferedReader d  = new BufferedReader(new InputStreamReader(in));
     
      	String count;
      	while((count = d.readLine()) != null){
          	String u = count.toUpperCase();
          	System.out.println(u);
          	out.writeBytes(u + "  ,");
      	}
      	d.close();
      	out.close();
   	}
}
/*输出:
RUNOOB1
RUNOOB2
RUNOOB3
RUNOOB4
RUNOOB5
*/
```

### File类

Java文件类以**抽象的方式**代表**文件名和目录路径名**。该类主要用于**文件和目录的创建、文件的查找和文件的删除**等。

**File对象**代表磁盘中**实际存在的文件和目录**。通过以下构造方法创建一个File对象。

1.通过给定的**父抽象路径名**和**子路径名字符串**创建一个新的File实例。

```java
File(File parent, String child);
```

2.通过将**给定路径名字符串转换成抽象路径名**来创建一个新 File 实例。

```java
File(String pathname) 
```

3.根据 **parent 路径名字符串**和 **child 路径名字符串**创建一个新 File 实例。

```java
File(String parent, String child) 
```

4.通过将**给定的 file: URI 转换成一个抽象路径名**来创建一个新的 File 实例。

```java
File(URI uri)
```

创建File对象成功后，可以使用以下列表中的方法操作文件。

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| **public String getName()**                                  | 返回由此**抽象路径名**表示的**文件或目录的名称**。           |
| **public String getParent()**                                | 返回此**抽象路径名的父路径名的路径名字符串**，如果此路径名**没有指定父目录**，则返回 `null`。 |
| **public File getParentFile()**                              | 返回此**抽象路径名的父路径名的抽象路径名**，如果此路径名没有指定父目录，则返回 `null`。 |
| **public String getPath()**                                  | 将此**抽象路径名**转换为一个**路径名字符串**。               |
| **public boolean isAbsolute()**                              | 测试此抽象路径名是否为**绝对路径名**。                       |
| **public String getAbsolutePath()**                          | 返回抽象路径名的**绝对路径名字符串**。                       |
| **public boolean canRead()**                                 | 测试应用程序**是否可以读取**此抽象路径名表示的文件。         |
| **public boolean canWrite()**                                | 测试应用程序**是否可以修改**此抽象路径名表示的文件。         |
| **public boolean exists()**                                  | 测试此抽象路径名表示的**文件或目录是否存在**。               |
| **public boolean isDirectory()**                             | 测试此抽象路径名表示的文件**是否是一个目录**。               |
| **public boolean isFile()**                                  | 测试此抽象路径名表示的文件**是否是一个标准文件**。           |
| **public long lastModified()**                               | 返回此抽象路径名表示的文件**最后一次被修改的时间**。         |
| **public long length()**                                     | 返回由此抽象路径名表示的**文件的长度**。                     |
| **public boolean createNewFile() throws IOException**        | **当且仅当不存在具有此抽象路径名指定的名称的文件时**，原地**创建由此抽象路径名指定的一个新的空文件**。 |
| **public boolean delete()**                                  | **删除**此抽象路径名表示的**文件或目录**。                   |
| **public void deleteOnExit()**                               | 在**虚拟机终止**时，**请求删除**此抽象路径名表示的**文件或目录**。 |
| **public String[] list()**                                   | 返回由此抽象路径名所表示的**目录中的文件**和**目录的名称**所**组成的字符串数组**。 |
| **public String[] list(FilenameFilter filter)**              | 返回由**包含**在**目录中的文件**和**目录的名称**所**组成的字符串数组**，这一目录是通过**满足指定过滤器的抽象路径名**来表示的。 |
| **public File[] listFiles()**                                | 返回一个**抽象路径名数组**，这些路径名表示**此抽象路径名所表示目录中的文件。** |
| **public File[] listFiles(FileFilter filter)**               | 返回表示此抽象路径名所表示**目录中的文件和目录的抽象路径名数组**，这些路径名**满足特定过滤器**。 |
| **public boolean mkdir()**                                   | **创建此抽象路径名指定的目录**。                             |
| **public boolean mkdirs()**                                  | **创建此抽象路径名指定的目录**，包括**创建必需但不存在的父目录**。 |
| **public boolean renameTo(File dest)**                       | **重新命名**此抽象路径名表示的**文件**。                     |
| **public boolean setLastModified(long time)**                | **设置**由此抽象路径名所指定的**文件或目录的最后一次修改时间**。 |
| **public boolean setReadOnly()**                             | **标记**此抽象路径名指定的**文件或目录**，以便**只可对其进行读操作**。 |
| **public static File createTempFile(String prefix, String suffix, File directory) throws IOException** | 在**指定目录中创建一个新的空文件**，**使用给定的前缀和后缀字符串**生成其名称。 |
| **public static File createTempFile(String prefix, String suffix) throws IOException** | 在**默认临时文件目录**中**创建一个空文件**，**使用给定前缀和后缀**生成其名称。 |
| **public int compareTo(File pathname)**                      | 按**字母顺序**比较**两个抽象路径名**。                       |
| **public int compareTo(Object o)**                           | 按**字母顺序**比较**抽象路径名**与**给定对象**。             |
| **public boolean equals(Object obj)**                        | 测试此抽象路径名与给定对象**是否相等**。                     |
| **public String toString()**                                 | 返回此抽象路径名的**路径名字符串**。                         |

**实例**

```java
import java.io.File;
 
public class DirList {
    public static void main(String args[]) {
        String dirname = "/java";
        File f1 = new File(dirname);
        FilenameFilter filter = new FilenameFilter() {  // 文件过滤器
            @Override
            public boolean accept(File dir, String name) {
                File currentfile = new File(dir, name);
                return currentfile.isFile() && name.endsWith(".txt");
            }
        };
        // 显示所有文件
        if (f1.isDirectory()) {
            System.out.println("Directory of " + dirname);
            String s[] = f1.list();
            for (int i = 0; i < s.length; i++) {
                File f = new File(dirname + "/" + s[i]);
                if (f.isDirectory()) {
                    System.out.println(s[i] + " is a directory");
                } else {
                    System.out.println(s[i] + " is a file");
                }
            }
        } else {
            System.out.println(dirname + " is not a directory");
        }
        // 显示txt结尾的文件
        if (f1.exists()){
            String[] str = f1.list(fillter)
            for (String s : str){
                System.out.println(s)  // 仅输出txt文件
            }
        }
    }
}
/*输出:
Directory of /java
bin is a directory
lib is a directory
demo is a directory
test.txt is a file
README is a file
index.html is a file
include is a directory

tset.txt
*/
```

### FileReader类

**FileReader类**从**InputStreamReader**类继承而来。该类按**字符读取流中数据**。

可以通过以下几种构造方法创建需要的对象。

1.在给定从中**读取数据的 File** 的情况下创建一个新 **FileReader**。

```Java
FileReader(File file)
```

2.在给定从中**读取数据的 FileDescriptor** 的情况下创建一个新 **FileReader**。

```Java
FileReader(FileDescriptor fd) 
```

3.在给定从中**读取数据的文件名**的情况下创建一个新 **FileReader**。

```Java
FileReader(String fileName) 
```

创建**FIleReader**对象成功后，可以参照以下列表里的方法操作文件。

| 方法                                                | 方法描述                                                |
| :-------------------------------------------------- | :------------------------------------------------------ |
| **public int read() throws IOException**            | 读取**单个字符**，返回一个**int型变量代表读取到的字符** |
| **public int read(char [] c, int offset, int len)** | **读取字符到c数组**，返回读取到**字符的个数**           |

**实例**

```Java
import java.io.*;
 
public class FileRead {
    public static void main(String args[]) throws IOException {
        File file = new File("Hello1.txt");
        // 创建文件
        file.createNewFile();
        // creates a FileWriter Object
        FileWriter writer = new FileWriter(file);
        // 向文件写入内容
        writer.write("This\n is\n an\n example\n");
        writer.flush();
        writer.close();
        // 创建 FileReader 对象
        FileReader fr = new FileReader(file);
        char[] a = new char[50];
        fr.read(a); // 读取数组中的内容
        for (char c : a)
            System.out.print(c); // 一个一个打印字符
        fr.close();
    }
}
/*输出:
This
is
an
example
*/
```

### FileWriter类

**FileWriter 类**从 **OutputStreamWriter** 类继承而来。该类按**字符向流中写入数据**。

可以通过以下几种构造方法创建需要的对象。

1.在给出 **File 对象**的情况下构造一个 **FileWriter 对象**。

```java
FileWriter(File file)
```

2.在给出 **File 对象**的情况下构造一个 **FileWriter 对象**。

```java
 FileWriter(File file, boolean append)
```

**参数：**

- **file**：要**写入数据的 File 对象**。
- **append**：如果 **append 参数为 true**，则将字节写入文件**末尾处**，**相当于追加信息**。如果 **append 参数为 false**, 则写入文件**开始处**。

3.构造与**某个文件描述符相关联**的 FileWriter 对象。

```java
FileWriter(FileDescriptor fd)
```

4.在给出**文件名**的情况下构造 **FileWriter 对象**，它具有指示**是否挂起写入数据的 boolean 值**。

```java
FileWriter(String fileName, boolean append)
```

创建**FileWriter**对象成功后，可以参照以下列表里的方法操作文件。

| 方法                                                  | 方法描述                                                |
| :---------------------------------------------------- | :------------------------------------------------------ |
| **public void write(int c) throws IOException**       | 写入**单个字符c**。                                     |
| **public void write(char [] c, int offset, int len)** | 写入**字符数组**中**开始为offset长度为len**的某一部分。 |
| **public void write(String s, int offset, int len)**  | 写入**字符串**中**开始为offset长度为len**的某一部分。   |

**实例**

```Java
import java.io.*;
 
public class FileRead {
    public static void main(String args[]) throws IOException {
        File file = new File("Hello1.txt");
        // 创建文件
        file.createNewFile();
        // creates a FileWriter Object
        FileWriter writer = new FileWriter(file);
        // 向文件写入内容
        writer.write("This\n is\n an\n example\n");
        writer.flush();
        writer.close();
        // 创建 FileReader 对象
        FileReader fr = new FileReader(file);
        char[] a = new char[50];
        fr.read(a); // 从数组中读取内容
        for (char c : a)
            System.out.print(c); // 一个个打印字符
        fr.close();
    }
}
/*输出:
This
is
an
example
*/
```

### Java中的目录

#### 创建目录：

File类中有两个方法可以用来创建文件夹：

- **mkdir( )** 方法创建一个文件夹，成功则返回**true**，失败则返回**false**。失败表明**File对象指定的路径已经存在**，或者由于**整个路径还不存在**，该文件夹不能被创建。
- **mkdirs()** 方法创建**一个文件夹和它的所有父文件夹**。

```java
import java.io.File;
 
public class CreateDir {
    public static void main(String args[]) {
        String dirname = "/tmp/user/java/bin";
        File d = new File(dirname);
        // 现在创建目录
        d.mkdirs();
    }
}
//编译并执行上面代码来创建目录 "/tmp/user/java/bin"。
```

#### 读取目录:

一个**目录**其实就是一个 **File 对象**，它包含**其他文件和文件夹**。

如果创建**一个 File 对象并且它是一个目录**，那么调用 **isDirectory()** 方法会返回 **true**。

可以通过调用该对象上的 **list()** 方法，来**提取它包含的文件和文件夹**的列表。

```java
import java.io.File;
 
public class DirList {
    public static void main(String args[]) {
        String dirname = "/tmp";
        File f1 = new File(dirname);
        if (f1.isDirectory()) {
            System.out.println("目录 " + dirname);
            String s[] = f1.list();
            for (int i = 0; i < s.length; i++) {
                File f = new File(dirname + "/" + s[i]);
                if (f.isDirectory()) {
                    System.out.println(s[i] + " 是一个目录");
                } else {
                    System.out.println(s[i] + " 是一个文件");
                }
            }
        } else {
            System.out.println(dirname + " 不是一个目录");
        }
    }
}
/*输出:
目录 /tmp
bin 是一个目录
lib 是一个目录
demo 是一个目录
test.txt 是一个文件
README 是一个文件
index.html 是一个文件
include 是一个目录
*/
```

#### 删除目录或文件:

删除文件可以使用 **java.io.File.delete()** 方法。

需要注意的是当**删除某一目录**时，必须保证该目录下**没有其他文件**才能**正确删除**，否则将**删除失败**。

```java
import java.io.File;
 
public class DeleteFileDemo {
    public static void main(String args[]) {
        // 这里修改为自己的测试目录
        File folder = new File("/tmp/java/");
        deleteFolder(folder);
    }
 
    // 删除文件及目录
    public static void deleteFolder(File folder) {
        File[] files = folder.listFiles();
        if (files != null) {
            for (File f : files) {
                if (f.isDirectory()) {
                    deleteFolder(f);
                } else {
                    f.delete();
                }
            }
        }
        folder.delete();
    }
}
```

## Java Scanner 类

下面是创建 **Scanner** 对象的基本语法：

```java
Scanner s = new Scanner(System.in);
```

#### 使用 next 方法：

```java
import java.util.Scanner; 
 
public class ScannerDemo {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        // 从键盘接收数据
 
        // next方式接收字符串
        System.out.println("next方式接收：");
        // 判断是否还有输入
        if (scan.hasNext()) {
            String str1 = scan.next();
            System.out.println("输入的数据为：" + str1);
        }
        scan.close();
    }
}
/*输出:
next方式接收：
runoob com
输入的数据为：runoob
*/
```

#### 使用 nextLine 方法：

```java
import java.util.Scanner;
 
public class ScannerDemo {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        // 从键盘接收数据
 
        // nextLine方式接收字符串
        System.out.println("nextLine方式接收：");
        // 判断是否还有输入
        if (scan.hasNextLine()) {
            String str2 = scan.nextLine();
            System.out.println("输入的数据为：" + str2);
        }
        scan.close();
    }
}
/*输出:
nextLine方式接收：
runoob com
输入的数据为：runoob com
*/
```

#### next() 与 nextLine() 区别

**next():**

- 1、一定要读取到**有效字符**后才可以**结束输入**。
- 2、对**输入有效字符之前遇到的空白**，**next()** 方法会**自动将其去掉**。
- 3、只有**输入有效字符后**才将其**后面输入的空白**作为**分隔符**或者**结束符**。
- **next() 不能得到带有空格的字符串**。

**nextLine()：**

- 1、以**Enter为结束符**,也就是说 **nextLine()**方法返回的是**输入回车之前的所有字符**。
- 2、可以**获得空白**。

#### 实例

如果要输入 **int** 或 **float** 类型的数据，在 Scanner 类中也有支持，但是在输入之前最好先使用 **hasNextXxx()** 方法进行**验证**，再使用 **nextXxx()** 来**读取**：

```java
import java.util.Scanner;
 
public class ScannerDemo {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        // 从键盘接收数据
        int i = 0;
        float f = 0.0f;
        System.out.print("输入整数：");
        if (scan.hasNextInt()) {
            // 判断输入的是否是整数
            i = scan.nextInt();
            // 接收整数
            System.out.println("整数数据：" + i);
        } else {
            // 输入错误的信息
            System.out.println("输入的不是整数！");
        }
        System.out.print("输入小数：");
        if (scan.hasNextFloat()) {
            // 判断输入的是否是小数
            f = scan.nextFloat();
            // 接收小数
            System.out.println("小数数据：" + f);
        } else {
            // 输入错误的信息
            System.out.println("输入的不是小数！");
        }
        scan.close();
    }
}
/*输出:
输入整数：12
整数数据：12
输入小数：1.2
小数数据：1.2
*/
```

输入多个数字，并求其总和与平均数，每输入一个数字用回车确认，通过**输入非数字来结束输入**并输出执行结果：

```java
import java.util.Scanner;
 
class ScannerDemo {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
 
        double sum = 0;
        int m = 0;
 
        while (scan.hasNextDouble()) {
            double x = scan.nextDouble();
            m = m + 1;
            sum = sum + x;
        }
 
        System.out.println(m + "个数的和为" + sum);
        System.out.println(m + "个数的平均值是" + (sum / m));
        scan.close();
    }
}
/*输出:
12
23
15
21.4
end
4个数的和为71.4
4个数的平均值是17.85
*/
```

## Java 异常处理

异常是程序中的一些错误，但**并不是所有的错误都是异常**，并且错误有时候是可以避免的。

比如说，你的代码**少了一个分号**，那么运行出来结果是提示是**错误 java.lang.Erro**r；如果你用**System.out.println(11/0)**，那么你是因为你用0做了除数，会**抛出 java.lang.ArithmeticException 的异常**。

**异常发生的原因**有很多，通常包含以下几大类：

- 用户输入了**非法数据**。
- 要**打开的文件不存在**。
- **网络通信时连接中断**，或者**JVM内存溢出**。

要理解Java异常处理是如何工作的，你需要掌握以下三种类型的异常：

- **检查性异常：**最具代表的检查性异常是用户错误或问题引起的异常，这是程序员**无法预见**的。例如要打开一个不存在文件时，一个异常就发生了，这些异常在编译时不能被简单地忽略。
- **运行时异常：** 运行时异常是可能被程序员避免的异常。与检查性异常相反，运行时异常可以在**编译时被忽略**。
- **错误：** **错误不是异常**，而是**脱离程序员控制的问题**。错误在代码中通常被忽略。例如，当栈溢出时，一个错误就发生了，它们在编译也检查不到的。

### Exception 类的层次

所有的异常类是从 **java.lang.Exception** 类**继承的子类**。

**Exception 类**是 **Throwable 类**的**子类**。除了Exception类外，**Throwable**还有一个**子类Error** 。

Java 程序通常**不捕获错误**。错误一般**发生在严重故障**时，它们在**Java程序处理的范畴之外**。

![Snipaste_2020-10-26_21-26-15](S:\Desktop\图片\Snipaste_2020-10-26_21-26-15.png)

### Java 内置异常类

 **Java 的非检查性异常**

| **异常**                            | **描述**                                                     |
| :---------------------------------- | :----------------------------------------------------------- |
| **ArithmeticException**             | 当出现**异常的运算条件**时，抛出此异常。例如，一个整数"除以零"时，抛出此类的一个实例。 |
| **ArrayIndexOutOfBoundsException**  | 用**非法索引访问数组**时抛出的异常。如果索引为负或大于等于数组大小，则该索引为非法索引。 |
| **ArrayStoreException**             | 试图将**错误类型的对象存储到一个对象数组**时抛出的异常。     |
| **ClassCastException**              | 当试图将**对象强制转换为不是实例的子类**时，抛出该异常。     |
| **IllegalArgumentException**        | 抛出的异常表明向方法传递了一个**不合法或不正确的参数**。     |
| **IllegalMonitorStateException**    | 抛出的异常表明**某一线程已经试图等待对象的监视器**，或者试图通知**其他正在等待对象的监视器而本身没有指定监视器的线程**。 |
| **IllegalStateException**           | 在**非法或不适当的时间调用方法时产生的信号**。换句话说，即 Java 环境或 Java 应用程序没有处于请求操作所要求的适当状态下。 |
| **IllegalThreadStateException**     | **线程没有处于请求操作所要求的适当状态**时抛出的异常。       |
| **IndexOutOfBoundsException**       | 指示**某排序索引（例如对数组、字符串或向量的排序）超出范围**时抛出。 |
| **NegativeArraySizeException**      | 如果应用程序试图创建**大小为负的数组**，则抛出该异常。       |
| **NullPointerException**            | 当应用程序试图在**需要对象的地方使用 `null` 时**，抛出该异常 |
| **NumberFormatException**           | 当应用程序试图将**字符串转换成一种数值类型**，**但该字符串不能转换为适当格式**时，抛出该异常。 |
| **SecurityException**               | 由安全管理器抛出的异常，**指示存在安全侵犯**。               |
| **StringIndexOutOfBoundsException** | 此异常由 **`String` 方法**抛出，**指示索引或者为负**，或者**超出字符串的大小**。 |
| **UnsupportedOperationException**   | 当**不支持请求的操作**时，抛出该异常。                       |

**Java的检查性异常类**

| **异常**                       | **描述**                                                     |
| :----------------------------- | :----------------------------------------------------------- |
| **ClassNotFoundException**     | 应用程序试图**加载类时，找不到相应的类**，抛出该异常。       |
| **CloneNotSupportedException** | 当**调用 `Object` 类中的 `clone` 方法克隆对象**，但该对象的类**无法实现 `Cloneable` 接口**时，抛出该异常。 |
| **IllegalAccessException**     | **拒绝访问一个类**的时候，抛出该异常。                       |
| **InstantiationException**     | 当试图**使用 `Class` 类中的 `newInstance` 方法创建一个类的实例**，而**指定的类对象因为是一个接口或是一个抽象类而无法实例化**时，抛出该异常。 |
| **InterruptedException**       | **一个线程被另一个线程中断**，抛出该异常。                   |
| **NoSuchFieldException**       | **请求的变量**不存在                                         |
| **NoSuchMethodException**      | **请求的方法**不存在                                         |

### 异常方法

**Throwable 类**的主要方法:

| **序号**                                        | **方法及说明**                                               |
| :---------------------------------------------- | :----------------------------------------------------------- |
| **public String getMessage()**                  | 返回**关于发生的异常的详细信息**。这个消息在**Throwable 类的构造函数中初始化**了。 |
| **public Throwable getCause()**                 | 返回一个**Throwable 对象**代表**异常原因**。                 |
| **public String toString()**                    | 使用**getMessage()的结果**返回**类的串级名字**。             |
| **public void printStackTrace()**               | 打印**toString()**结果和栈层次到**System.err**，即错误输出流。 |
| **public StackTraceElement [] getStackTrace()** | 返回一个包含**堆栈层次的数组**。**下标为0的元素代表栈顶**，**最后一个元素代表方法调用堆栈的栈底**。 |
| **public Throwable fillInStackTrace()**         | 用**当前的调用栈层次填充Throwable 对象栈层次**，**添加到栈层次任何先前信息**中。 |

### 捕获异常

使用 **try** 和 **catch** 关键字可以**捕获异常**。**try/catch** 代码块**放在异常可能发生的地方**。

```java
try
{
   // 程序代码
}catch(ExceptionName e1)
{
   //Catch 块
}
```

**Catch** 语句**包含要捕获异常类型的声明**。当保护代码块中**发生一个异常**时，try 后面的 **catch 块就会被检查**。

如果**发生的异常包含在 catch 块**中，**异常会被传递到该 catch 块**，这和传递一个参数到方法是一样。

```Java
// 文件名 : ExcepTest.java
import java.io.*;
public class ExcepTest{
 
   public static void main(String args[]){
      try{
         int a[] = new int[2];
         System.out.println("Access element three :" + a[3]);
      }catch(ArrayIndexOutOfBoundsException e){
         System.out.println("Exception thrown  :" + e);
      }
      System.out.println("Out of the block");
   }
}
/*输出:
Exception thrown  :java.lang.ArrayIndexOutOfBoundsException: 3
Out of the block
*/
```

### 多重捕获块

一个 **try 代码块后面跟随多个 catch 代码块**的情况就叫**多重捕获**。

```java
try{
   // 程序代码
}catch(异常类型1 异常的变量名1){
  // 程序代码
}catch(异常类型2 异常的变量名2){
  // 程序代码
}catch(异常类型3 异常的变量名3){
  // 程序代码
}
```

可以在 try 语句后面添加**任意数量的 catch 块**。

如果保护代码中发生异常，异常被抛给**第一个 catch 块**。

如果抛出异常的数据类型与 **ExceptionType1 匹配**，它在这里就会被**捕获**。

如果**不匹配**，它会被**传递给第二个 catch 块**。

如此，直到**异常被捕获或者通过所有的 catch 块**。

```java
try {
    file = new FileInputStream(fileName);
    x = (byte) file.read();
} catch(FileNotFoundException f) { // Not valid!
    f.printStackTrace();
    return -1;
} catch(IOException i) {
    i.printStackTrace();
    return -1;
}
```

### throws/throw 关键字

如果一个方法**没有捕获到一个检查性异常**，那么该方法**必须使用 throws 关键字**来声明。**throws** 关键字放在**方法签名的尾部**。

也可以使用 **throw 关键字抛出一个异常**，无论它是**新实例化**的还是**刚捕获到的**。

```java
import java.io.*;
public class className
{
  public void deposit(double amount) throws RemoteException
  {
    // Method implementation
    throw new RemoteException();
  }
  //Remainder of class definition
}
```

一个方法可以声明**抛出多个异常**，多个异常之间用**逗号隔开**。

```Java
import java.io.*;
public class className
{
   public void withdraw(double amount) throws RemoteException,InsufficientFundsException
   {
       // Method implementation
   }
   //Remainder of class definition
}
```

### finally关键字

**finally** 关键字用来创建在 **try 代码块后面执行的代码块**。

无论**是否发生异常**，**finally 代码块中的代码总会被执行**。

在 **finally** 代码块中，可以运行**清理类型等收尾善后性质的语句**。

```Java
public class ExcepTest{
  public static void main(String args[]){
    int a[] = new int[2];
    try{
       System.out.println("Access element three :" + a[3]);
    }catch(ArrayIndexOutOfBoundsException e){
       System.out.println("Exception thrown  :" + e);
    }
    finally{
       a[0] = 6;
       System.out.println("First element value: " +a[0]);
       System.out.println("The finally statement is executed");
    }
  }
}
/*输出:
Exception thrown  :java.lang.ArrayIndexOutOfBoundsException: 3
First element value: 6
The finally statement is executed
*/
```

注意下面事项：

- **catch 不能独立于 try 存在**。
- 在 **try/catch** 后面添加 **finally** 块并**非强制性要求**的。
- **try** 代码后**不能既没 catch 块也没 finally 块**。
- **try, catch, finally** 块**之间不能添加任何代码**。

### 声明自定义异常

在 Java 中你可以自定义异常。编写自己的异常类时需要记住下面的几点。

- 所有**异常**都必须是 **Throwable 的子类**。
- 如果希望写一个**检查性异常类**，则需要**继承 Exception 类**。
- 如果你想写一个**运行时异常类**，那么需要**继承 RuntimeException 类**。

可以像下面这样定义自己的异常类：

```java
class MyException extends Exception{
}
```

**只继承Exception 类**来创建的异常类是**检查性异常类**。

一个**异常类和其它任何类一样**，包含有**变量**和**方法**。

**实例**

一个银行账户的模拟，通过银行卡的号码完成识别，可以进行存钱和取钱的操作。

```java
// 文件名InsufficientFundsException.java
import java.io.*;
 
//自定义异常类，继承Exception类
public class InsufficientFundsException extends Exception
{
  //此处的amount用来储存当出现异常（取出钱多于余额时）所缺乏的钱
  private double amount;
  public InsufficientFundsException(double amount)
  {
    this.amount = amount;
  } 
  public double getAmount()
  {
    return amount;
  }
}
```

面的 CheckingAccount 类中包含一个 **withdraw() 方法抛出一个 InsufficientFundsException 异常**。

```Java
// 文件名称 CheckingAccount.java
import java.io.*;
 
//此类模拟银行账户
public class CheckingAccount
{
  //balance为余额，number为卡号
   private double balance;
   private int number;
   public CheckingAccount(int number)
   {
      this.number = number;
   }
  //方法：存钱
   public void deposit(double amount)
   {
      balance += amount;
   }
  //方法：取钱
   public void withdraw(double amount) throws InsufficientFundsException
   {
      if(amount <= balance)
      {
         balance -= amount;
      }
      else
      {
         double needs = amount - balance;
         throw new InsufficientFundsException(needs);
      }
   }
  //方法：返回余额
   public double getBalance()
   {
      return balance;
   }
  //方法：返回卡号
   public int getNumber()
   {
      return number;
   }
}
```

下面的 BankDemo 程序示范了如何调用 CheckingAccount 类的 deposit() 和 withdraw() 方法。

```Java
//文件名称 BankDemo.java
public class BankDemo
{
   public static void main(String [] args)
   {
      CheckingAccount c = new CheckingAccount(101);
      System.out.println("Depositing $500...");
      c.deposit(500.00);
      try
      {
         System.out.println("\nWithdrawing $100...");
         c.withdraw(100.00);
         System.out.println("\nWithdrawing $600...");
         c.withdraw(600.00);
      }catch(InsufficientFundsException e)
      {
         System.out.println("Sorry, but you are short $"
                                  + e.getAmount());
         e.printStackTrace();
      }
    }
}
/*输出:
Depositing $500...

Withdrawing $100...

Withdrawing $600...
Sorry, but you are short $200.0
InsufficientFundsException
        at CheckingAccount.withdraw(CheckingAccount.java:25)
        at BankDemo.main(BankDemo.java:13)
*/
```

### 通用异常

在Java中定义了两种类型的异常和错误。

- **JVM(Java虚拟机) 异常**：由 JVM 抛出的异常或错误。例如：**NullPointerException 类**，**ArrayIndexOutOfBoundsException 类**，**ClassCastException 类**。
- **程序级异常：**由程序或者API程序抛出的异常。例如 **IllegalArgumentException 类**，**IllegalStateException 类**。

