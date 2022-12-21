# Packer

使用Packer自动化构建机器镜像

## 在 Coding-CI 上使用

```yml
master:
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
: a list of actions to have packer perform

vars
: a map of variables to pass to the Packer `build` commands.

var_files
: a list of var files to use. Each value is passed as -var-file= `value`

except
: validate or build all builds other than these

only
: validate or build only the specified builds

template
: A json file will execute multiple builds in parallel.

syntax_only
: Only check syntax. Do not verify config of the template, defaults to `false`

color
: Disable color output (on by default), defaults to `false`

debug
: Debug mode enabled for builds, defaults to `false`

parallel
: Disable parallelization (on by default), defaults to `false`

force
: Force a build to continue if artifacts exist, deletes existing artifacts.

readable
: Machine-readable output, defaults to `false`

## 更多用法

更多用法参考：[appleboy/drone-packer](https://github.com/appleboy/drone-packer)
