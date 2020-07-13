#git本地仓库相关命令
###本文档记录 Git的本地操作
####git  分为三个局域（工作区， 暂存区， 本地仓库）

+ 1：初始化本地仓库   git init

+ 2: 提交本地文件<需要两步>
    + 2.1：文件推送到暂存区 
        + 2.1.1:  将指定文件添加到暂存区&emsp;&emsp;&emsp;git add file
        + 2.1.2:  多个文件一次提交到暂存区 &emsp;&emsp;git add file1 file2 file3
        +  2.1.3:  多个文件多次提交到暂存区 &emsp;&emsp;git add file1   git add file2   git add file3
        + 2.1.4:  home目录下所有文件&emsp;&emsp;&emsp;&emsp;&emsp;git add home/*  
        + 2.1.5:  home目录下的所有.php文件 &emsp;&emsp;git add home/*.php
        + 2.1.6:  提交文件夹到暂存区&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;git add 文件夹
        + 2.1.7:  提交所有修改的文件到暂存区&emsp;&emsp;git add .   或者 git add --all
    
    + 2.2：将文件提交到本地仓库 commit
        + 2.2.1   git commit -m "message" &emsp;-m 参数表示可以直接输入后面的“message”，如果不加 -m参数，那么是不能直接输入message的，而是会调用一个编辑器一般是vim来让你输入这个message。
        + 2.2.2   git commit -m `msg1 msg2 ... `&emsp;用于提交很长的message
        + 2.2.3   git commit -a -m "msg1"&emsp;其他功能如-m参数，加的-a参数可以将所有已跟踪文件中的执行修改或删除操作的文件都提交到本地仓库，即使它们没有经过git add添加到暂存区(新添加的文件必须git add 有才有效)
        + 2.2.4   git commit --amend&emsp;也叫追加提交， 将本次的修改提交的提交到上一次的commmit中，不会新增 commit id
        + 2.2.5   git commit --allow-empty-message -m ''&emsp;不带message的commit <非正常操作  慎用>

        

