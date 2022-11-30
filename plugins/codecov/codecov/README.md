# Codecov

推送测试报告到Codecov

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: codecov
      image: robertstettner/drone-codecov
      settings:
        token: your-codacy-token
```

## 参数含义

- `token`: set the private repository token. Required.
- `files`: list of target files to upload. Optional.
- `flags`: flag the upload to group coverage metrics. Optional.
- `debug`: debug mode, defaults to `false`.

## 更多用法

更多用法参考：[robertstettner/drone-codecov](https://github.com/robertstettner/drone-codecov)
