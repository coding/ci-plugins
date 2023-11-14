# trigger-cci-subpipeline

触发Coding-CI流水线运行

## 在 Coding-CI 上使用

```yml

master:
  push:
    - stages:
      - name: trigger sub pipeline
        imports: https://xxx/envs.yml
        image: cralazy/trigger_codingci_subpipeline:latest
        settings:
          job_id: 2726281
          reftype: "branch"
          revision: "master"
          envs: "env=env"
```

[envs.yml文件示例](https://x123456789x.coding.net/public/oci-demo-public/oci-qci-trigger-subpipeline-demo-envs/git/files/master/envs.yaml)

```yml
PROJECT_TOKEN: xxxxxx
CCI_CURRENT_WEB_PROTOCOL: https
CCI_CURRENT_DOMAIN: coding.net
CCI_CURRENT_TEAM: your_domain
PROJECT_ID: "1111111"
PROJECT_NAME: plugins
CCI_JOB_NAME: trigger sub pipeline
```

## 参数

* `job_id`：coding构建计划job id

* `reftype`：checkout类型，可选分支名branch或者revision

* `revision`：分支名/版本号

* `envs`：流水线环境变量
