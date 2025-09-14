# vscode remote 神秘行为

在给虚拟机ssh配key, 一直报错, 错误提示找不到密钥, 一开始以为是文件路径有问题, 改来改去不行, 搜SO发现有人说可能跟私钥最后缺一个换行有关. 改完之后好了. 不知道这是谁的锅.

<https://stackoverflow.com/questions/66160457/vscode-remote-ssh-cannot-identify-private-key-file>
