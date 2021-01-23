# Java(高级教程)

## Java 数据结构

Java工具包提供了强大的数据结构。在Java中的数据结构主要包括以下几种**接口和类**：

- **枚举**（Enumeration）
- **位集合**（BitSet）
- **向量**（Vector）
- **栈**（Stack）
- **字典**（Dictionary）
- **哈希表**（Hashtable）
- **属性**（Properties）
------

### 枚举（Enumeration）

**这种传统接口已被迭代器取代**。

枚举（Enumeration）接口虽然它**本身不属于数据结构**,但它在**其他数据结构的范畴里应用很广**。 枚举（The Enumeration）接口定义了一种从**数据结构中取回连续元素的方式**。它还是使用在诸如**Vector和Properties**这些传统类所定义的方法中。

**Enumeration声明的方法**：

| 方法                           |                         **方法描述**                         |
| :----------------------------- | :----------------------------------------------------------: |
| **boolean hasMoreElements( )** |              测试此枚举**是否包含更多的元素**。              |
| **Object nextElement( )**      | 如果此枚举对象**至少还有一个可提供的元素**，则返回**此枚举的下一个元素**。 |

**实例**

```Java
import java.util.Vector;
import java.util.Enumeration;
 
public class EnumerationTester {
 
   public static void main(String args[]) {
      Enumeration<String> days;
      Vector<String> dayNames = new Vector<String>();
      dayNames.add("Sunday");
      dayNames.add("Monday");
      dayNames.add("Tuesday");
      dayNames.add("Wednesday");
      dayNames.add("Thursday");
      dayNames.add("Friday");
      dayNames.add("Saturday");
      days = dayNames.elements();
      while (days.hasMoreElements()){
         System.out.println(days.nextElement()); 
      }
   }
}
/*输出:
Sunday
Monday
Tuesday
Wednesday
Thursday
Friday
Saturday
*/
```

------

### 位集合（BitSet）

一个Bitset类创建一种**特殊类型的数组来保存位值**。BitSet中**数组大小会随需要增加**。和位向量（vector of bits）比较类似。

**BitSet定义了两个构造方法**。

第一个构造方法**创建一个默认的对象**：

```java
BitSet()
```

第二个方法**允许用户指定初始大小**。所有位初始化为0。

```java
BitSet(int size)
```

**BitSet中实现了Cloneable接口中定义的方法**如下表所列：

| 方法                                                  | 方法描述                                                     |
| :---------------------------------------------------- | :----------------------------------------------------------- |
| **void and(BitSet set)**                              | 对**此目标位 set** 和**参数位 set** 执行**逻辑与**操作。     |
| **void andNot(BitSet set)**                           | **清除此 BitSet 中所有的位**，其**相应的位在指定的 BitSet** 中已设置。 |
| **int cardinality()**                                 | 返回此 BitSet 中**设置为 true 的位数**。                     |
| **void clear()**                                      | 将此 BitSet 中的**所有位设置为 false**。                     |
| **void clear(int index)**                             | 将**索引指定处的位设置为 false**。                           |
| **void clear(int startIndex, int endIndex)**          | 将指**定的 startIndex**（**包括**）到**指定的 toIndex**（**不包括**）范围内的**位设置为 false**。 |
| **Object clone()**                                    | **复制此 BitSet**，生成一个与之相等的新 BitSet。             |
| **boolean equals(Object bitSet)**                     | 将**此对象**与**指定的对象**进行**比较**。                   |
| **void flip(int index)**                              | 将**指定索引处的位设置为其当前值的补码**。                   |
| **void flip(int startIndex, int endIndex)**           | 将**指定的 fromIndex**（**包括**）到**指定的 toIndex**（**不包括**）范围内的每个位**设置为其当前值的补码**。 |
| **boolean get(int index)**                            | 返回**指定索引处的位值**。                                   |
| **BitSet get(int startIndex, int endIndex)**          | 返回**一个新的 BitSe**t，它由此 BitSet 中从 **fromIndex（包括）到 toIndex（不包括）范围内的位组成**。 |
| **int hashCode()**                                    | 返回**此位 set 的哈希码值**。                                |
| **boolean intersects(BitSet bitSet)**                 | 如果**指定的 BitSet 中有设置为 true 的位**，并且在**此 BitSet 中也将其设置为 true**，则**返回 true**。 |
| **boolean isEmpty()**                                 | 如果**此 BitSet 中没有包含任何设置为 true 的位**，则返回 **true**。 |
| **int length()**                                      | 返回**此 BitSet 的"逻辑大小"**：BitSet 中**最高设置位的索引加 1**。 |
| **int nextClearBit(int startIndex)**                  | 返回**第一个设置为 false 的位的索引**，这发生在**指定的起始索引或之后的索引上**。 |
| **int nextSetBit(int startIndex)**                    | 返回**第一个设置为 true 的位的索引**，这发生在**指定的起始索引或之后的索引上**。 |
| **void or(BitSet bitSet)**                            | 对**此位 set** 和**位 set 参数**执行**逻辑或**操作。         |
| **void set(int index)**                               | 将**指定索引处的位设置为 true**。                            |
| **void set(int index, boolean v)**                    | 将**指定索引处的位设置为指定的值**。                         |
| **void set(int startIndex, int endIndex)**            | 将**指定的 fromIndex**（**包括**）到**指定的 toIndex**（**不包括**）范围内的位设置为 **true**。 |
| **void set(int startIndex, int endIndex, boolean v)** | 将**指定的 fromIndex**（**包括**）到**指定的 toIndex**（**不包括**）范围内的位设置为**指定的值**。 |
| **int size()**                                        | 返回**此 BitSet 表示位值时实际使用空间的位数**。             |
| **String toString()**                                 | 返回**此位 set 的字符串表示形式**。                          |
| **void xor(BitSet bitSet)**                           | 对**此位 set** 和**位 set 参数**执行**逻辑异或**操作。       |

**实例**

```Java
import java.util.BitSet;
 
public class BitSetDemo {
 
  public static void main(String args[]) {
     BitSet bits1 = new BitSet(16);
     BitSet bits2 = new BitSet(16);
      
     // set some bits
     for(int i=0; i<16; i++) {
        if((i%2) == 0) bits1.set(i);
        if((i%5) != 0) bits2.set(i);
     }
     System.out.println("Initial pattern in bits1: ");
     System.out.println(bits1);
     System.out.println("\nInitial pattern in bits2: ");
     System.out.println(bits2);
 
     // AND bits 逻辑与
     bits2.and(bits1);
     System.out.println("\nbits2 AND bits1: ");
     System.out.println(bits2);
 
     // OR bits 逻辑或
     bits2.or(bits1);
     System.out.println("\nbits2 OR bits1: ");
     System.out.println(bits2);
 
     // XOR bits 逻辑异或
     bits2.xor(bits1);
     System.out.println("\nbits2 XOR bits1: ");
     System.out.println(bits2);
  }
}
/*输出:
Initial pattern in bits1:
{0, 2, 4, 6, 8, 10, 12, 14}

Initial pattern in bits2:
{1, 2, 3, 4, 6, 7, 8, 9, 11, 12, 13, 14}

bits2 AND bits1:
{2, 4, 6, 8, 12, 14}

bits2 OR bits1:
{0, 2, 4, 6, 8, 10, 12, 14}

bits2 XOR bits1:
{}
*/
```

------

### 向量（Vector）

**Vector** 类实现了一个**动态数组**。和 ArrayList 很相似，但是两者是不同的：

- Vector 是**同步访问**的。
- Vector 包含了**许多传统的方法**，这些方法不属于集合框架。

**Vector 类支持 4 种构造方法**。

第一种构造方法**创建一个默认的向量**，默认大小为 **10**：

```java
Vector()
```

第二种构造方法**创建指定大小的向量**。

```JAVA
Vector(int size)
```

第三种构造方法**创建指定大小的向量**，并且**增量用 incr 指定**。增量表示**向量每次增加的元素数目**。

```Java
Vector(int size,int incr)
```

第四种构造方法**创建一个包含集合 c 元素的向量**：

```Java
Vector(Collection c)
```

**Vector定义了以下方法**：

| 方法                                                       | 方法描述                                                     |
| :--------------------------------------------------------- | :----------------------------------------------------------- |
| **void add (int index, Object element)**                   | 在**此向量的指定位置插入指定的元素**。                       |
| **boolean add (Object o)**                                 | 将**指定元素**添加到此**向量的末尾**。                       |
| **boolean addAll (Collection c)**                          | 将**指定 Collection 中的所有元素**添加到此**向量的末尾**，按照指定 **collection 的迭代器所返回的顺序**添加这些元素。 |
| **boolean addAll (int index, Collection c)**               | 在**指定位置**将**指定 Collection 中的所有元素**插入到此向量中。 |
| **void addElement (Object obj)**                           | 将**指定的组件**添加到此**向量的末尾**，将**其大小增加 1**。 |
| **int capacity()**                                         | 返回**此向量的当前容量**。                                   |
| **void clear()**                                           | 从此向量中**移除所有元素**。                                 |
| **Object clone()**                                         | 返回**向量的一个副本**。                                     |
| **boolean contains(Object elem)**                          | 如果**此向量包含指定的元素**，则返回 **true**。              |
| **boolean containsAll(Collection c)**                      | 如果**此向量包含指定 Collection 中的所有元素**，则返回 **true**。 |
| **void copyInto(Object[] anArray)**                        | 将此**向量的组件复制到指定的数组**中。                       |
| **Object elementAt(int index)**                            | 返回**指定索引处的组件**。                                   |
| **Enumeration elements()**                                 | 返回**此向量的组件的枚举**。                                 |
| **void ensureCapacity(int minCapacity)**                   | **增加此向量的容量**（如有必要），以确保其至少能够保存最小容量参数指定的组件数。 |
| **boolean equals(Object o)**                               | 比较**指定对象**与**此向量**的**相等性**。                   |
| **Object firstElement()**                                  | 返回**此向量的第一个组件**（**位于索引 0) 处的项**）。       |
| **Object get(int index)**                                  | 返回**向量中指定位置的元素**。                               |
| **int hashCode()**                                         | 返回**此向量的哈希码值**。                                   |
| **int indexOf(Object elem)**                               | 返回**此向量中第一次出现的指定元素的索引**，如果**此向量不包含该元素**，则返回 **-1**。 |
| **int indexOf(Object elem, int index)**                    | 返回**此向量中第一次出现的指定元素的索引**，从 **index 处正向搜索**，如果未找到该元素，则返回 **-1**。 |
| **void insertElementAt(Object obj, int index)**            | 将**指定对象作为此向量中的组件**插入到**指定的 index 处**。  |
| **boolean isEmpty()**                                      | 测试此向量**是否不包含组件**。                               |
| **Object lastElement()**                                   | 返回**此向量的最后一个组件**。                               |
| **int lastIndexOf(Object elem)**                           | 返回**此向量中最后一次出现的指定元素的索引**；如果**此向量不包含该元素**，则返回 **-1**。 |
| **int lastIndexOf(Object elem, int index)**                | 返回**此向量中最后一次出现的指定元素的索引**，从 **index 处逆向搜索**，如果未找到该元素，则返回 **-1**。 |
| **Object remove(int index)**                               | **移除此向量中指定位置的元素**。                             |
| **boolean remove(Object o)**                               | **移除此向量中指定元素的第一个匹配项**，如果**向量不包含该元素**，则**元素保持不变**。 |
| **boolean removeAll(Collection c)**                        | 从此向量中**移除包含在指定 Collection 中的所有元素**。       |
| **void removeAllElements()**                               | 从此向量中**移除全部组件**，并将**其大小设置为零**。         |
| **boolean removeElement(Object obj)**                      | 从此向量中**移除变量的第一个（索引最小的）匹配项**。         |
| **void removeElementAt(int index)**                        | **删除指定索引处的组件**。                                   |
| **protected void removeRange(int fromIndex, int toIndex)** | 从此 List 中**移除**其索引位于 **fromIndex（包括）与 toIndex（不包括）之间的所有元素**。 |
| **boolean retainAll(Collection c)**                        | 在此向量中**仅保留包含在指定 Collection 中的元素**。         |
| **Object set(int index, Object element)**                  | 用**指定的元素替换此向量中指定位置处的元素**。               |
| **void setElementAt(Object obj, int index)**               | 将此向量**指定 index 处**的组件设置为**指定的对象**。        |
| **void setSize(int newSize)**                              | 设置此**向量的大小**。                                       |
| **int size()**                                             | 返回此**向量中的组件数**。                                   |
| **List subList(int fromIndex, int toIndex)**               | 返回此 **List 的部分视图**，元素范围为从 **fromIndex（包括）到 toIndex（不包括）**。 |
| **Object[] toArray()**                                     | 返回一个**数组**，包含此**向量中以恰当顺序存放的所有元素**。 |
| **Object[] toArray(Object[] a)**                           | 返回一个**数组**，包含此**向量中以恰当顺序存放的所有元素**；返回数组的**运行时类型为指定数组的类型**。 |
| **String toString()**                                      | 返回**此向量的字符串表示形式**，其中包含每个元素的 String 表示形式。 |
| **void trimToSize()**                                      | 对此**向量的容量进行微调**，使**其等于向量的当前大小**。     |

**实例**

```Java
import java.util.*;

public class VectorDemo {

   public static void main(String args[]) {
      // 初始容量为 3, 增量为 2
      Vector<Object> v = new Vector<>(3, 2);
      System.out.println("初始大小: " + v.size());
      System.out.println("初始容量: " + v.capacity());
      v.addElement(1);
      v.addElement(2);
      v.addElement(3);
      v.addElement(4);
      System.out.println("增加4个数后的容量: " + v.capacity());

      v.addElement(5.45);
      System.out.println("当前容量: " + v.capacity());
      v.addElement(6.08);
      v.addElement(7);
      System.out.println("当前容量: " + v.capacity());
      v.addElement(9.4);
      v.addElement(10);
      System.out.println("当前容量: " + v.capacity());
      v.addElement(11);
      v.addElement(12);
      System.out.println("首元素: " + v.firstElement());
      System.out.println("末尾元素: " + v.lastElement());
      if(v.contains(3))
         System.out.println("Vector 包含 3.");
       
      // enumerate the elements in the vector.
      Enumeration<Object> vEnum = v.elements();
      System.out.println("\nvector 中的元素:");
      while(vEnum.hasMoreElements())
         System.out.print(vEnum.nextElement() + " ");
      System.out.println();
   }
}
/*输出:
初始大小: 0
初始容量: 3
增加4个数后的容量: 5
当前容量: 5
当前容量: 7
当前容量: 9
首元素: 1
末尾元素: 12
Vector 包含 3.

vector 中的元素:
1 2 3 4 5.45 6.08 7 9.4 10 11 12
*/
```

------

### 栈（Stack）

**栈是Vector的一个子类**。

**栈（Stack）**实现了一个**后进先出（LIFO）**的数据结构。

堆栈只定义了默认构造函数，用来**创建一个空栈**。

```java
Stack()
```

除了**有Vector定义的所有方法**，**Stack也定义了一些方法**:

| 方法                             | 方法描述                                                 |
| :------------------------------- | :------------------------------------------------------- |
| **boolean empty ()**             | 测试**堆栈是否为空**。                                   |
| **Object peek ()**               | **查看堆栈顶部的对象**，但**不从堆栈中移除它**。         |
| **Object pop ()**                | **移除堆栈顶部的对象**，并**作为此函数的值返回该对象**。 |
| **Object push (Object element)** | 把**项压入堆栈顶部**。                                   |
| **int search(Object element)**   | 返回**对象在堆栈中的位置**，以 **1 为基数**。            |

**实例**

```Java
import java.util.*;
 
public class StackDemo {
 
    static void showpush(Stack<Integer> st, int a) {
        st.push(a);
        System.out.println("push(" + a + ")");
        System.out.println("stack: " + st);
    }
 
    static void showpop(Stack<Integer> st) {
        System.out.print("pop -> ");
        Integer a = st.pop();
        System.out.println(a);
        System.out.println("stack: " + st);
    }
 
    public static void main(String args[]) {
        Stack<Integer> st = new Stack<>();
        System.out.println("stack: " + st);
        showpush(st, 42);
        showpush(st, 66);
        showpush(st, 99);
        showpop(st);
        showpop(st);
        showpop(st);
        try {
            showpop(st);
        } catch (EmptyStackException e) {
            System.out.println("empty stack");
        }
    }
}
/*输出:
Stack: []
push(42)
Stack: [42]
push(66)
Stack: [42, 66]
push(99)
Stack: [42, 66, 99]
pop -> 99
Stack: [42, 66]
pop -> 66
Stack: [42]
pop -> 42
Stack: []
pop -> empty Stack
*/
```

------

### 字典（Dictionary）

字典（Dictionary） 类是一个抽象类，它定义了**键映射到值的数据结构**。

**Dictionary类已经过时**了。在实际开发中，你可以实现**Map接口**来**获取键/值的存储功能**。

------

### 哈希表（Hashtable）

Hashtable类提供了一种在用户定义键结构的基础上来组织数据的手段。

Java 2 重构的Hashtable实现了Map接口。

**Hashtable**现在集成到了集合框架中。它和**HashMap**类很**相似**，但是**它支持同步**。

当使用一个哈希表，要**指定用作键的对象**，以及**要链接到该键的值**。

**Hashtable定义了四个构造方法**：

第一个是默认构造方法：

```java
Hashtable()
```

第二个构造函数**创建指定大小的哈希表**：

```Java
Hashtable(int size)
```

第三个构造方法创建了一个**指定大小的哈希表**，并且**通过fillRatio指定填充比例**。

**填充比例必须介于0.0和1.0之间**，它决定了**哈希表在重新调整大小之前的充满程度**：

```Java
Hashtable(int size,float fillRatio)
```

第四个构造方法创建了**一个以M中元素为初始化元素的哈希表**。

**哈希表的容量被设置为M的两倍**。

```Java
Hashtable(Map m)
```

**Hashtable中除了从Map接口中定义的方法**外，还定义了以下方法：

| 方法                                     | **方法描述**                                                 |
| :--------------------------------------- | :----------------------------------------------------------- |
| **void clear( )**                        | 将此**哈希表清空**，使其**不包含任何键**。                   |
| **Object clone( )**                      | **创建此哈希表的浅表副本**。                                 |
| **boolean contains(Object value)**       | 测试**此映射表中是否存在与指定值关联的键**。                 |
| **boolean containsKey(Object key)**      | 测试**指定对象是否为此哈希表中的键**。                       |
| **boolean containsValue(Object value)**  | 如果此 Hashtable 将**一个或多个键映射到此值**，则返回 **true**。 |
| **Enumeration elements( )**              | 返回此哈希表中的**值的枚举**。                               |
| **Object get(Object key)**               | 返回**指定键所映射到的值**，如果此映射**不包含此键的映射**，则返回 **null**. 更确切地讲，如果此映射**包含满足 (key.equals(k)) 的从键 k 到值 v 的映射**，则此方法返回 **v**；否则，返回 **null**。 |
| **boolean isEmpty( )**                   | 测试此哈希表**是否没有键映射到值**。                         |
| **Enumeration keys( )**                  | 返回此哈希表中的**键的枚举**。                               |
| **Object put(Object key, Object value)** | 将**指定 key 映射到此哈希表中的指定 value**。                |
| **void rehash( )**                       | **增加此哈希表的容量**并**在内部对其进行重组**，以便更有效地容纳和访问其元素。 |
| **Object remove(Object key)**            | 从哈希表中**移除该键及其相应的值**。                         |
| **int size( )**                          | 返回此哈希表中的**键的数量**。                               |
| **String toString( )**                   | 返回此 **Hashtable 对象的字符串表示形式**，其形式为 ASCII 字符 ", " （**逗号加空格）分隔开的**、括在括号中的一组条目。 |

**实例**

```Java
import java.util.*;

public class HashTableDemo {

   public static void main(String args[]) {
      // Create a hash map
      Hashtable<String, Double> balance = new Hashtable<>();
      Enumeration<String> names;
      String str;
      double bal;

      balance.put("Zara", new Double(3434.34));
      balance.put("Mahnaz", new Double(123.22));
      balance.put("Ayan", new Double(1378.00));
      balance.put("Daisy", new Double(99.22));
      balance.put("Qadir", new Double(-19.08));

      // Show all balances in hash table.
      names = balance.keys();
      while(names.hasMoreElements()) {
         str = (String) names.nextElement();
         System.out.println(str + ": " + balance.get(str));
      }
      System.out.println();
      // Deposit 1,000 into Zara's account
      bal = balance.get("Zara");
      balance.put("Zara", new Double(bal+1000));
      System.out.println("Zara's new balance: " + balance.get("Zara"));
   }
}
/*输出:

*/
```



------

### 属性（Properties）

**Properties 继承于 Hashtable.Properties 类**表示了一个**持久的属性集**.属性列表中**每个键及其对应值都是一个字符串**。

**Properties 类被许多Java类使用**。例如，**在获取环境变量时它就作为System.getProperties()方法的返回值**。

Properties 定义如下实例变量.**这个变量持有一个Properties对象相关的默认属性列表**。

```java
properties default;
```

**Properties类定义了两个构造方法.**

 第一个构造方法**没有默认值**。

```java
Properties()
```

第二个构造方法**使用propDefault 作为默认值**。两种情况下，**属性列表都为空**：

```java
Properties(Properties propDefault)
```

除了**从Hashtable中所定义的方法**，**Properties定义了以下方法**：

| 方法                                                       | **方法描述**                                                 |
| :--------------------------------------------------------- | :----------------------------------------------------------- |
| **String getProperty(String key)**                         | 用**指定的键**在**此属性列表中搜索属性**。                   |
| **String getProperty(String key, String defaultProperty)** | 用**指定的键**在**属性列表中搜索属性**。                     |
| **void list(PrintStream streamOut)**                       | 将**属性列表输出到指定的输出流**。                           |
| **void list(PrintWriter streamOut)**                       | 将**属性列表输出到指定的输出流**。                           |
| **void load(InputStream streamIn) throws IOException**     | 从**输入流中读取属性列表**（键和元素对）。                   |
| **Enumeration propertyNames( )**                           | 按**简单的面向行的格式**从**输入字符流中读取属性列表**（键和元素对）。 |
| **Object setProperty(String key, String value)**           | **调用 Hashtable 的方法 put**。                              |
| **void store(OutputStream streamOut, String description)** | 以**适合使用 load(InputStream)方法加载到 Properties 表中的格式**，将此 **Properties 表中的属性列表（键和元素对）写入输出流**。 |

**实例**

```Java
import java.util.*;
 
public class PropDemo {
   public static void main(String args[]) {
      	Properties capitals = new Properties();
        Set<Object> states;
        String str;

        capitals.put("Illinois","Springfiled");
        capitals.put("Missouri","Jefferson City");
        capitals.put("Washington","Olympia");
        capitals.put("Claifornia","Sacramento");
        capitals.put("Indiana","Indianapolis");

        states = capitals.keySet();
        for (Object state : states) {
            str = (String) state;
            System.out.println("The capital of " + str + " is " + capitals.getProperty(str) + ".");
        }
        System.out.println();

        str = capitals.getProperty("Florida","Not Found");
        System.out.println("The capital of Florida is " + str + ".");
   }
}
/*输出:
The capital of Missouri is Jefferson City.
The capital of Illinois is Springfiled.
The capital of Claifornia is Sacramento.
The capital of Indiana is Indianapolis.
The capital of Washington is Olympia.

The capital of Florida is Not Found.
*/
```

## Java 集合框架

集合框架被设计成要满足以下几个目标。

- 该框架必须是高性能的。基本集合（动态数组，链表，树，哈希表）的实现也必须是高效的。
- 该框架允许不同类型的集合，以类似的方式工作，具有高度的互操作性。
- 对一个集合的扩展和适应必须是简单的。

![](https://www.runoob.com/wp-content/uploads/2014/01/2243690-9cd9c896e0d512ed.gif)

**Java 集合框架**主要包括**两种类型的容器**，一种是**集合（Collection）**，**存储一个元素集合**，另一种是**图（Map）**，**存储键/值对映射**。

**Collection 接口**又有 3 种子类型，**List**、**Set** 和 **Queue**，再下面是一些抽象类，最后是**具体实现类**，常用的有 **ArrayList**、**LinkedList**、**HashSet**、**LinkedHashSet**、**HashMap**、**LinkedHashMap** 等等。

**集合框架**是一个用来**代表和操纵集合的统一架构**。所有的集合框架都包含如下内容：

- **接口：**是代表集合的**抽象数据类型**。例如 **Collection、List、Set、Map** 等。之所以定义多个接口，是为了以不同的方式操作集合对象
- **实现（类）：**是**集合接口的具体实现**。从本质上讲，它们是**可重复使用的数据结构**，例如：**ArrayList、LinkedList、HashSet、HashMap。**
- **算法：**是**实现集合接口的对象**里的方法执行的一些有用的计算，例如：搜索和排序。这些算法被称为**多态**，那是因为相同的方法可以在相似的接口上有着不同的实现。

![](https://www.runoob.com/wp-content/uploads/2014/01/java-coll-2020-11-16.png)

### 集合接口

| 接口            | 接口描述                                                     |
| :-------------- | :----------------------------------------------------------- |
| **Collection**  | **Collection** 是**最基本的集合接口**，**一个 Collection 代表一组 Object**，即 Collection 的元素, **Java不提供直接继承自Collection的类，只提供继承于的子接口(如List和set)**。Collection 接口**存储一组不唯一**，**无序**的对象。 |
| **List**        | **List**接口是一个**有序的 Collection**，使用此接口能够**精确的控制每个元素插入的位置**，能够通过**索引**(元素在List中位置，类似于数组的下标)来**访问List中的元素**，**第一个元素的索引为 0**，而且**允许有相同的元素**。List 接口**存储一组不唯一**，**有序（插入顺序）**的对象。 |
| **Set**         | **Set** 具有**与 Collection 完全一样的接口**，只是行为上不同，**Set 不保存重复的元素**。Set 接口**存储一组唯一**，**无序**的对象。 |
| **SortedSet**   | **继承于Set保存有序**的集合。                                |
| **Map**         | Map 接口**存储一组键值对象**，提供**key（键）到value（值）的映射**。 |
| **Map.Entry**   | 描述在**一个Map中的一个元素**（键/值对）。是一个**Map的内部类**。 |
| **SortedMap**   | **继承于 Map**，使 **Key 保持在升序排列**。                  |
| **Enumeration** | 这是一个**传统的接口和定义的方法**，通过它可以枚举（一次获得一个）对象集合中的元素。这个传统接口**已被迭代器取代**。 |

**Set和List的区别**

- **Set** 接口实例存储的是**无序的，不重复的数据**。**List** 接口实例存储的是**有序的，可以重复的元素**。
- **Set检索效率低下**，**删除和插入效率高**，**插入和删除不会引起元素位置改变** **<实现类有HashSet,TreeSet>**。
- **List和数组类似**，可以**动态增长**，根据实际存储的数据的长度自动增长List的长度。**查找元素效率高，插入删除效率低**，因为会引起**其他元素位置改变** **（实现类有ArrayList,LinkedList,Vector）**

### 集合实现类（集合类）

| 序号                       | 类描述                                                       |
| :------------------------- | :----------------------------------------------------------- |
| **AbstractCollection**     | 实现了**大部分的集合接口**。                                 |
| **AbstractList**           | **继承于AbstractCollection** 并且**实现了大部分List接口**。  |
| **AbstractSequentialList** | **继承于 AbstractList**，提供了**对数据元素的链式访问**而不是随机访问。 |
| **LinkedList**             | 该类**实现了List接口**，允许有**null（空）元素**。主要用于**创建链表数据结构**，该类**没有同步方法**，如果多个线程同时访问一个List，则必须自己实现访问同步，解决方法就是在创建List时候构造一个同步的List。例如：`List list=Collections.synchronizedList(newLinkedList(...));`**LinkedList 查找效率低**。 |
| **ArrayList**              | 该类也是**实现了List的接口**，实现了**可变大小的数组**，随机访问和遍历元素时，提供更好的性能。该类也是**非同步**的,在多线程的情况下不要使用。ArrayList 增长当前长度的50%，**插入删除效率低**。 |
| **AbstractSet**            | **继承于AbstractCollection** 并且**实现了大部分Set接口**。   |
| **HashSet**                | 该类**实现了Set接口**，**不允许出现重复元素**，**不保证集合中元素的顺序**，允许**包含值为null的元素**，但**最多只能一个**。 |
| **LinkedHashSet**          | 具有**可预知迭代顺序**的 `Set` 接口的哈希表和链接列表实现。  |
| **TreeSet**                | 该类**实现了Set接口**，可以**实现排序等功能**。              |
| **AbstractMap**            | 实现了**大部分的Map接口**。                                  |
| **HashMap**                | **HashMap** 是一个**散列表**，它存储的内容是**键值对(key-value)映射**。 该类实现了Map接口，根据**键的HashCode值存储数据**，具有**很快的访问速度**，**最多允许一条记录的键为null**，**不支持线程同步**。 |
| **TreeMap**                | **继承了AbstractMap**，并且**使用一颗树**。                  |
| **WeakHashMap**            | **继承AbstractMap类**，使用**弱密钥的哈希表**。              |
| **LinkedHashMap**          | **继承于HashMap**，使用**元素的自然顺序对元素进行排序**.     |
| **IdentityHashMap**        | **继承AbstractMap类**，**比较文档时使用引用相等**。          |

### 迭代器的使用

迭代器，使你能够通过**循环来得到或删除集合的元素**。**ListIterator 继承了 Iterator**，以**允许双向遍历列表和修改元素**

**遍历ArrayList**

```Java
package com.Study.Iterator;

import java.util.*;

/**
 * @author SH_YJ
 * @date 2020/12/6 15:52
 */
public class test1 {
    public static void main(String[] args) {
        List<String> list = new ArrayList<>();
        list.add("Hello");
        list.add("World");
        list.add("HAHAHAHA");

        //第一种遍历方式使用 For-Each 遍历list
        for (String str : list) {
            System.out.println(str);
        }

        //第二种遍历，把链表变为数组相关的内容进行遍历
        String[] strArray = new String[list.size()];
        list.toArray(strArray);
        for (String s : strArray) {
            System.out.println(s);
        }
        
        //第三种遍历 使用迭代器进行相关遍历
        Iterator<String> iterator = list.iterator();
        while (iterator.hasNext()){
            System.out.println(iterator.next());
        }
    }
}
```

**遍历Map**

```Java
package com.Study.Iterator;

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;

/**
 * @author SH_YJ
 * @date 2020/12/6 16:01
 */
public class Map_iterator {
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<>();
        map.put("1", "value1");
        map.put("2", "value2");
        map.put("3", "value3");

        // 第一种：普遍使用，二次取值
        System.out.println("通过Map.keySet遍历key和value：");
        for (String key : map.keySet()) {
            System.out.println("key= " + key + " and value= " + map.get(key));
        }

        // 第二种
        System.out.println("通过Map.entrySet使用iterator遍历key和value：");
        Iterator<Map.Entry<String, String>> iterator = map.entrySet().iterator();
        while (iterator.hasNext()){
            Map.Entry<String,String> entry = iterator.next();
            System.out.println("key= " + entry.getKey() + " and value= " + entry.getValue());
        }

        //第三种：推荐，容量大时
        System.out.println("通过Map.entrySet遍历key和value");
        for (Map.Entry<String,String> entry : map.entrySet()){
            System.out.println("key= " + entry.getKey() + " and value= " + entry.getValue());
        }

        // 第四种
        System.out.println("通过Map.value()遍历所有的value，但不能遍历key");
        for (String v: map.values()) {
            System.out.println("value= " + v);
        }
    }
}
```

### 总结

Java集合框架为程序员提供了预先包装的数据结构和算法来操纵他们。

集合是一个对象，可容纳其他对象的引用。集合接口声明对每一种类型的集合可以执行的操作。

**集合框架的类和接口均在java.util包中**。

任何对象加入集合类后，**自动转变为Object类型**，所以在取出的时候，**需要进行强制类型转换**。

## Java ArrayList

**ArrayList 类**是一个**可以动态修改的数组**，与普通数组的区别就是它是**没有固定大小的限制**，我们可以添加或删除元素。

ArrayList 继承了 AbstractList ，并实现了 List 接口。

**ArrayList 类**位于 **java.util** 包中，使用前需要引入它，语法格式如下：

```Java
import java.util.ArrayList;  // 引入 ArrayList 类
ArrayList<E> objectName =  new ArrayList<>();  //初始化
// E 泛型数据类型，用于设置objectName的数据类型，只能为引用数据类型，需要使用基本数据类型的包装类
// objectName 对象名
```

### 添加元素

```java 
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Weibo");
        System.out.println(sites);
    }
}
// [Google, Runoob, Taobao, Weibo]
```

### 访问元素

```java
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Weibo");
        //索引从0开始
        System.out.println(sites.get(1));  // 访问第二个元素
    }
}
// Runoob
```

### 修改元素

```Java
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Weibo");
    	sites.set(2,"Wiki");  // 第一个参数为索引位置，第二个位置为要修改的值
        System.out.println(sites);
    }
}
// [Google, Runoob, Wiki, Weibo]
```

### 删除元素

```Java
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
		sites.add("Weibo");
    	sites.remove(2);  // 删除第三个元素
        System.out.println(sites);
    }
}
// [Google, Runoob, Weibo]
```

### 计算大小

```Java
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
		sites.add("Weibo");
 		System.out.println(sites.size());
    }
}
// 4
```

### 迭代数组列表

```Java
import java.util.ArrayList;

public interface ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
		sites.add("Weibo");
 		// 使用for-each
        for (String str : sites) {
            System.out.println(str);
        }
    }
}
/*
Google
Runoob
Taobao
Weibo
*/
```

### ArrayList 排序

**字母排序**

```Java
import java.util.ArrayList;
import java.util.Collections;  // 引入 Collections 类

public interface ArrayList_Test1 {
    public static void main(String[] args) {
 		 ArrayList<String> sites = new ArrayList<String>();
        sites.add("Taobao");
        sites.add("Wiki");
        sites.add("Runoob");
        sites.add("Weibo");
        sites.add("Google");
        Collections.sort(sites);  // 字母排序
        for (String i : sites) {
            System.out.println(i);
        }
    }
}
/*
Google
Runoob
Taobao
Weibo
Wiki
*/
```

**数字排序**

```Java
import java.util.ArrayList;
import java.util.Collections;  // 引入 Collections 类

public class ArrayList_Test1 {
    public static void main(String[] args) {
        ArrayList<Integer> myNumbers = new ArrayList<Integer>();
        myNumbers.add(33);
        myNumbers.add(15);
        myNumbers.add(20);
        myNumbers.add(34);
        myNumbers.add(8);
        myNumbers.add(12);

        Collections.sort(myNumbers);  // 数字排序

        for (int i : myNumbers) {
            System.out.println(i);
        }
    }
}
/*
8
12
15
20
33
34
*/
```

### ArrayList方法

#### add()

将元素**插入到指定位置**的 arraylist 中

**语法**

```java
arraylist.add(int index, E element)
// index 表示元素插入处的索引值
// element 要插入的元素
// 若index超出范围，则抛出异常IndexOutOfBoundsException
```

**实例**

```Java
import javv.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        ArrayList<Integer> Numbers = new ArrayList<>();
        // 在数据末尾插入元素
        Numbers.add(2);
        Numbers.add(3);
        Numbers.add(5);
        // 指定位置插入
        Numbers.add(1,4);  
        System.out.println(Numbers);
    }
}
// [2, 4, 3, 5]
```

#### addAll()

**添加集合中的所有元素**到 arraylist 中

**语法**

```Java
arraylist.addAll(int index, Collection c)
//index 表示集合元素，未指定则插入数组末尾
//c 要插入的集合元素
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<Integer> primeNumbers = new ArrayList<>();
        primeNumbers.add(3);
        primeNumbers.add(5);
		
        // 创建另一个动态数组
        ArrayList<Integer> numbers = new ArrayList<>();
        numbers.add(1);
        numbers.add(2);
        // 插入primeNumbers集合元素到末尾
        numbers.addAll(primeNumbers);
        System.out.println("Numbers: " + numbers);
        // 指定位置插入
        numbers.addAll(1, primeNumbers)
        System.out.println("Numbers: " + numbers);
    }
}
/*
Numbers: [1, 2, 3, 5]
Numbers: [1, 3, 5, 2]
*/
```

#### clear()

**删除** arraylist 中的**所有元素**

**语法**

```java
arraylist.clear()
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 删除所有元素
        sites.clear();
        System.out.println("所有 clear() 方法后: " + sites);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
所有 clear() 方法后: []
*/
//clear()和remove()功能一样，但clear()速度更快，更高效
```

#### clone()

 **复制**一份 arraylist

**语法**

```java
arraylist.clone()
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 对 sites 进行拷贝
        ArrayList<String> cloneSites = (ArrayList<String>)sites.clone();
        System.out.println("拷贝 ArrayList: " + cloneSites);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
拷贝 ArrayList: [Google, Runoob, Taobao]
*/
```

#### contains()

判断**元素是否在 arraylist**

**语法**

```Java
arraylist.contains(Object obj)
// obj 要检测的元素
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        // 检查 Runoob 是否在这个数组中
        System.out.print("Runoob 是否存在于 arraylist: ");
        System.out.println(sites.contains("Runoob"));

        // 检查 Weibo 是否在这个数组中
        System.out.print("Weibo 是否存在于 arraylist: ");
        System.out.println(sites.contains("Weibo"));
    }
}
/*
Runoob 是否存在于 arraylist: true
Weibo 是否存在于 arraylist: false
*/
```

#### get()

通过**索引值**获取 **arraylist 中的元素**
**语法**

```java
arraylist.get(int index)
//index 索引值
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 获取在索引值为1处的元素
        String element = sites.get(1);
        System.out.println("索引值为 1 的元素为: " + element);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
索引值为 1 的元素为: Runoob
*/
```

#### indexOf()

返回 arraylist 中**元素的索引值**

**语法**

```java
arraylist.get(Object obj)
// obj 查找的元素
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        // 查找位置索引值为 Runoob 的元素
        int position1 = sites.indexOf("Runoob");
        System.out.println("Runoob 的索引位置: " + position1);

        // 查找位置索引值为 Weibo 的元素
        int position2 = sites.indexOf("Weibo");
        System.out.println("Weibo 的索引位置: " + position2);
    }
}
/*
Runoob 的索引位置: 1
Weibo 的索引位置: -1
*/
//元素不存在数组中则返回-1
```

#### removeAll()

**删除**存在于**指定集合**中的 arraylist 里的**所有元素**

**语法**

```Java
arraylist.removeAll(Collection c)
// c 动态数组列表中要删除的元素集合
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

            sites.add("Google");
            sites.add("Runoob");
            sites.add("Taobao");
            System.out.println("网站列表: " + sites);

        // 删除所有元素
        sites.removeAll(sites);
        System.out.println("所有 removeAll() 方法后: " + sites);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
所有 removeAll() 方法后: []
*/
```

#### remove()

**删除** arraylist 里的**单个元素**

**语法**

```Java
// 删除指定元素
arraylist.remove(Object obj)
// obj 要删除的元素，若obj元素出现两次，则删除动态数组第一次出现的元素

// 删除指定索引位置的元素
arraylist.remove(int index)
// index 要删除元素索引值
```

**实例**

```java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);


        // 删除元素 Taobao
        boolean result = sites.remove("Taobao");
        System.out.println("Taoabo 是否被删除? " + result);
        System.out.println("使用 remove() 后: " + sites);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
Taoabo 是否被删除? true
使用 remove() 后: [Google, Runoob]
*/
```

#### size()

返回 arraylist 里**元素数量**

**语法**

```Java
arraylist.size()
```

实例

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);


        // 得到数组中的元素个数
        int size = sites.size();
        System.out.println("动态数组长度: " + size);
    }
}
/*
网站列表: [Google, Runoob, Taobao]
动态数组长度: 3
*/
```

#### isEmpty()

判断 arraylist **是否为空**

**语法**

```Java
arraylist.isEmpty()
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        // 检查数组中是否含有元素
        boolean result = sites.isEmpty(); // true
        System.out.println("sites 是否为空? " + result);

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 检查该数组是否为空
        result = sites.isEmpty();  // false
        System.out.println("sites 是否为空? " + result);
    }
}
/*
sites 是否为空? true
网站列表: [Google, Runoob, Taobao]
sites 是否为空? false
*/
```

#### subList()

**截取部分** arraylist 的**元素**

**语法**

```Java
arraylist.subList(int fromIndex, int toIndex)
// fromIndex 截取元素的起始位置，包含该索引位置元素
// toIndex 截取元素的结束位置，不包含该索引位置元素
```

**实例**

```java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Wiki");
        System.out.println("网站列表: " + sites);

        // 元素位置为1到3
        System.out.println("SubList: " + sites.subList(1, 3));
    }
}
/*
网站列表: [Google, Runoob, Taobao, Wiki]
SubList: [Runoob, Taobao]
*/
```

#### set()

**替换** arraylist 中**指定索引的元素**

**语法**

```Java
arraylist.set(int index, E element)
// index 索引位置
// element 将在index位置替换进去的新元素
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        // 索引 2 的元素被替换
        String element = sites.set(2, "Wiki");
        System.out.println("替换后: " + sites);
        System.out.println("被替换的元素: " + element);
    }
}
/*
替换后: [Google, Runoob, Wiki]
被替换的元素: Taobao
*/
```

**set()与add()方法区别：**

- set() 方法在**指定位置**对元素进行**更新**。
- add() 方法将元素**插入**到**指定位置**的动态数组中。

#### sort()

对 arraylist 元素进行**排序**

**语法**

```Java
arraylist.sort(Comparator c)
// comparator 顺序方式
```

**实例**

```java
import java.util.ArrayList;
import java.util.Comparator;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Runoob");
        sites.add("Google");
        sites.add("Wiki");
        sites.add("Taobao");
        System.out.println("不排序: " + sites);

        //升序排列
        sites.sort(Comparator.naturalOrder());
        System.out.println("升序排序: " + sites);
        
        // 降序排序
        sites.sort(Comparator.reverseOrder());
        System.out.println("降序排序: " + sites);
    }
}
/*
不排序: [Runoob, Google, Wiki, Taobao]
升序排序: [Google, Runoob, Taobao, Wiki]
降序排序: [Wiki, Taobao, Runoob, Google]
*/
```

#### toArray()

将 arraylist **转换为数组**

**语法**

```Java
arraylist.toArray(T[] arr)
// T [] arr 用于存储数组元素的数组 
// T 指的是数组的类型
```

**实例**

```Java
import java.util.ArrayList;
import java.util.Comparator;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	// 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Runoob");
        sites.add("Google");
        sites.add("Wiki");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 创建一个新的 String 类型的数组
        // 数组长度和 ArrayList 长度一样
        String[] arr = new String[sites.size()];
        // 将ArrayList对象转换成数组
        sites.toArray(arr);
        
        // 使用无参数的方法
        Object[] obj = sites.toArray();
        
        // 两种输出方式结果都一样

        // 第一种方式输出
        System.out.print("Array1: ");
        for(String item:arr) {
            System.out.print(item+", ");
        
        // 第二种方式输出    
        System.out.print("Array2: ");
        for(Object item : obj) {
            System.out.print(item+", ");
        }
    }
}
/*
网站列表: [Runoob, Google, Wiki, Taobao]
Array1: Runoob, Google, Wiki, Taobao, 
Array2: Runoob, Google, Wiki, Taobao, 
*/
```

#### toString()

将 arraylist **转换为字符串**

**语法**

```Java
arraylist.toString()
```

**实例**

```Java
import java.util.ArrayList;
import java.util.Comparator;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Runoob");
        sites.add("Google");
        sites.add("Wiki");
        sites.add("Taobao");
        System.out.println("网站列表: " + sites);

        // 将ArrayList转换为String类型
        String list = sites.toString();
        System.out.println("String: " + list);
    }
}
/*
网站列表: [Runoob, Google, Wiki, Taobao]
String: [Runoob, Google, Wiki, Taobao]
*/
```

#### ensureCapacity()

设置**指定容量大小**的 arraylist

**语法**

```Java
arraylist.ensureCapacity(int minCapacity)
// minCapacity 动态数组的容量
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        // 设置 arraylist的容量大小
        sites.ensureCapacity(3);
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        
        // 添加第四个元素
        sites.add("Wiki");
        
        // 添加 3 个以上的元素，它将自动调整自身大小
        
        System.out.println("网站列表: " + sites);
    }
}
// 网站列表: [Google, Runoob, Taobao, Wiki]
```

#### lastIndexOf()

返回**指定元素**在 arraylist 中**最后一次出现的位置**

**语法**

```Java
arraylist.lastIndexOf(Object obj)
// obj 查找的元素
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
    	 // 创建一个数组
        ArrayList<String> sites = new ArrayList<>();

        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Runoob");
        System.out.println("网站列表: " + sites);


        // 获取 Runoob 最后一次出现的位置
        int position1 = sites.lastIndexOf("Runoob");
        System.out.println("Runoob 最后出现的位置: " + position1);

        // Wiki 不在 arraylist 中返回 -1
        int position2 = sites.lastIndexOf("Wiki");
        System.out.println("Wiki 最后出现的位置: " + position2);
    }
}
/*
网站列表: [Google, Runoob, Taobao, Runoob]
Runoob 最后出现的位置: 3
Wiki 最后出现的位置: -1
*/
```

#### retainAll()

**保留** arraylist 中在**指定集合中也存在的那些元素**

**语法**

```Java
arraylist.retainAll(Collection c)
// collection 集合参数    
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        System.out.println("ArrayList 1: " + sites);

        // 创建另一个动态数组
        ArrayList<String> sites2 = new ArrayList<>();

        // 往动态数组中添加元素
        sites2.add("Wiki");
        sites2.add("Runoob");
        sites2.add("Google");
        System.out.println("ArrayList 2: " + sites2);

        // 保留两个共有的元素
        sites.retainAll(sites2);
        System.out.println("保留的元素: " + sites);
    }
}
/*
ArrayList 1: [Google, Runoob, Taobao]
ArrayList 2: [Wiki, Runoob, Google]
保留的元素: [Google, Runoob]
*/
```

#### containsAll()

查看 arraylist 是否**包含指定集合中的所有元素**

**语法**

```java 
arraylist.containsAll(Collection c)
// collection 集合参数
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        System.out.println("ArrayList 1: " + sites);

        // 创建另一个动态数组
        ArrayList<String> sites2 = new ArrayList<>();

        // 往动态数组中添加元素
        sites2.add("Runoob");
        sites2.add("Google");
        System.out.println("ArrayList 2: " + sites2);

        // 检查动态数组1是否包含动态数组2
        boolean result1 = sites.containsAll(sites2);
        System.out.println("ArrayList 1 包含了 ArrayList 2 的所有元素: " + result1);

        // 检查数组2是否包含数组1
        boolean result2 = sites2.containsAll(sites);
        System.out.println("ArrayList 2 包含了 ArrayList 1 的所有元素: " + result2);
    }
}
/*
ArrayList 1: [Google, Runoob, Taobao]
ArrayList 2: [Runoob, Google]
ArrayList 1 包含了 ArrayList 2 的所有元素: true
ArrayList 2 包含了 ArrayList 1 的所有元素: false
*/
```

#### trimToSize()

 将 arraylist 中的**容量调整为数组中的元素个数**

**语法**

```Java
arraylist.trimToSize()
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        ArrayList<String> sites = new ArrayList<>();
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        System.out.println("ArrayList : " + sites);

        // 调整容量为3
        sites.trimToSize();
        System.out.println("ArrayList 大小: " + sites.size());
    }
}
/*
ArrayList : [Google, Runoob, Taobao]
ArrayList 大小: 3
*/
//trimToSize()的优点：删除未分配的空间并更改 ArrayList 的容量，使其等于 ArrayList 中的元素个数
```

#### removeRange()

**删除** arraylist 中**指定索引之间存在的元素**

**语法**

```Java
arraylist.removeRange(int fromIndex, int toIndex)
// fromIndex 索引起始位置，包含该索引位置的值
// toIndex 索引结束位置，不包含该索引位置的值
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        // 创建一个动态数组
        Main sites = new Main();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Wiki");
        sites.add("Weibo");

        System.out.println("ArrayList : " + sites);

        // 删除从索引值1到3的元素
        sites.removeRange(1, 3);
        System.out.println("删除后的 ArrayList: " + sites);
    }
}
/*
ArrayList : [Google, Runoob, Taobao, Wiki, Weibo]
删除后的 ArrayList: [Google, Wiki, Weibo]
*/
```

#### replaceAll()

将**给定的操作内容替换掉数组中每一个元素**

**语法**

```Java
arraylist.replaceAll(UnaryOperator<E> operator)
// operator 要替换到动态数组的元素或者一系列操作
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        ArrayList<Integer> numbers = new ArrayList<>();
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        System.out.println("ArrayList1: " + sites);

        // 将所有元素更改为大写
        sites.replaceAll(e -> e.toUpperCase());
        System.out.println("更新后的 ArrayList: " + sites);

        // 往数组中添加元素
        numbers.add(1);
        numbers.add(2);
        numbers.add(3);
        System.out.println("ArrayList2: " + numbers);
        // 所有元素乘以 2
        numbers.replaceAll(e -> e * 2);;
        System.out.println("更新后的 ArrayList: " + numbers);
    }
}
/*
ArrayList1: [Google, Runoob, Taobao]
更新后的 ArrayList: [GOOGLE, RUNOOB, TAOBAO]
ArrayList2: [1, 2, 3]
更新后的 ArrayList: [2, 4, 6]
*/
```

#### removeIf()

**删除所有满足特定条件**的 arraylist 元素

**语法**

```Java
arraylist.removeIf(Predicate<E> filter)
// filter 过滤器，判断元素是否删除
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
        ArrayList<String> sites = new ArrayList<>();
        ArrayList<Integer> numbers = new ArrayList<>();
       
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");

        System.out.println("ArrayList1: " + sites);

        // 删除名称中带有 Tao 的元素
        sites.removeIf(e -> e.contains("Tao"));;
        System.out.println("删除后的 ArrayList: " + sites);

        // 往数组中插入元素
        numbers.add(1);
        numbers.add(2);
        numbers.add(3);
        numbers.add(4);
        numbers.add(5);
        numbers.add(6);
        System.out.println("Numbers: " + numbers);

        // 删除所有偶数元素
        numbers.removeIf(e -> (e % 2) == 0);  //括号内为lambda格式 
        System.out.println("Odd Numbers: " + numbers);
    }
}
/*
ArrayList1: [Google, Runoob, Taobao]
删除后的 ArrayList: [Google, Runoob]
Numbers: [1, 2, 3, 4, 5, 6]
Odd Numbers: [1, 3, 5]
*/
```

#### forEach()

 **遍历** arraylist 中每一个元素并执行特定操作

**语法**

```Java
arraylist.forEach(Consumer<E> action)
// action 对每个元素执行的操作
// forEach() 不同于 for-each
```

**实例**

```Java
import java.util.ArrayList;

public class ArrayList_Test2 {
    public static void main(String[] args) {
         // 创建一个数组
        ArrayList<Integer> numbers = new ArrayList<>();

        // 往数组中添加元素
        numbers.add(1);
        numbers.add(2);
        numbers.add(3);
        numbers.add(4);
        System.out.println("ArrayList: " + numbers);

        // 所有元素乘以 10
        System.out.print("更新 ArrayList: ");
       
        // 将 lambda 表达式传递给 forEach
        numbers.forEach((e) -> {e = e * 10; System.out.print(e + " ");});
    }
}
```

## Java LinkedList

**链表（Linked list）**是一种常见的基础数据结构，是一种**线性表**，但是并不会按线性的顺序存储数据，而是在**每一个节点里存到下一个节点的地址**。

与 ArrayList 相比，**LinkedList 的增加和删除对操作效率更高**，而**查找和修改的操作效率较低**。

**以下情况使用 ArrayList :**

- 频繁访问列表中的某一个元素。
- 只需要在列表末尾进行添加和删除元素操作。

**以下情况使用 LinkedList :**

- 你需要通过循环迭代来访问列表中的某些元素。
- 需要频繁的在列表开头、中间、末尾等位置进行添加和删除元素操作。

LinkedList 继承了 **AbstractSequentialList** 类。

LinkedList 实现了 **Queue** 接口，可作为**队列**使用。

LinkedList 实现了 **List** 接口，可进行**列表**的相关操作。

LinkedList 实现了 **Deque** 接口，可作为**队列**使用。

LinkedList 实现了 **Cloneable** 接口，可实现**克隆**。

LinkedList 实现了 **java.io.Serializable** 接口，即**可支持序列化**，能通过序列化去传输。

LinkedList 类位于 java.util 包中，使用前需要引入它，语法格式如下：

```Java
// 引入 LinkedList 类
import java.util.LinkedList; 

LinkedList<E> list = new LinkedList<>();   // 普通创建方法

LinkedList<E> list = new LinkedList(Collection<? extends E> c); // 使用集合创建链表

// E 泛型数据类型，用于设置objectName的数据类型，只能为引用数据类型，需要使用基本数据类型的包装类
```

### 添加元素

```Java
import java.util.LinkedList;

public class Test1 {
    public static void main(String[] args) {
        // 创建链表
        LinkedList<String> list = new LinkedList<>();
        // 添加元素
        list.add("a");
        list.add("b");
        list.add("c");
        list.add(1,"aa");  // 向指定位置插入元素
        list.addFirst("First");  // 添加元素到首部
        list.addLast("Last");  // 添加元素到尾部
        System.out.println(list);
    }
}
// [First, a, b, c, Last]
```

### 删除元素

```Java
import java.util.LinkedList;

public class Test1 {
    public static void main(String[] args) {
        // 创建链表
        LinkedList<String> list = new LinkedList<>();
        list.add("a");
        list.add("b");
        list.add("c");
        list.remove("b");  // 移除元素为b的元素
        list.remove(1);  // 移除index为1的元素
        list.removeFirst();  // 移除首元素
        list.removeLast();  // 移除末尾元素
        System.out.println(list);
    }
}
```

### 访问元素

```java
import java.util.LinkedList;

public class Test1 {
    public static void main(String[] args) {
        // 创建链表
        LinkedList<String> list = new LinkedList<>();
        list.add("a");
        list.add("b");
        list.add("c");
        list.get(1); // 访问index为1的元素 b
        list.getFirst();  // 访问首元素 a
        list.getLast();  //  访问末尾元素 c
        System.out.println(list);
    }
}
```

### 迭代元素

```Java
import java.util.LinkedList;

public class Test1 {
    public static void main(String[] args) {
        // 创建链表
        LinkedList<String> list = new LinkedList<>();
        list.add("a");
        list.add("b");
        list.add("c");
        for (String str : list){  // 也可用for循环，利用size()方法获得链表长度
        	System.out.println(str);
        }
        
    }
}
/*
a
b
c
*/
```

### 常用方法

| 方法                                               | 描述                                                         |
| :------------------------------------------------- | :----------------------------------------------------------- |
| **public boolean add(E e)**                        | 链表**末尾添加元素**，返回是否成功，成功为 true，失败为 false。 |
| **public void add(int index, E element)**          | 向**指定位置插入元素**。                                     |
| **public boolean addAll(Collection c)**            | 将**一个集合的所有元素**添加到**链表后面**，返回是否成功，成功为 true，失败为 false。 |
| **public boolean addAll(int index, Collection c)** | 将**一个集合的所有元素**添加到**链表的指定位置后面**，返回是否成功，成功为 true，失败为 false。 |
| **public void addFirst(E e)**                      | **元素添加到头部**。                                         |
| **public void addLast(E e)**                       | **元素添加到尾部**。                                         |
| **public boolean offer(E e)**                      | 向**链表末尾添加元素**，返回是否成功，成功为 true，失败为 false。 |
| **public boolean offerFirst(E e)**                 | **头部插入元素**，返回是否成功，成功为 true，失败为 false。  |
| **public boolean offerLast(E e)**                  | **尾部插入元素**，返回是否成功，成功为 true，失败为 false。  |
| **public void clear()**                            | **清空链表**。                                               |
| **public E removeFirst()**                         | **删除**并**返回第一个元素**。                               |
| **public E removeLast()**                          | **删除**并**返回最后一个元素**。                             |
| **public boolean remove(Object o)**                | **删除某一元素**，返回是否成功，成功为 true，失败为 false。  |
| **public E remove(int index)**                     | **删除指定位置的元素**。                                     |
| **public E poll()**                                | **删除**并**返回第一个元素**。                               |
| **public E remove()**                              | **删除**并**返回第一个元素**。                               |
| **public boolean contains(Object o)**              | 判断**是否含有某一元素**。                                   |
| **public E get(int index)**                        | 返回**指定位置的元素**。                                     |
| **public E getFirst()**                            | 返回**第一个元素**。                                         |
| **public E getLast()**                             | 返回**最后一个元素**。                                       |
| **public int indexOf(Object o)**                   | 查找**指定元素**从**前往后第一次出现的索引**。               |
| **public int lastIndexOf(Object o)**               | 查找**指定元素最后一次出现的索引**。                         |
| **public E peek()**                                | 返回**第一个元素**。                                         |
| **public E element()**                             | 返回**第一个元素**。                                         |
| **public E peekFirst()**                           | 返回**头部元素**。                                           |
| **public E peekLast()**                            | 返回**尾部元素**。                                           |
| **public E set(int index, E element)**             | 设置**指定位置的元素**。                                     |
| **public Object clone()**                          | **克隆**该列表。                                             |
| **public Iterator descendingIterator()**           | 返回**倒序迭代器**。                                         |
| **public int size()**                              | 返回**链表元素个数**。                                       |
| **public ListIterator listIterator(int index)**    | 返回从**指定位置开始到末尾的迭代器**。                       |
| **public Object[] toArray()**                      | 返回一个由**链表元素组成的数组**。                           |
| **public T[] toArray(T[] a)**                      | 返回一个**由链表元素转换类型而成的数组**。                   |

## Java HashSet

HashSet **基于 HashMap 来实现的**，是一个**不允许有重复元素的集合**。

HashSet **允许有 null 值**。

HashSet 是**无序**的，即**不会记录插入的顺序**。

HashSet **不是线程安全**的， 如果多个线程尝试同时修改 HashSet，则最终结果是不确定的。 您必须在多线程访问时显式同步对 HashSet 的并发访问。

HashSet **实现了 Set 接口**。

HashSet 类位于 java.util 包中，使用前需要引入它，语法格式如下：

```Java
import java.util.HashSet; // 引入 HashSet 类

HashSet<String> sites = new HashSet<>();
```

### 添加元素

```Java
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("a");
        set.add("b");
        set.add("c");
        System.out.println(set);
    }
}
//[a, b, c]
```

### 判断元素是否存在

```java 
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("a");
        set.add("b");
        set.add("c");
        System.out.println(set.contains("a"));
    }
}
// true
```

### 删除元素

```Java
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("a");
        set.add("b");
        set.add("c");
        set.remove("c");
        set.clear();  // 清空所有元素
        System.out.println(set);
    }
}
// [a, b]
```

### 计算大小

```Java
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("a");
        set.add("b");
        set.add("c");
        System.out.println(set.size());
    }
}
// 3
```

### 迭代元素

```Java
import java.util.HashSet;

public class Test1 {
    public static void main(String[] args) {
        HashSet<String> set = new HashSet<>();
        set.add("a");
        set.add("b");
        set.add("c");
        for (String str : set){
        	System.out.println(str);
        }
    }
}
/*
a
b
c
*/                               
```

## Java HashMap

HashMap 是一个**散列表**，它存储的内容是**键值对(key-value)映射**。

HashMap **实现了 Map 接口**，根据**键的 HashCode 值存储数据**，具有**很快的访问速度**，**最多允许一条记录的键为 null**，**不支持线程同步**。

HashMap 是**无序**的，即**不会记录插入的顺序**。

HashMap 继承于AbstractMap，**实现了 Map、Cloneable、java.io.Serializable 接口**。

HashMap 的 **key 与 value 类型可以相同也可以不同**

HashMap 类位于 java.util 包中，使用前需要引入它，语法格式如下：

```Java
import java.util.HashMap; // 引入 HashMap 类

HashMap<Integer, String> Sites = new HashMap<Integer, String>();
```

### 添加元素

```Java
import java.util.HashMap;

public class Test1 {
    public static void main(String[] args) {
        HashMap<String, String> Sites = new HashMap<Integer, String>();
        Sites.put("one", "Google");
        Sites.put("two", "Runoob");
        Sites.put("three", "Taobao");
        Sites.put("four", "Zhihu");
        System.out.println(Sites);
    }
}
// {four=Zhihu, one=Google, two=Runoob, three=Taobao}
```

### 访问元素

```java
import java.util.HashMap;

public class Test2 {
    public static void main(String[] args) {
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        System.out.println(Sites.get(3));
    }
}
// Taobao
```

### 删除元素

```java
import java.util.HashMap;

public class Test3 {
    public static void main(String[] args) {
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        Sites.remove(4);
        // Sites.claer()  清除所有键值对
        System.out.println(Sites);
    }
}
// {1=Google, 2=Runoob, 3=Taobao}
```

### 计算大小

```Java
import java.util.HashMap;

public class Test4 {
    public static void main(String[] args) {
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        System.out.println(Sites.size());
    }
}
// 4
```

### 迭代元素

```Java
import java.util.HashMap;

public class Test4 {
    public static void main(String[] args) {
        HashMap<Integer, String> Sites = new HashMap<Integer, String>();
        // 添加键值对
        Sites.put(1, "Google");
        Sites.put(2, "Runoob");
        Sites.put(3, "Taobao");
        Sites.put(4, "Zhihu");
        // 输出 key 和 value
        for (Integer i : Sites.keySet()) {
            System.out.println("key: " + i + " value: " + Sites.get(i));
        }
        // 返回所有 value 值
        for(String value: Sites.values()) {
          System.out.print(value + ", ");
        }
    }
}
/*
key: 1 value: Google
key: 2 value: Runoob
key: 3 value: Taobao
key: 4 value: Zhihu
Google, Runoob, Taobao, Zhihu,
*/
```

### HashMap方法

#### clear()

**删除** hashMap 中的**所有键/值对**

**语法**

```Java
hashmap.clear()
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {

        HashMap<Integer, String> sites = new HashMap<>();
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);

        // 从HashMap中删除所有映射
        sites.clear();
        System.out.println("使用 clear() 方法后: " + sites);
    }
}
/*
HashMap: {1=Google, 2=Runoob, 3=Taobao}
使用 clear() 方法后: {}
*/
// clear()可对HasMap重新初始化
```

#### clone()

**复制**一份 hashMap，属于**浅拷贝**。

**拓展：**

​	**浅拷贝**只复制指向某个对象的指针，而不复制对象本身，新旧对象还是共享同一块内存， 所以**如果其中一个对象改变了这个地址，就会影响到另一个对象**。。

​	**浅拷贝**对应的就是深拷贝，深拷贝是将一个对象从内存中完整的拷贝一份出来,从堆内存中开辟一个新的区域存放新对象,且**修改新对象不会影响原对象**。

**语法**

```java
hashmap.clone()
```

**实例**

```Java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {

        HashMap<Integer, String> sites = new HashMap<>();
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);

        // 复制 sites
        HashMap<Integer, String> cloneSites = (HashMap<Integer, String>)sites.clone();
        System.out.println("Cloned HashMap: " + cloneSites);
    }
}
/*
HashMap: {1=Google, 2=Runoob, 3=Taobao}
Cloned HashMap: {1=Google, 2=Runoob, 3=Taobao}
*/
```

#### isEmpty()

判断 hashMap **是否为空**

**语法**

```java
hashmap.imEmpty()
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {

        HashMap<Integer, String> sites = new HashMap<>();
        // 检查该 HashMap 是否含有元素
        boolean result = sites.isEmpty(); // true
        System.out.println("是否为空? " + result);

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);

        result = sites.isEmpty(); // false
        System.out.println("是否为空? " + result);
    }
}
```

#### size()

计算 hashMap 中**键/值对的数量**

**语法**

```Java
hashmap.size()
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);

        // 获得该 HashMap 中键/值对映射的数量
        int size = sites.size();
        System.out.println("Size of HashMap: " + size);
    }
}
/*
HashMap: {1=Google, 2=Runoob, 3=Taobao}
Size of HashMap: 3
*/
```

#### put()

将**键/值对添加**到 hashMap 中

**语法**

```Java
hashmap.put(K key，V value)
// key : 键
// value : 值
// 如果插入的 key 对应的 value 已经存在，则执行 value 替换操作，返回旧的 value 值，如果不存在则执行插入，返回 null。
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // 创建一个 HashMap
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);
        // 添加重复的key元素
        String value = sites.put(1, "Weibo");
        System.out.println("修改后的 HashMap: " + sites);

        // 查看所代替的值
        System.out.println("替换的值: " + value);
    }
}
/*
HashMap: {1=Google, 2=Runoob, 3=Taobao}
修改后的 HashMap: {1=Weibo, 2=Runoob, 3=Taobao}
替换的值: Google
*/
```

#### putAll()

将**所有键/值对添加**到 hashMap 中

**语法**

```Java
hashmap.putAll(Map m)
//m : 包含插入到 HashMap 的映射关系
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);
        // 创建另一个 HashMap
        HashMap<Integer, String> sites2 = new HashMap<>();
        sites2.put(1, "Weibo");  // 已存在会被替换
        sites2.put(4, "Wiki");

        // 将所有的映射关系从 sites 添加到 sites2
        sites2.putAll(sites);
        System.out.println("sites2 HashMap: " + sites2);
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
sites2 HashMap: {1=Google, 2=Runoob, 3=Taobao, 4=Wiki}
*/
```

#### putIfAbsent()

如果 hashMap 中**不存在指定的键**，则将**指定的键/值对插入**到 hashMap 中。

**语法**

``` java
hashmap.putIfAbsent(K key, V value)
// key : 键
// value : 值
// 如果所指定的 key 已经在 HashMap 中存在，返回和这个 key 值对应的 value, 如果所指定的 key 不在 HashMap 中存在，则返回 null。
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);
       
        // HashMap 不存在该key
        sites.putIfAbsent(4, "Weibo");

        // HashMap 中存在 Key
        sites.putIfAbsent(2, "Wiki");
        System.out.println("Updated sites HashMap: " + sites);
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Updated sites HashMap: {1=Google, 2=Runoob, 3=Taobao, 4=Weibo}
*/
```

#### remove()

**删除** hashMap 中**指定键 key 的映射关系**

**语法**

```Java
hashmap.remove(Object key, Object value);
// key : 值
// value（可选）: 键值对(key-value)中 key 对应的 value 值
// 如果指定 key，返回指定键 key 关联的值，如果指定的 key 映射值为 null 或者该 key 并不存在于该 HashMap 中，此方法将返回null。
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("HashMap: " + sites);

        // 删除key为2的映射关系
        String siteName = sites.remove(2);  // return Runoob
        Boolean flag1 = sites.remove(1, "Google");  // return true
        Boolean flag2 = sites.remove(2, "Weibo");  // return false
        System.out.println("返回值: " + siteName);
        System.out.println("删除后的 HashMap: " + sites);
    }
}
/*
HashMap: {1=Google, 2=Runoob, 3=Taobao}
返回值: Runoob
删除后的 HashMap: {1=Google, 3=Taobao}
*/
```

#### containsKey()

检查 hashMap 中**是否存在指定的 key 对应的映射关系**。

**语法**

```java
hashmap.containsKey(Object key)
// key : 键
```

**实例**

```java
import java.util.HashMap;

publlic class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        //检查 key 为 1 是否存在
        if(sites.containsKey(1)) {
            System.out.println("key 为 1 存在于 sites 中");
        }
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
key 为 1 存在于 sites 中
*/
```

#### containsValue()

检查 hashMap 中**是否存在指定的 value 对应的映射关系**。

**语法**

```java
hashmap.containsValue(Object value)
// value : 值
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        //检查映射中值value是否有Runo0b
        if(sites.containsValue("Runoob")) {
            System.out.println("Runoob 存在于 sites 中");
        }
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Updated sites HashMap: {1=Google, 2=Runoob, 3=Taobao, 4=Wiki}
*/
```

#### replace()

**替换** hashMap 中是**指定的 key 对应的 value**。

**语法**

```java
hashmap.replace(K key, V oldValue, V newValue)
// key : 键
// oldValue : 旧的value值
// newValue : 新的value值
// 替换成功返回true,否则返回false
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);
        
        // 替换key为2的映射
        String value = sites.replace(2, "Wiki");
        System.out.println("Replaced Value: " + value);
        System.out.println("Updated HashMap: " + sites);

        // 替换映射关系{1 = Google}，执行替换
        sites.replace(1, "Google", "Wiki");  // 返回 true
        // 不存在映射关系{2 = Weibo}，没有任何操作
        sites.replace(2, "Weibo", "Zhihu");  // 返回 false
        System.out.println("sites after replace():\n" + sites);
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Replaced Value: Runoob
Updated HashMap: {1=Google, 2=Wiki, 3=Taobao}
sites after replace():
{1=Wiki, 2=Wiki, 3=Taobao}
*/
```

#### replaceAll()

将 hashMap 中的**所有映射关系替换**成**给定的函数所执行的结果**。

**语法**

```java
hashmap.replaceAll(Bifunction<K, V> function)
// 执行对函数
// 无返回值，仅替换
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // 将所有的值更改为大写
        sites.replaceAll((key, value) -> value.toUpperCase());  //使用lambda表达式
        System.out.println("Updated HashMap: " + sites);
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Updated HashMap: {1=GOOGLE, 2=RUNOOB, 3=TAOBAO}
*/
```

#### get()

**获取指定 key 对应对 value**

**语法**

```java
hashmap.get(Object key)
// key : 键
// 返回key所关联的value
```

**实例**

```java
import java.util.HashMap;

public class Main{
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // 得到 value
        String value = sites.get(1);
        System.out.println("key 1 对应的 value: " + value);
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
key 1 对应的 value: Google
*/
```

#### getOrDefault()

**获取指定 key 对应对 value**，如果**找不到 key** ，则返回**设置的默认值**

**语法**

```java
hashmap.get(Object key, V defaultValue)
// key : 键
// defaultValue : 当指定的key并不存在映射关系中，则返回的该默认值
```

**实例**

```Java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // key 的映射存在于 HashMap 中
        // Not Found - 如果 HashMap 中没有该 key，则返回默认值
        String value1 = sites.getOrDefault(1, "Not Found");
        System.out.println("Value for key 1:  " + value1);

        // key 的映射不存在于 HashMap 中
        // Not Found - 如果 HashMap 中没有该 key，则返回默认值
        String value2 = sites.getOrDefault(4, "Not Found");
        System.out.println("Value for key 4: " + value2);
    }
}
/*
Value for key 1:  Google
Value for key 4: Not Found
*/
```

#### forEach()

对 hashMap 中的**每个映射执行指定的操作**。

**语法**

```java
hashmap.forEach(BiConsumer<K, V> action)
// action : 要执行的操作
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // 创建一个 HashMap
        HashMap<String, Integer> prices = new HashMap<>();

        // 往 HashMap 中插入映射项
        prices.put("Shoes", 200);
        prices.put("Bag", 300);
        prices.put("Pant", 150);
        System.out.println("Normal Price: " + prices);

        System.out.print("Discounted Price: ");

        //通过 lambda 表达式使用 forEach()
        prices.forEach((key, value) -> {
            // value 价格减少百分之 10
            value = value - value * 10/100;
            System.out.print(key + "=" + value + " ");
        });
    }
}
/*
Normal Price: {Pant=150, Bag=300, Shoes=200}
Discounted Price: Pant=135 Bag=270 Shoes=180
*/
```

#### entrySet()

返回 hashMap 中**所有映射项的集合集合视图**。

**语法**

```java
hashmap.entrySet()
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // 返回映射关系中 set view
        System.out.println("Set View: " + sites.entrySet());
        
        //entrySet与 for-each 循环一起使用，用来遍历迭代 HashMap 中每一个映射项
        HashMap<String, Integer> numbers = new HashMap<>();
        numbers.put("One", 1);
        numbers.put("Two", 2);
        numbers.put("Three", 3);
        System.out.println("numbers HashMap: " + numbers);

        // 访问 HashMap 中的每一个映射项
        System.out.print("Entries: ");

        // entrySet()返回了 HashMap 中所有映射项的一个 set 集合视图
        // for-each loop 在该视图中访问了每一映射项
        for(Entry<String, Integer> entry: numbers.entrySet()) {
            System.out.print(entry);
            System.out.print(", ");
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Set View: [1=Google, 2=Runoob, 3=Taobao]
numbers HashMap: {One=1, Two=2, Three=3}
Entries: One=1, Two=2, Three=3, 
*/
```

#### keySet()

返回 hashMap 中**所有 key 组成的集合视图**。

**语法**

```java
hashmap.keySet()
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // 返回所有 key 组成的 set 集合视图
        System.out.println("Keys: " + sites.keySet());
        
        // keySet与 for-each 循环一起使用，用来遍历迭代 HashMap 中的所有键。

        // keySet() 返回所有 key 组成的 set 视图
        // for-each loop 在该视图中访问每一个 key
        for(int key: sites.keySet()) {
            System.out.print(key + ", ");
        }
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Keys: [1, 2, 3]
1, 2, 3, 
*/
```

#### values()

返回 hashMap 中**存在的所有 value 值**。

**语法**

```java
hashmap.values()
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // 创建一个 HashMap
        HashMap<Integer, String> sites = new HashMap<>();

        // 往 HashMap 添加一些元素
        sites.put(1, "Google");
        sites.put(2, "Runoob");
        sites.put(3, "Taobao");
        System.out.println("sites HashMap: " + sites);

        // 返回所有value值组成的视图
        System.out.println("Values: " + sites.values());
        
        // values()与for-each循环一起使用，用来遍历迭代HashMap中的所有值
        
        // values() 返回所有 value 的一个视图
        // for-each 循环可以 从view中访问每一个value值
        for(String value: sites.values()) {
            System.out.print(value + ", ");
        }
    }
}
/*
sites HashMap: {1=Google, 2=Runoob, 3=Taobao}
Values: [Google, Runoob, Taobao]
values: Google, Runoob, Taobao, 
*/
```

#### merge()

**添加键值对**到 hashMap 中

**语法**

```java
hashmap.merge(key, value, remappingFunction)
// key : 键
// value : 值
// remappingFunction : 重新映射函数，用于重新计算值
// 如果 key 对应的 value 不存在，则返回该 value 值，如果存在，则返回通过 remappingFunction 重新计算后的值
```

**实例**

```java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {
    HashMap<String, Integer> prices = new HashMap<>();

    // 往 HashMap 插入映射
    prices.put("Shoes", 200);
    prices.put("Bag", 300);
    prices.put("Pant", 150);
    System.out.println("HashMap: " + prices);

    int returnedValue = prices.merge("Shirt", 100, (oldValue, newValue) -> oldValue + newValue);  // lambda表达式
    System.out.println("Price of Shirt: " + returnedValue);

    // 输出更新后的 HashMap
    System.out.println("Updated HashMap: " + prices);
    }
}
/*键值都是字符串也是如此方法
HashMap: {Pant=150, Bag=300, Shoes=200}
Price of Shirt: 100
Updated HashMap: {Pant=150, Shirt=100, Bag=300, Shoes=200}
*/
```

#### compute()

对 hashMap 中**指定 key 的值进行重新计算**

**语法**

```java
hashmap.compute(K key, BiFunction remappingFunction)
// key - 键
// remappingFunction - 重新映射函数，用于重新计算值
// 如果 key 对应的 value 不存在，则返回该 null，如果存在，则返回通过 remappingFunction 重新计算后的值
```

**实例**

```java
import java.util.HashMap;

class Main {
    public static void main(String[] args) {
        HashMap<String, Integer> prices = new HashMap<>();

        // 往HashMap中添加映射项
        prices.put("Shoes", 200);
        prices.put("Bag", 300);
        prices.put("Pant", 150);
        System.out.println("HashMap: " + prices);

        // 重新计算鞋子打了10%折扣后的值
        int newPrice = prices.compute("Shoes", (key, value) -> value - value * 10/100);
        System.out.println("Discounted Price of Shoes: " + newPrice);

        // 输出更新后的HashMap
        System.out.println("Updated HashMap: " + prices);
    }
}
/*
HashMap: {Pant=150, Bag=300, Shoes=200}
Discounted Price of Shoes: 180
Updated HashMap: {Pant=150, Bag=300, Shoes=180
*/
```

#### computeIfAbsent()

对 hashMap 中**指定 key 的值进行重新计算**，如果**不存在这个 key**，则**添加到 hasMap 中**

**语法**

```java
hashmap.computeIfAbsent(K key, Function remappingFunction)
// key - 键
// remappingFunction - 重新映射函数，用于重新计算值
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // 创建一个 HashMap
        HashMap<String, Integer> prices = new HashMap<>();

        // 往HashMap中添加映射项
        prices.put("Shoes", 200);
        prices.put("Bag", 300);
        prices.put("Pant", 150);
        System.out.println("HashMap: " + prices);

        // key不存在,计算Shit的值
        int shirtPrice = prices.computeIfAbsent("Shirt", key -> 280);
        System.out.println("Price of Shirt: " + shirtPrice);

        // 输出更新后的HashMap
        System.out.println("Updated HashMap: " + prices);
        
        // key不存在的时候
        
        // Shoes中的映射关系已经存在
        // Shoes并没有计算新值
        int shoePrice = prices.computeIfAbsent("Shoes", (key) -> 280);
        System.out.println("Price of Shoes: " + shoePrice);
    }
}
/*
HashMap: {Pant=150, Bag=300, Shoes=200}
Price of Shirt: 280
Updated HashMap: {Pant=150, Shirt=280, Bag=300, Shoes=200}
Price of Shoes: 180
*/
```

#### computeIfPresent()

对 hashMap 中**指定 key 的值进行重新计算**，**前提是该 key 存在于 hashMap 中**。

**语法**

```java
hashmap.computeIfPresent(K key, BiFunction remappingFunction)
// key - 键
// remappingFunction - 重新映射函数，用于重新计算值
```

**实例**

```java
import java.util.HashMap;

public class Main {
    public static void main(String[] args) {
        // 创建一个 HashMap
        HashMap<String, Integer> prices = new HashMap<>();

        // 往HashMap中添加映射关系
        prices.put("Shoes", 200);
        prices.put("Bag", 300);
        prices.put("Pant", 150);
        System.out.println("HashMap: " + prices);

        // 重新计算鞋加上10%的增值税后的价值
        int shoesPrice = prices.computeIfPresent("Shoes", (key, value) -> value + value * 10/100);
        System.out.println("Price of Shoes after VAT: " + shoesPrice);

        // 输出更新后的HashMap
        System.out.println("Updated HashMap: " + prices);
    }
}
/*
HashMap: {Pant=150, Bag=300, Shoes=200}
Price of Shoes after VAT: 220
Updated HashMap: {Pant=150, Bag=300, Shoes=220}}
*/
```

## Java Iterator

**Iterator（迭代器）不是一个集合**，它是一种用于**访问集合的方法**，可用于**迭代 ArrayList 和 HashSet 等集合**。

迭代器 it 的两个基本操作是 next 、hasNext 和 remove。

- 调用 **it.next()** 会返回**迭代器的下一个元素**，并且**更新迭代器的状态**。

- 调用 **it.hasNext()** 用于**检测集合中是否还有元素**。

- 调用 **it.remove()** 将迭代器**返回的元素删除**。

### 获取迭代器

```java
import java.util.ArrayList;
import java.util.Iterator;

public class RunoobTest {
    public static void main(String[] args) {

        // 创建集合
        ArrayList<String> sites = new ArrayList<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Zhihu");

        // 获取迭代器
        Iterator<String> it = sites.iterator();

        // 输出集合中的第一个元素
        System.out.println(it.next());  // Google
    }
}
```

### 循环集合元素

**输出所有元素**

```java
import java.util.ArrayList;
import java.util.Iterator;

public class RunoobTest {
    public static void main(String[] args) {

        // 创建集合
        ArrayList<String> sites = new ArrayList<String>();
        sites.add("Google");
        sites.add("Runoob");
        sites.add("Taobao");
        sites.add("Zhihu");

        // 获取迭代器
        Iterator<String> it = sites.iterator();

        // 输出集合中的所有元素
        while(it.hasNext()) {
            System.out.println(it.next());
        }
    }
}
/*
Google
Runoob
Taobao
Zhihu
*/
```

**删除元素**

```java
import java.util.ArrayList;
import java.util.Iterator;

public class RunoobTest {
    public static void main(String[] args) {
        ArrayList<Integer> numbers = new ArrayList<Integer>();
        numbers.add(12);
        numbers.add(8);
        numbers.add(2);
        numbers.add(23);
        Iterator<Integer> it = numbers.iterator();
        while(it.hasNext()) {
            Integer i = it.next();
            if(i < 10) {  
                it.remove();  // 删除小于 10 的元素
            }
        }
        System.out.println(numbers);
    }
}
// [12, 23]
```

## Java Object



## Java 泛型