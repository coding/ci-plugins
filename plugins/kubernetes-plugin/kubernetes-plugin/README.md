# Kubernetes Plugin

创建和更新K8s资源的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: deploy
      image: zc2638/drone-k8s-plugin
      settings:
        k8s_server: https://localhost:6443
        k8s_token:
          from_secret: k8s_token
        k8s_ca_crt:
          from_secret: k8s_ca_crt
        k8s_skip_tls: false
        namespace: default
        config_files:
          - default:test-config:testdata/config.yaml
          - default:test-config:testdata/config.yaml:a.yaml
        templates:
          - testdata/deployment.yaml
          - testdata/service.yaml
        app_name: ${DRONE_REPO_NAME}
```

## 参数含义

kubernetes_server
: Kubernetes API服务器的地址和端口。

kubernetes_token
: 来自 ServiceAccount 的令牌，用于 API 服务器的身份验证

kubernetes_ca_crt
: 来自 ServiceAccount 的证书，用于向 API 服务器进行身份验证

kubernetes_skip_tls
: 如果为 true，则不会检查服务器证书的有效性

init_templates
: 基于 Kubernetes 资源 yaml 的定义文件的路径

templates
: 基于 Kubernetes 资源 yaml 的定义文件的路径

config_files
: 用于自动创建/更新 ConfigMap 的配置文件路径。

namespace
: 未设置命名空间时使用的默认命名空间。

debug
: 用于启用调试级别日志记录。

`*`
: Other parameters will be made available for interpolation.

## 更多用法

更多用法参考：[zc2638/drone-k8s-plugin](https://github.com/zc2638/drone-k8s-plugin)
