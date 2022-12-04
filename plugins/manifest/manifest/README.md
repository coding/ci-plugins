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
: Username for DockerHub authentication (Skip for anonymous access)

password
: Password for DockerHub authentication (Skip for anonymous access)

insecure
: Enable insecure (not TLS) registry support

platforms
: List of platforms in format OS/ARCH

target
: Target image for manifest

template
: Template for manifest sources, OS and ARCH are replaced

spec
: Path to a manifest specification file

ignore_missing
: Ignore missing source images

tag, tags
: List of tags, only used within `spec`

default_tags, auto_tag
: Use default/auto tags like the Docker plugin, only used within `spec`

## 更多用法

更多用法参考：[drone-plugins/drone-manifest](https://github.com/drone-plugins/drone-manifest)
