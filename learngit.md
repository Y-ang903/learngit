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

提交的message信息，显示为乱码

![image-20200724101728216](C:\Users\26369\AppData\Roaming\Typora\typora-user-images\image-20200724101728216.png)

**解决办法**：三条命令

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







[以下是菜鸟教程的解析]: https://www.runoob.com/git/git-workspace-index-repo.html

> # Git 工作区、暂存区和版本库
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

