# Manifest

推送Docker manifest多架构镜像文件的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: manifest
      image: plugins/manifest
      settings:
        username: kevinbacon
        password: pa55word
        target: foo/bar:v1.0.0
        template: foo/bar:v1.0.0-OS-ARCH
        platforms:
          - linux/amd64
          - linux/arm
          - linux/arm64

```

## 参数含义

username
: DockerHub认证用户名（匿名访问跳过）

password
: DockerHub认证密码（匿名访问跳过）

insecure
: 启用不安全（非 TLS）注册表支持

platforms
: 格式为 OS/ARCH 的平台列表

target
: Target image for manifest

template
: Template for manifest sources, OS and ARCH are replaced

spec
: manifest指定文件的路径

ignore_missing
: 忽略丢失的源镜像

tag, tags
: tag列表， 仅在 `spec`中使用

default_tags, auto_tag
: 使用默认/自动标签，如 Docker 插件，仅在 `spec` 中使用

## 更多用法

更多用法参考：[drone-plugins/drone-manifest](https://github.com/drone-plugins/drone-manifest)
