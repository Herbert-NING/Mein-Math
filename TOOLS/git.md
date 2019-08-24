# Git 的简略使用笔记

*<https://www.liaoxuefeng.com/>*  
官方文档可以查询:*<https://git-scm.com/doc>*.  
其他可查阅信息:*<http://rogerdudler.github.io/git-guide/>*  
*<https://www.git-tower.com/learn/?utm_source=Tower+Blog&utm_medium=cheat+sheet+pdf&utm_content=german+version&utm_campaign=Tower+website>*  

>本文档只为我使用git的时候的方便查询而抄写.  
本大部分来自廖雪峰的个人主页中git教程.  
为求精简在部分章节为了**省略\删去**了部分内容.  
NING  
14/08/2019

```text
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

---

## 目录

| 序号  |                                        内容                                        |
| :---: | :--------------------------------------------------------------------------------: |
|   0   |                            [介绍](#%e4%bb%8b%e7%bb%8d)                             |
|   1   |                         [安装git](#%e5%ae%89%e8%a3%85git)                          |
|   2   |            [创建版本库](#%e5%88%9b%e5%bb%ba%e7%89%88%e6%9c%ac%e5%ba%93)            |
|   3   |            [时光穿梭机](#%e6%97%b6%e5%85%89%e7%a9%bf%e6%a2%ad%e6%9c%ba)            |
|   4   |                 [版本回退](#%e7%89%88%e6%9c%ac%e5%9b%9e%e9%80%80)                  |
|   5   | [工作区与暂存区](#%e5%b7%a5%e4%bd%9c%e5%8c%ba%e5%92%8c%e6%9a%82%e5%ad%98%e5%8c%ba) |
|   6   |                 [修改管理](#%e7%ae%a1%e7%90%86%e4%bf%ae%e6%94%b9)                  |
|   7   |                 [撤销修改](#%e6%92%a4%e9%94%80%e4%bf%ae%e6%94%b9)                  |
|   8   |                 [删除文件](#%e5%88%a0%e9%99%a4%e6%96%87%e4%bb%b6)                  |
|   9   |                 [远程仓库](#%e8%bf%9c%e7%a8%8b%e4%bb%93%e5%ba%93)                  |
|  10   |      [从远程库克隆](#%e4%bb%8e%e8%bf%9c%e7%a8%8b%e5%ba%93%e5%85%8b%e9%9a%86)       |
|  11   |                 [分支管理](#%e5%88%86%e6%94%af%e7%ae%a1%e7%90%86)                  |
|  12   | [创建与合并分支](#%e5%88%9b%e5%bb%ba%e4%b8%8e%e5%90%88%e5%b9%b6%e5%88%86%e6%94%af) |
|  13   |                 [解决冲突](#%e8%a7%a3%e5%86%b3%e5%86%b2%e7%aa%81)                  |
|  14   |      [分支管理策略](#%e5%88%86%e6%94%af%e7%ae%a1%e7%90%86%e7%ad%96%e7%95%a5)       |
|  15   |                         [Bug分支](#bug%e5%88%86%e6%94%af)                          |
|  16   |                     [Feature分支](#feature%e5%88%86%e6%94%af)                      |
|  17   |                 [多人协作](#%e5%a4%9a%e4%ba%ba%e5%8d%8f%e4%bd%9c)                  |
|  18   |                                 [Rebase](#rebase)                                  |
|  19   |                 [标签管理](#%e6%a0%87%e7%ad%be%e7%ae%a1%e7%90%86)                  |
|  20   |                 [创建标签](#%e5%88%9b%e5%bb%ba%e6%a0%87%e7%ad%be)                  |
|  21   |                 [标签操作](#%e6%93%8d%e4%bd%9c%e6%a0%87%e7%ad%be)                  |
|  22   |      [忽略特殊文件](#%e5%bf%bd%e7%95%a5%e7%89%b9%e6%ae%8a%e6%96%87%e4%bb%b6)       |
|   n   |                 [常见命令](#%e5%b8%b8%e8%a7%81%e5%91%bd%e4%bb%a4)                  |

## 介绍

Git是目前世界上最先进的分布式版本控制系统（没有之一）.  

这个软件用起来就应该像这个样子,能记录每次文件的改动:  

| 版本 | 文件名      | 用户 | 说明                   | 日期       |
| ---- | ----------- | ---- | ---------------------- | ---------- |
| 1    | service.doc | 张三 | 删除了软件服务条款5    | 7/12 10:38 |
| 2    | service.doc | 张三 | 增加了License人数限制  | 7/12 18:09 |
| 3    | service.doc | 李四 | 财务部门调整了合同金额 | 7/13 9:51  |
| 4    | service.doc | 张三 | 延长了免费升级周期     | 7/14 15:17 |

这样,你就结束了手动管理多个"版本"的史前时代,进入到版本控制的20世纪.

## 安装git

在Windows上使用Git,可以从Git官网直接下载安装程序(网速慢的话可以用迅雷).  
安装完成后,在开始菜单里找到"Git"->"Git Bash",蹦出一个类似命令行窗口的东西,就说明Git安装成功!  

## 创建版本库

`git init`设置为版本库 (**repository**).  

**使用windows:** 请不要使用windows自带的记事本.原因是Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件,他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符,你会遇到很多不可思议的问题,比如,网页第一行可能会显示一个"?",明明正确的程序一编译就报语法错误,等等,都是由记事本的弱智行为带来的.建议你下载Notepad++代替记事本,不但功能强大,而且免费!记得把Notepad++的默认编码设置为UTF-8 without BOM即可.

言归正传, 可以编写一个`readme.txt`文件.

```nothing
Git is a version control system.
Git is free software.
```

然后必须将之放到仓库(或子目录)下,然后把一个文件放到Git仓库只需要两步.  

第一步,用命令git add告诉Git,把文件添加到仓库:  

```cmd
git add readme.txt
```

执行上面的命令,没有任何显示,这就对了,Unix的哲学是"没有消息就是好消息",说明添加成功.  

第二步,用命令`git commit`告诉Git,把文件提交到仓库:

```cmd
$ git commit -m "wrote a readme file"
[master (root-commit) eaadf4e] wrote a readme file
 1 file changed, 2 insertions(+)
 create mode 100644 readme.txt
```

简单解释一下`git commit`命令,`-m`后面输入的是本次提交的说明,可以输入任意内容,当然最好是有意义的,这样你就能从历史记录里方便地找到改动记录.

同时`commit`可以一次提交很多文件,所以你可以多次`add`不同的文件,比如:

```cmd
git add file1.txt
git add file2.txt file3.txt
git commit -m "add 3 files."
```

**小结**  
初始化一个`Git`仓库,使用`git init`命令.  
添加文件到`Git`仓库,分两步:  

1. 使用命令`git add <file>`,注意,可反复多次使用z添加多个文件;  
2. 使用命令`git commit -m <message>`,完成.  

## 时光穿梭机

我们已经成功地添加并提交了一个`readme.txt`文件,现在,是时候继续工作了,于是,我们继续修改`readme.txt`文件,改成如下内容:

```text
Git is a distributed version control system.
Git is free software.
```

现在,运行`git status`命令看看结果:

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

     modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态,上面的命令输出告诉我们,`readme.txt`被修改过了,但还没有准备提交的修改.

在这里Git只告诉了我们`readme.txt`被修改了,如果想查看具体修改了什么内容,可以用`git diff`:

```shell
$ git diff readme.txt  
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
 ```

`git diff`(difference),显示的格式正是Unix通用的diff格式,可以从上面的命令输出看到,我们在第一行添加了一个`distributed`单词.

知道了对`readme.txt`作了什么修改后,就可以把他提交了,提交修改和提交新文件是一样的两步,第一步是`git add`:

```shell
git add readme.txt
```

同样没有任何输出.在执行第二步`git commit`之前,我们再运行`git status`看看当前仓库的状态:

```shell
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

     modified:   readme.txt
```

`git status`告诉我们,将要被提交的修改包括`readme.txt`,下一步,就可以放心地提交了:

```shell
$ git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
```

提交后,我们再用git status命令看看仓库的当前状态:  

```shell
$ git status
On branch master
nothing to commit, working tree clean
```

**小结**:

1. 要随时掌握工作区的状态,使用`git status`命令.
2. 如果`git status`告诉你有文件被修改过,用`git diff`可以查看修改内容.

### 版本回退

现在,你已经学会了修改文件,然后把修改提交到Git版本库,现在,再练习一次,修改`readme.txt`文件如下:  

```shell
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

像这样,你不断对文件进行修改,然后不断提交修改到版本库里,每当你觉得文件修改到一定程度的时候,就可以"保存一个快照",这个快照在Git中被称为`commit`.一旦你把文件改乱了,或者误删了文件,还可以从最近的一个`commit`恢复,然后继续工作,而不是把几个月的工作成果全部丢失.

然后尝试提交:  

```shell
$ git add readme.txt
$ git commit -m "append GPL"
[master 1094adb] append GPL
 1 file changed, 1 insertion(+), 1 deletion(-)
 ```

现在,我们回顾一下`readme.txt`文件一共有几个版本被提交到Git仓库里了:  

版本1:wrote a readme file  

```shell
Git is a version control system.
Git is free software.
```

版本2:add distributed  

```shell
Git is a distributed version control system.
Git is free software.
```

版本3:append GPL  

```shell
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

在Git中,我们可以用`git log`命令查看历史记录:

```shell
$ git log
commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -> master)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

commit e475afc93c209a690c39c13a46716e8fa000c366
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

`git log`命令显示从最近到最远的提交日志,我们可以看到3次提交,最近的一次是`append GPL`,上一次是`add distributed`,最早的一次是`wrote a readme file`.  

需要友情提示的是,你看到的一大串类似`1094adb...`的是`commit id`（版本号）,和SVN不一样,Git的`commit id`不是1,2,3……递增的数字,而是一个`SHA1`计算出来的一个非常大的数字,用十六进制表示,而且你看到的`commit id`和我的肯定不一样,因为Git是分布式的版本控制系统,还要研究多人在同一个版本库里工作,如果大家都用1,2,3……作为版本号,那肯定就冲突了.

好了,现在我们启动时光穿梭机,准备把`readme.txt`回退到上一个版本,也就是`add distributed`的那个版本,怎么做呢?  

首先,Git必须知道当前版本是哪个版本,在Git中,用`HEAD`表示当前版本,也就是最新的提交`1094adb...`,上一个版本就是`HEAD^`,上上一个版本就是`HEAD^^`,当然往上100个版本写100个^比较容易数不过来,所以写成`HEAD~100`.  

现在,我们要把当前版本`append GPL`回退到上一个版本`add distributed`,就可以使用`git reset`命令:  

```shell
$ git reset --hard HEAD^
HEAD is now at e475afc add distributed
```

看看`readme.txt`的内容是不是版本`add distributed`:

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software.
```

果然被还原了.  

还可以继续回退到上一个版本wrote a readme file,我们可以再用git log再看看现在版本库的状态:  

```shell
$ git log
commit e475afc93c209a690c39c13a46716e8fa000c366 (HEAD -> master)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

最新的那个版本`append GPL`已经看不到了!如果要返回`append GPL`.只要上面的命令行窗口还没有被关掉,你就可以找到那个`append GPL`的`commit id`是`1094adb...`,于是就可以指定回到未来的某个版本:

```shell
$ git reset --hard 1094a
HEAD is now at 83b0afe append GPL
```

版本号没必要写全,前几位就可以了.  
再小心翼翼地看看`readme.txt`的内容:

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
```

Git的版本回退速度非常快,因为Git在内部有个指向当前版本的`HEAD`指针,当你回退版本的时候,Git仅仅是把HEAD从指向`append GPL`,改为指向`add distributed`.

但是如果已经关掉了窗口还想回到`append GPL`,那必须找到它的`commit id`. Git提供了一个命令`git reflog`用来记录你的每一次命令:  

```shell
$ git reflog
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file
```

这样也可找到所有的`commit id`.

### 工作区和暂存区

Git和其他版本控制系统如SVN的一个不同之处就是有暂存区的概念.  

**工作区（Working Directory）**:就是你在电脑里能看到的目录.

**版本库（Repository）**:
工作区有一个隐藏目录`.git`,这个不算工作区,而是Git的版本库.
Git的版本库里存了很多东西,其中最重要的就是称为`stage`（或者叫`index`）的暂存区,还有Git为我们自动创建的第一个分支`master`,以及指向`master`的一个指针叫`HEAD`.

前面讲了我们把文件往Git版本库里添加的时候,是分两步执行的:  

第一步是用`git add`把文件添加进去,实际上就是把文件修改添加到暂存区;  

第二步是用`git commit`提交更改,实际上就是把暂存区的所有内容提交到当前分支.  

因为我们创建Git版本库时,Git自动为我们创建了唯一一个`master`分支,所以,现在,`git commit`就是往`master`分支上提交更改.  

你可以简单理解为,需要提交的文件修改通通放到暂存区,然后,一次性提交暂存区的所有修改.  

俗话说,实践出真知.现在,我们再练习一遍,先对`readme.txt`做个修改,比如加上一行内容:  

```text
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
```

然后,在工作区新增一个`LICENSE.txt`文本文件.  

先用`git status`查看一下状态:  

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

     modified:   readme.txt

Untracked files:
  (use "git add <file>..." to include in what will be committed)

     LICENSE

no changes added to commit (use "git add" and/or "git commit -a")
```

Git非常清楚地告诉我们,`readme.txt`被修改了,而`LICENSE`还从来没有被添加过,所以它的状态是`Untracked`.  

现在,使用两次命令`git add`,把`readme.txt`和`LICENSE`都添加后,用`git status`再查看一下:

```shell
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

     new file:   LICENSE
     modified:   readme.txt
```

所以,`git add`命令实际上就是把要提交的所有修改放到暂存区（`Stage`）,然后,执行`git commit`就可以一次性把暂存区的所有修改提交到分支.

```shell
$ git commit -m "understand how stage works"
[master e43a48b] understand how stage works
 2 files changed, 2 insertions(+)
 create mode 100644 LICENSE
```

一旦提交后,如果你又没有对工作区做任何修改,那么工作区就是"干净"的:  

```shell
$ git status
On branch master
nothing to commit, working tree clean
```

**小结**:
暂存区是Git非常重要的概念,弄明白了暂存区,就弄明白了Git的很多操作到底干了什么.

### 管理修改

现在,假定你已经完全掌握了暂存区的概念.下面,我们要讨论的就是,为什么Git比其他版本控制系统设计得优秀,因为Git跟踪并管理的是修改,而非文件.  

第一步,对`readme.txt`做一个修改,比如加一行内容:

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes.
```

然后,添加:  

```shell
$ git add readme.txt
$ git status
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#       modified:   readme.txt
#
```

然后,再修改readme.txt:  

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
```

提交:  

```shell
$ git commit -m "git tracks changes"
[master 519219b] git tracks changes
 1 file changed, 1 insertion(+)
```

提交后,再看看状态:  

```shell  
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

     modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

咦,怎么第二次的修改没有被提交?  

别激动,我们回顾一下操作过程:  

第一次修改 -> git add -> 第二次修改 -> git commit  

你看,我们前面讲了,Git管理的是修改,当你用`git add`命令后,在工作区的第一次修改被放入暂存区,准备提交,但是,在工作区的第二次修改并没有放入暂存区,所以,`git commit`只负责把暂存区的修改提交了,也就是第一次的修改被提交了,第二次的修改不会被提交.
提交后,用`git diff HEAD -- readme.txt`命令可以查看工作区和版本库里面最新版本的区别:  

```shell
$ git diff HEAD -- readme.txt  
diff --git a/readme.txt b/readme.txt
index 76d770f..a9c5755 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,4 +1,4 @@
 Git is a distributed version control system.
 Git is free software distributed under the GPL.
 Git has a mutable index called stage.
-Git tracks changes.
+Git tracks changes of files.
```

可见,第二次修改确实没有被提交.  

那怎么提交第二次修改呢?你可以继续`git add`再`git commit`,也可以别着急提交第一次修改,先`git add`第二次修改,再`git commit`,就相当于把两次修改合并后一块提交了:  
第一次修改 -> `git add` -> 第二次修改 -> `git add` -> `git commit`  

**小结**:
现在,你又理解了Git是如何跟踪修改的,每次修改,如果不用`git add`到暂存区,那就不会加入到`commit`中.

### 撤销修改

自然,你是不会犯错的.不过现在是凌晨两点,你正在赶一份工作报告,你在readme.txt中添加了一行:  

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
My stupid boss still prefers SVN.
```

在你准备提交前,一杯咖啡起了作用,你猛然发现了stupid boss可能会让你丢掉这个月的奖金!  

既然错误发现得很及时,就可以很容易地纠正它.你可以删掉最后一行,手动把文件恢复到上一个版本的状态.如果用`git status`查看一下:  

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

你可以发现,Git会告诉你,`git checkout -- file`可以丢弃工作区的修改:  

`$ git checkout -- readme.txt`  

命令`git checkout -- readme.txt`意思就是,把`readme.txt`文件在工作区的修改全部撤销,这里有两种情况:  

一种是`readme.txt`自修改后还没有被放到暂存区,现在,撤销修改就回到和版本库一模一样的状态;  

一种是`readme.txt`已经添加到暂存区后,又作了修改,现在,撤销修改就回到添加到暂存区后的状态.  

总之,就是让这个文件回到最近一次`git commit`或`git add`时的状态.  

现在,看看`readme.txt`的文件内容:  

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.  
```

文件内容果然复原了.  

`git checkout -- file`命令中的--很重要,没有--,就变成了"切换到另一个分支"的命令,我们在后面的分支管理中会再次遇到`git checkout`命令.  

现在假定是凌晨3点,你不但写了一些胡话,还git add到暂存区了:  

```shell
$ cat readme.txt
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
My stupid boss still prefers SVN.

$ git add readme.txt
```

庆幸的是,在commit之前,你发现了这个问题.用git status查看一下,修改只是添加到了暂存区,还没有提交:

```shell
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  modified:   readme.txt  
```

Git同样告诉我们,用命令`git reset HEAD <file>`可以把暂存区的修改撤销掉（**unstage**）,重新放回工作区:  

```shell
$ git reset HEAD readme.txt
Unstaged changes after reset:
M     readme.txt
```

`git reset`命令既可以回退版本,也可以把暂存区的修改回退到工作区.当我们用`HEAD`时,表示最新的版本.  

再用git status查看一下,现在暂存区是干净的,工作区有修改:  

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   readme.txt
```

然后可以丢弃工作区的修改.

```shell
$ git checkout -- readme.txt

$ git status
On branch master
nothing to commit, working tree clean
```

**小结**:  
又到了小结时间.  
场景1:当你改乱了工作区某个文件的内容,想直接丢弃工作区的修改时,用命令git checkout -- file.  
场景2:当你不但改乱了工作区某个文件的内容,还添加到了暂存区时,想丢弃修改,分两步,第一步用命令`git reset HEAD <file>`,就回到了场景1,第二步按场景1操作.  
场景3:已经提交了不合适的修改到版本库时,想要撤销本次提交,参考版本回退一节,不过前提是没有推送到远程库.  

### 删除文件

在Git中,删除也是一个修改操作,我们实战一下,先添加一个新文件`test.txt`到Git并且提交:  

```shell
$ git add test.txt

$ git commit -m "add test.txt"
[master b84166e] add test.txt
 1 file changed, 1 insertion(+)
 create mode 100644 test.txt
```

一般情况下,你通常直接在文件管理器中把没用的文件删了,或者用rm命令删了:  

```shell
rm test.txt
```

这个时候,Git知道你删除了文件,因此,工作区和版本库就不一致了,git status命令会立刻告诉你哪些文件被删除了:  

```shell
$ git status
On branch master
Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  deleted:    test.txt

no changes added to commit (use "git add" and/or "git commit -a")

```

现在你有两个选择,一是确实要从版本库中删除该文件,那就用命令`git rm`删掉,并且`git commit`:  

```shell
$ git rm test.txt
rm 'test.txt'

$ git commit -m "remove test.txt"
[master d46f35e] remove test.txt
 1 file changed, 1 deletion(-)
 delete mode 100644 test.txt
```

现在,文件就从版本库中被删除了.

另一种情况是删错了,因为版本库里还有呢,所以可以很轻松地把误删的文件恢复到最新版本:  

```shell
git checkout -- test.txt  
```

`git checkout`其实是用版本库里的版本替换工作区的版本,无论工作区是修改还是删除,都可以"一键还原".

git就暂时只到这里了

---

## 远程仓库

Github:  
你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的,所以,需要一点设置：  

第1步：创建SSH Key.在用户主目录下,看看有没有.ssh目录,如果有,再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件,如果已经有了,可直接跳到下一步.如果没有,打开Shell（Windows下打开Git Bash）,创建SSH Key：  

```shell
ssh-keygen -t rsa -C "youremail@example.com"
```

如果一切顺利的话,可以在用户主目录里找到.ssh目录,里面有id_rsa和id_rsa.pub两个文件,这两个就是SSH Key的秘钥对,id_rsa是私钥,不能泄露出去,id_rsa.pub是公钥,可以放心地告诉任何人.  

第2步：登陆GitHub,打开"Account settings","SSH Keys"页面：  

然后,点"Add SSH Key",填上任意Title,在Key文本框里粘贴id_rsa.pub文件的内容：  

点"Add Key",你就应该看到已经添加的Key：  

GitHub需要SSH Key用以识别出你推送的提交确实是你推送的,Git支持SSH协议,GitHub只要知道了你的公钥,就可以确认只有你自己才能推送.  

**小结**:  
"有了远程仓库,妈妈再也不用担心我的硬盘了."——Git点读机  

### 添加远程库

现在的情景是,你已经在本地创建了一个Git仓库后,又想在GitHub创建一个Git仓库,并且让这两个仓库进行远程同步:

首先,登陆GitHub,然后,在右上角找到`"Create a new repo"`按钮,创建一个新的仓库：  

在`Repository name`填入`learngit`,其他保持默认设置,点击`"Create repository"`按钮,就成功地创建了一个新的Git仓库：  

目前,在GitHub上的这个`learngit`仓库还是空的,GitHub告诉我们,可以从这个仓库克隆出新的仓库,也可以把一个已有的本地仓库与之关联,然后,把本地仓库的内容推送到GitHub仓库.  

现在,我们根据GitHub的提示,在本地的`learngit`仓库下运行命令：  

```shell
git remote add origin git@github.com:michaelliao/learngit.git  
```

添加后,远程库的名字就是`origin`,这是Git默认的叫法,也可以改成别的,但是`origin`这个名字一看就知道是远程库.  

下一步,就可以把本地库的所有内容推送到远程库上：  

```shell
$ git push -u origin master
Counting objects: 20, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (15/15), done.
Writing objects: 100% (20/20), 1.64 KiB | 560.00 KiB/s, done.
Total 20 (delta 5), reused 0 (delta 0)
remote: Resolving deltas: 100% (5/5), done.
To github.com:michaelliao/learngit.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
```

把本地库的内容推送到远程,用`git push`命令,实际上是把当前分支`master`推送到远程.  

由于远程库是空的,我们第一次推送`master`分支时,加上了`-u`参数,Git不但会把本地的`master`分支内容推送的远程新的`master`分支,还会把本地的`master`分支和远程的`master`分支关联起来,在以后的推送或者拉取时就可以简化命令.  

推送成功后,可以立刻在GitHub页面中看到远程库的内容已经和本地一模一样：  

从现在起,只要本地作了提交,就可以通过命令：  

```shell
git push origin master  
```

把本地`master`分支的最新修改推送至GitHub,现在,你就拥有了真正的分布式版本库!  

**SSH警告**:  
当你第一次使用Git的clone或者push命令连接GitHub时,会得到一个警告：  

```shell
The authenticity of host 'github.com (xx.xx.xx.xx)' can't be established.
RSA key fingerprint is xx.xx.xx.xx.xx.
Are you sure you want to continue connecting (yes/no)?  
```

这是因为Git使用SSH连接,而SSH连接在第一次验证GitHub服务器的Key时,需要你确认GitHub的Key的指纹信息是否真的来自GitHub的服务器,输入yes回车即可.  

Git会输出一个警告,告诉你已经把GitHub的Key添加到本机的一个信任列表里了：  

```shell
Warning: Permanently added 'github.com' (RSA) to the list of known hosts.  
```

这个警告只会出现一次,后面的操作就不会有任何警告了.  

如果你实在担心有人冒充GitHub服务器,输入yes前可以对照GitHub的RSA Key的[指纹信息](https://help.github.com/en/articles/githubs-ssh-key-fingerprints)是否与SSH连接给出的一致.  

**小结**:

要关联一个远程库,使用命令`git remote add origin git@server-name:path/repo-name.git`;  

关联后,使用命令`git push -u origin master`第一次推送`master`分支的所有内容;
此后,每次本地提交后,只要有必要,就可以使用命令`git push origin master`推送最新修改;  

分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程库的存在,也就是有没有联网都可以正常工作.  

### 从远程库克隆

先准备好要克隆的远程库, 比如`git@github.com:zmx0142857/math-note.git`

现在,远程库已经准备好了,下一步是用命令git clone克隆一个本地库：

```shell
$ git clone git@github.com:zmx0142857/math-note.git
Cloning into 'gitskills'...
remote: Counting objects: 3, done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 3
Receiving objects: 100% (3/3), done.
```

注意把Git库的地址换成你自己的,然后进入gitskills目录看看,已经有README.md文件了：

```shell
cd math-note
ls
```

如果有多个人协作开发,那么每个人各自从远程克隆一份就可以了.  

*注意*:在国内,不要使用`https`协议,请使用`ssh`协议

**小结**:  
要克隆一个仓库,首先必须知道仓库的地址,然后使用`git clone`命令克隆.  
Git支持多种协议,通过`ssh`支持的原生`git`协议速度最快.  

## 分支管理

分支就是科幻电影里面的平行宇宙,当你正在电脑前努力学习Git的时候,另一个你正在另一个平行宇宙里努力学习SVN.  
如果两个平行宇宙互不干扰,那对现在的你也没啥影响.不过,在某个时间点,两个平行宇宙合并了,结果,你既学会了Git又学会了SVN!  

### 创建与合并分支

在版本回退里,你已经知道,每次提交,Git都把它们串成一条时间线,这条时间线就是一个分支.截止到目前,只有一条时间线,在Git里,这个分支叫主分支,即master分支.HEAD严格来说不是指向提交,而是指向master,master才是指向提交的,所以,HEAD指向的就是当前分支.  

一开始的时候,master分支是一条线,Git用master指向最新的提交,再用HEAD指向master,就能确定当前分支,以及当前分支的提交.  

每次提交,master分支都会向前移动一步,这样,随着你不断提交,master分支的线也越来越长.  

当我们创建新的分支,例如dev时,Git新建了一个指针叫dev,指向master相同的提交,再把HEAD指向dev,就表示当前分支在dev上.  

你看,Git创建一个分支很快,因为除了增加一个dev指针,改改HEAD的指向,工作区的文件都没有任何变化!  

不过,从现在开始,对工作区的修改和提交就是针对dev分支了,比如新提交一次后,dev指针往前移动一步,而master指针不变.  

假如我们在dev上的工作完成了,就可以把dev合并到master上.Git怎么合并呢?最简单的方法,就是直接把master指向dev的当前提交,就完成了合并：  

所以Git合并分支也很快!就改改指针,工作区内容也不变!  

合并完分支后,甚至可以删除dev分支.删除dev分支就是把dev指针给删掉,删掉后,我们就剩下了一条master分支：  

真是太神奇了,你看得出来有些提交是通过分支完成的吗?  

下面开始实战.  

首先,我们创建`dev`分支,然后切换到`dev`分支：  

```shell
$ git checkout -b dev
Switched to a new branch 'dev'
```

`git checkout`命令加上`-b`参数表示创建并切换,相当于以下两条命令：  

```shell
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

然后,用git branch命令查看当前分支：  

```shell
$ git branch
* dev
  master

```

`git branch`命令会列出所有分支,当前分支前面会标一个`*`号.  
然后,我们就可以在`dev`分支上正常提交,比如对`readme.txt`做个修改,加上一行：  

```shell
Creating a new branch is quick.
```

然后提交：  

```shell
$ git add readme.txt
$ git commit -m "branch test"
[dev b17d20e] branch test
 1 file changed, 1 insertion(+)
```

现在,`dev`分支的工作完成,我们就可以切换回`master`分支：  

```shell
$ git checkout master
Switched to branch master
```

切换回`master`分支后,再查看一个`readme.txt`文件,刚才添加的内容不见了!因为那个提交是在`dev`分支上,而`master`分支此刻的提交点并没有变：

现在,我们把`dev`分支的工作成果合并到`master`分支上：

```shell
$ git merge dev
Updating d46f35e..b17d20e
Fast-forward
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
```

`git merge`命令用于合并指定分支到当前分支.合并后,再查看`readme.txt`的内容,就可以看到,和`dev`分支的最新提交是完全一样的.  
注意到上面的Fast-forward信息,Git告诉我们,这次合并是"快进模式",也就是直接把`master`指向`dev`的当前提交,所以合并速度非常快.  
当然,也不是每次合并都能Fast-forward,我们后面会讲其他方式的合并.  
合并完成后,就可以放心地删除`dev`分支了：  

```shell
$ git branch -d dev
Deleted branch dev (was b17d20e).
```

删除后,查看branch,就只剩下master分支了：  

```shell
$ git branch
* master
```

因为创建、合并和删除分支非常快,所以Git鼓励你使用分支完成某个任务,合并后再删掉分支,这和直接在`master`分支上工作效果是一样的,但过程更安全.

**小结**:  

Git鼓励大量使用分支：  

查看分支：`git branch`
  
创建分支：`git branch <name>`  
  
切换分支：`git checkout <name>`  

创建+切换分支：`git checkout -b <name>`  

合并某分支到当前分支：`git merge <name>`  

删除分支：`git branch -d <name>`  

### 解决冲突

人生不如意之事十之八九,合并分支往往也不是一帆风顺的.  
准备新的`feature1`分支,继续我们的新分支开发：  

```shell
$ git checkout -b feature1
Switched to a new branch 'feature1'
```

修改`readme.txt`最后一行,改为：

```text
Creating a new branch is quick AND simple.
```

在`feature1`分支上提交：

```shell
$ git add readme.txt

$ git commit -m "AND simple"
[feature1 14096d0] AND simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

切换到`master`分支：  

```shell
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)
```

Git还会自动提示我们当前`master`分支比远程的`master`分支要超前1个提交.  
在master分支上把`readme.txt`文件的最后一行改为：  

```shell
Creating a new branch is quick & simple.
```

提交：

```shell
$ git add readme.txt  
$ git commit -m "& simple"
[master 5dc6824] & simple
 1 file changed, 1 insertion(+), 1 deletion(-)
```

现在,`master`分支和`feature1`分支各自都分别有新的提交,变成了这样：  

这种情况下,Git无法执行"快速合并",只能试图把各自的修改合并起来,但这种合并就可能会有冲突,我们试试看：  

```shell
$ git merge feature1
Auto-merging readme.txt
CONFLICT (content): Merge conflict in readme.txt
Automatic merge failed; fix conflicts and then commit the result.
```

果然冲突了!Git告诉我们,`readme.txt`文件存在冲突,必须手动解决冲突后再提交.git `status`也可以告诉我们冲突的文件：  

```shell
$ git status
On branch master
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)

You have unmerged paths.
  (fix conflicts and run "git commit")
  (use "git merge --abort" to abort the merge)

Unmerged paths:
  (use "git add <file>..." to mark resolution)

  both modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

我们可以直接查看`readme.txt`的内容：  

```shell
Git is a distributed version control system.
Git is free software distributed under the GPL.
Git has a mutable index called stage.
Git tracks changes of files.
<<<<<<< HEAD
Creating a new branch is quick & simple.
=======
Creating a new branch is quick AND simple.
>>>>>>> feature1
```

Git用`<<<<<<<,=======,>>>>>>>`标记出不同分支的内容,我们修改如下后保存：  

```shell
Creating a new branch is quick and simple.
```

再提交：  

```shell
$ git add readme.txt
$ git commit -m "conflict fixed"
[master cf810e4] conflict fixed
```

现在,`master`分支和`feature1`分支变成了下图所示：

用带参数的`git log`也可以看到分支的合并情况：  

```shell
$ git log --graph --pretty=oneline --abbrev-commit
*   cf810e4 (HEAD -> master) conflict fixed
|\  
| * 14096d0 (feature1) AND simple
* | 5dc6824 & simple
|/  
* b17d20e branch test
* d46f35e (origin/master) remove test.txt
* b84166e add test.txt
* 519219b git tracks changes
* e43a48b understand how stage works
* 1094adb append GPL
* e475afc add distributed
* eaadf4e wrote a readme file
```

最后,删除feature1分支：

```shell
$ git branch -d feature1
Deleted branch feature1 (was 14096d0).
```

工作完成.  

**小结**:
当Git无法自动合并分支时,就必须首先解决冲突.解决冲突后,再提交,合并完成.  
解决冲突就是把Git合并失败的文件手动编辑为我们希望的内容,再提交.  
用`git log --graph`命令可以看到分支合并图.  

### 分支管理策略

通常,合并分支时,如果可能,Git会用`Fast forward`模式,但这种模式下,删除分支后,会丢掉分支信息.  
如果要强制禁用Fast forward模式,Git就会在`merge`时生成一个新的`commit`,这样,从分支历史上就可以看出分支信息.  
下面我们实战一下`--no-ff`方式的`git merge`：  
首先,仍然创建并切换`dev`分支：  

```shell
$ git checkout -b dev
Switched to a new branch 'dev'
```

修改`readme.txt`文件,并提交一个新的`commit`：

```shell
$ git add readme.txt  
$ git commit -m "add merge"
[dev f52c633] add merge
 1 file changed, 1 insertion(+)
```

现在,我们切换回`master`：

```shell
$ git checkout master
Switched to branch 'master'
```

准备合并`dev`分支,请注意`--no-ff`参数,表示禁用`Fast forward`：

```shell
$ git merge --no-ff -m "merge with no-ff" dev
Merge made by the 'recursive' strategy.
 readme.txt | 1 +
 1 file changed, 1 insertion(+)
```

因为本次合并要创建一个新的`commit`,所以加上`-m`参数,把`commit`描述写进去.  
合并后,我们用`git log`看看分支历史：  

```shell
$ git log --graph --pretty=oneline --abbrev-commit
*   e1e9c68 (HEAD -> master) merge with no-ff
|\  
| * f52c633 (dev) add merge
|/  
*   cf810e4 conflict fixed
...
```

可以看到,不使用`Fast forward`模式,`merge`后就像这样：

**分支策略**  
在实际开发中,我们应该按照几个基本原则进行分支管理：  
首先,`master`分支应该是非常稳定的,也就是仅用来发布新版本,平时不能在上面干活;  
那在哪干活呢?干活都在`dev`分支上,也就是说,`dev`分支是不稳定的,到某个时候,比如`1.0`版本发布时,再把`dev`分支合并到`master`上,在`master`分支发布`1.0`版本;  
你和你的小伙伴们每个人都在`dev`分支上干活,每个人都有自己的分支,时不时地往`dev`分支上合并就可以了.  

**小结**  
Git分支十分强大,在团队开发中应该充分应用.  
合并分支时,加上`--no-ff`参数就可以用普通模式合并,合并后的历史有分支,能看出来曾经做过合并,而`fast forward`合并就看不出来曾经做过合并.

### BUG分支

软件开发中,`bug`就像家常便饭一样.有了`bug`就需要修复,在Git中,由于分支是如此的强大,所以,每个`bug`都可以通过一个新的临时分支来修复,修复后,合并分支,然后将临时分支删除.  
当你接到一个修复一个代号`101`的`bug`的任务时,很自然地,你想创建一个分支`issue-101`来修复它,但是,等等,当前正在`dev`上进行的工作还没有提交：  

```shell
$ git status
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  new file:   hello.py

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   readme.txt
```

并不是你不想提交,而是工作只进行到一半,还没法提交,预计完成还需1天时间.但是,必须在两个小时内修复该`bug`,怎么办?  
幸好,Git还提供了一个`stash`功能,可以把当前工作现场"储藏"起来,等以后恢复现场后继续工作：  

```shell
$ git stash
Saved working directory and index state WIP on dev: f52c633 add merge
```

现在,用`git status`查看工作区,就是干净的（除非有没有被Git管理的文件）,因此可以放心地创建分支来修复`bug`.  
首先确定要在哪个分支上修复`bug`,假定需要在`master`分支上修复,就从`master`创建临时分支：  

```shell
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

$ git checkout -b issue-101
Switched to a new branch 'issue-101'
```

现在修复`bug`,需要把"`Git is free software ...`"改为"`Git is a free software ...`",然后提交：  

```shell
$ git add readme.txt  
$ git commit -m "fix bug 101"
[issue-101 4c805e2] fix bug 101
 1 file changed, 1 insertion(+), 1 deletion(-)
```

修复完成后,切换到`master`分支,并完成合并,最后删除`issue-101`分支：  

```shell
$ git checkout master
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 6 commits.
  (use "git push" to publish your local commits)

$ git merge --no-ff -m "merged bug fix 101" issue-101
Merge made by the 'recursive' strategy.
 readme.txt | 2 +-
 1 file changed, 1 insertion(+), 1 deletion(-)
```

太棒了,原计划两个小时的`bug`修复只花了5分钟!现在,是时候接着回到`dev`分支干活了!

```shell
$ git checkout dev
Switched to branch 'dev'

$ git status
On branch dev
nothing to commit, working tree clean
```

工作区是干净的,刚才的工作现场存到哪去了?用`git stash list`命令看看：

```shell
$ git stash list
stash@{0}: WIP on dev: f52c633 add merge
```

工作现场还在,Git把`stash`内容存在某个地方了,但是需要恢复一下,有两个办法：
一是用`git stash apply`恢复,但是恢复后,`stash`内容并不删除,你需要用`git stash drop`来删除;
另一种方式是用`git stash pop`,恢复的同时把`stash`内容也删了：

```shell
$ git stash pop
On branch dev
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  new file:   hello.py

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

  modified:   readme.txt

Dropped refs/stash@{0} (5d677e2ee266f39ea296182fb2354265b91b3b2a)
```

再用`git stash list`查看,就看不到任何`stash`内容了：

```shell
git stash list
```

你可以多次`stash`,恢复的时候,先用`git stash list`查看,然后恢复指定的`stash`,用命令：

```shell
git stash apply stash@{0}
```

在`master`分支上修复了`bug`后,我们要想一想,`dev`分支是早期从`master`分支分出来的,所以,这个`bug`其实在当前`dev`分支上也存在.  
那怎么在`dev`分支上修复同样的`bug`?重复操作一次,提交不就行了?  
有木有更简单的方法?  
有!  
同样的`bug`,要在`dev`上修复,我们只需要把`4c805e2 fix bug 101`这个提交所做的修改"复制"到`dev`分支.注意：我们只想复制`4c805e2 fix bug 101`这个提交所做的修改,并不是把整个`master`分支`merge`过来.  

为了方便操作,Git专门提供了一个`cherry-pick`命令,让我们能复制一个特定的提交到当前分支：

```shell
$ git branch
* dev
  master
$ git cherry-pick 4c805e2
[master 1d4b803] fix bug 101
 1 file changed, 1 insertion(+), 1 deletion(-)
```

Git自动给`dev`分支做了一次提交,注意这次提交的`commit`是`1d4b803`,它并不同于`master`的`4c805e2`,因为这两个`commit`只是改动相同,但确实是两个不同的`commit`.用`git cherry-pick`,我们就不需要在`dev`分支上手动再把修`bug`的过程重复一遍.  
有些聪明的童鞋会想了,既然可以在`master`分支上修复`bug`后,在`dev`分支上可以"重放"这个修复过程,那么直接在`dev`分支上修复`bug`,然后在`master`分支上"重放"行不行?当然可以,不过你仍然需要`git stash`命令保存现场,才能从`dev`分支切换到`master`分支.  

**小结**  
修复`bug`时,我们会通过创建新的`bug`分支进行修复,然后合并,最后删除;  
当手头工作没有完成时,先把工作现场`git stash`一下,然后去修复`bug`,修复后,再`git stash pop`,回到工作现场;  
在`master`分支上修复的`bug`,想要合并到当前`dev`分支,可以用`git cherry-pick <commit>`命令,把`bug`提交的修改"复制"到当前分支,避免重复劳动.  

### Feature分支

软件开发中,总有无穷无尽的新的功能要不断添加进来.  

添加一个新功能时,你肯定不希望因为一些实验性质的代码,把主分支搞乱了,所以,每添加一个新功能,最好新建一个`feature`分支,在上面开发,完成后,合并,最后,删除该`feature`分支.  

现在,你终于接到了一个新任务：开发代号为`Vulcan`的新功能,该功能计划用于下一代星际飞船.  

于是准备开发：  

```shell
$ git checkout -b feature-vulcan
Switched to a new branch 'feature-vulcan'
```

5分钟后,开发完毕：

```shell
$ git add vulcan.py

$ git status
On branch feature-vulcan
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  new file:   vulcan.py

$ git commit -m "add feature vulcan"
[feature-vulcan 287773e] add feature vulcan
 1 file changed, 2 insertions(+)
 create mode 100644 vulcan.py
```

切回`dev`,准备合并：  

```shell
git checkout dev  
```

一切顺利的话,`feature`分支和`bug`分支是类似的,合并,然后删除.
但是!

就在此时,接到上级命令,因经费不足,新功能必须取消!  
虽然白干了,但是这个包含机密资料的分支还是必须就地销毁：  

```shell
$ git branch -d feature-vulcan
error: The branch 'feature-vulcan' is not fully merged.
If you are sure you want to delete it, run 'git branch -D feature-vulcan'.
```

销毁失败.Git友情提醒,feature-vulcan分支还没有被合并,如果删除,将丢失掉修改,如果要强行删除,需要使用大写的-D参数..
现在我们强行删除：

```shell
$ git branch -D feature-vulcan
Deleted branch feature-vulcan (was 287773e).
```

终于删除成功!

**小结**  
开发一个新`feature`,最好新建一个分支;  
如果要丢弃一个没有被合并过的分支,可以通过`git branch -D <name>`强行删除.  

### 多人协作

当你从远程仓库克隆时,实际上Git自动把本地的`master`分支和远程的`master`分支对应起来了,并且,远程仓库的默认名称是`origin`.  

要查看远程库的信息,用`git remote`：

```shell
$ git remote
origin
```

或者,用`git remote -v`显示更详细的信息：

```shell
$ git remote -v
origin  git@github.com:michaelliao/learngit.git (fetch)
origin  git@github.com:michaelliao/learngit.git (push)
```

上面显示了可以抓取和推送的origin的地址.如果没有推送权限,就看不到push的地址.  
**推送分支**  
推送分支,就是把该分支上的所有本地提交推送到远程库.推送时,要指定本地分支,这样,Git就会把该分支推送到远程库对应的远程分支上：

```shell
git push origin master
```

如果要推送其他分支,比如dev,就改成：

```shell
git push origin dev
```

但是,并不是一定要把本地分支往远程推送,那么,哪些分支需要推送,哪些不需要呢?  
`master`分支是主分支,因此要时刻与远程同步;  
`dev`分支是开发分支,团队所有成员都需要在上面工作,所以也需要与远程同步;  
`bug`分支只用于在本地修复`bug`,就没必要推到远程了,除非老板要看看你每周到底修复了几个`bug`;  
`feature`分支是否推到远程,取决于你是否和你的小伙伴合作在上面开发.  
总之,就是在Git中,分支完全可以在本地自己藏着玩,是否推送,视你的心情而定!  

**抓取分支**  
多人协作时,大家都会往`master`和`dev`分支上推送各自的修改.  
现在,模拟一个你的小伙伴,可以在另一台电脑（注意要把`SSH Key`添加到`GitHub`）或者同一台电脑的另一个目录下克隆：  

```shell
$ git clone git@github.com:michaelliao/learngit.git
Cloning into 'learngit'...
remote: Counting objects: 40, done.
remote: Compressing objects: 100% (21/21), done.
remote: Total 40 (delta 14), reused 40 (delta 14), pack-reused 0
Receiving objects: 100% (40/40), done.
Resolving deltas: 100% (14/14), done.
```

当你的小伙伴从远程库`clone`时,默认情况下,你的小伙伴只能看到本地的`master`分支.不信可以用`git branch`命令看看：

```shell
$ git branch
* master
```

现在,你的小伙伴要在`dev`分支上开发,就必须创建远程origin的dev分支到本地,于是他用这个命令创建本地`dev`分支：

```shell
git checkout -b dev origin/dev
```

现在,他就可以在`dev`上继续修改,然后,时不时地把`dev`分支`push`到远程：

```shell
$ git add env.txt

$ git commit -m "add env"
[dev 7a5e5dd] add env
 1 file changed, 1 insertion(+)
 create mode 100644 env.txt

$ git push origin dev
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 308 bytes | 308.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To github.com:michaelliao/learngit.git
   f52c633..7a5e5dd  dev -> dev
```

你的小伙伴已经向`origin/dev`分支推送了他的提交,而碰巧你也对同样的文件作了修改,并试图推送：

```shell
$ cat env.txt
env

$ git add env.txt

$ git commit -m "add new env"
[dev 7bd91f1] add new env
 1 file changed, 1 insertion(+)
 create mode 100644 env.txt

$ git push origin dev
To github.com:michaelliao/learngit.git
 ! [rejected]        dev -> dev (non-fast-forward)
error: failed to push some refs to 'git@github.com:michaelliao/learngit.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

推送失败,因为你的小伙伴的最新提交和你试图推送的提交有冲突,解决办法也很简单,Git已经提示我们,先用`git pull`把最新的提交从`origin/dev`抓下来,然后,在本地合并,解决冲突,再推送：

```shell
$ git pull
There is no tracking information for the current branch.
Please specify which branch you want to merge with.
See git-pull(1) for details.

    git pull <remote> <branch>

If you wish to set tracking information for this branch you can do so with:

    git branch --set-upstream-to=origin/<branch> dev
```

`git pull`也失败了,原因是没有指定本地`dev`分支与远程`origin/dev`分支的链接,根据提示,设置`dev`和`origin/dev`的链接：

```shell
$ git branch --set-upstream-to=origin/dev dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
```

再`pull`：

```shell
$ git pull
Auto-merging env.txt
CONFLICT (add/add): Merge conflict in env.txt
Automatic merge failed; fix conflicts and then commit the result.
```

这回`git pull`成功,但是合并有冲突,需要手动解决,解决的方法和分支管理中的解决冲突完全一样.解决后,提交,再`push`：  

```shell
$ git commit -m "fix env conflict"
[dev 57c53ab] fix env conflict

$ git push origin dev
Counting objects: 6, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 621 bytes | 621.00 KiB/s, done.
Total 6 (delta 0), reused 0 (delta 0)
To github.com:michaelliao/learngit.git
   7a5e5dd..57c53ab  dev -> dev
```

因此,多人协作的工作模式通常是这样：  
首先,可以试图用`git push origin <branch-name>`推送自己的修改;  
如果推送失败,则因为远程分支比你的本地更新,需要先用`git pull`试图合并;  
如果合并有冲突,则解决冲突,并在本地提交;  
没有冲突或者解决掉冲突后,再用`git push origin <branch-name>`推送就能成功!  
如果`git pull`提示`no tracking information`,则说明本地分支和远程分支的链接关系没有创建,用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`.  
这就是多人协作的工作模式,一旦熟悉了,就非常简单.  

**小结**  
查看远程库信息,使用`git remote -v`;  
本地新建的分支如果不推送到远程,对其他人就是不可见的;  
从本地推送分支,使用`git push origin branch-name`,如果推送失败,先用`git pull`抓取远程的新提交;  
在本地创建和远程分支对应的分支,使用`git checkout -b branch-name origin/branch-name`,本地和远程分支的名称最好一致;  
建立本地分支和远程分支的关联,使用`git branch --set-upstream branch-name origin/branch-name`;  
从远程抓取分支,使用`git pull`,如果有冲突,要先处理冲突.  

### Rebase

在上一节我们看到了,多人在同一个分支上协作时,很容易出现冲突.即使没有冲突,后`push`的童鞋不得不先`pull`,在本地合并,然后才能`push`成功.  
每次合并再`push`后,分支变成了这样：  

```shell
$ git log --graph --pretty=oneline --abbrev-commit
* d1be385 (HEAD -> master, origin/master) init hello
*   e5e69f1 Merge branch 'dev'
|\  
| *   57c53ab (origin/dev, dev) fix env conflict
| |\  
| | * 7a5e5dd add env
| * | 7bd91f1 add new env
| |/  
* |   12a631b merged bug fix 101
|\ \  
| * | 4c805e2 fix bug 101
|/ /  
* |   e1e9c68 merge with no-ff
|\ \  
| |/  
| * f52c633 add merge
|/  
*   cf810e4 conflict fixed
```

总之看上去很乱,有强迫症的童鞋会问：为什么Git的提交历史不能是一条干净的直线?  
其实是可以做到的!  
Git有一种称为`rebase`的操作,有人把它翻译成"变基".  

先不要随意展开想象.我们还是从实际问题出发,看看怎么把分叉的提交变成直线.  
在和远程分支同步后,我们对`hello.py`这个文件做了两次提交.用`git log`命令看看：  

```shell
$ git log --graph --pretty=oneline --abbrev-commit
* 582d922 (HEAD -> master) add author
* 8875536 add comment
* d1be385 (origin/master) init hello
*   e5e69f1 Merge branch 'dev'
|\  
| *   57c53ab (origin/dev, dev) fix env conflict
| |\  
| | * 7a5e5dd add env
| * | 7bd91f1 add new env
...
```

注意到Git用`(HEAD -> master)`和`(origin/master)`标识出当前分支的`HEAD`和远程`origin`的位置分别是`582d922 add author`和`d1be385 init hello`,本地分支比远程分支快两个提交.  
现在我们尝试推送本地分支：  

```shell
$ git push origin master
To github.com:michaelliao/learngit.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'git@github.com:michaelliao/learngit.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

很不幸,失败了,这说明有人先于我们推送了远程分支.按照经验,先`pull`一下：

```shell
$ git pull
remote: Counting objects: 3, done.
remote: Compressing objects: 100% (1/1), done.
remote: Total 3 (delta 1), reused 3 (delta 1), pack-reused 0
Unpacking objects: 100% (3/3), done.
From github.com:michaelliao/learngit
   d1be385..f005ed4  master     -> origin/master
 * [new tag]         v1.0       -> v1.0
Auto-merging hello.py
Merge made by the 'recursive' strategy.
 hello.py | 1 +
 1 file changed, 1 insertion(+)
再用git status看看状态：
$ git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean
```

加上刚才合并的提交,现在我们本地分支比远程分支超前3个提交.
用`git log`看看：

```shell
$ git log --graph --pretty=oneline --abbrev-commit
*   e0ea545 (HEAD -> master) Merge branch 'master' of github.com:michaelliao/learngit
|\  
| * f005ed4 (origin/master) set exit=1
* | 582d922 add author
* | 8875536 add comment
|/  
* d1be385 init hello
...
```

对强迫症童鞋来说,现在事情有点不对头,提交历史分叉了.如果现在把本地分支`push`到远程,有没有问题?  
有!  
什么问题?  
不好看!  
有没有解决方法?  
有!  
这个时候,`rebase`就派上了用场.我们输入命令`git rebase`试试：  

```shell
$ git rebase
First, rewinding head to replay your work on top of it...
Applying: add comment
Using index info to reconstruct a base tree...
M hello.py
Falling back to patching base and 3-way merge...
Auto-merging hello.py
Applying: add author
Using index info to reconstruct a base tree...
M hello.py
Falling back to patching base and 3-way merge...
Auto-merging hello.py
输出了一大堆操作,到底是啥效果?再用git log看看：
$ git log --graph --pretty=oneline --abbrev-commit
* 7e61ed4 (HEAD -> master) add author
* 3611cfe add comment
* f005ed4 (origin/master) set exit=1
* d1be385 init hello
...
```

原本分叉的提交现在变成一条直线了!这种神奇的操作是怎么实现的?其实原理非常简单.我们注意观察,发现Git把我们本地的提交"挪动"了位置,放到了`f005ed4 (origin/master) set exit=1`之后,这样,整个提交历史就成了一条直线.rebase操作前后,最终的提交内容是一致的,但是,我们本地的`commit`修改内容已经变化了,它们的修改不再基于`d1be385 init hello`,而是基于`f005ed4 (origin/master) set exit=1`,但最后的提交`7e61ed4`内容是一致的.  
这就是`rebase`操作的特点：把分叉的提交历史"整理"成一条直线,看上去更直观.缺点是本地的分叉提交已经被修改过了.  
最后,通过`push`操作把本地分支推送到远程：  

```shell
Mac:~/learngit michael$ git push origin master
Counting objects: 6, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (6/6), 576 bytes | 576.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0)
remote: Resolving deltas: 100% (2/2), completed with 1 local object.
To github.com:michaelliao/learngit.git
   f005ed4..7e61ed4  master -> master
再用git log看看效果：
$ git log --graph --pretty=oneline --abbrev-commit
* 7e61ed4 (HEAD -> master, origin/master) add author
* 3611cfe add comment
* f005ed4 set exit=1
* d1be385 init hello
...
```

远程分支的提交历史也是一条直线.  

**小结**
`rebase`操作可以把本地未`push`的分叉提交历史整理成直线;  
`rebase`的目的是使得我们在查看历史提交的变化时更容易,因为分叉的提交需要三方对比.  

## 标签管理

发布一个版本时,我们通常先在版本库中打一个标签（tag）,这样,就唯一确定了打标签时刻的版本.将来无论什么时候,取某个标签的版本,就是把那个打标签的时刻的历史版本取出来.所以,标签也是版本库的一个快照.
在Git中tag就是一个让人容易记住的有意义的名字,它跟某个commit绑在一起.

### 创建标签

在Git中打标签非常简单,首先,切换到需要打标签的分支上：  

```shell
$ git branch
* dev
  master
$ git checkout master
Switched to branch 'master'
```

然后,敲命令`git tag <name>`就可以打一个新标签：  

```shell
git tag v1.0
```

可以用命令git tag查看所有标签：  

```shell
$ git tag
v1.0
```

默认标签是打在最新提交的`commit`上的.有时候,如果忘了打标签,比如,现在已经是周五了,但应该在周一打的标签没有打,怎么办?  

方法是找到历史提交的`commit id`,然后打上就可以了：  

```shell
$ git log --pretty=oneline --abbrev-commit
12a631b (HEAD -> master, tag: v1.0, origin/master) merged bug fix 101
4c805e2 fix bug 101
e1e9c68 merge with no-ff
f52c633 add merge
cf810e4 conflict fixed
5dc6824 & simple
14096d0 AND simple
b17d20e branch test
d46f35e remove test.txt
b84166e add test.txt
519219b git tracks changes
e43a48b understand how stage works
1094adb append GPL
e475afc add distributed
eaadf4e wrote a readme file
```

比方说要对`add merge`这次提交打标签,它对应的`commit id`是`f52c633`,敲入命令：

```shell
git tag v0.9 f52c633
```

再用命令`git tag`查看标签：

```shell
$ git tag
v0.9
v1.0
```

注意,标签不是按时间顺序列出,而是按字母排序的.可以用`git show <tagname>`查看标签信息：

```shell
$ git show v0.9
commit f52c63349bc3c1593499807e5c8e972b82c8f286 (tag: v0.9)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:56:54 2018 +0800

    add merge

diff --git a/readme.txt b/readme.txt
...
```

可以看到,`v0.9`确实打在`add merge`这次提交上.  

还可以创建带有说明的标签,用-a指定标签名,-m指定说明文字：  

```shell
git tag -a v0.1 -m "version 0.1 released" 1094adb
```

用命令`git show <tagname>`可以看到说明文字：  

```shell
$ git show v0.1
tag v0.1
Tagger: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 22:48:43 2018 +0800

version 0.1 released

commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (tag: v0.1)
Author: Michael Liao <askxuefeng@gmail.com>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

diff --git a/readme.txt b/readme.txt
...
```

**小结**:
命令`git tag <tagname>`用于新建一个标签,默认为`HEAD`,也可以指定一个`commit id`;  
命令`git tag -a <tagname> -m "blablabla..."`可以指定标签信息;  
命令`git tag`可以查看所有标签.  

### 操作标签

如果标签打错了,也可以删除：  

```shell
$ git tag -d v0.1
Deleted tag 'v0.1' (was f15b0dd)
```

因为创建的标签都只存储在本地,不会自动推送到远程.所以,打错的标签可以在本地安全删除.  
如果要推送某个标签到远程,使用命令`git push origin <tagname>`：

```shell
$ git push origin v1.0
Total 0 (delta 0), reused 0 (delta 0)
To github.com:michaelliao/learngit.git
 * [new tag]         v1.0 -> v1.0
```

或者,一次性推送全部尚未推送到远程的本地标签：  

```shell
$ git push origin --tags
Total 0 (delta 0), reused 0 (delta 0)
To github.com:michaelliao/learngit.git
 * [new tag]         v0.9 -> v0.9
```

如果标签已经推送到远程,要删除远程标签就麻烦一点,先从本地删除：  

```shell
$ git tag -d v0.9
Deleted tag 'v0.9' (was f52c633)
```

然后,从远程删除.删除命令也是`push`,但是格式如下：  

```shell
$ git push origin :refs/tags/v0.9
To github.com:michaelliao/learngit.git
 - [deleted]         v0.9
```

要看看是否真的从远程库删除了标签,可以登陆GitHub查看.

**小结**:  
命令`git push origin <tagname>`可以推送一个本地标签;  
命令`git push origin --tags`可以推送全部未推送过的本地标签;  
命令`git tag -d <tagname>`可以删除一个本地标签;  
命令`git push origin :refs/tags/<tagname>`可以删除一个远程标签.  

## 忽略特殊文件

有些时候,你必须把某些文件放到Git工作目录中,但又不能提交它们,每次`git status`都会显示`Untracked files ...`,有强迫症的童鞋心里肯定不爽.  

好在Git考虑到了大家的感受,这个问题解决起来也很简单,在Git工作区的根目录下创建一个特殊的`.gitignore`文件,然后把要忽略的文件名填进去,Git就会自动忽略这些文件.  
不需要从头写`.gitignore`文件,GitHub已经为我们准备了各种配置文件,只需要组合一下就可以使用了.所有配置文件可以直接在线浏览：<https://github.com/github/gitignore>  

忽略文件的原则是：  

忽略操作系统自动生成的文件,比如缩略图等;  

忽略编译生成的中间文件、可执行文件等,也就是如果一个文件是通过另一个文件自动生成的,那自动生成的文件就没必要放进版本库,比如Java编译产生的.class文件;  

忽略你自己的带有敏感信息的配置文件,比如存放口令的配置文件.  

举个例子：
假设你在Windows下进行`Python`开发,Windows会自动在有图片的目录下生成隐藏的缩略图文件,如果有自定义目录,目录下就会有`Desktop.ini`文件,因此你需要忽略`Windows`自动生成的垃圾文件：

```shell
# Windows:
Thumbs.db
ehthumbs.db
Desktop.ini
```

然后,继续忽略`Python`编译产生的`.pyc、.pyo、dist`等文件或目录：

```shell  
# Python:
*.py[cod]
*.so
*.egg
*.egg-info
dist
build
```

加上你自己定义的文件,最终得到一个完整的`.gitignore`文件,内容如下：  

```shell
# Windows:
Thumbs.db
ehthumbs.db
Desktop.ini

# Python:
*.py[cod]
*.so
*.egg
*.egg-info
dist
build

# My configurations:
db.ini
deploy_key_rsa
```

最后一步就是把`.gitignore`也提交到Git,就完成了!当然检验`.gitignore`的标准是`git status`命令是不是说`working directory clean`.  

使用Windows的童鞋注意了,如果你在资源管理器里新建一个`.gitignore`文件,它会非常弱智地提示你必须输入文件名,但是在文本编辑器里"保存"或者"另存为"就可以把文件保存为`.gitignore`了.  

有些时候,你想添加一个文件到Git,但发现添加不了,原因是这个文件被`.gitignore`忽略了：  

```shell
$ git add App.class
The following paths are ignored by one of your .gitignore files:
App.class
Use -f if you really want to add them.
```

如果你确实想添加该文件,可以用-f强制添加到Git：

```shell
git add -f App.class
```

或者你发现,可能是`.gitignore`写得有问题,需要找出来到底哪个规则写错了,可以用`git check-ignore`命令检查：

```shell
$ git check-ignore -v App.class
.gitignore:3:*.class  App.class
```

Git会告诉我们,`.gitignore`的第3行规则忽略了该文件,于是我们就可以知道应该修订哪个规则.

**小结**:
忽略某些文件时,需要编写`.gitignore`;  
`.gitignore`文件本身要放到版本库里,并且可以对`.gitignore`做版本管理!  

## 常见命令

|                            命令                            |              作用              |              说明              |
| :--------------------------------------------------------: | :----------------------------: | :----------------------------: |
|                          `mkdir`                           |           新建文件夹           |         Make Directory         |
|                            `cd`                            |            移动目录            |        Change directory        |
|                           `pwd`                            |          显示当前目录          |    Print Working Directory     |
|                            `ls`                            |         显示目录内文件         |    `ls -ah`显示包括隐形文件    |
|                         `git init`                         |        变成可管理的仓库        |              git               |
|                 `git commit -m <message>`                  |              提交              |              git               |
|                        `git commit`                        |              提交              |  使用文本编辑器编辑`message`   |
|                        `git status`                        |            查看状态            |              git               |
|                         `git diff`                         |            查看改变            |         git difference         |
|                         `git log`                          |            提交日志            |       `--pretty=oneline`       |
|                        `git reflog`                        |       查看所有的修改记录       |              git               |
|                  `git reset --hard HEAD^`                  |        回退到上一个版本        |  `HEAD`上`^`个数即回退版本数   |
|               `git reset --hard <commit id>`               |    回退到`commit id`的版本     |              git               |
|                   `git checkout -- file`                   |  撤销`file`在工作区的全部修改  |              git               |
|                  `git reset HEAD <file>`                   |      把在暂存区的修改撤销      |              git               |
|       `ssh-keygen -t rsa -C "youremail@example.com"`       |           创建`ssh`            |              ssh               |
| `git remote add origin git@github.com:yourname/XXXXXX.git` |       创建和Github的连接       |              git               |
|                  `git push origin master`                  |          提交所有内容          |        第一次需要加`-u`        |
|   `$ git clone git@github.com:zmx0142857/math-note.git`    |        从远程库`clone`         |              git               |
|                   `git checkout -b dev`                    |      创建分支`dev`并前往       |              git               |
|                      `git branch dev`                      |         创建分支`dev`          |              git               |
|                        `git branch`                        |          查看所有分支          |     当前分支前会有一个`*`      |
|                      `git merge dev`                       | 命令用于合并指定分支到当前分支 |              git               |
|                    `git branch -d dev`                     |          删除指定分支          |              git               |
|                     `git log --graph`                      |         查看分支合并图         | `--graph` or `--abbrev-commit` |
|           `git merge --no-ff -m "<message>" dev`           |     合并指定分支到当前分支     |       禁用`Fast forward`       |
|                        `git stash`                         |      把当前工作现场"储藏"      |              git               |
|                      `git stash list`                      |        查看`stash`内容         |              git               |
|                     `git stash apply`                      |    恢复`stash`内容但不删除     |              git               |
|                      `git stash drop`                      |        删除`stash`内容         |              git               |
|                      `git stash pop`                       | 恢复的同时把`stash`内容也删除  |              git               |
|               `$ git stash apply stash@{0}`                |        恢复指定`stash`         |              git               |
|              `$ git cherry-pick <commit id>`               |  复制一个特定的提交到当前分支  |              git               |
|                    `git branch -D dev`                     |        强制删除指定分支        |              git               |
|                        `git remote`                        |         显示远程库信息         |        `-v`显示详细信息        |
|       `git branch --set-upstream-to=origin/dev dev`        | 设置`dev`和`origin/dev`的链接  |              git               |
|                         `git pull`                         |              拉去              |              git               |
|                        `git rebase`                        |              变基              |              git               |
|                    `git tag <tagname>`                     |         给`HEAD`打标签         |              git               |
|              `git tag <tagname> <commit id>`               |             打标签             |              git               |
|     `git tag -a <tagname> -m "<message>" <commit id>`      |             打标签             |              git               |
|                         `git tag`                          |          查看所有标签          |              git               |
|                `git push origin <tagname>`                 |        推送一个本地标签        |              git               |
|                  `git push origin --tags`                  |   推送全部未推送过的本地标签   |              git               |
|                   `git tag -d <tagname>`                   |        删除一个本地标签        |              git               |
|           `git push origin :refs/tags/<tagname>`           |        删除一个远程标签        |              git               |
>常见命令不全

**git-cheatsheet**:  
|                         Code                         |                                          Usage                                           |
| :--------------------------------------------------: | :--------------------------------------------------------------------------------------: |
|                        Create                        |                                                                                          |
|                 `$ git clone <ssh>`                  |                              Clones an existing repository                               |
|                     `$ git init`                     |                              Create a new local repository                               |
|                     Local Change                     |                                                                                          |
|                    `$ git status`                    |                         Changed files in your working directory                          |
|                     `$ git diff`                     |                                 Changes to tracked files                                 |
|                    `$ git add .`                     |                        Add all current changes to the next commit                        |
|                `$ git add -p <file>`                 |                      Add some changes in \<file> to the next commit                      |
|                  `$ git commit -a`                   |                        Commit all local changes in tracked files                         |
|                    `$ git commit`                    |                             Commit previously staged changes                             |
|               `$ git commit -- amend`                |                  Change the last commit  Don‘t amend published commits!                  |
|                    Commit History                    |                                                                                          |
|                      `$git log`                      |                          Show all commits, starting with newest                          |
|                `$ git log -p <file>`                 |                        Show changes over time for a specific file                        |
|                 `$ git blame <file>`                 |                           Who changed what and when in \<file>                           |
|                    Branch & Tags                     |                                                                                          |
|                  `$ git branch -av`                  |                                List all existing branches                                |
|              `$ git checkout <branch>`               |                                    Switch HEAD branch                                    |
|             `$ git branch <new-branch>`              |                     Create a new branch based  on your current HEAD                      |
|       `$ git checkout --track <remote/branch>`       |                  Create a new tracking branch based on  a remote branch                  |
|              `$ git branch -d <branch>`              |                                  Delete a local branch                                   |
|                `$ git tag <tag-name>`                |                            Mark the current commit with a tag                            |
|                   Update & Publish                   |                                                                                          |
|                  `$ git remote -v`                   |                          List all currently configured remotes                           |
|             `$ git remote show <remote>`             |                             Show information about a remote                              |
|         `$ git remote add <shortname> <url>`         |                        Add new remote repository, named \<remote>                        |
|                `$ git fetch <remote>`                |            Download all changes from \<remote>,but don‘t integrate into HEAD             |
|            `$ git pull <remote> <branch>`            |                 Download changes and directly merge/integrate into HEAD                  |
|            `$ git push <remote> <branch>`            |                            Publish local changes on a remote                             |
|          `$ git branch -dr <remote/branch>`          |                              Delete a branch on the remote                               |
|                 `$ git push --tags`                  |                                    Publish your tags                                     |
|                    Merge & Rebase                    |                                                                                          |
|                `$ git merge <branch>`                |                          Merge \<branch> into your current HEAD                          |
|               `$ git rebase <branch>`                |         Rebase your current HEAD onto \<branch>. Don‘t rebase published commits!         |
|                `$ git rebase --abort`                |                                      Abort a rebase                                      |
|              `$ git rebase --continue`               |                       Continue a rebase after resolving conflicts                        |
|                  `$ git mergetool`                   |                    Use your configured merge tool to  solve conflicts                    |
| `$ git add <resolved-file> $ git rm <resolved-file>` | Use your editor to manually solve conflicts and  (after resolving) mark file as resolved |
|                         Undo                         |                                                                                          |
|              `$ git reset --hard HEAD`               |                   Discard all local changes in your working directory                    |
|             `$ git checkout HEAD <file>`             |                         Discard local changes in a specific file                         |
|               `$ git revert <commit>`                |            Revert a commit (by producing a new commit with contrary changes)             |
|            `$ git reset --hard <commit>`             |     Reset your HEAD pointer to a previous commit …and discard all changes since then     |  |
|                `$ git reset <commit>`                |                      …and preserve all changes as unstaged changes                       |
|            `$ git reset --keep <commit>`             |                         …and preserve uncommitted local changes                          |
Finished
