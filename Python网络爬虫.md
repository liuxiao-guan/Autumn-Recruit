## Python网络爬虫

### 一. 方法：

```python
## 使用urllib
from urllib import request
## 获取响应对象
response = request.urlopen("http://baidu.com")
## 输出HTML信息
html = response.read().decode('utf-8') #因为返回的是自己，所以要解码
## html的响应对象
url = response.geturl()## 响应对象的地址
code = response.getcode()#获取请求时的http响应码
#每爬取一个页面随机休眠1-2秒钟的时间
time.sleep(random.randint(1,2)) ## 随机休眠可以使爬虫程序模仿成人类的样子
```

### 二. 用户代理与代理池

1. 作用：防止反爬虫机制，因为如果是网络爬虫，请求头的信息会为```Python-urllib/3.7```类似这种的

2. 使用

   ```python
   from urllib import request
   # 定义变量：URL 与 headers
   url = 'http://httpbin.org/get' #向测试网站发送请求
   #重构请求头，伪装成 Mac火狐浏览器访问，可以使用上表中任意浏览器的UA信息
   headers = {
   'User-Agent':'Mozilla/5.0 (Macintosh; Intel Mac OS X 10.12; rv:65.0) Gecko/20100101 Firefox/65.0'}
   # 1、创建请求对象，包装ua信息
   req = request.Request(url=url,headers=headers)
   # 2、发送请求，获取响应对象
   res = request.urlopen(req)
   # 3、提取响应内容
   html = res.read().decode('utf-8')
   print(html)
   ```

   自定义用户代理

   ```python
   
   my_headers = [
       "Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/39.0.2171.95 Safari/537.36",
       "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.153 Safari/537.36",
       "Mozilla/5.0 (Windows NT 6.1; WOW64; rv:30.0) Gecko/20100101 Firefox/30.0",
       "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_9_2) AppleWebKit/537.75.14 (KHTML, like Gecko) Version/7.0.3 Safari/537.75.14",
       "Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.2; Win64; x64; Trident/6.0)",
       'Mozilla/5.0 (Windows; U; Windows NT 5.1; it; rv:1.8.1.11) Gecko/20071127 Firefox/2.0.0.11',
       'Opera/9.25 (Windows NT 5.1; U; en)',
       'Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1; SV1; .NET CLR 1.1.4322; .NET CLR 2.0.50727)',
       'Mozilla/5.0 (compatible; Konqueror/3.5; Linux) KHTML/3.5.5 (like Gecko) (Kubuntu)',
       'Mozilla/5.0 (X11; U; Linux i686; en-US; rv:1.8.0.12) Gecko/20070731 Ubuntu/dapper-security Firefox/1.5.0.12',
       'Lynx/2.8.5rel.1 libwww-FM/2.14 SSL-MM/1.4.1 GNUTLS/1.2.9',
       "Mozilla/5.0 (X11; Linux i686) AppleWebKit/535.7 (KHTML, like Gecko) Ubuntu/11.04 Chromium/16.0.912.77 Chrome/16.0.912.77 Safari/535.7",
       "Mozilla/5.0 (X11; Ubuntu; Linux i686; rv:10.0) Gecko/20100101 Firefox/10.0 "
   ]
   ua_list = [
       'Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0',
       'Mozilla/5.0 (Macintosh; Intel Mac OS X 10_7_0) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11',
       'User-Agent:Opera/9.80 (Windows NT 6.1; U; en) Presto/2.8.131 Version/11.11',
       'Mozilla/5.0 (Windows NT 6.1; rv:2.0.1) Gecko/20100101 Firefox/4.0.1',
       'Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0)',
       'Mozilla/5.0 (Windows; U; Windows NT 6.1; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50',
       'Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0',
       ' Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1',
       'Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1',
       ' Mozilla/5.0 (Macintosh; Intel Mac OS X 10.6; rv:2.0.1) Gecko/20100101 Firefox/4.0.1',
   ]
   ## 随机切换用户代理
   header = random.choice(my_headers)
   ```

   模块随机获取----fake-useragent

   ```python
   from fake_useragent import UserAgent
   #实例化一个对象
   ua=UserAgent()
   #随机获取一个ie浏览器ua
   print(ua.ie)
   #随机获取一个火狐浏览器ua
   print(ua.firefox)
   
   ## 结果
   # Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.0; Trident/4.0; GTB7.4; InfoPath.3; SV1; .NET CLR 3.1.76908; WOW64; en-US)
   # Mozilla/5.0 (Macintosh; Intel Mac OS X 10.8; rv:21.0) Gecko/20100101 Firefox/21.0
   ```



;

### url编码与解码

1. 作用：使用搜索引擎搜索内容时需要编码成url能理解的字符，而不只是我们常见的汉字，python中有对应的模块 解码与编码

### 有用的网址

```html
http://httpbin.org/
```

