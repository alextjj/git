# git branch 命令:
+ 官方文档: https://git-scm.com/docs/git-branch
+ 中文Url: http://www.1ju.org/git/git-branch
+ git branch [--color[=<when>] | --no-color] [-r | -a]
    [--list] [-v [--abbrev=<length> | --no-abbrev]]
    [--column[=<options>] | --no-column] [--sort=<key>]
    [(--merged | --no-merged) [<commit>]]
    [--contains [<commit]] [--no-contains [<commit>]]
    [--points-at <object>] [--format=<format>] [<pattern>…​]
+ git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
+ git branch [--set-upstream | --track | --no-track] [-l] [-f] <branchname> [<start-point>]
+ git branch --unset-upstream [<branchname>]
+ git branch (-m | -M) [<oldbranch>] <newbranch>
+ git branch (-d | -D) [-r] <branchname>…
+ git branch --edit-description [<branchname>]


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
    --pretty[=<format>] | --format=<format>
        以给定格式漂亮地打印提交日志的内容，其中<format>可以是
            oneline，short，medium， full，fuller，reference，email，raw
            format：<string> 和tformat：<string>之一。
        如果<format>都不是上述内容，并且其中包含％placeholder，则它的作用就像 给出了--pretty = tformat：<format>一样。

