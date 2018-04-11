# 刘晓庆课题组网站


This README.md is composed in Chinese for it's mainly a tutorial for Chinese users who maintain the website under Windows environment.  

----------
这是为[刘晓庆课题组](http://xiaoqingliu.whu.edu.cn)搭建的静态网站，使用[jekyll](https://www.jekyll.com.cn/)和[bootstrap3](https://v3.bootcss.com/)完成。网站基于[Riggleman Lab](http://rrgroup.seas.upenn.edu)和[Bedford Lab](http://bedford.io/)的开源代码完成，在此表示感谢。  
The framework is highly inspired by [Riggleman Lab](http://rrgroup.seas.upenn.edu) and [Bedford Lab](http://bedford.io/), thank you for kindly making your code open-source.

## 1. 环境配置
环境配置分三步，第一步为ruby的安装，第二步使用gem安装jekyll和bundler，第三步使用bundler安装其他组件。  
请参考[Jekyll on Windows](https://jekyllrb.com/docs/windows/)在windows环境下安装ruby, jekyll和bundler。由于libv8无适配windows的版本，推荐使用WSL(Windows Subsystem for Linux)作为环境。  
1. 安装WSL，可参考[https://www.cnblogs.com/JettTang/p/8186315.html](https://www.cnblogs.com/JettTang/p/8186315.html)
2. 命令行（或powershell）下执行bash进入WSL
3. 依次执行
	sudo apt-get update -y && sudo apt-get upgrade -y  
	sudo apt-add-repository ppa:brightbox/ruby-ng  
	sudo apt-get update  
	sudo apt-get install ruby2.3 ruby2.3-dev build-essential dh-autoreconf  
	完成对ruby的安装。  
4. 执行
	sudo gem update
	sudo gem install jekyll bundler
	完成jekyll和bundle的安装。
5. 执行（请确保在网站的根目录下，此目录包含Gemfile.lock文件）
	bundle install  
	完成环境配置。  


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
markdown文件的命名必须按照yyyy-mm-dd-title.md的格式。（如2018.03.09-This-is-a-test.md），每个markdown文件中包含一个yaml文件头（由3个 '-' 字符分隔），参考同目录下其他md文件完成填写即可。yaml文件头下方为正文，可以使用markdown语法（可参考http://www.cnblogs.com/math/p/se-tools-001.html 或自行百度教程）进行编辑。

## 4.网站上传
在完成 '2. 网站搭建' 的步骤后，生成的网页文件位于_site文件夹中，上传到空间的指定路径即可。