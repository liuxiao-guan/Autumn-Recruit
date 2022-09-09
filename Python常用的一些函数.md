## Python常用的一些函数

### 一.爬取网页上的所有链接

```Python
# 利用 requests_html
from requests_html import HTMLSession
session = HTMLSession()
url = 'https://www.baidu.com'
r = session.get(url)
print(r.html.links)
print('*'*100)
# 利用 BeautifulSoup
import requests
from bs4 import BeautifulSoup
url = 'http://www.baidu.com'
res = requests.get(url)
soup = BeautifulSoup(res.text, 'lxml')
for a in soup.find_all('a'):
    print(a['href'])
print('*'*100)
# 利用 re (不推荐用正则,太麻烦)
# 利用 lxml.etree
from lxml import etree
tree = etree.HTML(r.text)
for link in tree.xpath('//@href'):
    print(link)
print('*'*100)
# 利用 selenium
from selenium import webdriver
#chrome_options = webdriver.ChromeOptions()
#chrome_options.add_argument('--headless')
#browser = webdriver.Chrome(chrome_options=chrome_options)
#browser.get(url)
url = 'www.baidu.com'
path = r'D:/GuanXiaoLiu/Phishing/brand_crawl/chromedriver.exe'
s= Service(executable_path=path)
browser = webdriver.Chrome(service =s)
browser.get(url)
for link in browser.find_elements_by_tag_name('a'):
    print(link.get_attribute('href'))
```

### 二. CSV文件的处理

注：[(13条消息) pandas——对csv文件进行增加列、删除列、删除行、修改、查找重复等系列操作_Dear Slim.的博客-CSDN博客_csv.drop](https://blog.csdn.net/weixin_43525427/article/details/98745889)

```python
#读取CSV文件 后面也可以不转为list类型
df = pd.read_csv('.\\Client\\' + "client" + '.csv', engine='python', encoding='gbk', header=0，usecols=["用户编号"]).values.tolist()
#1. header默认时代表第一行为表头，header = None代表无表头
#2. usecols 代表选择所要的数据列
#新增一列
df_csv = pd.DataFrame(df)
df_csv['beianhao'] = result #其中result为list类型
#一行行读取
df_csv[start:end] #前闭后开
#读取每一个值
title = df_csv['title'][i]#i是行数
#切片操作
data = df_csv.iloc[:,0:2] #行列
#转为csv
df_csv.to_csv('.\\Client\\' +"client1" + '.csv',index = False)
#读取某几行
df[start:end]
#读取
#读取某几行几列
df.loc[]
## 新建csv文件
with open("test.csv",'w') as fw：
	writer = csv.write(fw)## 创建fw
    writer.writerow(list) ## 添加头
fw.close()
```

### 三.产生随机数

```python
import random
random.randint(0,99) ##产生随机数
#random.random()：生成一个 0-1 之间的随机浮点数；
#random.uniform(a, b)：生成[a,b]之间的浮点数；
#random.randint(a, b)：生成[a,b]之间的整数；
#random.randrange(a, b, step)：在指定的集合[a,b)中，以 step 为基数随机取一个数；
#random.choice(sequence)：从特定序列中随机取一个元素，这里的序列可以是字符串，列表，元组等。
```

### 四. 备案号查询

```
/^[京津晋冀蒙辽吉黑沪苏浙皖闽赣鲁豫鄂湘粤桂琼渝川贵云藏陕甘青宁新]ICP备\d{8}(-[1-9]\d?)?$/
```

```
[\u4e00-\u9fa5]ICP备\d{8}号-\d{1,3}
```

### 五.基础知识

```python
range(start, stop [,step])#step代表步长
range(1,10)#左闭右开
b = "长城|皮卡"
a = b.replace('|',"a")#此时b并没有改变 而是返回的a改变了
```

### 六.容器的操作

#### Set

```python
#新建一个set
data = set()
data = set("hello")
#增加
data.add()
#删除
remove()#必须存在否则会报错
discard()#不存在也不会报错
pop() #随机删除 如果set为空则会报错
#清空
clear()
#某一个元素是否在集合中
in #返回相应的布尔值 True False
not in 
```

#### String

```python
#首字母大写 其余小写
str.capitalize()
#字符串全大写
str.upper()
#是否为全大写
str.isupper()
#小写类似 upper --> lower
#字符串末尾
str[-1]
#去除字符串最后一个字符
str[:-1]
#是否有某字符
str.find("#")
```

### 七.读写文件 txt

```python
## 写入t
with open("D:\GuanXiaoLiu\Phishing\\brand_crawl\\request_zero_filename.txt","w",encoding="utf8") as fw:
    for i in remain:   
    	fw.write(i+"\n")
    fw.close()
```

### 八. 时间操作

```python
## 时间戳转为年月日时间
date = time.localtime(time.time())## time.time()是获取当前时间的时间戳
```

