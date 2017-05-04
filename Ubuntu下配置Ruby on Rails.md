# Ubuntu下配置Ruby on Rails
##1.安装RVM   ( ruby管理工具)


----------


可以到[RVM的官网](http://www.rvm.io/)去查看RVM的安装命令
[1]
`gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3`
[2]
 `sudo apt-get install curl`
[3] 
`\curl -sSL https://get.rvm.io | bash -s stable`
执行以上三条命令之后重启（切记，一定要重启）
重启后输入`rvm -v`来确认rvm安装成功
##2.使用rvm安装ruby


----------


执行`rvm list known`查看可获取的ruby版本

执行`rvm install 2.2`安装2.2版本的ruby

安装成功之后，执行`rvm list`查看已安装的ruby版本

可以用`rvm use 版本号 --default`来切换不同版本的ruby
其中default参数是设置默认的ruby版本，如果不加default参数，那在另一个终端中会选择默认的ruby版本，而不是当前的版本.

在使用`rvm use 版本号 --default`的时候可能出现以下错误

```
RVM is not a function, selecting rubies with 'rvm use ...' will not work.

You need to change your terminal emulator preferences to allow login shell.
Sometimes it is required to use `/bin/bash --login` as the command.
Please visit https://rvm.io/integration/gnome-terminal/ for an example.

```
此时不要慌~
解决方案:执行`bash --login`
我这里选择的版本时ruby2.2.6
##3.用gem安装rails
直接`gem install rails`
可以用`gem list`来查看rails版本


----------


##4.分布式版本控制工具git的使用（可忽略）
1.创建目录learngit
```
mkdir learngit
cd learngit
```
2.初始化git仓库

```
git init .
```
3.往仓库中添加文件readme

```
git add readme
```
提交到当前版本库

```
git commit -am"添加了readme"
```

```
git status查看版本更新信息


----------


```
#5创建rails项目

```
rails new _版本号_ 项目名
```
在这里创建一个名为learnRails的项目,其中`_版本号_`可以省略，如果省略就默认最高版本的rails

```
rails new _5.1.0_ learnRails
```
这样，我们的rails项目创建成功


----------


#6修改镜像文件---这一步可以略过，但以后的开发过程中会用到
为了提高效率，我们选择国内的镜像
修改工程目录下的gamFile文件，具体修改如下图
![修改GemFile文件中的gem镜像地址](http://img.blog.csdn.net/20170504190748205?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2VsYTA3MDg=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

修改完之后需要更新以下项目
在learnRails(工程目录)下执行`bundle install`


----------


#7运行rails项目
接下来我们就可以运行项目了

```
cd learnRails
```
```
rails s
```
如果你电脑上没有安装node.js环境，会报下图所示错误
![没有node.js环境下会报错](http://img.blog.csdn.net/20170504193326999?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2VsYTA3MDg=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

只需要安装node.js就可以解决了

```
sudo apt-get install nodejs
```
好了，配置rails环境真是不容易，有没有一种过五关斩六将神挡杀神佛挡杀佛的感觉。。。
到目前位置，环境配置完成，接下来嘛~就可以开启服务喽

```
rails s
```
这时候服务就开启了
![这里写图片描述](http://img.blog.csdn.net/20170504194304254?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvc2VsYTA3MDg=/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
接下来就可以打开浏览器进行访问了

在浏览器中输入0.0.0.0:3000
大功告成！