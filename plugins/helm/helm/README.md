# Helm

Helm插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: helm_deploy
      image: fpedrazas/drone-helm
      settings:
        skip_tls_verify: true
        chart: ./charts/my-chart
        release: ${DRONE_BRANCH}
        values: secret.password=${SECRET_PASSWORD},image.tag=${TAG}
        prefix: STAGING
        namespace: development

```

## 参数

namespace
: 要安装chart的namespace

chart
: 要安装的chart

release
: helm命令中用于指定release的名称.

values
: 在helm命令中要注入的values，注入的值会被覆盖

prefix
: 定义插件中使用的所有的secret前缀

tiller_ns
: 安装 `tiller` 的namespace

debug
: 非常详细的输出

skip_tls_verify
: 如果创建自己的SSL证书，需要此标志为真，以避免出现连接问题

api_server
: kubernetes api server

kubernetes_token
: 用于连接api server的kubernetes token

## 更多用法

更多用法参考：[ipedrazas/drone-helm](https://github.com/ipedrazas/drone-helm)
