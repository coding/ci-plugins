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
: location of the docker image archive

registry
: authenticates to this registry (default: docker.io)

username
: authenticates with this username

password
: authenticates with this password

repo
: repository name for the image

debug
: enable verbose logging

## 更多用法

更多用法参考：[allgreed/drone-load-and-store](https://github.com/allgreed/drone-load-and-store)
