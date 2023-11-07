# trigger-codingci-sub-pipeline

触发coding CI流水线运行

## 在 Coding-CI 上使用

```yml

master:
  push:
    - stages:
      - name: trigger sub pipeline
        imports: https://xxx/envs.yml
        image: cralazy/coding:v2
        settings:
          job_id: 2726281
          reftype: "branch"
          revision: "master"
          envs: "env=env"
```

## 参数

* `job_id`：coding构建计划job id

* `reftype`：checkout类型，可选分支名branch或者revision

* `revision`：分支名/版本号

* `envs`：流水线环境变量


