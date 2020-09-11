# git基础命令

## git --version
    * 显示git程序的版本号


## git --help
    * 打印概要最常用命令的列表。如果选项--all或者-a给出，则打印所有可用的命令。如果命名Git命令，此选项将显示该命令的手册页。
    * 其他选项可用于控制手册页面的显示方式。有关更多信息，请参阅git-help（1），因为git --help ...内部转换为git help ...。


## git -C < path >
    * 在<path>而不是当前的工作目录中运行git 。当-C给出多个选项时，每个后续的非绝对值-C <path>相 对于前一个解释-C <path>。
    * 此选项会影响预期的路径名的选项一样--git-dir，并 --work-tree在他们的路径名的解释，将相对于 所造成的工作目录进行-C选择。例如，以下调用是等效的：
    * git --git-dir = a.git --work-tree = b -C c status
    * git --git-dir = c / a.git --work-tree = c / b状态


## git -c < name > = < value >
    * 将配置参数传递给命令。给定的值将覆盖配置文件中的值。预期的<name>格式与git config（由点分隔的子项）列出的格式相同。
    * 注意，省略=in git -c foo.bar ...是允许的，并将其设置 foo.bar为布尔值true（就像[foo]bar在配置文件中一样）。包含equals，但空值（如git -c foo.bar= ...）设置foo.bar为空字符串。


## git --exec-path[=< path >]
    * 通向任何安装了核心Git程序的路径。这也可以通过设置GIT_EXEC_PATH环境变量来控制。如果没有给出路径，git将打印当前设置，然后退出。


## git --html-path
    * 打印Git的HTML文档安装并退出的路径，不带斜杠。


## git --man-path
    * 打印man(1)此版本Git并退出的手册页的manpath（参见）。


## git --info-path
    * 打印文件记录此Git版本的Info文件的路径，并退出。


## git -p   ||   git --paginate
    * 如果标准输出是终端，则将所有输出管道更少（或如果设置为$ PAGER）。这将覆盖pager.<cmd> 配置选项（请参阅下面的“配置机制”部分）。



## git --no-pager
    * 不要将Git输出管道传输到寻呼机。


## git --git-dir=< path >
    * 设置存储库的路径。这也可以通过设置GIT_DIR环境变量来控制。它可以是当前工作目录的绝对路径或相对路径。



## git --work-tree=< path >
    * 设置工作树的路径。它可以是相对于当前工作目录的绝对路径或相对路径。这也可以通过设置GIT_WORK_TREE环境变量和core.worktree配置变量来控制（参见git-config（1）中的core.worktree 进行更详细的讨论）。



## git --namespace=< path >
    * 设置Git命名空间。有关详细信息，请参阅gitnamespaces（7）。相当于设置GIT_NAMESPACE环境变量。


## git --super-prefix=< path >
    * 目前仅供内部使用。设置一个前缀，该前缀从存储库上方到根的路径。一个用途是给调用它的超级项目的子模块上下文。


## git --bare
    * 将存储库视为空仓库。如果GIT_DIR环境未设置，则将其设置为当前工作目录。

## git --replace
    * 

## git --no-replace-objects
    * 



## git --literal-pathspecs
    *


## --glob-pathspecs
    *


## --noglob-pathspecs
    *


## --icase-pathspecs
    *



