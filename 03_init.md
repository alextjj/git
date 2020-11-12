# git init  初始仓库:
+ 官方文档: https://git-scm.com/docs/git-init
+ git init [-q | --quiet] [--bare] [--template=<template_directory>]
	  [--separate-git-dir <git dir>] [--object-format=<format>]
	  [-b <branch-name> | --initial-branch=<branch-name>]
	  [--shared[=<permissions>]] [directory]

## git init
    * 主要用来初始化一个空的git本地仓库。执行完上面的命令，当前目录下会自动生成.git隐藏文件夹，该隐藏文件夹就是git版本库

## git init --bare
    * 创建一个所谓的裸仓库，之所以叫裸仓库是因为这个仓库只保存git历史提交的版本信息，
    * 而不允许用户在上面进行各种git操作，如果你硬要操作的话，
    * 只会得到错误（”This operation must be run in a work tree”）
    * 这个就是最好把远端仓库初始化成bare仓库的原因。
