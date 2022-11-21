# rsync

 rsync 同步文件工具

## 在 Docker 上使用

```shell
docker run --rm -t -v $(pwd):$(pwd) -w $(pwd) drillster/drone-rsync .
```

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: rsync
      image: drillster/drone-rsync
      settings:
        key: xxx
        hosts:
          - ip1
          - ip2
        target: .
        prescript: echo 'pre script'
        script: echo 'script'
        args: args
```
