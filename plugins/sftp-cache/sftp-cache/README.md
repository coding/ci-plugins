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
: target hostname or IP

port
: ssh port of target host

username
: account for target host user

password
: password for target host user

key
: plain text of user private key

rebuild
: boolean flag to trigger a rebuild

restore
: boolean flag to trigger a restore

ignore_branch
: boolean flag to ignore commit branch name on hash value

## 更多用法

更多用法参考：[appleboy/drone-sftp-cache](https://github.com/appleboy/drone-sftp-cache)
