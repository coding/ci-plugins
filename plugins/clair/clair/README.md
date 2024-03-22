# Clair

通过 Clair 扫描 docker 镜像插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: clair
      image: jmccann/drone-clair:1
      env:
        DOCKER_USERNAME: xxxxx
        DOCKER_PASSWORD: xxxxx
        CLAIR_URL: xxxxx
        CLAIR_CA_CERT: xxxxx
      settings: xxxxx
        url: http://clair.company.com
        username: johndoe
        password: mysecret
        scan_image: python:2.7
```

### 环境变量

  DOCKER_USERNAME
  : 通过环境变量传递 `username`。

  DOCKER_PASSWORD
  : 通过环境变量传递 `password`。

  CLAIR_URL
  : 通过环境变量传递 `url`。

  CLAIR_CA_CERT
  : 通过环境变量传递 `ca_cert`。

### 参数

* url：Clair 服务器 URL。

* username：Docker Registry用户名，用于下载 `scan_image`。

* password：Docker Registry密码，用于下载 `scan_image`。

* scan_image：要扫描的 docker 镜像。支持 Docker Hub 或私有仓库。

* ca_cert：用于验证 https 的 CA 证书。

## 更多用法

更多用法参考：[jmccann/drone-clair](https://github.com/jmccann/drone-clair)。
