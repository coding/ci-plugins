# 腾讯云 COS 命令行工具

使用 COSCMD 工具，用户可通过简单的命令行指令实现对对象（Object）的批量上传、下载、删除等操作。

## 在 Docker 上使用

```shell
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) tencentcom/tencentyun-coscmd --version
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) tencentcom/tencentyun-coscmd -h
```

## 在 云原生构建 上使用

```yaml
main:
  push:
  - stages:
    - name: run with tencentyun-coscmd
      image: tencentcom/tencentyun-coscmd
      commands: |
        coscmd --version
        coscmd -h
```

## 更多用法

更多用法，参照 [COSCMD 工具][t-url]

[t-url]:https://cloud.tencent.com/document/product/436/10976
