# git commit 命令:
+ 官方文档: https://git-scm.com/docs/git-commit
+ 中文Url: http://www.1ju.org/git/git-commit
+ git commit [-a | --interactive | --patch] [-s] [-v]
        [-u< mode >] [--amend] [--dry-run]
        [(-c | -C | --fixup | --squash) < commit >]
        [-F < file > | -m < msg >] [--reset-author] [--allow-empty]
	    [--allow-empty-message] [--no-verify] [-e]
        [--author=< author>] [--date=< date >] 
        [--cleanup=< mode >] [--[no-]status]
	    [-i | -o] [--pathspec-from-file=< file > 
        [--pathspec-file-nul]] [-S[< keyid >]] [--] [< pathspec >…​]


## 描述
    git commit命令將索引的當前內容與描述更改的用戶和日誌消息一起存儲在新的提交中。


## 参数选项   
    -a | --all
        -a 参数可以将所有已跟踪文件中的执行修改或删除操作的文件都提交到本地仓库，即使它们没有经过git add添加到暂存区，
        注意:
        新加的文件（即没有被git系统管理的文件）是不能被提交到本地仓库的。
        建议一般不要使用-a参数，正常的提交还是使用git add先将要改动的文件添加到暂存区，再用git commit 提交到本地版本库。


    --amend
         git commit --amend //也叫追加提交，它可以在不增加一个新的commit-id的情况下将新修改的代码追加到前一次的commit-id中，
            1.  假如现在版本库里最近的一版正是我们想要追加进去的版版本，
                此时是最简单的，直接修改工作区代码，然后git add,  git commit --amend,
                之后就可以直接进行git push到服务器，中间不需要进行其他的操作如git pull等
        
            2.  如果我们知道我们需要的版本与现在最近的版本中间隔着 n 个提交，
                那么我们可以直接使用git reset --hard HEAD～n命令，关于git reset 命令有详解，此时这个命令执行完后，
                运行git log -1 命令我们会发现现在版本库里最近的一版就是我们需要的那版，此时再在工作区直接修改代码，
                改完之后进行git add，再执行本git commit --amend命令，之后git push.

            3.  如果我们不知道我们需要的版本与现在最近的版本中间隔着 n 个提交，
                那么我们可以使用git log来查看版本库中的commit-id，
                找到我们需要的commit-id后，在终端中执行git reset --hard commit-id，


    --allow-empty
        允许您创建一个带有空提交消息的提交。
        这个选项绕过了安全性，主要由外部SCM接口脚本使用。   


    --allow-empty-message
        像 --allow-empty一样，这个命令主要用于外部配置管理接口脚本。
        它允许您创建一个带有空提交消息的提交，而不需要使用git-commit-tree 之类的管道命令    