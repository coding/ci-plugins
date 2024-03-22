# Codecov

推送测试报告到Codecov

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: codecov
      image: robertstettner/drone-codecov
      settings:
        token: your-codacy-token
```

## 参数

* `token`：设置专用存储库令牌。必修的

* `files`：要上载的目标文件列表。可选择的

* `flags`：标记上载到组的覆盖率度量。可选择的

* `debug`：调试模式，默认为`false`

## 更多用法

更多用法参考：[robertstettner/drone-codecov](https://github.com/robertstettner/drone-codecov)
