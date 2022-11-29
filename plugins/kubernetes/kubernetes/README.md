# Kubernetes

实现kubectl apply命令的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: Deploy app
      image: danielgormly/drone-plugin-kube:0.0.1
      settings:
        template: path/to/deployment.yaml # relative to repo root
        ca: LS0tLS1... # BASE64 encoded string of the K8s CA cert
        server: https://10.0.0.20:6443 # K8s master node address
        token:
          from_secret: kubernetes_token # Service account token to a service account that can manage deployments
```

## 参数含义

ca
: Base-64 encoded string of the K8s CA cert

server
: Full url of Kubernetes API endpoint including protocol & port

kubernetes_token
: Kubernetes service account token (Not base64 encoded)

template
: Path to Kubernetes yaml based definition file (Configmap or Deployment)

configmap_file
: path to file containing data to inject in configmap (They configmap key that contains the data will be the filename)

`*`
: Other parameters will be made available for interpolation within yaml templates (upper-case will be converted to lower-case)

## 更多用法

更多用法参考：[danielgormly/drone-plugin-kube](https://github.com/danielgormly/drone-plugin-kube)
