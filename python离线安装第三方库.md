## python离线安装第三方库

### 一. 下载安装包

```python
//可用的网址
https://pypi.org/
https://www.lfd.uci.edu/~gohlke/pythonlibs/   #提供Windows版本的后缀是".whl"，可以直接查找相关的包
http://pypi.doubanio.com/simple/  #豆瓣镜像源
#可以在地址栏直接输入查找的包，离线下载，例如：下载tensorflow
#http://pypi.doubanio.com/simple/tensorflow

#使用实例
pip install tensorflow -i http://pypi.doubanio.com/simple/
#<-d ./path>的意思是将下载的文件存放到当前目录下的path文件夹里面，<-i url>的意思是从中科大镜像源下载文件。    
pip download -d ./path pyinstaller -i https://pypi.mirrors.ustc.edu.cn/simple/
```

### 二. 不同软件安装包的安装

a. .whl的安装

```python
pip install numpy‑1.14.5+mkl‑cp27‑cp27m‑win_amd64.whl
```

b. tar.gz的安装

```python
#".tar.gz"文件解压
tar -xzvf numpy-1.15.0.tar.gz 
#".zip"文件解压
unzip numpy-1.15.0.zip
#进入目录"numpy-1.15.0"
cd numpy-1.15.0
#找到“setup.py”文件，然后安装
python setup.py install
```

### 三. 多个安装包同时下载

a. **生成requirement.txt**

根据之前安装包的下载，得到各个安装包的列表

![image-20220620202412036](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20220620202412036.png)

后面包文件名按照倒序的方式复制到文件夹内：

![image-20220620202437870](C:\Users\User\AppData\Roaming\Typora\typora-user-images\image-20220620202437870.png)

进入到安装包所在的文件夹

```shell
cd .\Desktop\path     ##先进入这个文件夹内
pip install -r requirement.txt    ##按照脚本内安装包的顺序安装库
```

b.**使用本地索引依赖包（推荐）**

pip提供了可以在本地目录搜索依赖包的选项，这样安装的好处是以前安装过的依赖包不会更新，避免出现升级带来的bug。

```shell
#pip提供了可以在本地目录搜索依赖包的选项，这样安装的好处是以前安装过的依赖包不会更新，避免出现升级带来的bug。
#其中pyinstaller为要安装的软件包
pip install --no-index --find-links=C:\Users\path\ pyinstaller 
```

