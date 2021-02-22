# 第1章：Git入门

> ==使用#号可以来表示1-6级别的标题==
>
> **# 一级标题** ctrl+1
>
> **##二级标题**ctrl+2
>
> ......
>
> ###### ######六级标题 快捷键为 Ctrl + 6

###### 

#### 本章功能

介绍几个最常用的git命令（绝大多数时间里仅用到它们）：

##### 1）初始化新的代码仓库

```
$ git init
```

初始化以后，当前目录出现一个名为.git的目录，包含Git需要的数据和资源

##### 2）跟踪文件，提交

```
$ git add *.c
$ git add README
$ git commit -m "initial project version"
$ git push
```

##### 3）从现有仓库克隆

```sa
$ git clone git://github.com/schacon/grit.git	
```

这会在当前目录下创建一个名为“grit"的目录，其中内含一个.git的目录，并从同步后的仓库中拉出所有的数据，取得最新版本的文件拷贝。

```
$ git clone git://github.com/grit.git mygrit
```

此命令唯一的差别是：新建的目录成了mygrit而不是grit

> 引用 ：**> +空格 +文字**
>
> 代码： **```+回车 **
>
> 原文显示： **

##### 5）记录每次更新到仓库

###### 检查当前文件状态

```
git status
```

###### 跟踪新文件

```
git add ****
```

###### 暂存已经修改的文件

使用git add命令，==不仅仅可以跟踪新文件==，还可以把已经跟踪的文件放到暂存区，还能用于合并时把有冲突的文件标记为已解决状态。

###### 查看尚未暂存的文件更新了哪些部分

```
git diff
```

###### 查看已经暂存的文件和上次提交时的快照之间的差异

```
git diff --cached
```

###### 提交

```
git commit -m "版本说明"
```

###### 跳过缓存区提交

```3
git commit -a -m "版本说明"
```

###### 查看提交历史

```
git log
```

默认不用任何参数的话，git log会按提交时间列出所有的更新。

```
git log -p -2
```

我们常用-p选项展开显示说，-2则仅显示最近的两次更新：

```
git log --stat
```

显示简要的增改行数统计













##### 6）忽略某些文件

有一些文件我们不需要把它放到Git的管理，但也不希望它出现在未跟踪文件列表。

通常是自动生成的文件：如日志或编译过程中产生的。

可以创建.gitignore文件

```
$cat .gitignore
* .[oa]
*~
```

忽略所有以.o或者.a结尾的文件

##### 7） 移除文件

```
rm grit.gemspec
git rm grit.gemspec
```

该命令可以从已经跟踪文件清单中移除（从暂存区域移除），然后提交。

git rm可以完成上述工作，并且连带从工作目录中删除制定的文件。

```
git rm -f grit.gemspec
```

如果删除之前修改过并且已经放到暂存区域的，需要用强制删除选项-f

```
git rm --cached readme.txt
```

要移除跟踪但是不删除文件

##### 8）移动文件

```
git mv file_from file_to
```

相当于执行了三条命令

```
mv README.txt README
git rm README.txt
git add README
```





















