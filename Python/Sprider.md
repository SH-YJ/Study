# Sprider(爬虫)

## urllib

## requests

## selenium

**selenium** 是一个**用于Web应用程序测试的工具**。Selenium测试直接运行在浏览器中，就像真正的用户在操作一样。支持的浏览器包括IE（7, 8, 9, 10, 11），Mozilla Firefox，Safari，Google Chrome，Opera等

**selenium用于爬虫**，主要是用来解决**javascript渲染的问题**

### selenium的基本使用

```python
# -*- coding: utf-8 -*-
from selenium import webdriver

if __name__ = '__main__':
    # 声明谷歌、Firefox、Safari等浏览器
    # 若浏览器非默认安装路径，需加入路径
    browser = webdriver.Chrome()  # 创建drive对象
    # 若webdriver.exe不与python解释器不在同一路径下，需手动声明
    # browser = webdriver.Chrome(executable_path=r'C:/chrome/chromedriver.exe')
    
    browser.get("http://www.baidu.com")  # 请求数据
    data = browser.page_source  # 获取当前页面的响应数据（源代码）
    print(type(data))  # data 的数据类型 <class 'str'>
    # 获取网页源代码并储存到本地
    with open('baidu.html','w',encoding='utf-8') as f:
        f.write(data_)
    
    # 使界面最大化
    browser.maximize_window()
    # 截取当前页面
	browser.save_screenshot('baidu.png')
    
    browser.close()  # 关闭浏览器当前页面
    browser.quit()  # 关闭浏览器
```

### 无头模式的设置

```python
import time
from selenium import webdriver
# 设置"无头模式"
from selenium.webdriver.chrome.options import Options

if __name__ == '__main__':
    # 实例化 创建一个新的的对象 option对象
    option = Options()
    # 添加参数设置'无头模式',
    option.add_argument('--headless')
    """
    第二种:option_.set_headless()
    第三种:option_.headless = True
    """

    driver_ = webdriver.Chrome(options=option)  # 1. 创建浏览器对象,打开对应浏览器
    driver_.get('https://www.baidu.com/')  # 2.get向url输入框输入网址
    data_ = driver_.page_source  # 3. 获取当前页面的响应数据（源代码）
    print(type(data_))
    time.sleep(1)
    driver_.close() # 关闭浏览器页面
    time.sleep(1)
    driver_.quit()  # 关闭浏览器
```

### selenium元素定位的方法

**定位元素的语法**

```python
find_element_by_id (返回一个元素)
find_elements_by_xpath （返回一个包含元素的列表）
find_elements_by_link_text （根据连接文本获取元素列表）
find_elements_by_partial_link_text （根据链接包含的文本获取元素列表）
find_elements_by_tag_name (根据标签名获取元素列表)
find_elements_by_class_name （根据类名获取元素列表）
```

**find_element和find_elements的区别**：单个元素和所有元素。

**by_link_text和by_partial_link_tex的区别**：全部文本和包含某个文本。

```python
# 查找单个元素与多个元素
from selenium import webdriver
from selenium.webdriver.common.by import By

browser = webdriver.Chorme()
browser.get("http://www.baidu.com")

# 单个元素的多种从查找方式
l1 = browser.find_element_by_id("q")
l2 = browser.find_element_by_css_selector("#q")
l3 = browser.find_element(By.ID, "q")

# 多个元素的多种查找方式
l4 = browser.find_elements_by_css_selector("ul")
l5 = browser.find_elements(By.CSS_SELECTOR, "ul")

browser.close()
```

