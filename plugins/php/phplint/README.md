# phplint

`phplint` 是一个可以通过一次运行几个 lint 进程来加速 PHP 文件检查的代码检查工具，
本项目主要提供了 phplint 的 Docker 镜像，主要目标是在 云原生构建 中对 PHP 代码进行检查。

## 使用方法

默认情况下，命令将会自动读取项目内的 `.phplint.yml` 进行配置。

```yaml
path: ./
jobs: 10
extensions:
  - php
exclude:
  - vendor
```

## 在 Docker 上使用

```shell
docker run --rm -t -v $(pwd):$(pwd) -w $(pwd) overtrue/phplint .
```

## 在 云原生构建 中使用

```yaml
master:
  merge_request:
  - stages:
    - name: git diff phplint
      image: overtrue/phplint
      commands: |
        phplint -h
```
