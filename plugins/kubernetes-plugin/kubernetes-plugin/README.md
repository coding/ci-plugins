# Kubernetes Plugin

创建和更新K8s资源的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: deploy
      image: zc2638/drone-k8s-plugin
      pull: if-not-exists
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
: The address and port of the Kubernetes API server.

kubernetes_token
: Token from ServiceAccount for authentication to the API server.

kubernetes_ca_crt
: Certificate from ServiceAccount for authentication to the API server.

kubernetes_skip_tls
: If true, the server's certificate will not be checked for validity.

init_templates
: Path to Kubernetes Resource yaml based definition file.

templates
: Path to Kubernetes Resource yaml based definition file.

config_files
: Config file paths for automatic creation/update of ConfigMap.

namespace
: Default namespace to use when namespace is not set.

debug
: Used to enable debug level logging.

`*`
: Other parameters will be made available for interpolation.

## 更多用法

更多用法参考：[zc2638/drone-k8s-plugin](https://github.com/zc2638/drone-k8s-plugin)
