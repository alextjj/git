# git init  初始仓库:
+ 官方文档: https://git-scm.com/docs/git-add

+ git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
	  [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]]
	  [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing] [--renormalize]
	  [--chmod=(+|-)x] [--pathspec-from-file=<file> [--pathspec-file-nul]]
	  [--] [<pathspec>…​]


## git add      
    该命令创建一个空的Git存储库, 本质上是一个 .git 目录，其中包含 objects、refs/heads、refs/tags`和模板文件的子目录。
    还将创建一个引用master分支 HEAD 的初始 `HEAD 文件。

    如果$GIT_DIR设置了环境变量，那么它将指定要使用的路径，而不是./.git存储库的基础。
    如果通过$GIT_OBJECT_DIRECTORY环境变量指定了对象存储目录，那么将在该目录下创建sha1目录，
    否则将使用替代的 $GIT_DIR/objects目录。
    在现有存储库中运行git init是安全的。它不会覆盖已经存在的内容。重新运行git init的主要原因 是选择新添加的模板
    （如果给定了--separate-git-dir，则将存储库移至另一个位置）。


  

  ## git add 参数选项
    -q | --quiet
        仅打印错误和警告消息；所有其他输出将不会显示。

    --bare
        创建一个纯仓库(裸仓库)。如果未设置 GIT_DIR 环境变量，则将其设置为当前工作目录。
        但是当我们想在这个文件目录下进行一些git操作的时候会出现报错： This operation must be run in a work tree。
        这个操作必须在工作树上面进行，这是因为git init –bare 生成的是一个裸仓库，是没有工作区的，只会记录git提交的历史信息，
        git log一下是可以看到各个版本信息的，但是没办法进行版本回退或者切换分支的操作，
        但是有一个好处是可以通过添加hooks钩子在仓库的同级目录下新建一个存放项目源码的文件夹，
        也就是说将git仓库与项目源码分离，这样推送的更新会马上显示到项目文件上，
        具体设置方法可以查看这篇博客
        [git仓库与项目源码分离](https://blog.csdn.net/sinat_34349564/article/details/52442526)

    --object-format=<format>
        指定存储库的对象格式（哈希算法）。有效值为 sha1 和（如果启用）sha256。sha1 是默认值。

    --template = <模板目录>
        指定要使用模板的目录。（请参见下面的“模板目录”部分。）

    --separate-git-dir=<git目录>
        并不将存储库初始化至 $GIT_DIR 或 ./.git/ 目录，而是在其中创建一个包含实际存储库路径的文本文件。
        此文件作为连接到仓库的 Git 符号链接，其与文件系统无关。
        如果为重新初始化操作，则将存储库移动到指定的路径。

    -b <branch-name> || --initial-branch=<branch-name>
        在新创建的仓库中为初始分支指定名称。如果没有指定，则使用默认名称：master。

    --shared[=(false|true|umask|group|all|world|everybody|0xxx)]
        指定 Git 存储库在多个用户之间共享。这允许属于同一组的用户推送到该存储库。指定时，
        将设置配置变量 "core.sharedRepository"，以便使用请求的权限创建 $GIT_DIR 下的文件和目录。
        未指定时，Git 将使用 umask(2) 返回的权限。

        此选项可以有以下值，如果未给定值，则默认为 group：
        umask（或 false）
            使用 umask(2) 返回的权限。未指定 --shared 时，此为默认值。

        group（或 true）
            使存储库组可写（并且 g+sx，因为 git 组可能不是所有用户的主要组）。这用于放宽原本安全的 umask(2) 值的权限。
            请注意，umask 仍然适用于其他权限位（例如，如果 umask 为 0022，则使用 group 不会删除其他（非组）用户的读取特权）。
            有关如何精确指定存储库权限的信息，请参见 0xxx。

        all （或 world 或 everybody）
            与使用 group 选项相同，但使存储库对所有用户可读。

        0xxx
            0xxx 是一个八进制数，每个文件的模式均为 0xxx。' 0xxx' 将覆盖用户的 umask(2) 值（不仅像 group 和 'all 那样放宽权限）。
            0640 将创建一个组可读取但不能组写入且其他用户无法访问的存储库。0660 将创建当前用户和组可读可写但其他用户无法访问的存储库。

        默认情况下，共享存储库中启用了配置标志 receive.denyNonFastForwards，因此您不能强制将非快速前进提交推送到其中。
        如果提供 dicrectory，则命令在其中运行。如果此目录不存在，则创建它。




##模板目录
    模板目录中名称不以点开头的文件和目录将在创建后复制到 $GIT_DIR 中。

    模板目录将是以下之一（按顺序）：

    用 --template 选项给出的参数；

    $GIT_TEMPLATE_DIR 环境变量；

    init.templateDir 配置变量；或者

    默认模板目录：/usr/share/git-core/templates。

    默认的模板目录包括一些目录结构，建议的“排除模式”（请参阅 gitignore[5]）和示例钩子文件。

    默认情况下，样例钩子都被禁用。要启用一个示例挂钩，请通过删除其后缀 .sample 对其重命名。
