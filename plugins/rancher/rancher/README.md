# Rancher

在Rancher 1.x部署或者更新项目

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: publish
      image: pelotech/drone-rancher
      settings:
        url: http://awesomehost:awesomeport
        access_key: superaccesskey
        secret_key: supersecretkey
        service: huh/service1
        docker_image: huh/hello
```

## 参数含义

url
: rancher server 主机地址

access_key
: rancher 环境访问密钥

secret_key
: rancher 环境密钥

service
: 环境要升级的rancher service

start_first
: 在停止旧容器之前启动新容器，默认为 true

confirm
: 服务升级成功后自动确认，默认为false

timeout
: 服务升级的最大等待时间，以秒为单位，默认为 30

docker_image
: 用于升级环境的docker镜像

interval_millis
: 容器升级之间的间隔（以毫秒为单位）

batch_size
: 服务升级的粒度大小

## 更多用法

更多用法参考：[josmo/drone-rancher](https://github.com/josmo/drone-rancher)
