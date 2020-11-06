# Java(面向对象)

## Java 继承

继承是java面向对象编程技术的一块基石，因为它允许创建**分等级层次的类**。

**继承**就是**子类继承父类的特征和行为**，使得**子类对象（实例）具有父类的实例域和方法**，或**子类从父类继承方法**，使得**子类具有父类相同的行为**。

### 类的继承格式

在 Java 中通过 **extends 关键字**可以申明一个类是从另外一个类继承而来的：

```Java
class 父类 {
    
}
class 子类 extends 父类 {
    
}
```

**实例**

**公共父类：**

```Java
public class Animal { 
    private String name;  
    private int id; 
    public Animal(String myName, int myid) { 
        name = myName; 
        id = myid;
    } 
    public void eat(){ 
        System.out.println(name+"正在吃"); 
    }
    public void sleep(){
        System.out.println(name+"正在睡");
    }
    public void introduction() { 
        System.out.println("大家好！我是"         + id + "号" + name + "."); 
    } 
}
```

**企鹅类：**

```Java
public class Penguin extends Animal { 
    public Penguin(String myName, int myid) { 
        super(myName, myid); 
    } 
}
```

**老鼠类：**

```Java
public class Mouse extends Animal { 
    public Mouse(String myName, int myid) { 
        super(myName, myid); 
    } 
}
```

### 继承类型

需要注意的是 **Java 不支持多继承**，但**支持多重继承**。

![img](https://www.runoob.com/wp-content/uploads/2013/12/types_of_inheritance-1.png)

### 继承的特性

- 子类拥有父类**非 private 的属性、方法**。
- 子类可以拥有自己的属性和方法，即**子类可以对父类进行扩展**。
- 子类可以**用自己的方式实现父类的方法**。
- Java 的继承是**单继承**，但是**可以多重继承**，**单继承**就是**一个子类只能继承一个父类**，**多重继承**就是，例如 **A 类继承 B 类，B 类继承 C 类**，所以按照关系就是 C 类是 B 类的父类，B 类是 A 类的父类，这是 Java 继承区别于 C++ 继承的一个特性。
- 提高了**类之间的耦合性**（继承的缺点，耦合度高就会**造成代码之间的联系越紧密，代码独立性越差**）。

### 继承关键字

#### extends关键字

在 Java 中，类的继承是**单一继承**，也就是说，一个子类只能拥有一个父类，所以 **extends 只能继承一个类**。

```Java
public class Animal { 
    private String name;   
    private int id; 
    public Animal(String myName, String myid) { 
        //初始化属性值
    }
    public void eat() {}//吃东西方法的具体实现 
    public void sleep() {}//睡觉方法的具体实现 
} 
        
public class Penguin  extends  Animal{ 
    
}
```

#### implements关键字

使用 **implements** 关键字可以**变相的使java具有多继承的特性**，使用范围为类继承接口的情况，可以**同时继承多个接口**

```Java
public interface A {
    public void eat();
    public void sleep();
}
 
public interface B {
    public void show();
}

public class C implements A,B {
}
```

#### super & this 关键字

**super关键字**：我们可以通过super关键字来实现**对父类成员的访问**，用来**引用当前对象的父类**。

**this关键字**：指向**自己的引用**。

```Java
class Animal {
  void eat() {
    System.out.println("animal : eat");
  }
}
 
class Dog extends Animal {
  void eat() {
    System.out.println("dog : eat");
  }
  void eatTest() {
    this.eat();   // this 调用自己的方法
    super.eat();  // super 调用父类方法
  }
}
 
public class Test {
  public static void main(String[] args) {
    Animal a = new Animal();
    a.eat();
    Dog d = new Dog();
    d.eatTest();
  }
}
/*输出:
animal : eat
dog : eat
animal : eat
*/
```

#### final关键字

final 关键字声明类可以**把类定义为不能继承**的，即**最终类**；或者用于**修饰方法**，该方法**不能被子类重写**：

- 声明类：

  ```java
  final class 类名 {//类体}
  ```

- 声明方法：

  ```java
  修饰符(public/private/default/protected) final 返回值类型 方法名(){}//方法体
  ```

**实例变量**也可以被定义为 **final**，被**定义为 final 的变量不能被修改**。

被**声明为 final 类的方法自动地声明为 final**，但是**实例变量并不是 final**。

### 构造器

**子类**是**不继承父类的构造器**（*构造方法或者构造函数*）的，它只是**调用**（隐式或显式）。

如果**父类的构造器带有参数**，则**必须**在**子类的构造器**中**显式**地通过 **super** 关键字**调用父类的构造器并配以适当的参数列表**。

如果**父类构造器没有参数**，则在子类的构造器中**不需要**使用 **super** 关键字调用父类构造器，系统会**自动调用父类的无参构造器**。

```java
class SuperClass {
      private int n;
      SuperClass(){
        System.out.println("SuperClass()");
      }
      SuperClass(int n) {
        System.out.println("SuperClass(int n)");
        this.n = n;
      }
}
// SubClass 类继承
class SubClass extends SuperClass{
      private int n;

      SubClass(){ // 自动调用父类的无参数构造器
        System.out.println("SubClass");
      }  

      public SubClass(int n){ 
        super(300);  // 调用父类中带有参数的构造器
        System.out.println("SubClass(int n):"+n);
        this.n = n;
      }
}
// SubClass2 类继承
class SubClass2 extends SuperClass{
      private int n;

      SubClass2(){
        super(300);  // 调用父类中带有参数的构造器
        System.out.println("SubClass2");
      }  

      public SubClass2(int n){ // 自动调用父类的无参数构造器
        System.out.println("SubClass2(int n):"+n);
        this.n = n;
      }
}
public class TestSuperSub{
	public static void main (String args[]){
        System.out.println("------SubClass 类继承------");
        SubClass sc1 = new SubClass();
        SubClass sc2 = new SubClass(100); 
        System.out.println("------SubClass2 类继承------");
        SubClass2 sc3 = new SubClass2();
        SubClass2 sc4 = new SubClass2(200); 
	}
}
/*输出:
------SubClass 类继承------
SuperClass()
SubClass
SuperClass(int n)
SubClass(int n):100
------SubClass2 类继承------
SuperClass(int n)
SubClass2
SuperClass()
SubClass2(int n):200
*/
```

## Java 重写(Override)& 重载(Overload)

### 重写(Override)

重写是**子类对父类**的**允许访问**的方法的实现过程进行重新编写, 返回值和形参都不能改变。**即外壳不变，核心重写！**

重写方法**不能抛出新的检查异常**或者**比被重写方法申明更加宽泛的异常**。

例如： 父类的一个方法申明了一个检查异常 IOException，但是在重写这个方法的时候不能抛出 Exception 异常，因为 Exception 是 IOException 的父类，只能抛出 IOException 的子类异常。

在面向对象原则里，重写意味着**可以重写任何现有方法**。

#### 实例

```java
class Animal{
   public void move(){
      System.out.println("动物可以移动");
   }
}
 
class Dog extends Animal{
   public void move(){
      System.out.println("狗可以跑和走");
   }
}
 
public class TestDog{
   public static void main(String args[]){
      Animal a = new Animal(); // Animal 对象
      Animal b = new Dog(); // Dog 对象
 
      a.move();// 执行 Animal 类的方法
 
      b.move();//执行 Dog 类的方法
   }
}
```

由于在**编译阶段**，**只是检查参数的引用类型**。

然而在**运行时**，Java 虚拟机(JVM)指定**对象的类型**并且**运行该对象的方法**。

```java
class Animal{
   public void move(){
      System.out.println("动物可以移动");
   }
}
 
class Dog extends Animal{
   public void move(){
      System.out.println("狗可以跑和走");
   }
   public void bark(){
      System.out.println("狗可以吠叫");
   }
}
 
public class TestDog{
   public static void main(String args[]){
      Animal a = new Animal(); // Animal 对象
      Animal b = new Dog(); // Dog 对象
 
      a.move();// 执行 Animal 类的方法
      b.move();//执行 Dog 类的方法
      b.bark();
   }
}
//程序编译报错，b的引用类型Animal没有bark方法
```

#### 方法的重写规则

- **参数列表**与**被重写方法的参数列**表必须**完全相同**。
- **返回类型与被重写方法的返回类型可以不相同**，但是**必须是父类返回值的派生类**（java5 及更早版本返回类型要一样，java7 及更高版本可以不同）。
- **访问权限不能比父类中被重写的方法的访问权限更低**。例如：如果**父类的一个方法**被声明为 **public**，那么在**子类中重写该方法**就**不能声明为 protected**。
- 父类的成员方法**只能被它的子类重写**。
- 声明为 **final 的方法不能被重写**。
- 声明为 **static 的方法不能被重写**，但是**能够被再次声明**。
- **子类和父类在同一个包**中，那么**子类可以重写父类所有方法**，**除了声明为 private 和 final 的方法**。
- **子类和父类不在同一个包**中，那么**子类只能够重写父类的声明为 public 和 protected 的非 final 方法**。
- 重写的方法能够**抛出任何非强制异常**，无论被重写的方法是否抛出异常。但是，重写的方法**不能抛出新的强制性异常**，或者**比被重写方法声明的更广泛的强制性异常**，反之则可以。
- **构造方法不能被重写**。
- 如果**不能继承一个类**，则**不能重写该类的方法**。

#### Super 关键字的使用

当需要在**子类中调用父类的被重写方法**时，要使用 **super** 关键字。

```java
class Animal{
    public void move(){
        System.out.println("动物可以移动");
    }
}

class Dog extends Animal{
    public void move(){
        super.move();//super的方法
        System.out.println("狗可以跑和走")
    }
}

public class TestDog{
    public static void main(String[] args){
        Animal b = new Dog();//Dog对象
        b.move();//执行Dog类的方法
    }
}
/*输出:
动物可以移动
狗可以跑和走
*/
```

### 重载(Overload)

**重载(overloading)** 是在**一个类里面**，**方法名字相同**，而**参数不同**。**返回类型可以相同也可以不同**。

每个重载的方法（或者构造函数）都必须有一个独一无二的参数类型列表。

**重载规则:**

- 被重载的方法**必须改变参数列表**(参数个数或类型不一样)；
- 被重载的方法**可以改变返回类型**；
- 被重载的方法**可以改变访问修饰符**；
- 被重载的方法**可以声明新的或更广的检查异常**；
- 方法能够在**同一个类中或者在一个子类中被重载**。
- **无法以返回值类型作为重载函数的区分标准**。

#### 实例

```java
public class Overloading {
    public int test(){
        System.out.println("test1");
        return 1;
    }
    
    public void test(int a){
        System.out.println("test2");
    }
    
    //以下两个参数类型顺序不同
    public String test(int a,String s){
        System.out.println("test3");
        return "returntest3";
    }
    
    public String test(String s,int a){
        System.out.println("test4");
        return "returntest4";
    }
    
    public static void main(String[] args){
        Overloading o = new Overloading();
        System.out.println(o.test());
        o.test(1);
        System.out.println(o.test(1,"test3"));
        System.out.println(o.test("test4",1));
    }
}
```

### 重写与重载之间的区别

| 区别点   | 重载方法 | 重写方法                                       |
| :------- | :------- | :--------------------------------------------- |
| 参数列表 | 必须修改 | 一定不能修改                                   |
| 返回类型 | 可以修改 | 一定不能修改                                   |
| 异常     | 可以修改 | 可以减少或删除，一定不能抛出新的或者更广的异常 |
| 访问     | 可以修改 | 一定不能做更严格的限制（可以降低限制）         |

### 总结

方法的重写(Overriding)和重载(Overloading)是java多态性的不同表现，重写是父类与子类之间多态性的一种表现，重载可以理解成多态的具体表现形式。

- 方法重载是一个类中定义了多个方法名相同,而他们的参数的数量不同或数量相同而类型和次序不同,则称为方法的重载(Overloading)。
- 方法重写是在子类存在方法与父类的方法的名字相同,而且参数的个数与类型一样,返回值也一样的方法,就称为重写(Overriding)。
- **方法重载是一个类的多态性表现,而方法重写是子类与父类的一种多态性表现**。

## Java 多态

多态是**同一个行为**具有**多个不同表现形式或形态的能力**。

多态就是同一个接口，使用不同的实例而执行不同操作

### 多态的优点

-  消除类型之间的耦合关系
- 可替换性
- 可扩充性
- 接口性
- 灵活性
- 简化性

### 多态存在的三个必要条件

- **继承**
- **重写**
- **父类引用指向子类对象**

当**使用多态方式调用方法时**，首先**检查父类中是否有该方法**，**如果没有，则编译错误**；如果有，**再去调用子类的同名方法**。

多态的好处：可以使**程序有良好的扩展**，并可以对**所有类的对象进行通用处理**。

**多态实例：**

```Java
public class Test {
    public static void main(String[] args){
        show(new Cat());  //以Cat对象调用show方法
        show(new Dog());  //以Dog对象调用show方法
        
        Animal a = new Cat(); //向上转型
        a.cat();              //调用的是Cat的eat
        Cat c = (Cat)a;       //向下转型
        c.work();             //调用的是Cat的work
    }
    
    public static void show(Animal a) {
        a.eat();
        //类型判断
        if (a instanceeof Cat) { //猫做的事情
            Cat c = (Cat)a;
            c.work();
        }else if (a instanceeof Dog) { //狗做的事情
            Dog c = (Dog)a;
            c.work();
        }
    }
}

abstract class Animal {
    abstract void eat();
}

class Cat extends Animal {
    public void eat() {
        System,oyt.println("吃鱼");
    }
    public void work() {
        System.out.println("抓老鼠");
    }
}

class Dog extends Animal {
    public void eat() {
        System,oyt.println("吃骨头");
    }
    public void work() {
        System.out.println("看家");
    }
}
/*输出:
吃鱼
抓老鼠
吃骨头
看家
吃鱼
抓老鼠
*/
```

### 虚函数

**虚函数的存在是为了多态。**

Java 中其**实没有虚函数的概念**，它的**普通函数就相当于 C++ 的虚函数**，**动态绑定**是Java的默认行为。如果 **Java 中不希望某个函数具有虚函数特性**，可以加上 **final 关键字变成非虚函数**。

#### **实例**

**Employee类**

```java
/* 文件名 : Employee.java */
public class Employee {
   private String name;
   private String address;
   private int number;
   public Employee(String name, String address, int number) {
      System.out.println("Employee 构造函数");
      this.name = name;
      this.address = address;
      this.number = number;
   }
   public void mailCheck() {
      System.out.println("邮寄支票给： " + this.name
       + " " + this.address);
   }
   public String toString() {
      return name + " " + address + " " + number;
   }
   public String getName() {
      return name;
   }
   public String getAddress() {
      return address;
   }
   public void setAddress(String newAddress) {
      address = newAddress;
   }
   public int getNumber() {
     return number;
   }
}
```

**Salary类**

```java
/* 文件名 : Salary.java */
public class Salary extends Employee
{
   private double salary; // 全年工资
   public Salary(String name, String address, int number, double salary) {
       super(name, address, number);
       setSalary(salary);
   }
   public void mailCheck() {
       System.out.println("Salary 类的 mailCheck 方法 ");
       System.out.println("邮寄支票给：" + getName() + " ，工资为：" + salary);
   }
   public double getSalary() {
       return salary;
   }
   public void setSalary(double newSalary) {
       if(newSalary >= 0.0) {
          salary = newSalary;
       }
   }
   public double computePay() {
      System.out.println("计算工资，付给：" + getName());
      return salary/52;
   }
}
```

**主类**

```java
/* 文件名 : VirtualDemo.java */
public class VirtualDemo {
   public static void main(String [] args) {
      Salary s = new Salary("员工 A", "北京", 3, 3600.00);
      Employee e = new Salary("员工 B", "上海", 2, 2400.00);
      System.out.println("使用 Salary 的引用调用 mailCheck -- ");
      s.mailCheck();
      System.out.println("\n使用 Employee 的引用调用 mailCheck--");
      e.mailCheck();
    }
}
/*输出:
Employee 构造函数
Employee 构造函数
使用 Salary 的引用调用 mailCheck -- 
Salary 类的 mailCheck 方法 
邮寄支票给：员工 A ，工资为：3600.0

使用 Employee 的引用调用 mailCheck--
Salary 类的 mailCheck 方法 
邮寄支票给：员工 B ，工资为：2400.0
*/
```

**例子解析**

- 实例中，实例化了两个 Salary 对象：一个使用 Salary 引用 s，另一个使用 Employee 引用 e。
- 当调用 s.mailCheck() 时，编译器在编译时会在 Salary 类中找到 mailCheck()，执行过程 JVM 就调用 Salary 类的 mailCheck()。
- e 是 Employee 的引用，但引用 e 最终运行的是 Salary 类的 mailCheck() 方法。
- 在编译的时候，编译器使用 Employee 类中的 mailCheck() 方法验证该语句， 但是在运行的时候，Java虚拟机(JVM)调用的是 Salary 类中的 mailCheck() 方法。

### 多态的实现方式

**方式一：[重写](#重写(Override))**

**方式二：[接口](#Java 接口)**

**方式三：[抽象类和抽象方法](#Java 抽象类)_**

## Java 抽象类

在面向对象的概念中，所有的对象都是通过类来描绘的，但是反过来，**并不是所有的类都是用来描绘对象的**，如果**一个类中没有包含足够的信息来描绘一个具体的对象**，这样的类就是**抽象类**。

**抽象类**除了**不能实例化对象**之外，**类的其它功能依然存在**，成员变量、成员方法和构造方法的访问方式和普通类一样。

由于抽象类不能实例化对象，所以**抽象类必须被继承**，才能被使用。

**父类包含了子类集合的常见的方法**，但是由于**父类本身是抽象**的，所以**不能使用这些方法。**

### 抽象类

**实例**

```Java
/* 文件名 : Employee.java */
public abstract class Employee // Employee类
{
   private String name;
   private String address;
   private int number;
   public Employee(String name, String address, int number)
   {
      System.out.println("Constructing an Employee");
      this.name = name;
      this.address = address;
      this.number = number;
   }
   public double computePay()
   {
     System.out.println("Inside Employee computePay");
     return 0.0;
   }
   public void mailCheck()
   {
      System.out.println("Mailing a check to " + this.name
       + " " + this.address);
   }
   public String toString()
   {
      return name + " " + address + " " + number;
   }
   public String getName()
   {
      return name;
   }
   public String getAddress()
   {
      return address;
   }
   public void setAddress(String newAddress)
   {
      address = newAddress;
   }
   public int getNumber()
   {
     return number;
   }
}
```

**错误例子**

```Java
/* 文件名 : AbstractDemo.java */
public class AbstractDemo
{
   public static void main(String [] args)
   {
      /* 以下是不允许的，会引发错误 ,不可实例化，所以编译错误*/
      Employee e = new Employee("George W.", "Houston, TX", 43);
 
      System.out.println("\n Call mailCheck using Employee reference--");
      e.mailCheck();
    }
}
/*报错:
Employee.java:46: Employee is abstract; cannot be instantiated
      Employee e = new Employee("George W.", "Houston, TX", 43);
                   ^
1 error
*/
```

### 继承抽象类

通过一般的方法继承**Employee类**:

```java 
/* 文件名 : Salary.java */
public class Salary extends Employee //Salary类，继承Employee类
{
   private double salary; //Annual salary
   public Salary(String name, String address, int number, double salary)
   {
       super(name, address, number);
       setSalary(salary);
   }
   public void mailCheck()
   {
       System.out.println("Within mailCheck of Salary class ");
       System.out.println("Mailing check to " + getName() + " with salary " + salary);
   }
   public double getSalary()
   {
       return salary;
   }
   public void setSalary(double newSalary)
   {
       if(newSalary >= 0.0)
       {
          salary = newSalary;
       }
   }
   public double computePay()
   {
      System.out.println("Computing salary pay for " + getName());
      return salary/52;
   }
}
```

```java
/* 文件名 : AbstractDemo.java */
public class AbstractDemo
{
   public static void main(String [] args)
   {
      Salary s = new Salary("Mohd Mohtashim", "Ambehta, UP", 3, 3600.00);
      Employee e = new Salary("John Adams", "Boston, MA", 2, 2400.00);
 
      System.out.println("Call mailCheck using Salary reference --");
      s.mailCheck();
 
      System.out.println("\n Call mailCheck using Employee reference--");
      e.mailCheck();
    }
}
/*输出；
Constructing an Employee
Constructing an Employee
Call mailCheck using  Salary reference --
Within mailCheck of Salary class
Mailing check to Mohd Mohtashim with salary 3600.0

Call mailCheck using Employee reference--
Within mailCheck of Salary class
Mailing check to John Adams with salary 2400.
*/
```

### 抽象方法

**Abstract** 关键字同样可以用来声明抽象方法，抽象方法**只包含一个方法名**，而**没有方法体**。

```java 
public abstract class Employee
{
   private String name;
   private String address;
   private int number;
   
   public abstract double computePay();
   
   //其余代码
}
```

声明抽象方法会造成以下两个结果：

- 如果**一个类包含抽象方法**，那么该类**必须是抽象类**。
- **任何子类必须重写父类的抽象方法**，**或者声明自身为抽象类**。

继承抽象方法的子类**必须重写该方法**。否则，该子类也必须声明为抽象类。最终，**必须有子类实现该抽象方法**，否则，从**最初的父类到最终的子类都不能用来实例化对象**。

```java
/* 文件名 : Salary.java */
public class Salary extends Employee  //Salary类继承了Employee类，那么它必须实现computePay()方法
{
   private double salary; // Annual salary
  
   public double computePay()
   {
      System.out.println("Computing salary pay for " + getName());
      return salary/52;
   }
 
   //其余代码
}
```

### 抽象类总结

- **抽象类不能被实例化**，如果**被实例化，就会报错，编译无法通过**。只有**抽象类的非抽象子类可以创建对象**。
- 抽象类中**不一定包含抽象方法**，但是**有抽象方法的类必定是抽象类**。-
- 抽象类中的**抽象方法只是声明**，**不包含方法体**，就是**不给出方法的具体实现**也就是方法的具体功能。
- **构造方法**，类方法（**用 static 修饰的方法**）**不能声明为抽象方法**。
- 抽象类的**子类必须给出抽象类中的抽象方法的具体实现**，**除非该子类也是抽象类**。

## Java 封装

封装可以被认为是一个保护屏障，**防止该类的代码和数据**被**外部类定义的代码随机访问**。

**封装最主要的功能**在于我们能**修改自己的实现代码**，而**不用修改那些调用我们代码的程序片段**。

要访问该类的代码和数据，必须通过严格的接口控制。

适当的封装可以让**程式码更容易理解与维护**，也**加强了程式码的安全性。**

### 封装的优点

- 良好的封装能够**减少耦合**。
- **类内部的结构可以自由修改**。
- 可以**对成员变量进行更精确的控制**。
- **隐藏信息，实现细节**。

### 实现Java封装的步骤

1. 修改属性的可见性来限制**对属性的访问**（一般限制为**private**）、

   ```Java
   public class Person {
       private String name;
       private int age;
   }
   //将 name 和 age 属性设置为私有的，只能本类才能访问，其他类都访问不了
   ```

2.  对每个值属性**提供对外的公共方法访问**，也就是**创建一对赋取值方法**，用于**对私有属性的访问**

   ```java
   public class Person{
       private String name;
       private int age;
   
       public int getAge(){
         return age;
       }
   
       public String getName(){
         return name;
       }
   
       public void setAge(int age){
         this.age = age;
       }
   
       public void setName(String name){
         this.name = name;
       }
   }
   //采用 this 关键字是为了解决实例变量（private String name）和局部变量（setName(String name)中的name变量）之间发生的同名的冲突。
   ```

#### 实例

```java
/* 文件名: EncapTest.java */
public class EncapTest{
 
   private String name;
   private String idNum;
   private int age;
 
   public int getAge(){
      return age;
   }
 
   public String getName(){
      return name;
   }
 
   public String getIdNum(){
      return idNum;
   }
 
   public void setAge( int newAge){
      age = newAge;
   }
 
   public void setName(String newName){
      name = newName;
   }
 
   public void setIdNum( String newId){
      idNum = newId;
   }
}
```

以上实例中**public方法是外部类访问该类成员变量的入口**。

通常情况下，这些方法被称为**getter和setter方法**。

```java
/* F文件名 : RunEncap.java */
public class RunEncap{
   public static void main(String args[]){
      EncapTest encap = new EncapTest();
      encap.setName("James");
      encap.setAge(20);
      encap.setIdNum("12343ms");
 
      System.out.print("Name : " + encap.getName()+ " Age : " + encap.getAge());
    }
}
//输出:Name : James Age : 20
```

## Java 接口

**接口**在JAVA编程语言中是一个**抽象类型**，是**抽象方法的集合**，接口通常以**interface来声明**。

一个类通过**继承接口的方式**，从而来**继承接口的抽象方法**。

**接口并不是类**，编写接口的方式和类很相似，但是它们属于不同的概念。**类描述对象的属性和方法**。**接口则包含类要实现的方法**。

**除非实现接口的类是抽象类**，否则**该类要定义接口中的所有方法**。

接口**无法被实例化**，但是**可以被实现**。一个**实现接口的类**，**必须实现接口内所描述的所有方法，否则就必须声明为抽象类**。

在 Java 中，**接口类型可用来声明一个变量**，他们**可以成为一个空指针**，或是**被绑定在一个以此接口实现的对象**。

### 接口与类相似点：

- 一个接口可以**有多个方法**。
- 接口文件保存在 .java 结尾的文件中，文件名使用接口名。
- 接口的字节码文件保存在 .class 结尾的文件中。
- 接口相应的字节码文件必须在与包名称相匹配的目录结构中。

### 接口与类的区别：

- 接口**不能用于实例化对象**。
- 接口**没有构造方法**。
- 接口中**所有的方法必须是抽象方法**。
- 接口**不能包含成员变量**，**除了 static 和 final 变量**。
- 接口**不是被类继承了，而是要被类实现**。
- 接口**支持多继承**。

### 接口特性

- 接口中每一个方法也是**隐式抽象**的,接口中的方法会被隐式的指定为 **public abstract**（**只能是 public abstract**，其他修饰符都会报错）。
- 接口中**可以含有变量**，但是接口中的变量会被隐式的指定为 **public static final** 变量（**并且只能是 public**，用 private 修饰会报编译错误）。
- **接口中的方法是不能在接口中实现的**，只能由**实现接口的类来实现接口中的方法**。

### 抽象类和接口的区别

- 抽象类中的方法可以有方法体，就是能实现方法的具体功能，但是接口中的方法不行。
- 抽象类中的成员变量可以是各种类型的，而接口中的成员变量只能是 **public static final** 类型的。
- 接口中不能含有静态代码块以及静态方法(用 static 修饰的方法)，而抽象类是可以有静态代码块和静态方法。
- 一个类**只能继承一个抽象类**，而一个类却可以**实现多个接口**。

> **注**：**JDK 1.8 以后，接口里可以有静态方法和方法体了**。

### 接口的声明

```java
[可见度] interface 接口名称 [extends 其他的接口名] {
        // 声明变量
        // 抽象方法
}
//[]内可有可无
```

```Java
/* 文件名 : NameOfInterface.java  例子*/
import java.lang.*;
//引入包
 
public interface NameOfInterface
{
   //任何类型 final, static 字段
   //抽象方法
}
/*
接口是隐式抽象的，当声明一个接口的时候，不必使用abstract关键字。
接口中每一个方法也是隐式抽象的，声明时同样不需要abstract关键字。
接口中的方法都是公有的。
*/
```

**实例**

```Java
/* 文件名 : Animal.java */
interface Animal {
   public void eat();
   public void travel();
}
```

### 接口的实现

当类实现接口的时候，**类要实现接口中所有的方法**。否则，**类必须声明为抽象的类**。

类使用**implements关键字**实现接口。在类声明中，**Implements关键字放在class声明后面**。

**实例**

```Java
/* 文件名 : MammalInt.java */
public class MammalInt implements Animal{
 
   public void eat(){
      System.out.println("Mammal eats");
   }
 
   public void travel(){
      System.out.println("Mammal travels");
   } 
 
   public int noOfLegs(){
      return 0;
   }
 
   public static void main(String args[]){
      MammalInt m = new MammalInt();
      m.eat();
      m.travel();
   }
}
/*输出；
Mammal eats
Mammal travels
*/
```

**重写接口中声明的方法**时，需要注意以下规则：

- 类在实现接口的方法时，**不能抛出强制性异常**，只能在接口中，或者继承接口的抽象类中抛出该强制性异常。
- 类在重写方法时要保持一致的方法名，并且应该保持相同或者相兼容的返回值类型。
- **如果实现接口的类是抽象类，那么就没必要实现该接口的方法**。

在**实现接口的**时候，也要注意一些规则：

- 一个类可以同时**实现多个接口**。
- 一个类**只能继承一个类**，但是**能实现多个接口**。
- 一**个接口能继承另一个接口**，这和类之间的继承比较相似。

### 接口的继承

接口的继承使用**extends**关键字，子接口继承父接口的方法。

```java
// 文件名: Sports.java
public interface Sports
{
   public void setHomeTeam(String name);
   public void setVisitingTeam(String name);
}
 
// 文件名: Football.java
public interface Football extends Sports
{
   public void homeTeamScored(int points);
   public void visitingTeamScored(int points);
   public void endOfQuarter(int quarter);
}
 
// 文件名: Hockey.java
public interface Hockey extends Sports
{
   public void homeGoalScored();
   public void visitingGoalScored();
   public void endOfPeriod(int period);
   public void overtimePeriod(int ot);
}
//Hockey接口自己声明了四个方法，从Sports接口继承了两个方法，这样，实现Hockey接口的类需要实现六个方法。
//实现Football接口的类需要实现五个方法，其中两个来自于Sports接口。
```

### 接口的多继承

**类的多继承是不合法，但接口允许多继承。**

在接口的多继承中extends关键字只需要使用一次，在其后跟着继承接口。

```java
public interface Hockey extends Sports, Event
```

### 标记接口

**标记接口**是**没有任何方法和属性的接口**，它**仅仅表明它的类属于一个特定的类型**,**供其他代码来测试允许做一些事情**。

**java.awt.event 包中的 MouseListener 接口继承的 java.util.EventListener 接口定义如下：**

```java
packge java.util;
public interface EventListener{
}
```

**标记接口主要用于以下两种目的：**

- **建立一个公共的父接口：**

  正如EventListener接口，这是由几十个其他接口扩展的Java API，你可以使用一个标记接口来建立一组接口的父接口。例如：当一个接口继承了EventListener接口，Java虚拟机(JVM)就知道该接口将要被用于一个事件的代理方案。

- **向一个类添加数据类型：**

  这种情况是标记接口最初的目的，实现标记接口的类不需要定义任何接口方法(因为标记接口根本就没有方法)，但是该类通过多态性变成一个接口类型。

## Java 枚举(enum)

Java 枚举是一个**特殊的类**，**一般表示一组常量**，比如一年的 4 个季节，一个年的 12 个月份，一个星期的 7 天，方向有东南西北等。

Java 枚举类使用 **enum 关键字**来定义，各个常量使用**逗号 , 来分割**。\

**实例**

```java
enum Color //定义一个颜色的枚举类
{
    RED, GREEN, BLUE;
}
 
public class Test
{
    // 执行输出结果
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
//输出:RED
```

### 内部类中使用枚举

```Java
public class Test
{
    enum Color
    {
        RED, GREEN, BLUE;
    }
 
    // 执行输出结果
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
    }
}
//输出:RED
```

**每个枚举**都是**通过 Class 在内部实现**的，且**所有的枚举值都是 public static final 的**。

```java
class Color//枚举类 Color 转化在内部类实现
{
     public static final Color RED = new Color();
     public static final Color BLUE = new Color();
     public static final Color GREEN = new Color();
}
```

### 迭代枚举元素

```java
enum Color
{
    RED, GREEN, BLUE;
}
public class MyClass {
  public static void main(String[] args) {
    for (Color myVar : Color.values()) {
      System.out.println(myVar);
    }
  }
}
/*输出；
RED
GREEN
BLUE
*/
```

### switch 中使用枚举类

```Java
enum Color
{
    RED, GREEN, BLUE;
}
public class MyClass {
  public static void main(String[] args) {
    Color myVar = Color.BLUE;

    switch(myVar) {
      case RED:
        System.out.println("红色");
        break;
      case GREEN:
         System.out.println("绿色");
        break;
      case BLUE:
        System.out.println("蓝色");
        break;
    }
  }
}
//输出:蓝色
```

### values(), ordinal() 和 valueOf() 方法

**enum** 定义的枚举类默认**继承了 java.lang.Enum 类**，并**实现了 java.lang.Seriablizable 和 java.lang.Comparable 两个接口**。

values(), ordinal() 和 valueOf() 方法位于 **java.lang.Enum 类**中：

- **values()** 返回**枚举类中所有的值**。
- **ordinal()**方法可以**找到每个枚举常量的索引**，就像数组索引一样。
- **valueOf()**方法返回**指定字符串值的枚举常量**。

```Java
enum Color
{
    RED, GREEN, BLUE;
}
 
public class Test
{
    public static void main(String[] args)
    {
        // 调用 values()
        Color[] arr = Color.values();
 
        // 迭代枚举
        for (Color col : arr)
        {
            // 查看索引
            System.out.println(col + " at index " + col.ordinal());
        }
 
        // 使用 valueOf() 返回枚举常量，不存在的会报错 IllegalArgumentException
        System.out.println(Color.valueOf("RED"));
        // System.out.println(Color.valueOf("WHITE"));
    }
}
/*输出；
RED at index 0
GREEN at index 1
BLUE at index 2
RED
*/
```

### 枚举类成员

枚举跟普通类一样可以用自己的**变量、方法和构造函数**，**构造函数只能使用 private 访问修饰符**。

枚举既可以**包含具体方法**，也可以**包含抽象方法**。 如果枚举类**具有抽象方法**，则**枚举类的每个实例都必须实现它**。

```Java
enum Color
{
    RED, GREEN, BLUE;
 
    // 构造函数
    private Color()
    {
        System.out.println("Constructor called for : " + this.toString());
    }
 
    public void colorInfo()
    {
        System.out.println("Universal Color");
    }
}
 
public class Test
{    
    // 输出
    public static void main(String[] args)
    {
        Color c1 = Color.RED;
        System.out.println(c1);
        c1.colorInfo();
    }
}
/*输出;
Constructor called for : RED
Constructor called for : GREEN
Constructor called for : BLUE
RED
Universal Color
*/
```

## Java 包(package）

为了更好地组织类，Java 提供了包机制，用于**区别类名的命名空间**。

**包的作用**

- 把**功能相似或相关的类或接口组织在同一个包**中，**方便类的查找和使用**。
- 如同文件夹一样，**包也采用了树形目录的存储方式**。**同一个包中的类名字是不同的**，**不同的包中的类的名字是可以相同的**，当**同时调用两个不同包中相同类名的类时，应该加上包名加以区别**。因此，包可以避免名字冲突。
- 包也**限定了访问权限**，**拥有包访问权限的类才能访问某个包中的类**。

Java 使用**包（package）**这种机制是为了**防止命名冲突**，**访问控制**，提供**搜索和定位类（class）**、**接口**、**枚举（enumerations）**和**注释（annotation）**等。

```java
package pkg1[．pkg2[．pkg3…]];//包的语法格式
```

### 创建包

包声明应该在**源文件的第一行**，每个源文件**只能有一个包声明**，这个文件中的每个类型都应用于它。

如果一个源文件中**没有使用包声明**，那么其中的类，函数，枚举，注释等将被**放在一个无名的包（unnamed package）中**。

**实例**

```java
/* 文件名: Animal.java */
package animals;
 
interface Animal {
   public void eat();
   public void travel();
}
```

在同一个包中加入该接口的实现:

```java
package animals;
 
/* 文件名 : MammalInt.java */
public class MammalInt implements Animal{
 
   public void eat(){
      System.out.println("Mammal eats");
   }
 
   public void travel(){
      System.out.println("Mammal travels");
   } 
 
   public int noOfLegs(){
      return 0;
   }
 
   public static void main(String args[]){
      MammalInt m = new MammalInt();
      m.eat();
      m.travel();
   }
}
/*输出:
Mammal eats
Mammal travel
*/
```

### import 关键字

为了能够使用某一个包的成员，我们需要在 Java 程序中明确导入该包。使用 "import" 语句可完成此功能。

```java
import package1[.package2…].(classname|*);
```

**实例**

下面的 payroll 包已经包含了 Employee 类，接下来向 payroll 包中添加一个 Boss 类。Boss 类引用 Employee 类的时候可以不用使用 payroll 前缀

```Java
package payroll;
 
public class Boss
{
   public void payEmployee(Employee e)
   {
      e.mailCheck();
   }
}
```

 **Boss 类不在 payroll 包中**

```java
payroll.Employee  //使用类全名描述

import payroll.*; //用 import 关键字引入，使用通配符 "*"

import payroll.Employee;  //使用 import 关键字引入 Employee 类
```

**import 声明必须在包声明之后，类声明之前。**