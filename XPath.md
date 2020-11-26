# XPath

**XPath** 是一门在 **HTML\XML  文档中查找信息的语言**。

**XPath** 是 **XSLT 中的主要元素**。

**XQuery** 和 **XPointer** 均**构建于 XPath 表达式之上**。

## XPath简介

- XPath 使用**路径表达式**在 **HTML\XML  文档**中进行导航
- XPath 包含一个**标准函数库**
- XPath 是 **XSLT 中的主要元素**
- XPath 是一个 **W3C 标准**

## XPath节点

### XPath术语

#### 节点(Node)

在XPath中，有七种类型的节点：**元素**、**属性**、**文本**、**命名空间**、**处理指令**、**注释**以及**文档（根）节点**。

**XML文档**是被作为**节点树**来对待的。**树的根**被称为**文档节点或根节点**。

```xml
<?xml version="1.0" encoding="UTF-8"?>

<bookstore>
  <book>
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>
</bookstore>
```

上述XML文档的节点例子:

```xml
<bookstore> (文档节点)
<author>J K. Rowling</author> (元素节点)
lang="en" (属性节点)
```

#### 基本值(Atomic value)

**基本值**是**无父或无子的节点**。

例子：

```xml
J K. Rowling

"en"
```

#### 项目(Item)

**项目**是**基本值或者节点**。

### 节点关系

#### 父(Parent)

**每个元素以及属性都有一个父**。

**book 元素**是 **title、author、year 以及 price 元素的父**：

```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>
```

#### 子(Children）

**元素节点**可有**零个、一个或多个子**。

**title、author、year 以及 price 元素**都是 **book 元素的子**：

```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>
```

#### 同胞(Sibling)

**拥有相同的父的节点**

**title、author、year 以及 price 元素都是同胞**：

```xml
<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>
```

#### 先辈(Ancestor)

**某节点的父、父的父，等等**。

**title 元素的先辈**是 **book 元素和 bookstore 元素**：

```xml
<bookstore>

<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

</bookstore>
```

#### 后代(Descendant)

**某个节点的子，子的子，等等。**

**bookstore 的后代**是 **book、title、author、year 以及 price 元素**：

```xml
<bookstore>

<book>
  <title>Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

</bookstore>
```

## XPath语法

XPath 使用**路径表达式**来选取 **XML 文档中的节点或节点集**。节点是通过沿着**路径 (path) 或者步 (steps)** 来选取的。

 **XML 文档实例**：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<bookstore>   
    <book>   
        <title lang="eng">Harry Potter</title>   
        <price>29.99</price> 
    </book>   
    <book>   
        <title lang="eng">Learning XML</title>   
        <price>39.95</price> 
    </book>   
</bookstore>
```

### 选取节点

**路径表达式：**

| 表达式       | 描述                                                         |
| :----------- | :----------------------------------------------------------- |
| **nodename** | 选取**此节点的所有子节点**。                                 |
| **/**        | 从**根节点选取**。                                           |
| **//**       | 从**匹配选择的当前节点选择文档中的节点**，而**不考虑它们的位置**。 |
| **.**        | 选取**当前节点**。                                           |
| **..**       | 选取**当前节点的父节点**。                                   |
| **@**        | 选取**属性**。                                               |

**实例：**

| 路径表达式          | 结果                                                         |
| :------------------ | :----------------------------------------------------------- |
| **bookstore**       | 选取 **bookstore 元素的所有子节点**。                        |
| **/bookstore**      | 选取**根元素 bookstore**。注释：假如路径起始于正斜杠( / )，则此路径始终代表到某元素的绝对路径！ |
| **bookstore/book**  | 选取**属于 bookstore 的子元素的所有 book 元素**。            |
| **//book**          | 选取**所有 book 子元素**，而**不管它们在文档中的位置**。     |
| **bookstore//book** | 选择**属于 bookstore 元素的后代的所有 book 元素**，而**不管它们位于 bookstore 之下的什么位置**。 |
| **//@lang**         | 选取**名为 lang 的所有属性**。                               |

### 谓语(Predicates)

**谓语**用来**查找某个特定的节点或者包含某个指定的值的节点**。

**谓语**被嵌在**方括号**中。

**实例：**

| 路径表达式                              | 结果                                                         |
| :-------------------------------------- | :----------------------------------------------------------- |
| **/bookstore/book[1]**                  | 选取**属于 bookstore 子元素的第一个 book 元素**。            |
| **/bookstore/book[last()]**             | 选取**属于 bookstore 子元素的最后一个 book 元素**。          |
| **/bookstore/book[last()-1]**           | 选取**属于 bookstore 子元素的倒数第二个 book 元素**。        |
| **/bookstore/book[position()<3]**       | 选取**最前面的两个属于 bookstore 元素的子元素的 book 元素**。 |
| **//title[@lang]**                      | 选取**所有拥有名为 lang 的属性的 title 元素**。              |
| **//title[@lang='eng']**                | 选取**所有 title 元素，且这些元素拥有值为 eng 的 lang 属性**。 |
| **/bookstore/book[price>35.00]**        | 选取 b**ookstore 元素的所有 book 元素，且其中的 price 元素的值须大于 35.00**。 |
| **/bookstore/book[price>35.00]//title** | 选取 **bookstore 元素中的 book 元素的所有 title 元素，且其中的 price 元素的值须大于 35.00**。 |

### 选取未知节点

XPath **通配符**可用来选取**未知的 XML 元素**。

| 通配符     | 描述                     |
| :--------- | :----------------------- |
| *****      | 匹配**任何元素节点**。   |
| **@***     | 匹配**任何属性节点**。   |
| **node()** | 匹配**任何类型的节点**。 |

**实例：**

| **路径表达式**   | 结果                              |
| ---------------- | --------------------------------- |
| **/bookstore/*** | 选取**bookstore元素的所有子元素** |
| **//***          | 选取**文档中的所有元素**          |
| **//title[@*]**  | 选取**所有带有属性的title元素**   |

### **选取若干路径**

路径表达式中使用"**|**"运算符，可以**选取若干个路径**。

**实例：**

| 路径表达式                           | 结果                                                         |
| :----------------------------------- | :----------------------------------------------------------- |
| **//book/title \| //book/price**     | 选取 **book 元素的所有 title 和 price 元素**。               |
| **//title \| //price**               | 选取**文档中的所有 title 和 price 元素**。                   |
| **/bookstore/book/title \| //price** | 选取**属于 bookstore 元素的 book 元素的所有 title 元素，以及文档中所有的 price 元素**。 |

## XPath 轴（Axes）

轴可定义相对于当前节点的节点集。

| 轴名称                 | 描述                                                         |
| :--------------------- | :----------------------------------------------------------- |
| **ancestor**           | 选取**当前节点的所有先辈（父、祖父等）**。                   |
| **ancestor-or-self**   | 选取**当前节点的所有先辈（父、祖父等）以及当前节点本身**。   |
| **attribute**          | 选取**当前节点的所有属性**。                                 |
| **child**              | 选取**当前节点的所有子元素**。                               |
| **descendant**         | 选取**当前节点的所有后代元素（子、孙等）**。                 |
| **descendant-or-self** | 选取**当前节点的所有后代元素（子、孙等）以及当前节点本身**。 |
| **following**          | 选取**文档中当前节点的结束标签之后的所有节点**。             |
| **following-sibling**  | 选取**当前节点之后的所有兄弟节点**                           |
| **namespace**          | 选取**当前节点的所有命名空间节点**。                         |
| **parent**             | 选取**当前节点的父节点**。                                   |
| **preceding**          | 选取**文档中当前节点的开始标签之前的所有节点**。             |
| **preceding-sibling**  | 选取**当前节点之前的所有同级节点**。                         |
| **self**               | 选取**当前节点**。                                           |

**实例：**

| 例子                       | 结果                                                         |
| -------------------------- | ------------------------------------------------------------ |
| **child::book**            | 选取**所有属于当前节点的子元素的 book 节点**。               |
| **attribute::lang**        | 选取**当前节点的 lang 属性**。                               |
| **child::***               | 选取**当前节点的所有子元素**。                               |
| **attribute::***           | 选取**当前节点的所有属性**。                                 |
| **child::text()**          | 选取**当前节点的所有文本子节点**。                           |
| **child::node()**          | 选取**当前节点的所有子节点**。                               |
| **descendant::book**       | 选取**当前节点的所有 book 后代**。                           |
| **ancestor::book**         | 选择**当前节点的所有 book 先辈**。                           |
| **ancestor-or-self::book** | 选取**当前节点的所有 book 先辈以及当前节点**（**如果此节点是 book 节点**） |
| **child::*/child::price**  | 选取**当前节点的所有 price 孙节点**。                        |

## XPath 运算符

| 运算符 | 描述               | 实例                      | 返回值                                                       |
| ------ | ------------------ | ------------------------- | ------------------------------------------------------------ |
| \|     | **计算两个节点集** | //book \| //cd            | 返回**所有拥有 book 和 cd 元素的节点集**                     |
| +      | **加法**           | 6 + 4                     | 10                                                           |
| -      | **减法**           | 6 - 4                     | 2                                                            |
| *      | **乘法**           | 6 * 4                     | 24                                                           |
| div    | **除法**           | 8 div 4                   | 2                                                            |
| =      | **等于**           | price=9.80                | 如果 price 是 9.80，则返回 true。如果 price 是 9.90，则返回 false。 |
| !=     | **不等于**         | price!=9.80               | 如果 price 是 9.90，则返回 true。如果 price 是 9.80，则返回 false。 |
| <      | **小于**           | price<9.80                | 如果 price 是 9.00，则返回 true。如果 price 是 9.90，则返回 false。 |
| <=     | **小于或等于**     | price<=9.80               | 如果 price 是 9.00，则返回 true。如果 price 是 9.90，则返回 false。 |
| >      | **大于**           | price>9.80                | 如果 price 是 9.90，则返回 true。如果 price 是 9.80，则返回 false。 |
| >=     | **大于或等于**     | price>=9.80               | 如果 price 是 9.90，则返回 true。如果 price 是 9.70，则返回 false。 |
| or     | **或**             | price=9.80 or price=9.70  | 如果 price 是 9.80，则返回 true。如果 price 是 9.50，则返回 false。 |
| and    | **与**             | price>9.00 and price<9.90 | 如果 price 是 9.80，则返回 true。如果 price 是 8.50，则返回 false。 |
| mod    | **计算除法的余数** | 5 mod 2                   | 1                                                            |

## 在python中使用XPath

```python
# coding=utf-8
 
from lxml import etree
 
xml_data = '''
<bookstore>
<book>
  <title lang="eng">Harry Potter</title>
  <price>29.99</price>
</book>
<book>
  <title lang="eng">Learning XML</title>
  <price>39.95</price>
</book>
</bookstore>
'''
 
# etree.HTML()可以接收str或者bytes类型数据，将其转化成 Element 对象
html = etree.HTML(xml_data)
# 从文件加载 HTML
# html = etree.parse('test.html',etree.HTMLParser())
 
# lxml 会自动修 HTML ，查看一下 lxml 修正后的结果
print(etree.tostring(html, pretty_print=True).decode('utf-8'))
 
# 获取 Learning XML 这本书的价格
ret = html.xpath('//title[text()="Learning XML"]/following::price/text()')[0] if len(
    html.xpath('//title[text()="Learning XML"]/following::price/text()')) else None

print(ret)
'''
输出结果：
<html>
  <body><bookstore>
 
<book>
  <title lang="eng">Harry Potter</title>
  <price>29.99</price>
</book>
 
<book>
  <title lang="eng">Learning XML</title>
  <price>39.95</price>
</book>
 
</bookstore>
</body>
</html>
 
39.95
'''
```

