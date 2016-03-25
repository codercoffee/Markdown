## Git教程

[廖雪峰的官方网站](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)

***

### 1. 安装Git

* 首先，你可以试着输入 `git` ，看看系统有没有安装Git;
* 安装完成后，还需要最后一步设置，在命令行输入：

```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```
因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。

注意 `git config` 命令的 `--global` 参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

***
***

### 2. 创建版本库

版本库又名仓库，英文名repository

* 选择一个合适的地方，创建一个空目录，然后用 `cd` 命令进入到该目录
* 第二步，通过 `git init` 命令把这个目录变成Git可以管理的仓库：

```
git init
Initialized empty Git repository in /Users/wk/Desktop/learngit/.git/
```

##### 把文件添加到版本库

编写一个readme.txt文件，内容如下：

```
Git is a version control system.
Git is free software.
```

一定要放到learngit目录下（子目录也行），因为这是一个Git仓库，放到其他地方Git再厉害也找不到这个文件。

* 第一步，用命令 `git add` 告诉Git，把文件添加到仓库：

`
git add readme.txt
`
 
执行上面的命令，没有任何显示，这就对了，Unix的哲学是“没有消息就是好消息”，说明添加成功。

* 第二步，用命令 `git commit` 告诉Git，把文件提交到仓库：

`
git commit -m "wrote a readme file"
`

 `-m` 后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。
 
##### 小结

* **初始化一个Git仓库，使用 `git init` 命令。**
* **添加文件到Git仓库，分两步：**

	* **第一步，使用命令 `git add <file>` ，注意，可反复多次使用，添加多个文件；**
	* **第二步，使用命令 `git commit` ，完成。**

***
***

### 3. 时光穿梭机

##### 小结

* **要随时掌握工作区的状态，使用git status命令。**
* **如果 `git status` 告诉你有文件被修改过，用 `git diff` 可以查看修改内容。**


#### 版本回退
 
##### 小结

现在总结一下：

* **HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。**
* **穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。**
* **要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。**

#### 工作区和暂存区

##### 小结

暂存区是Git非常重要的概念，弄明白了暂存区，就弄明白了Git的很多操作到底干了什么。

没弄明白暂存区是怎么回事的童鞋，请向上滚动页面，再看一次。

