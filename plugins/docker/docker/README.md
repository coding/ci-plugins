# docker

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
: path to the dockerfile to be used, defaults to Dockerfile

<!--
auth
: auth token for the registry
-->

dry_run
: boolean if the docker image should be pushed at the end

purge
: boolean if cleanup of the docker image should be done at the end

context
: the context path to use, defaults to root of the git repo

target
: the build target to use, must be defined in the docker file

force_tag=false
: replace existing matched image tags

insecure=false
: enable insecure communication to this registry

mirror
: use a mirror registry instead of pulling images directly from the central Hub

bip=false
: use for pass bridge ip

custom_dns
: set custom dns servers for the container

custom_dns_search
: docker daemon dns search domains

storage_driver
: supports `aufs`, `overlay` or `vfs` drivers

storage_path
: docker daemon storage path

build_args
: pass custom arguments to docker build

build_args_from_env
: pass the envvars as custom arguments to docker build

auto_tag=false
: generate tag names automatically based on git branch and git tag

auto_tag_suffix
: generate tag names with this suffix

debug, launch_debug
: launch the docker daemon in verbose debug mode

mtu
: docker daemon custom mtu setting

ipv6
: docker daemon IPv6 networking

experimental
: docker daemon Experimental mode

daemon_off
: don't start the docker daemon

cache_from
: images to consider as cache sources

squash
: squash the layers at build time

pull_image
: force pull base image at build time

compress
: compress the build context using gzip

custom_labels
: additional k=v labels

label_schema
: label-schema labels

email
: docker email

no_cache
: do not use cached intermediate containers

add_host
: additional host:IP mapping

## 更多用法

更多用法参考：[drone-plugins/drone-docker](https://github.com/drone-plugins/drone-docker)
