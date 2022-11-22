# clair

通过Clair扫描docker镜像插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: clair
      image: jmccann/drone-clair:1
      settings:
        url: http://clair.company.com
        username: johndoe
        password: mysecret
        scan_image: python:2.7
```

## 参数含义

# Secret Reference

  DOCKER_USERNAME
  : paired with `username` - The username to authenticate to the docker registry with

  DOCKER_PASSWORD
  : paired with `password` - The password to authenticate to the docker registry with

  CLAIR_URL
  : paired with `url` - Clair server URL

  CLAIR_CA_CERT
  : paired with `ca_cert` - The CA Cert to verify https with

# Parameter Reference

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
