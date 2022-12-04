# gitleaks

检测git库中敏感信息的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: run gitleaks
      image: plugins/gitleaks
      settings:
        path: .

```

## 参数含义

## 更多用法

更多用法参考：[drone/drone-gitleaks](https://github.com/drone/drone-gitleaks)
