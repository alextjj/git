# git clone 克隆仓库:
+ 官方文档: https://git-scm.com/docs/git-clone
+ 腾讯文档: https://cloud.tencent.com/developer/section/1138669

+ git clone [--template=<template_directory>]
	  [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
	  [-o <name>] [-b <name>] [-u <upload-pack>] [--reference <repository>]
	  [--dissociate] [--separate-git-dir <git dir>]
	  [--depth <depth>] [--[no-]single-branch] [--no-tags]
	  [--recurse-submodules[=<pathspec>]] [--[no-]shallow-submodules]
	  [--[no-]remote-submodules] [--jobs <n>] [--sparse]
	  [--filter=<filter>] [--] <repository>
	  [<directory>]


## git clone < url > < dicName >
        * 这个命令是最基本的克隆命令，其可以从一个远程仓库中将Git仓库克隆岛本地.
        * 需要注意 第2个参数可以省略，如果省略则在本地当前目录创建一个和远程仓库名相同的目录，
        * 不省略则在本地创建的目录名即是设置的dicName值。
        * Git不只可以克隆远程仓库，也可以对本地的仓库进行克隆，但这并没有什么意义。

## git clone --local < localUrl > | git clone --l < localUrl >
        * 克隆本地仓库。

## git clone --quiet < url >
        * 克隆过程中只对错误信息进行输出。

## git clone --progress < url >
        * 克隆过程中报告进行状态。

## git clone --no-checkout < url >
        * 克隆完成后，不对当前分支进行检出。

## git clone --origin<name> < url >
        * 使用自定义的名称代替远程origin名。

## git clone --branch<name> < url >
        * 克隆仓库后直接将指定的分支检出。

## git clone --template< path >
        * 设置一个指定的模板进行克隆。

## git clone --config < key >=< value >
        * 对新克隆的仓库应用指定的配置

