# SCP

通过 ssh 复制文件或者代码。

## 在 Coding-CI 上使用

```yml
main:
  push:
  - stages:
    - name: scp files
      image: appleboy/drone-scp
      settings:
        host: example.com
        username: foo
        password: bar
        port: 22
        target: /var/www/deploy/${CODING_REPO_SLUG}
        source: release.tar.gz
```

## 参数含义

host
: 目标主机名或 IP。

port
: 目标主机的 ssh 端口。

username
: 目标主机用户的帐户。

password
: 目标主机用户的密码。

key
: 用户私钥明文。

passphrase
: 用于加密私钥。

target
: 目标主机的文件夹路径。

source
: 要复制的源列表。

rm
: 在复制文件和制品前删除目标文件夹。

timeout
: ssh连接建立的超时时间。

command_timeout
: 执行命令的超时时间。

strip_components
: 删除指定数量的路径前缀。

tar_tmp_path
: 目标主机上 tar 文件的临时路径。

tar_exec
: 在目标主机上替代 tar 可执行文件。

overwrite
: 为tar文件增加 `--overwrite` flag。

proxy_host
: 代理主机名或IP。

proxy_port
: 代理主机 ssh 端口。

proxy_username
: 代理主机用户账户。

proxy_password
: 代理主机用户密码。

proxy_key
: 代理私钥明文。

proxy_key_path
: 代理私钥路径。

proxy_passphrase
: 用于加密私钥。

## 更多用法

更多用法参考：[appleboy/drone-scp](https://github.com/appleboy/drone-scp)。
