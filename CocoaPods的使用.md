## CocoaPods的使用

[CocoaPods的使用(一) 安装](http://www.jianshu.com/p/44c894b69cf6)

### 一、CocoaPods安装前准备

CocoaPods使用Ruby语言编写而成。因此需要Ruby的环境, 庆幸的是OS X已经集成了Ruby环境。我们所需要的做的就是通过gem去安装CocoaPods即可。

首次安装CocoaPods之前，Ruby默认源在墙外, 因此我们需要修改下Ruby默认使用的源:

#### 1.查找Ruby的源

> gem source -l
> 
> 查询结果如下:
> 
> *** CURRENT SOURCES ***
> 
> [https://rubygems.org/](https://rubygems.org/)

查到的这个源是在墙外, 并且淘宝为我们提供了对应的源链接，因此我们需要先移除源链接, 再添加淘宝的源:

#### 2.移除Ruby的源

> gem source --remove [https://rubygems.org/](https://rubygems.org/)
> 
> 移除结果如下:
> 
> [https://rubygems.org/](https://rubygems.org/) removed from sources

#### 3.添加Ruby的源（最近做了修改，改为了https）

> gem source -a [https://ruby.taobao.org/](https://ruby.taobao.org/)
> 
> 添加结果如下:
> 
> [https://ruby.taobao.org/](https://ruby.taobao.org/) added to sources

对源的操作完成后，就可以安装CocoaPods了。

### 二、CocoaPods安装

运行以下命令, 即可实现CocoaPods的安装

> sudo gem install cocoapods

运行之后需要输入电脑的密码, 并且没有密码输入的位数提醒。输完密码就进行安装了，安装过程可能会很慢，耐心等待。

上述命令安装完成后，输入以下命令, 进行Cocoapods的建立

> pod setup

如果上述命令运行，皆无错误即完成了CocoaPods的安装！

#### CocoaPods安装过程中可能遇到的问题

xcrun找不到Xcode

> xcrun: error: active developer path
> ("/Applications/Xcode.app/Contents/Developer/") does not exist, use \ `xcode-select --switch path/to/Xcode.app` \ to specify the Xcode that you wish to use for command line developer tools (or see \ `man xcode-select` \)

运行以下命令, 让xcrun的运行路径找到对应的Xcode

> sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

### 三、CocoaPods的使用

#### 1.创建一个需要使用CocoaPods的工程, 并在工程目录下创建Podfile文件

> cd /Users/QCL/Desktop/CocoaPods
> 
> touch Podfile

创建完成如下图中, 会出现Podfile文件

![创建完Podfile](http://upload-images.jianshu.io/upload_images/791210-27a686d3b6fc7292.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

#### 2.编辑Podfile文件

右键Podfile，选择其他, 使用Xcode打开

![右键Podfile](http://upload-images.jianshu.io/upload_images/791210-9248352d46d2e152.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![选择Xcode](http://upload-images.jianshu.io/upload_images/791210-a66d10a9b31deac8.png?imageMogr2/auto-orient/strip%7CimageView2/2)

打开后, 即可输入你想导入的框架, 我们以AFNetworking为例:

> pod 'AFNetworking'

#### 3.执行cocoapods的安装操作

同样也是要在工程目录下
执行以下命令:

> pod install

等其执行完毕，即可完成第三方库的安装
其中还可以调用 `pod update` 方法, 也可以达到第三方库安装的目的, 并且会更新版本

在 `pod install` 或者 `pod update` 过程中会执行podspec索引的更新，需要等待很久，因此为了提升速度可以执行如下命令, 关掉索引的更新

> pod install --no-repo-update

并且在安装过程中, 我们不知道cocoapods做了什么, 还可以添加一个参数，用来提示我们，cococapods做了哪些操作

> pod install --verbose --no-repo-update

安装完成后, 工程目录下会多出一个白色的文件，如下图：

![通过CocoaPods安装完第三方后](http://upload-images.jianshu.io/upload_images/791210-0a7ec9372b872ee1.png?imageMogr2/auto-orient/strip%7CimageView2/2)

之后再打开工程，就用白色的工程文件打开，不再使用蓝色的工程文件。

打开之后，工程的目录层级如下图：

![打开工程后](http://upload-images.jianshu.io/upload_images/791210-9cf6000276be7b32.png?imageMogr2/auto-orient/strip%7CimageView2/2)

其中Pods工程目录是用来存放第三方库和配置文件的，上面的CocoaPods依旧是我们的工程文件, 在它之中，我们可以继续正常的编写代码。
为了验证是否安装成功, 我们可以在AppDelegate.m中引入我们所要使用的第三方库的头文件，如引入AFNetworking

> \#import <AFNetworking.h>

这里需要注意的是, 以后再引入第三方框架，要当系统框架去引入用\#import <框架头文件.h>

#### 4.pod搜索功能

CocoaPods上的大部分第三方框架均来自于GitHub, 因此数量也很庞大，记名字是很不明智的，因此，我们可以选择通过搜索来找到自己想要寻找的第三方框架。
pod search 框架关键字, 如下：

> pod search sdweb

通过搜索命令, 搜索到的内容如下图:

![搜索结果](http://upload-images.jianshu.io/upload_images/791210-51f8d5f85ef8445c.png?imageMogr2/auto-orient/strip%7CimageView2/2)

然后把你想要的框架的名字, 复制到Podfile文件中即可，Podfile文件中的第三方可以有多个, 需要几个，就填入几个，CocoaPods会全部帮你下载下来。

至此, 就完成了CocoaPods的创建和使用。

















