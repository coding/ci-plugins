# Kaniko

调用官方 Google Kaniko 的插件。

## 在 云原生构建 上使用

```yml
main:
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
: 对此注册表进行身份验证。

username
: 使用此用户名进行身份验证。

password
: 使用此密码进行身份验证。

repo
: 镜像仓库名。

tags
: 镜像仓库tag。

dockerfile
: 要使用的dockerfile，默认为 Dockerfile。

context
: 要使用的上下文路径, 默认为 git 仓库根目录。

target
: 要使用的构建目标，必须在 dockerfile 中定义。

build_args
: 传递给 docker build 的自定义参数。

## 更多用法

更多用法参考：[banzaicloud/drone-kaniko](https://github.com/banzaicloud/drone-kaniko)。
