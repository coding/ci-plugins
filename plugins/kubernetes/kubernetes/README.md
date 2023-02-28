# Kubernetes

实现 kubectl apply 命令的插件。

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: Deploy app
      image: danielgormly/drone-plugin-kube:0.0.1
      settings:
        template: path/to/deployment.yaml
        ca: LS0tLS1... 
        server: https://10.0.0.20:6443 
        token:
          from_secret: kubernetes_token
```

## 参数含义

ca
: K8s CA 证书的 Base-64 编码字符串。

server
: : Kubernetes API的完整 url，包括协议和端口。

kubernetes_token
: Kubernetes 账号 token (非 base64)。

template
: 基于 Kubernetes yaml 的定义文件（Configmap 或 Deployment）的路径。

configmap_file
: 包含要注入 configmap 的数据的文件的路径。

`*`
: 其他参数可以在 yaml 模板中被访问到。

## 更多用法

更多用法参考：[danielgormly/drone-plugin-kube](https://github.com/danielgormly/drone-plugin-kube)。
