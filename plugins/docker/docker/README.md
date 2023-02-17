# Docker

在docker里面用docker构建和部署docker镜像

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: docker  
      image: plugins/docker
      settings:
        username: kevinbacon
        password: pa55word
        repo: foo/bar
        tags: latest
```

## 参数含义

registry
: 注册认证

username
: 用户名认证

password
: 密码认证

repo
: 镜像仓库

tags
: 镜像仓库tag

dockerfile
: 要使用的dockerfile的路径，默认为Dockerfile

dry_run
: 是否在最后push docker镜像，布尔值

purge
: 是否在最后清除docker镜像，布尔值

context
: 要使用的上下文路径，默认为git repo的根目录

target
: 要使用的构建target，必须在dockerfile中定义

force_tag=false
: 替换现有匹配的图像标记

insecure=false
: 允许不安全的连接

mirror
: 使用镜像注册，而不是直接从hub pull镜像

bip=false
: 用于允许桥接ip通过

custom_dns
: 为容器设置自定义DNS服务器

custom_dns_search
: docker daemon DNS 搜索域

storage_driver
: 支持 `aufs`, `overlay` 或者 `vfs` 类型存储

storage_path
: docker daemon 存储路径

build_args
: 将自定义参数传递给docker build

build_args_from_env
: 将envvars作为自定义参数传递给docker build

auto_tag=false
: 根据git branch和git tag自动生成tag

auto_tag_suffix
: 使用此后缀生成tag

debug, launch_debug
: 在verbose模式下启动docker daemon

mtu
: docker daemon 自定义mtu设置

ipv6
: docker daemon IPv6 

experimental
: docker daemon 实验模式

daemon_off
: 不启动 docker daemon

cache_from
: 要作为cache的镜像

squash
: 构建时压缩层

pull_image
: 构建时强制拉取基础镜像

compress
: 使用gzip压缩构建上下文

custom_labels
: 添加 k=v 标签

label_schema
: label-schema 标签

email
: docker email

no_cache
: 不使用缓存的 intermediate containers

add_host
: 添加 host:IP 映射

## 更多用法

更多用法参考：[drone-plugins/drone-docker](https://github.com/drone-plugins/drone-docker)
