一个 Vagrant 项目用来快速创建一个 ansible 实验环境，默认包含两个虚拟机，一个centos 一个ubuntu

另外对vagrant 的默认挂载权限进行了设置，方便使用外部文件（比如包含密钥的文件），否则默认的挂载会使用777之类的挂载选项。导致外部的密钥无法使用。

里面还包含了vscode 的项目配置文件，这样.yml 或者.yaml 结尾的文件会默认关联ansible 的vscode 插件，否则会默认使用yaml的语法检测（ansible 的playbook用yaml 语法检测会有较多错误或者警告）
