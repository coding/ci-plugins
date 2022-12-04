# Clair

通过Clair扫描docker镜像插件

## 在 Coding-CI 上使用

```yml
master:
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

## 参数含义

### Env Reference

  DOCKER_USERNAME
  : 通过环境变量传递`username`

  DOCKER_PASSWORD
  : 通过环境变量传递 `password`

  CLAIR_URL
  : 通过环境变量传递 `url`

  CLAIR_CA_CERT
  : 通过环境变量传递 `ca_cert`

### Parameter Reference

  url
  : Clair server URL

  username
  : Docker Registry username to download the `scan_image` from

  password
  : Docker Registry password to download the `scan_image` from

  scan_image
  : The docker image to scan.  Supports Docker Hub or private repos.

  ca_cert
  : The CA Cert to verify https with

## 更多用法

更多用法参考：[jmccann/drone-clair](https://github.com/jmccann/drone-clair)
