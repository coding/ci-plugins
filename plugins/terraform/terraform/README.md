# Terraform

执行 Terraform `plan` 和 `apply`。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: terraform
      image: jmccann/drone-terraform:1
      settings:
        plan: false
      targets:
        - aws_security_group.generic_sg
        - aws_security_group.app_sg
```

## 参数含义

plan
: 如果为`true`，则生成一个 plan，但是不应用。

remote
: 包含 Terraform 远程状态跟踪的配置。

remote.backend
: 要使用的 Terraform 远程状态后端。

remote.config
: 远程状态后端的配置参数映射。

vars
: 要传递给 Terraform `plan` 和 `apply` 命令的变量映射。

secrets
: 要传递给 Terraform `plan` 和 `apply` 命令的变量映射。

ca_cert
: 添加到环境中的 ca_cert。

sensitive
: 是否将 Terraform 命令输出，默认为`false`。

role_arn_to_assume
: 在运行 terraform 命令之前设定的角色。

root_dir
: Terraform 文件所在的根目录。

parallelism
: Terraform 并发数。

## 更多用法

更多用法参考：[jmccann/drone-terraform](https://github.com/jmccann/drone-terraform)。
