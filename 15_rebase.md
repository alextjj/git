# git merge 命令:
+ 官方文档: https://git-scm.com/docs/git-rebase
+ 中文Url: http://www.1ju.org/git/git-rebase
+ git rebase [-i | --interactive] [<options>] [--exec < cmd >]
	[--onto < newbase > | --keep-base] [< upstream > [<branch>]]
+ git rebase [-i | --interactive] [<options>] [--exec < cmd >] [--onto < newbase >]
	--root [<branch>]
+ git rebase (--continue | --skip | --abort | --quit | --edit-todo | --show-current-patch)


## 描述
    git rebase命令在另一個分支基礎之上重新應用，用於把一個分支的修改合併到當前分支。


## 参数选项   
    <branch name>
        将目标分支给予HEAD,按时间线合并到 当前分支

    --continue
        解决合并冲突后，重新启动重新基准化过程。

    --abort
        终止变基操作并将HEAD重置为原始分支。如果在开始基准操作时提供了<branch>，则HEAD将重置为<branch>。
        否则，HEAD将被重置为开始变基操作时的位置。

    --quit
        中止rebase操作，但是HEAD不会重置回原始分支。结果，索引和工作树也保持不变。
        如果使用--autostash创建了一个临时存储项，它将被保存到存储列表中