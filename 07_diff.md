# [git diff  差异对比:](https://git-scm.com/docs/git-diff)
    git diff [<options>] [<commit>] [--] [<path>…​]
    git diff [<options>] --cached [<commit>] [--] [<path>…​]
    git diff [<options>] <commit> [<commit>…​] <commit> [--] [<path>…​]
    git diff [<options>] <commit>…​<commit> [--] [<path>…​]
    git diff [<options>] <blob> <blob>
    git diff [<options>] --no-index [--] <path> <path>
   

## git diff
    显示提交、提交和工作树之间的更改
    Show changes between commits, commit and working tree, etc

    显示工作树与索引或树之间的更改、索引与树之间的更改、两棵树之间的更改、合并导致的更改、两个blob对象之间的更改或磁盘上两个文件之间的更改。
    Show changes between the working tree and the index or a tree, changes between the index and a tree,
    changes between two trees, changes resulting from a merge, changes between two blob objects,
    or changes between two files on disk.


## git diff 使用实例:
    git diff 不加参数即默认比较工作区与暂存区
        比较工作区与暂存区
    git diff --cached  [<path>...] 
        比较暂存区与最新本地版本库（本地库中最近一次commit的内容）
    git diff HEAD [<path>...]  如果HEAD指向的是master分支，那么HEAD还可以换成master
        比较工作区与最新本地版本库
    git diff commit-id  [<path>...]
        比较工作区与指定commit-id的差异    
    git diff --cached [<commit-id>] [<path>...] 
        比较暂存区与指定commit-id的差异
    git diff [<commit-id>] [<commit-id>]
        比较两个commit-id之间的差异

 ## 使用git diff打补丁:
    git diff > patch
        patch的命名是随意的，不加其他参数时作用是当我们希望将我们本仓库工作区的修改拷贝一份到其他机器上使用，
        但是修改的文件比较多，拷贝量比较大，此时我们可以将修改的代码做成补丁，
        之后在其他机器上对应目录下使用 git apply patch 将补丁打上即可
    git diff --cached > patch 
        是将我们暂存区与版本库的差异做成补丁
    git diff --HEAD > patch 
        是将工作区与版本库的差异做成补丁
    git diff Testfile > patch
        将单个文件做成一个单独的补丁

    拓展：git apply patch 应用补丁，应用补丁之前我们可以先检验一下补丁能否应用，
    git apply --check patch 如果没有任何输出，那么表示可以顺利接受这个补丁,
    另外可以使用git apply --reject patch将能打的补丁先打上，有冲突的会生成.rej文件，
    此时可以找到这些文件进行手动打补丁　


 
   
