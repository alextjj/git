# git branch 命令:
+ 官方文档: https://git-scm.com/docs/git-branch
+ 中文Url: http://www.1ju.org/git/git-branch
+ git branch [--color[=< when >] | --no-color] [-r | -a]
    [ --list ] [-v [--abbrev=< length > | --no-abbrev]]
    [--column[=< options >] | --no-column] [--sort=< key >]
    [(--merged | --no-merged) [< commit >]]
    [--contains [< commit >]] [--no-contains [< commit >]]
    [--points-at < object >] [--format=< format >] [<pattern >…​]
+ git branch (--set-upstream-to=<upstream> | -u <upstream>) [< branchname >]
+ git branch [--set-upstream | --track | --no-track] [-l] [-f] < branchname > [< start-point >]
+ git branch --unset-upstream [< branchname >]
+ git branch (-m | -M) [< oldbranch >] <newbranch>
+ git branch (-d | -D) [-r] <branchname>…
+ git branch --edit-description [< branchname >]


## 描述
    如果給出了--list，或者如果沒有非選項參數，則列出現有的分支; 
    當前分支將以星號突出顯示。 選項-r導致遠程跟蹤分支被列出，而選項-a顯示本地和遠程分支。
    如果給出了一個<pattern>，它將被用作一個shell通配符，將輸出限制爲匹配的分支。
    如果給出多個模式，如果匹配任何模式，則顯示分支。 
    請注意，提供<pattern>時，必須使用--list; 否則命令被解釋爲分支創建。

    使用--contains，僅顯示包含命名提交的分支(換句話說，提示提交的分支是指定的提交的後代)，--no-contains會反轉它。 
    隨着已經有了，只有分支合併到命名提交(即從提交提交可以提   前提交的分支)將被列出。 
    使用--no合併只會將未合併到命名提交中的分支列出。 
    如果缺少<commit>參數，則默認爲HEAD(即當前分支的提示)。


## 参数选项   
    -d | --delete <branch name>
        删除一个分支。分支必须完全合并到它的上游分支中，
        如果没有使用——track或——set-upstream-to设置upstream分支，
        则合并到HEAD中

    -D <branch name>
        --delete --force 的快捷键

    --create-reflog
        创建分支的reflog。
        这将激活对分支ref所做的所有更改的记录，允许使用基于日期的sha1表达式，
        例如“<branchname>@{yesterday}”。
        注意，在非裸存储库中，核心通常默认启用reflogs。
        logAllRefUpdates配置选项。
        否定形式——no-create-reflog只覆盖以前的——create-reflog，
        但当前不否定core.logAllRefUpdates的设置。    

    -f | --force
        将<branchname>重置为<startpoint>，即使<branchname>已经存在。如果没有-f, git分支拒绝更改现有的分支。
        与-d(或--delete)结合使用，允许删除分支，无论其合并状态如何。
        与-m(或-- move)结合使用，允许重命名分支，即使新的分支名称已经存在，
        同样适用于-c(或——copy)

    -m | --move <oldbranch> <newbranch>
        移动/重命名 分支和该分支的reflog

    -M
        --move --force 的快捷键

    -c | --copy
        复制branch 和branch的reflog 

    -C
        --copy --force 的快捷键

    --color[=<when>]
        设置当前分支的显示颜色,三种模式(never/always/auto) 默认auto

    --no-color
        关闭分支颜色，即使配置文件提供默认颜色输出。——颜色=不一样。

    -i | --ignore-case
        排序和过滤分支不区分大小写

    --column[=< options >]
        以列显示分支列表。options分别等价于always和never。

    --no-column
        不以列显示分支列表。options分别等价于always和never。

    -r | --remotes
        查看远程所有分支列表
        结合-d 使用则为删除远程仓库的分支
        结合——list来匹配可选的模式

    -a | --all
        查看本地仓库和远程仓库的所有分支

    -l | --list
        List branches. With optional <pattern>..., e.g. git branch --list 'maint-*', list only the branches that match the pattern(s).

--show-current
Print the name of the current branch. In detached HEAD state, nothing is printed.

-v
-vv
--verbose
When in list mode, show sha1 and commit subject line for each head, along with relationship to upstream branch (if any). If given twice, print the path of the linked worktree (if any) and the name of the upstream branch, as well (see also git remote show <remote>). Note that the current worktree’s HEAD will not have its path printed (it will always be your current directory).

-q
--quiet
Be more quiet when creating or deleting a branch, suppressing non-error messages.

--abbrev=<length>
Alter the sha1’s minimum display length in the output listing. The default value is 7 and can be overridden by the core.abbrev config option.

--no-abbrev
Display the full sha1s in the output listing rather than abbreviating them.

-t
--track
When creating a new branch, set up branch.<name>.remote and branch.<name>.merge configuration entries to mark the start-point branch as "upstream" from the new branch. This configuration will tell git to show the relationship between the two branches in git status and git branch -v. Furthermore, it directs git pull without arguments to pull from the upstream when the new branch is checked out.

This behavior is the default when the start point is a remote-tracking branch. Set the branch.autoSetupMerge configuration variable to false if you want git switch, git checkout and git branch to always behave as if --no-track were given. Set it to always if you want this behavior when the start-point is either a local or remote-tracking branch.

--no-track
Do not set up "upstream" configuration, even if the branch.autoSetupMerge configuration variable is true.

--set-upstream
As this option had confusing syntax, it is no longer supported. Please use --track or --set-upstream-to instead.

-u <upstream>
--set-upstream-to=<upstream>
Set up <branchname>'s tracking information so <upstream> is considered <branchname>'s upstream branch. If no <branchname> is specified, then it defaults to the current branch.

--unset-upstream
Remove the upstream information for <branchname>. If no branch is specified it defaults to the current branch.

--edit-description
Open an editor and edit the text to explain what the branch is for, to be used by various other commands (e.g. format-patch, request-pull, and merge (if enabled)). Multi-line explanations may be used.

--contains [<commit>]
Only list branches which contain the specified commit (HEAD if not specified). Implies --list.

--no-contains [<commit>]
Only list branches which don’t contain the specified commit (HEAD if not specified). Implies --list.

--merged [<commit>]
Only list branches whose tips are reachable from the specified commit (HEAD if not specified). Implies --list.

--no-merged [<commit>]
Only list branches whose tips are not reachable from the specified commit (HEAD if not specified). Implies --list.

<branchname>
The name of the branch to create or delete. The new branch name must pass all checks defined by git-check-ref-format[1]. Some of these checks may restrict the characters allowed in a branch name.

<start-point>
The new branch head will point to this commit. It may be given as a branch name, a commit-id, or a tag. If this option is omitted, the current HEAD will be used instead.

<oldbranch>
The name of an existing branch to rename.

<newbranch>
The new name for an existing branch. The same restrictions as for <branchname> apply.

--sort=<key>
Sort based on the key given. Prefix - to sort in descending order of the value. You may use the --sort=<key> option multiple times, in which case the last key becomes the primary key. The keys supported are the same as those in git for-each-ref. Sort order defaults to the value configured for the branch.sort variable if exists, or to sorting based on the full refname (including refs/... prefix). This lists detached HEAD (if present) first, then local branches and finally remote-tracking branches. See git-config[1].

--points-at <object>
Only list branches of the given object.

--format <format>
A string that interpolates %(fieldname) from a branch ref being shown and the object it points at. The format is the same as that of git-for-each-ref[1].

