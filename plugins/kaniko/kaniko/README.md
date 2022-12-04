# Kaniko

调用官方Google Kaniko的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: kaniko
      image: plugins/kaniko
      settings:
        username: kevinbacon
        password: pa55word
        repo: foo/bar
        tags: latest
```

## 参数含义

registry
: authenticates to this registry

username
: authenticates with this username

password
: authenticates with this password

repo
: repository name for the image

tags
: repository tag for the image

dockerfile
: dockerfile to be used, defaults to Dockerfile

context
: the context path to use, defaults to root of the git repo

target
: the build target to use, must be defined in the docker file

build_args
: custom arguments passed to docker build

## 更多用法

更多用法参考：[banzaicloud/drone-kaniko](https://github.com/banzaicloud/drone-kaniko)
