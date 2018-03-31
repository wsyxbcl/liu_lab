# 刘晓庆课题组网站


This README.md is composed in Chinese for it's mainly a tutorial for Chinese users who maintain the website under Windows environment.  

----------
这是为[刘晓庆课题组](http://xiaoqingliu.whu.edu.cn)搭建的静态网站，使用[jekyll](https://www.jekyll.com.cn/)和[bootstrap3](https://v3.bootcss.com/)完成。网站基于[Riggleman Lab](http://rrgroup.seas.upenn.edu)和[Bedford Lab](http://bedford.io/)的开源代码完成，在此表示感谢。  
The framework is highly inspired by [Riggleman Lab](http://rrgroup.seas.upenn.edu) and [Bedford Lab](http://bedford.io/), thank you for kindly making your code open-source.

## 1. 环境配置
请参考[Jekyll on Windows](https://jekyllrb.com/docs/windows/)在windows环境下安装ruby。此处仅提供一种方法作为参考。
1. 使用[RubyInstaller](https://rubyinstaller.org/downloads/)安装Ruby
2. 命令行（或powershell）执行`gem install jekyll bundler`安装Jekyll和Bundler。
3. 在命令行中切换到网站根目录（比如`cd C:\xxx\liu_lab`），执行`bundle install`。

## 2. 网站搭建
在网站的根目录执行`bundle exec jekyll build`即可完成网站的搭建，生成的静态html文件位于_site文件夹中。使用`bundle exec jekyll serve`可在本地部署网站，在浏览器中输入`http://127.0.0.1:4000/`即可预览生成的网站。

## 3. 网站更新
更新网站的所需的主要目录结构如下：  
	├── about  
	├── contact  
	├── images  
	├── join  
	├── members  
	├── news  
	├── photos  
	├── publications  
	└── research  
更新时将需要上传的markdown文件(.md)放入各文件夹中的_post文件夹中即可。  
markdown文件的命名必须按照yyyy-mm-dd-title.md的格式（如2018.03.09-This-is-a-test.md）。每个markdown文件中包含一个yaml文件头（由3个 '-' 字符分隔），参考同目录下其他md文件完成填写即可。yaml文件头下方为正文，可以使用markdown语法（可参考http://www.cnblogs.com/math/p/se-tools-001.html 或自行百度教程）进行编辑。  
member中成员的年级数由文件名中年份决定，是否为离组人员由yaml文件头中的alumni变量决定。

images文件夹包含网站所用的所有图片（背景、标题栏和首页展示图片可直接替换），增加新的图片内容时请将图片文件置于此目录下的相应目录内，并在对应md文件的yaml文件头中声明正确的图片路径。  

根目录的index.html为网站首页内容，新闻板块自动调用了最新的五条新闻，其余板块可在此自行修改。  

其余文件夹（主要为_开头的文件夹）用途请自行参考jekyll官方文档，并根据需要对框架、版式进行修改。 // Good luck

## 4.网站上传
在完成 '2. 网站搭建' 的步骤后，生成的网页文件位于_site文件夹中，上传到空间的指定路径即可。
