# diagnostics

一个 cli 工具插件，用于诊断构建过程中出现的问题。

## 在 云原生构建 上使用

插件内置了一些诊断工具，可以用命令行来调用它们。

内置的工具：

- ping
- traceroute
- dig

```yml
main:
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

## 更多用法

更多用法参考：
[drone-plugins/drone-diagnostics](https://github.com/drone-plugins/drone-diagnostics)。
