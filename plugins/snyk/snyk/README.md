# Snyk

使用 snyk 扫描容器镜像漏洞。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: scan
      image: drone-plugins/drone-snyk
      # https://xxx/secret.yaml中存放变量snyk token: $SNYKTOKEN
      imports: https://xxx/secret.yaml
      settings:
          dockerfile: link to dockerfile in repo
          image: image name
          snyk: $SNYKTOKEN
          fail_on_issues: false
```

## 参数含义

```text
REGISTRY // docker registry address
USERNAME // Docker registry username
PASSWORD // Docker registry password
EMAIL    // Docker registry email
CONFIG   // Docker Auth Config
MIRROR              // Docker registry mirror
INSECURE            // Docker daemon enable insecure registries
STORAGE_DRIVER      // Docker daemon storage driver
STORAGE_PATH        // Docker daemon storage path
DAEMON_OFF          // Docker daemon is disabled (already running)
DEBUG               // Docker daemon started in debug mode
BIP                 // Docker daemon network bridge IP address
CUSTOM_DNS          // Docker daemon dns server
CUSTOM_DNS_SEARCH   // Docker daemon dns search domain
MTU                 // Docker daemon mtu setting
IPV6                // Docker daemon IPv6 networking
EXPERIMENTAL        // Docker daemon enable experimental mode
```

## 更多用法

更多用法参考：[drone-plugins/drone-snyk](https://github.com/drone-plugins/drone-snyk)。
