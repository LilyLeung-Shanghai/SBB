# SBB

**SBB**(**S**ina **B**log **B**ook) is a script to download all artcles from a specific [Sina Blog](http://blog.sina.com.cn/) blogger.

Based on these downloaded HTML files, you may generate an ebook by importing into [Calibre](http://calibre-ebook.com/). Or, you can simply save them anywhere as archives.

Tested with Python 2.7.8

Now SBB3 created for Python 3.x

## Usage
SBB.py (Sina Blog URL) (asc|desc)

The sort order argument is optional. By default, articles will be sorted chronically (asc).

###Example:

- SBB.py http://blog.sina.com.cn/gongmin desc
- SBB.py http://blog.sina.com.cn/u/1239657051

## Roadmap
- [x] Add a datestamp for Index.html
- [x] 'SELECT * FROM AllBlogPosts ORDER BY DatePosted DESC / ASC'
- [ ] Download the embed pictures
- [ ] Intergrate Calibre lib to generate eBook in one place

## License
Licensed under the Apache License, Version 2.0


#中文

**SBB**(**S**ina **B**log **B**ook) 是一个用于下载指定新浪博客作者全部文章的脚本。

基于这些下载来的 HTML 文件，您可以借助 [Calibre](http://calibre-ebook.com/) 来生成电子书，或者当作存档。

请在 Python 2.7.8 下使用。

现在我加上了适合Python 3.x的版本。感谢 @Vjmms 老师赐教。

## @Vjmms 老师的讲解

把所有读网络请求返回的地方，解码成字符串形式供后面的代码使用。
即 objResponse.read() 改成 objResponse.read().decode()
最后写文件的时候要用 utf-8 的编码方式，这样才与代码中构造html文件的地方保持一致。
另外，python3不能使用urllib2这个库，需要修改成 import urllib.request，代码中所有 urllib2.urlopen 要改为 urllib.request.urlopen。
不同的python，可以考虑用 sys.version 判断一下，代码中做相应的处理，使用适用于不同版本的语句。

## 用法
SBB.py (新浪博客地址) (desc|asc)

排序开关是可选的，默认为按发表时间顺序排列（即 asc）。

例子：

- SBB.py http://blog.sina.com.cn/gongmin desc
- SBB.py http://blog.sina.com.cn/u/1239657051
	
## Roadmap
- [x] 首页增加时间戳
- [x] 'SELECT * FROM AllBlogPosts ORDER BY DatePosted DESC / ASC'
- [ ] 增加下载图片选项
- [ ] 整合 Calibre 库，一站式打包成 .mobi 或 .ePub

## 授权
Licensed under the Apache License, Version 2.0
