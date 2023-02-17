# Load and store

将镜像发布到Docker仓库的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: push-docker-image
      image: allgreed/drone-load-and-store
      settings:
        archive: docker-image.tar.gz
        repo: username/repository
        username:
          from_secret: docker_username
        password:
          from_secret: docker_password
```

## 参数含义

archive
: docker镜像archive位置

registry
: 对此注册表进行身份验证（默认值：docker.io）

username
: 使用此用户名进行身份验证

password
: 使用此密码进行身份验证

repo
: 镜像仓库名

debug
: 启用详细日志记录

## 更多用法

更多用法参考：[allgreed/drone-load-and-store](https://github.com/allgreed/drone-load-and-store)
