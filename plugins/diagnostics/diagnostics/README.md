# diagnostics

用来诊断构建中问题的带cli工具的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: run plugins/drone-diagnostics plugin
      image: plugins/drone-diagnostics
      commands:
        - env
        - ping www.github.com -w 5
        - traceroute -T -p 443 www.github.com
        - dig www.apple.com
        - echo "end of test"
```

## 参数

已安装的工具:

- ping
- traceroute
- dig

## 更多用法

更多用法参考：[drone-plugins/drone-diagnostics](https://github.com/drone-plugins/drone-diagnostics)
