# git log 日志:  
+ 官方文档: https://git-scm.com/docs/git-log 
+ 腾讯云Url: https://cloud.tencent.com/developer/section/1138655
+ git log [< options >] [< revision range >] [ [ -- ] < path >…​]

## git log 使用实例:
    git log
        无参数状态git log 默认不用任何参数的话，git log 会按提交时间列出所有的更新，最近的更新排在最上面。
        每次更新都有一个 SHA-1 校验和、作者的名字 和 电子邮件地址、提交时间，最后缩进一个段落显示提交说明。

    git shortlog
        这个命令会返回这个 git 目录下每个用户进行 commit 的次数，以及每次 commit 的注释。
        -s 参数省略每次 commit 的注释，仅仅返回一个简单的统计。
        -n 参数按照 commit 数量从多到少的顺利对用户进行排序

    git log -p -2
        参数的说明, 代码审查-展开内容差异: git log -p 展开显示每次提交的内容差异, 以diff模式展示， 
        用 -2 则仅显示最近的两次更新 git log -p -2 在做代码审查，
        或者要快速浏览其他协作者提交的更新都作了哪些改动时，就可以用这个选项。

    git show
        git show命令同git log -p输出类似，只不过它只显示最近一次commit的内容，
        如果不指定commit hash, 它默认输出HEAD指向commit的

    git log --stat
        增改行数统计 git log --stat 仅显示简要的增改行数统计 git log --stat每个提交都列出了修改过的文件，
        以及其中添加和移除的行数，并在最后列出所有增减行数小计。

    git log --pretty
        可以指定使用完全不同于默认格式的方式展示提交历史。
        简单模式:
            git log --pretty=oneline    //单行显示日志
            git log --pretty=short      //简略信息
            git log --pretty=full 
            git log --pretty=fuller
         定制格式:  format，可以定制要显示的记录格式，这样的输出便于后期编程提取分析：
            git log --pretty=format:"%h - %an, %ar : %s"

    git log --author
        显示指定作者的提交

     git log --grep
        用 --grep 选项搜索提交说明中的关键字。（请注意，如果要得到同时满足这两个选项搜索条件的提交，就必须用--all-match 选项。）

    git log -- < path >
        如果只关心某些文件或者目录的历史提交，可以在 git log 选项的最后指定它们的路径。因为是放在最后位置上的选项，
        所以用两个短划线（--）隔开之前的选项和后面限定的路径名。

    git log -(n)	
        仅显示最近的 n 条提交

    git log --since, --after	
        仅显示指定时间之后的提交。

    git log --since   |  git log --until
        下面的命令列出所有最近两周内的提交：
         git log --since=2.weeks
            你可以给出各种时间格式，比如说具体的某一天（“2008-01-15”），或者是多久以前（“2 years 1 day 3 minutes ago”）。
            --until, --before	仅显示指定时间之前的提交。
            --author	仅显示指定作者相关的提交。
            --committer	仅显示指定提交者相关的提交。

    git log --pretty="%h - %s" --author=gitster --since="2008-10-01" 
        查看 Git 仓库中，2008年10月期间，gitster 提交的但未合并的测试脚本（位于项目的 t/ 目录下的文件）



---------------



# git relog 所有操作记录: 
+ 官方文档:  https://git-scm.com/docs/git-relog    
+ 腾讯云Url: https://cloud.tencent.com/developer/section/1138645
+ git reflog <subcommand> <options>
+ git reflog [show] [log-options] [<ref>]
+ git reflog expire [--expire=<time>] [--expire-unreachable=<time>]    [--rewrite] [--updateref] [--stale-fix]    [--dry-run | -n] [--verbose] [--all [--single-worktree] | <refs>…​]
+ git reflog delete [--rewrite] [--updateref]    [--dry-run | -n] [--verbose] ref@{specifier}…​
+ git reflog exists <ref>


## git relog    
    查看所有分支的所有操作记录（包括（包括commit和reset的操作），包括已经被删除的commit记录，
    git log则不能察看已经删除了的commit记录，而且跟进结果可以回退道某一个修改


  