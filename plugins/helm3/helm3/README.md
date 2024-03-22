# Helm3

Helm3 插件

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: deploy_production
      image: pelotech/drone-helm3
      # https://xxx/secret.yaml中存放变量KUBE_API_SERVER和KUBE_TOKEN
      imports: https://xxx/secret.yaml
      settings:
        helm_command: upgrade
        chart: ./
        release: my-project
        api_server: $KUBE_API_SERVER
        kubernetes_token: $KUBE_TOKEN

```

## 参数

mode
: 要运行的 Helm 命令；有效选项为`upgrade`、`lint` 和 `uninstall`。此设置在版本0.11.0之前称为“helm_command”。

update_dependencies
: 在运行主helm命令之前运行 `helm dependency update`。

add_repos
: 在运行主helm命令之前运行 `helm repo add`。此设置在版本0.11.0之前称为“helm_repos”。

repo_certificate
: chart 仓库的 Base64 编码TLS证书。

repo_ca_certificate
: chart 仓库证书颁发机构的 Base64 编码TLS证书。

namespace
: 安装/卸载的 Kubernetes namespace。

debug
: 生成 plugin 和 helm 自身的 debug 输出。

chart
: 部署安装用到的 chart。

release
: 安装/卸载的 Release 名称。

values
: Arguments for helm's `--set` flag。

string_values
:参数用于helm的`--set-string`标志。

values_files:
参数用于helm的`--values`标志。

kube_api_server
:Kubernetes api服务器。此设置在版本0.11.0之前称为 `api_server`。

kube_token
:用于连接Kubernetes api的令牌。此设置在版本0.11.0之前称为 `kubernetes_token`。

kube_service_account
:用于连接Kubernetes api的帐户名称。此设置在版本0.11.0之前称为 `service_account`。

kube_certificate
:基于64位编码的TLS证书，用于使用自签名CA证书的集群。此设置在版本0.11.0之前称为 `kubernetes_certificate`。

chart_version
:要安装的特定chart版本。

dry_run
:准备安装/卸载，但不执行它。

wait_for_upgrade
:等待Kubernetes资源处于就绪状态。此设置在版本0.11.0之前称为 `wait`。

timeout
:任何单个Kubernetes操作的超时时间。

force_upgrade
:将 `--force` 传递给 `helm upgrade`。此设置在版本0.11.0之前称为 `force`。

reuse_values
:重用以前发布的值。

keep_history
:将 `--keep-history` 传递给 `helm uninstall`。

lint_strictly
:将 `--strict` 传递给 `helm lint`。

atomic_upgrade
:将 `--atomic` 传递给 `helm upgrade`。

cleanup_failed_upgrade
:将 `--cleanup-on-fail` 传递给 `helm upgrade`。

skip_tls_verify
:连接到Kubernetes api时不检查有效证书。

## 更多用法

更多用法参考：[pelotech/drone-helm3](https://github.com/pelotech/drone-helm3)。
