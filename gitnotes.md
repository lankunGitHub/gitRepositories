#git学习笔记
<br>
<br>
<br>

***
## 第一节  git初始化
### 创建版本库及提交
1. **git版本查看**
```
$git version  //查看git版本
```
2. **配置用户姓名和邮件地址(只需配置一次)**
```
$git config --global user.name "名字"
$git config --global user.email 邮箱
```
3. **可以为一些git命令取别名(非必要)**
```
$git config --global alias.st status  //git staus可以写成git st
$git config --global alias.ci commit  //git commit 可以写成git ci
$git config --global alias.co checkout //git checkout可以写成git co
$git config --global alias.br branch  //git branch可以写成git br
```
使用global参数表示只在本用户中配置了别名，如果将global换成system则所有用户都可以使用该配置，同时在配置时要用sudo,即系统的配置需要管理者权限，如
```
$sudo git config --system alias.st status
```
4. **可以在git命令输出中开启颜色显示**
```
$git config --global color.ui ture
```
5. **版本库的初始化**
首先创建一个空目录(空文件夹)作为工作目录，如在home中创建一个gittest,然后进入
```
~ $mkdir gittest
$cd gittest
```
然后在该目录中进行初始化
```
$git init
Initialized empty Git repository in 路径
```
我们发现，会有一个隐藏文件.git生成，这就是Git的版本库。.git所在的目录就成为工作区
6. **文件的提交**
首先我们在工作区创建一个文件,并写入内容
```
$touch welcome.txt
输入内容：1
```
然后就是我们的提交步骤
```
$git add welcome.txt
$git commit -m "Add welcome"
[master (root-commit) 09bfc1d] Add welcome.txt
 1 file changed, 1 insertion(+)
 create mode 100644 welcome.txt
```
-m参数表示提交说明，也即是对于我们提交的注释
命令输出的第一行说明此次提交是在master分支上，root-commit说明是该分支上的第一个提交，提交的ID为09bfc1d
命令输出的第二行说明这次提交改变了一个文件，有一行插入
命令输出第三行说明提交了welcome.txt文件
<br>

### 为什么工作区根目录下有一个.git目录
1. 这使得版本控制操作可以在本地完成，因为.git中包含储存版本控制的所有信息，使用者在本地就可以完成而无需依赖远程服务器，且安全属性更高，因为只需保护好这一个文件就可以防止安全泄漏
### git的相关操作一定要在根目录下执行吗
git在子目录执行某个操作的时候，会在工作区目录中依次向上递归查找.git，也即是说在子目录下是可以使用git相关操作的。但同时，在非git工作区下执行git命令会因找不到.git报错
### git config命令的各参数有何区别
```
在git工作区目录
$git config -e
```
打开.git/config文件
```
$git config -e --global
```
打开户主目录下的.gitconfig文件，即全局配置文件进行编辑
```
$git config -e system
```
打开系统级配置文件进行编辑
其中版本库级别配置文件优先级最高，依次优先级下降，同时，高优先级的文件能覆盖低优先级文件的配置环境