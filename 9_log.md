# ***git log 的使用***

## git log 
>无参数状态git log 默认不用任何参数的话，git log 会按提交时间列出所有的更新，最近的更新排在最上面。每次更新都有一个 SHA-1 校验和、作者的名字 和 电子邮件地址、提交时间，最后缩进一个段落显示提交说明。

## git shortlog
>这个命令会返回这个 git 目录下每个用户进行 commit 的次数，以及每次 commit 的注释。
-s 参数省略每次 commit 的注释，仅仅返回一个简单的统计。
-n 参数按照 commit 数量从多到少的顺利对用户进行排序

##  git log -p -2
>参数的说明, 代码审查-展开内容差异: git log -p 展开显示每次提交的内容差异, 以diff模式展示， 用 -2 则仅显示最近的两次更新 git log -p -2 在做代码审查，或者要快速浏览其他协作者提交的更新都作了哪些改动时，就可以用这个选项。

## git show
>git show命令同git log -p输出类似，只不过它只显示最近一次commit的内容，如果不指定commit hash, 它默认输出HEAD指向commit的

## git log --stat
>增改行数统计 git log --stat 仅显示简要的增改行数统计 git log --stat每个提交都列出了修改过的文件，以及其中添加和移除的行数，并在最后列出所有增减行数小计。

## git log --pretty
> 可以指定使用完全不同于默认格式的方式展示提交历史。
> + 4.1 简单模式:
&emsp;&emsp;git log --pretty=oneline &emsp;&emsp;单行显示日志
&emsp;&emsp;git log --pretty=short &emsp;&emsp;简略信息
&emsp;&emsp;git log --pretty=full 
&emsp;&emsp;git log --pretty=fuller
>+ 4.2 定制格式:
&emsp;&emsp;format，可以定制要显示的记录格式，这样的输出便于后期编程提取分析：
&emsp;&emsp;git log --pretty=format:"%h - %an, %ar : %s"

## git log --author
> 显示指定作者的提交

## git log --grep
>用 --grep 选项搜索提交说明中的关键字。（请注意，如果要得到同时满足这两个选项搜索条件的提交，就必须用--all-match 选项。）

## git log -- < path >
>如果只关心某些文件或者目录的历史提交，可以在 git log 选项的最后指定它们的路径。因为是放在最后位置上的选项，所以用两个短划线（--）隔开之前的选项和后面限定的路径名。

## 9. git log -(n)	
>仅显示最近的 n 条提交

## 10. git log --since, --after	
>仅显示指定时间之后的提交。

## 5. git log --since   /  git log --until
> 下面的命令列出所有最近两周内的提交：
$ git log --since=2.weeks
你可以给出各种时间格式，比如说具体的某一天（“2008-01-15”），或者是多久以前（“2 years 1 day 3 minutes ago”）。
--until, --before	仅显示指定时间之前的提交。
--author	仅显示指定作者相关的提交。
--committer	仅显示指定提交者相关的提交。
来看一个实际的例子，如果要查看 Git 仓库中，2008 年 10 月期间，Junio Hamano 提交的但未合并的测试脚本（位于项目的 t/ 目录下的文件），可以用下面的查询命令：

## $ git log --pretty="%h - %s" --author=gitster --since="2008-10-01" 
>   --before="2008-11-01" --no-merges -- t/
5610e3b - Fix testcase failure when extended attribute
acd3b9e - Enhance hold_lock_file_for_{update,append}()
f563754 - demonstrate breakage of detached checkout wi
d1a43f2 - reset --hard/read-tree --reset -u: remove un
51a94af - Fix "checkout --track -b newbranch" on detac
b0ad11e - pull: allow "git pull origin $something:$cur
Git 项目有 20,000 多条提交，但我们给出搜索选项后，仅列出了其中满足条件的 6 条。
使用图形化工具查阅提交历史
有时候图形化工具更容易展示历史提交的变化，随 Git 一同发布的 gitk 就是这样一种工具。它是用 Tcl/Tk 写成的，基本上相当于 git log 命令的可视化版本，凡是git log 可以用的选项也都能用在 gitk 上。在项目工作目录中输入 gitk 命令后，就会启动图 2-2 所示的界面。

图 2-2. gitk 的图形界面

上半个窗口显示的是历次提交的分支祖先图谱，下半个窗口显示当前点选的提交对应的具体差异。

