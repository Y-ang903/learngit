# 安装git后的第一次操作

## 创建本地仓库-init-add-commit

[参考廖雪峰的官方网站教程]: https://www.liaoxuefeng.com/wiki/896043488029600/896827951938304	"git教程"

![image-20200724094304275](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724094304275.png)

1. mkdir
2. cd 跳到本地仓库目录下
3. git init 初始化一个git仓库，把这个目录变成git可以管理的仓库
4. git add <file> 往暂存区添加文件，**git add 只是往暂存区里添加，只是将文件放进来待提交的清单里，一次commit可以提交多个文件，所以可以多次add多个文件，一次commit把多个文件提交到本地仓库**
5. git commit -m “ 增加了什么什么”提交文件到本地仓库

> · **Workspace:工作区**
>
> **· Index/Stage :暂存区**
>
> **· Local Repository: 本地仓库**
>
> **· Remote Repository：远程仓库**
>
> 工作区、暂存区和本地仓库，逻辑上是本地计算机。当我们新建一个文件时，文件位于工作区，处于已修改（modified）状态，表明文件已进行了修改，但还没有提交保存；通过命令git add 将其添加到暂存区，文件是已暂存（staged）状态，表示把已修改的文件放到下次提交时要保存的清单中；***\*通过命令\*******\*git commit\*******\*将文件放入本地仓库\****，文件为已提交（commited）状态，表示该文件已经被安全地保存在本地数据库中，到这一步可以说是成功生成了一个新的版本。
> 远程仓库用来将本地仓库上传到网络，实现备份、共享和合作。我们选用开源中国的[码云Git@OSC](https://git.oschina.net/)作为代码托管平台。

------

## 错误

### 问题描述

提交的message信息，显示为乱码

![image-20200724101728216](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724101728216.png)

~~**解决办法**：三条命令~~

> 文件提交编码格式

> ```bash
> git config --global i18n.commitencoding utf-8
> ```

> 这个主要就是log输出的编码格式

> ```bash
> git config --global i18n.logoutputencoding utf-8
> ```

>
> 界面编码格式

> ```bash
> git config --global gui.encoding utf-8
> ```

[参考]: https://blog.csdn.net/qq_43356428/article/details/105192940

![image-20200724102547158](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724102547158.png)



![image-20200724102916900](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724102916900.png)

~~**另一办法**~~

> ```bash
> git config --global core.quotePath false
> ```

![image-20200724103124928](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724103124928.png)



**以上搜索的办法都是解决GitHub或者gitee码云上message显示为乱码的**

**不是解决git bash乱码的**

所以在GitHub上是正常的（因为是在连接GitHub之前操作的，所以不知道因果关系，万一不操作GitHub-message也是正常的呢）：

这里的message信息中文不是乱码，为什么在git bash反回的是乱码呢？

另外，md文档里的图片好像显示不出来

![image-20200724113202083](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724113202083.png)

### git bash中文乱码解决办法

1.在git bash命令右键选择-options

![image-20200724141308058](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724141308058.png)

2.按图操作。

![image-20200724172335346](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724172335346.png)

![image-20200724172431866](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724172431866.png)

![image-20200724173157195](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724173157195.png)

关闭当前gitbash，重新打开一个试试---还是不行

![image-20200724173517908](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724173517908.png)

改成GBK试试：

![image-20200724174059349](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724174059349.png)

**我要疯了**，，这又是什么操作111

![image-20200724174341944](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724174341944.png)

### 第二次push仍需在弹窗中输入GitHub的用户名和密码

**这是怎么回事？难道每次push都要吗？**

答：第三次push又不用了，观察后续吧

![image-20200724173533735](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724173533735.png)

# 连接GitHub

## 生成ssh key

[参考菜鸟教程]: https://www.runoob.com/git/git-remote-repo.html

## 测试是否连接成功

![image-20200724110839452](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724110839452.png)

## 在GitHub上新建仓库

> 目前，在GitHub上的这个`learngit`仓库还是空的，GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。
>
> 现在，我们根据GitHub的提示，在本地的`learngit`仓库下运行命令：（绿色框）

![image-20200724111637719](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724111637719.png)

## 将本地仓库push到GitHub

![image-20200724111838147](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724111838147.png)

![image-20200724112626468](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724112626468.png)

![image-20200724112608829](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724112608829.png)

![image-20200724112634639](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724112634639.png)

刷新下GitHub，会发现和本地仓库一样了

这里的message信息中文不是乱码，为什么在git bash反回的是乱码呢？

另外，md文档里的图片好像显示不出来

![image-20200724113202083](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724113202083.png)

# 小结

**第一次使用git、且关联GitHub操作比较麻烦，以后熟悉了，就轻松了**

**后续往GitHub push命令就简单了**

> 把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。
>
> 由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

> 从现在起，只要**<u>*本地作了提交*</u>**，就可以通过命令：
>
> ```bash
> $ git push origin master
> ```
>
> 把本地`master`分支的最新修改推送至GitHub，现在，你就拥有了真正的分布式版本库！

## 关于工作区、暂存区和版本库

[以下是菜鸟教程的解析]: https://www.runoob.com/git/git-workspace-index-repo.html

> # Git 工作区、暂存区和版本库b
>
> ------
>
> ## 基本概念
>
> 我们先来理解下Git 工作区、暂存区和版本库概念
>
> - **工作区：**就是你在电脑里能看到的目录。
> - **暂存区：**英文叫stage, 或index。一般存放在 ".git目录下" 下的index文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
> - **版本库：**工作区有一个隐藏目录.git，这个不算工作区，而是Git的版本库。
>
> 下面这个图展示了工作区、版本库中的暂存区和版本库之间的关系：
>
> ![img](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)
>
> 图中左侧为工作区，右侧为版本库。在版本库中标记为 "index" 的区域是暂存区（stage, index），标记为 "master" 的是 master 分支所代表的目录树。
>
> 图中我们可以看出此时 "HEAD" 实际是指向 master 分支的一个"游标"。所以图示的命令中出现 HEAD 的地方可以用 master 来替换。
>
> 图中的 objects 标识的区域为 Git 的对象库，实际位于 ".git/objects" 目录下，里面包含了创建的各种对象及内容。
>
> 当对工作区修改（或新增）的文件执行 "git add" 命令时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的ID被记录在暂存区的文件索引中。
>
> 当执行提交操作（git commit）时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。
>
> 当执行 "git reset HEAD" 命令时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。
>
> 当执行 "git rm --cached <file>" 命令时，会直接从暂存区删除文件，工作区则不做出改变。
>
> 当执行 "git checkout ." 或者 "git checkout -- <file>" 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动。
>
> 当执行 "git checkout HEAD ." 或者 "git checkout HEAD <file>" 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。

