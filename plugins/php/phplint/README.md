# phplint

`phplint` 是一个可以通过一次运行几个 lint 进程来加速 PHP 文件检查的代码检查工具，

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
# .cnb.yml
main:
  pull_request:
  - stages:
    - name: git diff phplint
      image: overtrue/phplint
      commands: |
        phplint -h
```

## 在 Coding-CI 中使用

```yaml
# .coding-ci.yml
master:
  merge_request:
  - stages:
    - name: git diff phplint
      image: overtrue/phplint
      commands: |
        phplint -h
```
