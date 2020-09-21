# git show命令:
    官网Url: https://git-scm.com/docs/git-show
    中文Url: http://www.1ju.org/git/git-show
    git show [options] <object>…​

## 描述
    顯示一個或多個對象(blobs，樹，標籤和提交)。
    對於提交，它顯示日誌消息和文本差異。 它還以git diff-tree --cc生成的特殊格式呈現合併提交。
    對於標籤，它顯示標籤消息和引用對象。
    對於樹，它顯示的名稱(相當於使用git ls-tree和--name-only選項)。  對於簡單的blobs，它顯示了普通的內容。
    該命令採用適用於git diff-tree命令的選項來控制如何顯示提交引入的更改。


## 参数选项
    --pretty[=<format>] | --format=<format>
        以给定格式漂亮地打印提交日志的内容，其中<format>可以是
            oneline，short，medium， full，fuller，reference，email，raw
            format：<string> 和tformat：<string>之一。
        如果<format>都不是上述内容，并且其中包含％placeholder，则它的作用就像 给出了--pretty = tformat：<format>一样。



  