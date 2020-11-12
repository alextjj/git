# git grep  查找匹配的行:
+ 官方文档: https://git-scm.com/docs/git-grep
+ git grep [-a | --text] [-I] [--textconv] [-i | --ignore-case] [-w | --word-regexp]
	   [-v | --invert-match] [-h|-H] [--full-name]
	   [-E | --extended-regexp] [-G | --basic-regexp]
	   [-P | --perl-regexp]
	   [-F | --fixed-strings] [-n | --line-number] [--column]
	   [-l | --files-with-matches] [-L | --files-without-match]
	   [(-O | --open-files-in-pager) [<pager>]]
	   [-z | --null]
	   [ -o | --only-matching ] [-c | --count] [--all-match] [-q | --quiet]
	   [--max-depth <depth>] [--[no-]recursive]
	   [--color[=<when>] | --no-color]
	   [--break] [--heading] [-p | --show-function]
	   [-A <post-context>] [-B <pre-context>] [-C <context>]
	   [-W | --function-context]
	   [--threads <num>]
	   [-f <file>] [-e] <pattern>
	   [--and|--or|--not|(|)|-e <pattern>…​]
	   [--recurse-submodules] [--parent-basename <basename>]
	   [ [--[no-]exclude-standard] [--cached | --no-index | --untracked] | <tree>…​]
	   [--] [<pathspec>…​]

    可以使用 git help grep 来查看帮助


## git grep 使用实例:
    git grep -n "target string"
        在git仓库中查找"target string"出现在哪些文件里, 支持正则查找
        
    git grep --count "target string"
        只会显示在哪些文件里有几个要查找的字符串

    git grep --break --heading -n "target string"    
        排版显示  -n 查找到的信息

    git grep -n -w "target string"
        -w 全词匹配查找




  