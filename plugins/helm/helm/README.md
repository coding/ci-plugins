# Helm

部署 Helm chart 的插件。

## 在 云原生构建 上使用

```yml
main:
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
: 要安装 chart 的 namespace。

chart
: 要安装的chart

release
: helm 命令中用于指定 release 的名称。

values
: 在 helm 命令中要注入的values，注入的值会被覆盖。

prefix
: 定义插件中使用的所有的secret前缀。

tiller_ns
: 安装 `tiller` 的 namespace。

debug
: 非常详细的输出。

skip_tls_verify
: 如果创建自己的 SSL 证书，需要此标志为真，以避免出现连接问题。

api_server
: kubernetes api server。

kubernetes_token
: 用于连接api server 的 kubernetes token。

## 更多用法

更多用法参考：[ipedrazas/drone-helm](https://github.com/ipedrazas/drone-helm)。
