生成 SSH 密钥对
如果没有密钥需要先生成，执行以下命令后一路回车即可。
ssh-keygen -t ecdsa -b 521

用法
bash <(curl -fsSL https://raw.githubusercontent.com/auto8624/ssh_key/master/cssh.sh) -og auto8624 -p 22221 -d

选项
-o- 覆盖模式，此选项在顶部有效。
-g- 从 GitHub 获取公钥，参数是 GitHub ID
-u- 从 URL 获取公钥，参数为 URL。
-f- 从本地文件中获取公钥，参数为本地文件路径。
-p- 更改 SSH 端口，参数为端口号
-d- 禁用密码登录
