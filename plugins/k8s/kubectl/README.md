# kubectl

Kubectl 是 Kubernetes 命令行接口。通过 Kubectl 命令可以方便的管理 Kubernetes 集群。

Kubectl 同样可以管理腾讯云 tke 集群。

## 在 Coding-CI 上使用

```yml
master:
  push:
  - name: 使用 kubectl 操作腾讯 TKE
    image: bitnami/kubectl
    commaned: |
      kubectl -h
      cat ./kube-config > ~/.kube/config
      kubectl set image $POD_TYPE/$POD $CONTAINER=$IMAGE:$TAG -n $NS
```

## 参数含义

- `$POD` - pod 的名字
- `$POD_TYPE` - pod 类型，常见如 `Deployment\StatefulSet` 等
- `$CONTAINER` - pod 中容器的名字
- `$IMAGE` - 期望部署的 docker 镜像名
- `$IMAGE_TAG` - 是镜像标签

## kube-config

```yml
apiVersion: v1
clusters:
- cluster:
    certificate-authority-data: xxxx
    server: https://cls-xxxx.ccs.tencent-cloud.com
  name: cls-xxxx
contexts:
- context:
    cluster: cls-xxxx
    user: "xxxx"
  name: cls-xxxx-xxxx-context-default
current-context: cls-xxxx-xxxx-context-default
kind: Config
preferences: {}
users:
- name: "xxxx"
  user:
    client-certificate-data: xxxx
    client-key-data: xxxx
```

`kube-config` 的具体内容，可以从腾讯云控制台，集群「基本信息」中的「集群 APIServer 信息」中获取。

## 更多用法

更多用法参考：[kubernetes/kubectl](https://github.com/kubernetes/kubectl)。
