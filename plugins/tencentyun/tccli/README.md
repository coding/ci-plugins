# 腾讯云命令行工具(TCCLI)

通过腾讯云命令行工具，您可以快速轻松的调用腾讯云 API来管理您的腾讯云资源。

## 在 Docker 上使用

```shell
docker run --rm -it tencentcom/tencentcloud-cli --version
docker run --rm -it tencentcom/tencentcloud-cli help
```

## 在 云原生构建 上使用

```yaml
main:
  push:
  - stages:
    - name: run with tencentcloud-cli
      image: tencentcom/tencentcloud-cli
      commands: |
        tccli --version
        tccli help
```
