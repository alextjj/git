// 本文档记录 Git的本地操作
// git  分为三个局域（工作区， 暂存区， 本地仓库）

1：初始化本地仓库   git init


2: 提交本地文件<需要两步>
    2.1：文件推送到暂存区 
        2.1.1:  将指定文件添加到暂存区          git add file
        2.1.2:  多个文件一次提交到暂存区         git add file1 file2 file3
        2.1.3:  多个文件多次提交到暂存区         git add file1   git add file2   git add file3
        2.1.4:  home目录下所有文件             git add home/*  
        2.1.5:  home目录下的所有.php文件        git add home/*.php
        2.1.6:  提交文件夹到暂存区              git add 文件夹
        2.1.7:  提交所有修改的文件到暂存区        git add .   或者 git add --all
    
    2.2：将文件提交到本地仓库

