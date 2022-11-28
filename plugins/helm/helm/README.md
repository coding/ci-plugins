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

## 参数含义

### Parameter Reference

namespace
: namespace where you want to install your chart. If you don't specify this parameter, `default` namespace will be used.

chart
: chart that you want to install

release
: name used in the helm command to specify the release. If you don't specify the release, helm will generate a random name and you will not be able to upgrade that release.

values
: values injected in helm command. These are the values you want to overwrite.

prefix
: defines the prefix of all the secrets used in the plugin. If prefix is `DEV` and your secret should be named `DEV_PASSWORD` and the values would be `${PASSWORD}`. If `prefix` is `PROD` the secret should be defined as `PROD_PASSWORD`. This allows you to define different secrets for different

tiller_ns
: namespace where `tiller` will be installed. By default, `tiller` is installed in `kube-system`

debug
: very verbose output. it will display all the ENVVARS passed to the container. Very handy when debugging secrets.

skip_tls_verify
: if you create your own SSL certificates, youi will need this flag to be true to avoid having connectivity issues.

api_server
: kubernetes api server

kubernetes_token
: kubernetes token to connect to the api server

### Secret Reference

There are a few secrets that the plugin expects to be able to connect to a kubernetes cluster

: API_SERVER url to connect to the Kubernetes api server

: KUBERNETES_TOKEN Kubernetes token used to connect to the api server.

## 更多用法

更多用法参考：[ipedrazas/drone-helm](https://github.com/ipedrazas/drone-helm)
