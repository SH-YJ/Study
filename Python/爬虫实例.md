# Python of Sprider(网络爬虫)

## 爬取图片

### 最简单下载图片

```python
import urllib.request

#图片下载

img_url = url	#网址
urllib.request.urlretrieve(img_url, 'S:/'+img_url.split('/')[-1])
```

### 例1：taotuxp.com

```python
#一次可爬取12个套图
# -- coding:UTF-8 --
import requests
from bs4 import BeautifulSoup
import os
import re
'''
思路：获取网址
      获取图片地址
      爬取图片并保存
'''
# 获取网址
def getUrl(url):
    try:
        read = requests.get(url)  #获取url
        read.raise_for_status()   #状态响应 返回200连接成功
        read.encoding = read.apparent_encoding  #从内容中分析出响应内容编码方式
        return read.text   #Http响应内容的字符串，即url对应的页面内容
    except:
        return "连接失败！"

while True:
    os.system('cls')
    S_page =input("输入第几页:")
    a_html_url = getUrl("https://www.taotuxp.com/xinggan/page/"+str(S_page))	#主界面网址
    sum_url = re.findall('<a href="(.*?)" class=".*?" target=".*?">',a_html_url) #获取一网页12个网址
    for s_url in sum_url :
        html_urls = getUrl(s_url)
        soups = BeautifulSoup(html_urls, "html.parser")
        # 通过分析网页内容，查找img的统一父类及属性
        pagelist = soups.find('div', class_='pagelist').find_all('a')   #获取当前网页总页数
        sum_page = int(pagelist[-1].string)+1
        for page in range(1,int(sum_page)):   #页数爬取
            html_url = getUrl(s_url+ '/' +str(page))
            dir_name = re.findall('<h1>(.*?)</h1>', html_url)[-1]   #获取标题名
            soup = BeautifulSoup(html_url, "html.parser")
            # 通过分析网页内容，查找img的统一父类及属性
            all_img = soup.find('div', class_='context').find_all('img')  # img为图片的标签
            for img in all_img:
                src = img['src']  # 获取img标签里的src内容
                img_url = src
                print(img_url)
                root = "S:/Pic/" + dir_name +'/'# 保存的路径
                path = root + img_url.split('/')[-1] # 获取img的文件名
                print(path)
                try:
                    if not os.path.exists(root):  # 判断是否存在文件并下载img
                        os.mkdir(root)
                    if not os.path.exists(path):
                        read = requests.get(img_url)
                        with open(path, "wb")as f:
                            f.write(read.content)
                            f.close()
                            print("文件保存成功！")
                    else:
                        print("文件已存在！")
                except:
                    print("文件爬取失败！")
```

### 例2：woyaogexing.com

```python
import requests
from bs4 import BeautifulSoup
import urllib.request

def getUrl(url):
    try:
        read = requests.get(url)  #获取url
        read.raise_for_status()   #状态响应 返回200连接成功
        read.encoding = read.apparent_encoding  #从内容中分析出响应内容编码方式
        return read.text   #Http响应内容的字符串，即url对应的页面内容
    except:
        return "连接失败！"

while True:
    kind = input("类型:")
    num = input("地址:")
    html_url = getUrl('https://www.woyaogexing.com/touxiang/'+str(kind)+'/2020/' + str(num) + '.html')
    soup = BeautifulSoup(html_url, "html.parser")
    all_img = soup.find('ul', class_='artCont cl').find_all('img')
    for img in all_img:
        src = img['src']
        img_url = 'https:' + src
        urllib.request.urlretrieve(img_url, 'S:/' + img_url.split('/')[-1])
```

### 例3：obzhi.com

```python
# -- coding:UTF-8 --
import requests
from bs4 import BeautifulSoup
import os
import re
'''
思路：获取网址
      获取图片地址
      爬取图片并保存
'''
headers ={
    'user-agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/78.0.3904.116 Safari/537.36'
}

# 获取网址
def getUrl(url):
    try:
        read = requests.get(url,headers=headers)  #获取url
        read.raise_for_status()   #状态响应 返回200连接成功
        read.encoding = read.apparent_encoding  #从内容中分析出响应内容编码方式
        return read.text   #Http响应内容的字符串，即url对应的页面内容
    except:
        return "连接失败！"

if __name__ == '__main__':
    for i in range(2,15):
        html_url = getUrl('http://www.obzhi.com/category/fengjingbizhi/page/'+str(i))
        soup = BeautifulSoup(html_url,"html.parser")
        url = soup.find('ul',class_='masonry clearfix').find_all('a', class_='zoom')#获取所有图片所在网页
        for u in url:
            u_url = u['href']
            html_url2 = getUrl(u_url)
            soup2 = BeautifulSoup(html_url2, "html.parser")
            img_url = soup2.find('img', class_='alignnone')#获取具体图片地址
            img = img_url['src']
            root = "S:/Pic/"   # 保存的路径
            path = root + img.split('/')[-1]  # 获取img的文件名
            print(path)
            try:
                if not os.path.exists(root):  # 判断是否存在文件并下载img
                    os.mkdir(root)
                if not os.path.exists(path):
                    read = requests.get(img)
                    with open(path, "wb")as f:
                        f.write(read.content)
                        f.close()
                        print("文件保存成功！")
                else:
                    print("文件已存在！")
            except:
                print("文件爬取失败！")
```

### 例4：pic.netbian.com

```python
import requests
from bs4 import BeautifulSoup
import os
import re

# 获取网址
def getUrl(url):
    try:
        read = requests.get(url)  #获取url
        read.raise_for_status()   #状态响应 返回200连接成功
        read.encoding = read.apparent_encoding  #从内容中分析出响应内容编码方式
        return read.text   #Http响应内容的字符串，即url对应的页面内容
    except:
        return "连接失败！"

if __name__ == '__main__':
    for i in range(2,200):
        html_url = getUrl('http://pic.netbian.com/4kfengjing/index_'+ str(i) +'.html')
        soup =BeautifulSoup(html_url,"html.parser")
        img_urls = soup.find('ul',class_='clearfix').find_all('a')#获取图片所在网址
        for img_url in img_urls:
            img = "http://pic.netbian.com" + img_url['href']
            html_url2 = getUrl(img)
            soup2 = BeautifulSoup(html_url2,"html.parser")
            i_img_url = soup2.find('div',class_='photo-pic').find('img')#获取图片具体地址
            ii_img = 'http://pic.netbian.com' + str(i_img_url['src'])
            root = "S:/4K/"  # 保存的路径
            path = root + ii_img.split('/')[-1]  # 获取img的文件名
            print(path)
            try:
                if not os.path.exists(root):  # 判断是否存在文件并下载img
                    os.mkdir(root)
                if not os.path.exists(path):
                    read = requests.get(ii_img)
                    with open(path, "wb")as f:
                        f.write(read.content)
                        f.close()
                        print("文件保存成功！")
                else:
                    print("文件已存在！")
            except:
                print("文件爬取失败！")
```

