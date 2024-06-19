# Manifest

推送 Docker manifest 多系统架构镜像文件的插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: manifest
      image: plugins/manifest
      settings:
        username: your-registry-usernname
        password: your-registry-password
        target: foo/bar:v1.0.0
        template: foo/bar:v1.0.0-OS-ARCH
        platforms:
          - linux/amd64
          - linux/arm64

```

通过上面的配置，可以在 DockerHub 给 `foo/bar` 打上 `v1.0.0` 标签，并且 `v1.0.0` 跟 DockerHub 上这两个标签的镜像关联：

- foo/bar:v1.0.0-linux-amd64
- foo/bar:v1.0.0-linux-arm64

执行 `docker pull foo/bar:v1.0.0` 时会基于运行环境的系统架构，拉取对应的镜像。

## 参数含义

username
: 注册表（例如 DockerHub）认证用户名（匿名访问跳过）

password
: 注册表认证密码（匿名访问跳过）

insecure
: 启用不安全（非 TLS）注册表支持

platforms
: 格式为 OS/ARCH 的系统架构列表，它会基于 `template` 模板生成 `target` 要关联的镜像列表

target
: manifest 目标镜像

template
: 关联镜像的名称模板，模板中的 OS 和 ARCH 字符串会被替换成具体系统和架构

ignore_missing
: 忽略丢失的源镜像

## 原理

使用 [manifest-tool](https://github.com/estesp/manifest-tool)
修改镜像的 [docker manifest](https://docs.docker.com/engine/reference/commandline/manifest/)，
docker 拉取镜像时，就可以根据 manifest 内容拉取运行环境对应架构的镜像。

## 更多用法

更多用法参考：[drone-plugins/drone-manifest](https://github.com/drone-plugins/drone-manifest)

注意：该插件由 drone 提供，它提供的 `spec` 参数用法，只适用于 drone 环境。
