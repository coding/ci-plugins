# SFTP Cache

使用 rsync 将制品缓存到中央服务器。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: restore_cache
      image: appleboy/drone-sftp-cache
      settings:
        server: example.com
        port: 22
        username: test
        password: test
        path: /var/cache/drone
        restore: true
        mount:
          - node_modules
    - name: build
      image: node:latest
      commands:
        - npm install
    - name: rebuild_cache
      image: appleboy/drone-sftp-cache
      settings:
        server: example.com
        port: 22
        username: test
        password: test
        path: /var/cache/drone
        rebuild: true
        mount:
          - node_modules
```

## 参数含义

server
: 目标主机名或 IP。

port
: 目标主机 ssh 端口。

username
: 目标主机用户账户。

password
: 目标主机用户密码。

key
: 用户私钥明文。

rebuild
: 触发重复构建的布尔值。

restore
: 触发 restore 的布尔值。

ignore_branch
: 忽略 commit 分支名的布尔值。

## 更多用法

更多用法参考：[appleboy/drone-sftp-cache](https://github.com/appleboy/drone-sftp-cache)。
