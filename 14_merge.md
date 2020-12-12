# git merge 命令:
+ 官方文档: https://git-scm.com/docs/git-merge
+ 中文Url: http://www.1ju.org/git/git-merge
+ git merge [-n] [--stat] [--no-commit] [--squash] [--[no-]edit]
    [-s < strategy >] [-X < strategy-option >] [-S[< keyid >]]
    [--[no-]allow-unrelated-histories]
    [--[no-]rerere-autoupdate] [-m < msg >] [< commit >…​]
+ git merge (--continue | --abort | --quit)


## 描述
    git-merge命令是用于将两个或两个以上的开发历史合并在一起的操作，通常也可写作：git merge。
    git-merge命令是用于从指定的commit(s)合并到当前分支的操作。
    注：这里的指定commit(s)是指从这些历史commit节点开始，一直到当前分开的时候。

## 警告：
    运行git-merge时含有大量的未commit文件很容易让你陷入困境，这将使你在冲突中难以回退。
    因此非常不鼓励在使用git-merge时存在未commit的文件，建议使用git-stash命令将这些未commit文件暂存起来，
    并在解决冲突以后使用git stash pop把这些未commit文件还原出来。


## 参数选项   
    -m <msg>
        设置用于创建合并节点时的提交信息。
        如果指定了--log参数，那么commit节点的短日志将会附加在提交信息里。

    --abort
        抛弃当前合并冲突的处理过程并尝试重建合并前的状态。

    --commit和--no-commit
        --commit参数使得合并后产生一个合并结果的commit节点。该参数可以覆盖--no-commit。
        --no-commit参数使得合并后，为了防止合并失败并不自动提交，能够给使用者一个机会在提交前审视和修改合并结果。

    --edit和-e以及--no-edit
        --edit和-e用于在成功合并、提交前调用编辑器来进一步编辑自动生成的合并信息。因此使用者能够进一步解释和判断合并的结果。
        --no-edit参数能够用于接受自动合并的信息（通常情况下并不鼓励这样做）。
    
    --ff命令
        --ff是指fast-forward命令。当使用fast-forward模式进行合并时，将不会创造一个新的commit节点。默认情况下，git-merge采用fast-forward模式。
        关于fast-forward模式的详细解释，请看我的另一篇文章：一个成功的Git分支模型的“关于fast forward”一节。

    --no-ff命令
        即使可以使用fast-forward模式，也要创建一个新的合并节点。这是当git merge在合并一个tag时的默认行为。

    --ff-only命令
        除非当前HEAD节点已经up-to-date（更新指向到最新节点）或者能够使用fast-forward模式进行合并，否则的话将拒绝合并，并返回一个失败状态。

    --log[=<n>]和 --no-log
        --log[=<n>]将在合并提交时，除了含有分支名以外，还将含有最多n个被合并commit节点的日志信息。
        --no-log并不会列出该信息。

    --stat, -n, --no-stat命令
        --stat参数将会在合并结果的末端显示文件差异的状态。文件差异的状态也可以在git配置文件中的merge.stat配置。
        相反，-n, --no-stat参数将不会显示该信息。

    --squash 和--no-squash
        --squash 当一个合并发生时，从当前分支和对方分支的共同祖先节点之后的对方分支节点，一直到对方分支的顶部节点将会压缩在一起，使用者可以经过审视后进行提交，产生一个新的节点。

    -s <strategy>和 --strategy=<strategy>
        -s <strategy>和 --strategy=<strategy>用于指定合并的策略。默认情况如果没有指定该参数，git将按照下列情况采用默认的合并策略：

    --verify-signatures, --no-verify-signatures
        用于验证被合并的节点是否带有GPG签名，并在合并中忽略那些不带有GPG签名验证的节点。
        
    —summary,--no-summary
        和--stat与 --no-stat相似，并将在未来版本移除。

    -q和 --quiet
        静默操作，不显示合并进度信息。

    -v和 --verbose
        显示详细的合并结果信息。

    --progress和 --no-progress
        切换是否显示合并的进度信息。如果二者都没有指定，那么在标准错误发生时，将在连接的终端显示信息。请注意，并不是所有的合并策略都支持进度报告。

    -S[<keyid>]和 --gpg-sign[=<keyid>]
        GPG签名。

 
    --[no-]rerere-autoupdate
        rerere即reuse recorded resolution，重复使用已经记录的解决方案。它允许你让 Git 记住解决一个块冲突的方法，这样在下一次看到相同冲突时，Git 可以为你自动地解决它。

    