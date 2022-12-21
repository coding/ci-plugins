# Helm3

Helm3插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: deploy_production
      image: pelotech/drone-helm3
      settings:
        helm_command: upgrade
        chart: ./
        release: my-project
        api_server:
          from_secret: prod_api_server
        kubernetes_token:
          from_secret: prod_kubernetes_token

```

## 参数含义

mode
: Helm command to run; valid options are `upgrade`, `lint`, and `uninstall`.
: This setting was called `helm_command` prior to version 0.11.0.

update_dependencies
: Run `helm dependency update` before running the main helm command.

add_repos
: Run `helm repo add` before running the main helm command.
: This setting was called `helm_repos` prior to version 0.11.0.

repo_certificate
: Base64 encoded TLS certificate for a chart repository.

repo_ca_certificate
: Base64 encoded TLS certificate for a chart repository certificate authority.

namespace
: Kubernetes namespace for the un/installation.

debug
: Produce debug output from the plugin and helm itself.

chart
: Helm chart to install or lint.

release
: Release name to un/install.

values
: Arguments for helm's `--set` flag.

string_values
: Arguments for helm's `--set-string` flag.

values_files
: Arguments for helm's `--values` flag.

kube_api_server
: Kubernetes api server.
: This setting was called `api_server` prior to version 0.11.0.

kube_token
: Token for connecting to the kubernetes api.
: This setting was called `kubernetes_token` prior to version 0.11.0.
kube_service_account
: Account name for connecting to the kubernetes api.
: This setting was called `service_account` prior to version 0.11.0.

kube_certificate
: Base64-encoded TLS certificate, for clusters using a self-signed CA certificate
: This setting was called `kubernetes_certificate` prior to version 0.11.0.

chart_version
: Specific chart version to install.

dry_run
: Prepare the un/installation, but do not perform it.

wait_for_upgrade
: Wait until kubernetes resources are in a ready state.
: This setting was called `wait` prior to version 0.11.0.

timeout
: Timeout for any individual kubernetes operation.

force_upgrade
: Pass `--force` to `helm upgrade`.
: This setting was called `force` prior to version 0.11.0.

reuse_values
: Reuse the values from a previous release.

keep_history
: Pass `--keep-history` to `helm uninstall`.

lint_strictly
: Pass `--strict` to `helm lint`.

atomic_upgrade
: Pass `--atomic` to `helm upgrade`.

cleanup_failed_upgrade
: Pass `--cleanup-on-fail` to `helm upgrade`.

skip_tls_verify
: Do not check for a valid certificate when connecting to the kubernetes api.

## 更多用法

更多用法参考：[pelotech/drone-helm3](https://github.com/pelotech/drone-helm3)
