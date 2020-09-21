# [git status命令:]
    官网Url: https://git-scm.com/docs/git-status
    中文Url: http://www.1ju.org/git/git-status
    git status [<options>…​] [--] [<pathspec>…​]

## git status:
    git status命令用於顯示工作目錄和暫存區的狀態。
    使用此命令能看到那些修改被暫存到了, 哪些沒有, 哪些文件沒有被Git tracked到。
    git status不顯示已經commit到項目歷史中去的信息。
    看項目歷史的信息要使用git log.

## 参数选项:
    -s | --short
        以短格式给出输出。

    -b | --branch
        即使以短格式显示分支和跟踪信息。

    --show-stash
        显示当前藏匿的条目数

    --long
        以长格式给出输出。这是默认值。
