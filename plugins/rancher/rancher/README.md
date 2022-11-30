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
: rancher server host url

access_key
: rancher environment access key

secret_key
: rancher environment secret key

service
: rancher service on that environment to upgrade

start_first
: start new container before stopping old one, default to true

confirm
: auto confirm the service upgrade if successful, defaults to false

timeout
: the maximum wait time in seconds for the service to upgrade, default to 30

docker_image
: docker image to use to upgrade the environment

interval_millis
: interval in milliseconds between upgrades of the containers

batch_size
: batch size for the service upgrade

## 更多用法

更多用法参考：[josmo/drone-rancher](https://github.com/josmo/drone-rancher)
