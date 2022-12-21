# Terraform

执行Terraform plan和apply

## 在 Coding-CI 上使用

```yml
master:
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
: if true, calculates a plan but does __NOT__ apply it.

remote
: contains the configuration for the Terraform remote state tracking.

remote.backend
: the Terraform remote state backend to use.

remote.config
: a map of configuration parameters for the remote state backend.
Each value is passed as a `-backend-config=<key>=<value>` option.

vars
: a map of variables to pass to the Terraform `plan` and `apply` commands.
Each value is passed as a `-var <key>=<value>` option.

secrets
: a map of variables to pass to the Terraform `plan` and `apply` commands.
Each value is passed as a `-var <key>=<ENVVAR>` option.

ca_cert
: ca cert to add to your environment.
sensitive
: (default: `false`) - Whether or not to suppress terraform commands to stdout.

role_arn_to_assume
: A role to assume before running the terraform commands.

root_dir
: The root directory where the terraform files live.

parallelism
: The number of concurrent operations as Terraform walks its graph.

## 更多用法

更多用法参考：[jmccann/drone-terraform](https://github.com/jmccann/drone-terraform)
