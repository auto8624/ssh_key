##

## 一.用法

生成 SSH 密钥对  
如果没有密钥需要先生成，执行以下命令后一路回车即可。

```
ssh-keygen -t ecdsa -b 521
```


> 
> **TIPS：** 此方法适用于 Win­dows 10 (1803后)的 Pow­er­Shell 或 WSL，Linux 发行版和 ma­cOS 自带的终端，但不仅限于这些环境。
> **科普：** 521 位的 ECDSA 密钥比起 RSA 密钥更安全且验证速度更快。
> 

操作完后会在 `~/.ssh` 目录中生两个密钥文件，`id_ecdsa` 为私钥，`id_ecdsa.pub` 为公钥。公钥就是我们需要安装在远程主机上的。

> 

**科普：**`~`符号代表**用户主目录**，俗称**家目录**。其路径与当前登陆的用户有关，在 Linux 中普通用户家目录的路径是`/home/用户名`，而 root 用户是`/root`。Win­dows 10 中路径是`C:\Users\用户名`。在 ma­cOS 中路径是`/Users/用户名`。
  



### 二.安装公钥

#### 1.从 GitHub 获取公钥

在 [GitHub密钥管理页面](https://github.com/settings/keys) 添加公钥，比如我的用户名是 `auto8624`，那么在主机上输入以下命令即可：

```
bash <(curl -fsSL [https://raw.githubusercontent.com/auto8624/ssh_key/master/cssh.sh](https://raw.githubusercontent.com/auto8624/ssh_key/master/cssh.sh)) -og auto8624 -p 22221 -d
```


#### 2.从 URL 获取公钥

把公钥上传到网盘，通过网盘链接获取公钥：

```language-none
bash <(curl -fsSL https://raw.githubusercontent.com/auto8624/ssh_key/master/cssh.shhttps://raw.githubusercontent.com/auto8624/ssh_key/master/cssh.sh) -u https://p3terx.com/key.pub
```


## 选项

- `-o`- 覆盖模式，此选项在顶部有效。
- `-g`- 从 GitHub 获取公钥，参数是 GitHub ID
- `-u`- 从 URL 获取公钥，参数为 URL。
- `-f`- 从本地文件中获取公钥，参数为本地文件路径。
- `-p`- 更改 SSH 端口，参数为端口号
- `-d`- 禁用密码登录

 
