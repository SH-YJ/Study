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



## Java ArrayList



## Java LinkedList