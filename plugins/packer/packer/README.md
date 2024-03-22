# Packer

使用 Packer 自动化构建机器镜像。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: packer
      image: appleboy/drone-packer
      settings:
        template: aws.json
        actions: build
```

## 参数含义

actions
: packer 执行的 action 列表。

vars
: 要传递给 Packer `build` 命令的变量映射。

var_files
: 要使用的 var 文件列表，每个值都以 -var-file= `value` 传递。

except
: 验证或构建除except之外的所有构建。

only
: 仅验证或构建指定构建。

template
: json 文件，并行执行多个构建。

syntax_only
: 只检查语法，默认为 `false`。

color
: 禁用颜色输出（默认开启），默认为 `false`。

debug
: 为构建启用调试模式，默认为 `false`。

parallel
: 禁止并发执行，默认为 `false`。

force
: 如果制品存在，强制执行构建并删除之前的制品。

readable
: Machine-readable 输出，默认为 `false`。

## 更多用法

更多用法参考：[appleboy/drone-packer](https://github.com/appleboy/drone-packer)。
