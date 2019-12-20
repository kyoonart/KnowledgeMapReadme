# Git的安装以及使用(MAC)-使用Homebrew版
## 1. Git的介绍
* Git(读音为/gɪt/。)是一个开源的分布式版本控制系统，可以有效、高速地处理从很小到非常大的项目版本管理。
* Git的功能特性（使用过程）如下
从一般开发者的角度来看，git有以下功能：
1、从服务器上克隆完整的Git仓库（包括代码和版本信息）到单机上。
2、在自己的机器上根据不同的开发目的，创建分支，修改代码。
3、在单机上自己创建的分支上提交代码。
4、在单机上合并分支。
5、把服务器上最新版的代码fetch下来，然后跟自己的主分支合并。
6、生成补丁（patch），把补丁发送给主开发者。
7、看主开发者的反馈，如果主开发者发现两个一般开发者之间有冲突（他们之间可以合作解决的冲突），就会要求他们先解决冲突，然后再由其中一个人提交。如果主开发者可以自己解决，或者没有冲突，就通过。
8、一般开发者之间解决冲突的方法，开发者之间可以使用pull 命令解决冲突，解决完冲突之后再向主开发者提交补丁。

##2. 安装步骤
有软件基础者，建议使用廖雪峰的教学版本。
https://www.liaoxuefeng.com/wiki/896043488029600
本教程较为简洁，可以快速实现git的安装及常规使用，适合没有软件基础及时间紧迫的初学者。
###2.1 安装Homebrew
网址如下，进入后使用命令行安装。

    https://brew.sh
###2.2 使用Homebrew安装Git
    brew install git
使用Homebrew方式安装，Git被安装在/usr/local/Cellar/git/2.21.0路径下。

安装完成后，使用如下命令查看Git版本：

    git --version
###2.3 配置GitHub中的SSH key值

####2.3.1 输入如下命令产生新的key

    ssh-keygen -t rsa -C "your_email@example.com"
####2.3.2 将SSH key添加到Github

登录到Github页面 -> 右上角Setttings -> SSH keys ->Add key
查看生成的key内容：

    cat ~/.ssh/id_rsa.pub
将以上内容复制到Key所对应的输入框中并保存。
####2.3.3 配置Git用户信息
    git config --global user.name   "你的名字或昵称"
    git config --global user.email  "你的邮箱"
####2.3.4 提交第一行代码
    git clone https://gitlab.testgu.com/ycyzharry/HelloGit.git 
    #将远程仓库克隆到本地
    git add . #将当前目录所有文件添加到git暂存区
    git commit -m "my first commit" #提交并备注提交信息
    git push origin master  #将本地提交推送到远程仓库
    
    

