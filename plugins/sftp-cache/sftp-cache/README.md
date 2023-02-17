# SFTP Cache

使用rsync将制品缓存到中央服务器

## 在 Coding-CI 上使用

```yml
master:
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
: 目标主机名或IP

port
: 目标主机ssh端口

username
: 目标主机用户账户

password
: 目标主机用户密码

key
: 用户私钥明文

rebuild
: 触发重复构建的布尔值

restore
: 触发restore的布尔值

ignore_branch
: 忽略commit分支名的布尔值

## 更多用法

更多用法参考：[appleboy/drone-sftp-cache](https://github.com/appleboy/drone-sftp-cache)
