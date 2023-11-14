# tem-deploy-application

TEM 部署应用

## 在 Coding-CI 上使用

```yml

master:
  push:
    - stages:
      - name: tem-deploy-application
        imports: https://xxx/envs.yaml
        image: cralazy/tem_deploy_application:latest
        settings:
          secret_id: $SECRET_ID
          secret_key: $SECRET_KEY
          big_region: "China"
          application_name: "appname"
          environment_name: "env"
          coding_language: "JAVA"
          deploy_mode: "IMAGE"
          cpu_spec: 1
          memory_spec: 1024
          init_pod_num: 1
          repo_type: 0
          tcr_instance_id: "id"
          image_repo: "ccr.ccs.tencentyun.com/namespace/repo:tag"
          pkg_path: "/path"
          jdk_version: "master"
          deploy_version: "version"
          deploy_strategy_type: 0
          total_batch_count: 2
          batch_interval: 1
          min_available: 1
          beta_batch_num: 0
```

[envs.yml文件示例](https://x123456789x.coding.net/public/oci-demo-public/oci-qci-trigger-subpipeline-demo-envs/git/files/master/envs.yaml)

```yml
SECRET_ID: xxxxxx
SECRET_KEY: xxxxxx
```

## 参数

* `secret_id`：API 个人密钥 id, 请前往腾讯云 访问管理-访问密钥 获取

* `secret_key`：API 个人密钥 key, 请前往腾讯云 访问管理-访问密钥 获取

* `big_region`：所在地域。China

* `application_name`：应用名称, 支持根据名称新建应用, 或选择存量应用部署至新环境

* `environment_name`：环境名称, 若无合适环境, 请前往控制台创建 <https://console.cloud.tencent.com/tem/env>

* `coding_language`：编程语言，可选：JAVA PHP GO PYTHON NODE OTHER

* `deploy_mode`：部署方式，可选：IMAGE JAR WAR

* `cpu_spec`：CPU 规格 (单位: 核)

* `memory_spec`：内存规格 (单位: Gi)

* `init_pod_num`：初始化实例数

* `repo_type`：镜像仓库类型, 镜像部署时必填。0:个人版TCR，1:企业版TCR，2:公共镜像

* `image_repo`：镜像部署: 仓库地址，例: ccr.ccs.tencentyun.com/namespace/repo:tag, 镜像部署时必填

* `tcr_instance_id`：镜像部署: 企业版TCR实例ID，例: tcr-xxxxxxxx, 企业版TCR镜像部署时必填

* `jdk_version`：Jdk版本, Jar 包/War 包部署时必填，可选："KONA:8"，"KONA:11","OPEN:8","OPEN:11"

* `pkg_path`：Jar 包/War 包在构建环境内的文件路径, 一般为 /root/workspace/xxx, Jar 包/War 包部署时必填

* `deploy_version`：程序包版本号, Jar 包/War 包部署时必填

* `deploy_strategy_type`：发布触发策略，可选：0:自动触发，1:全手动触发，2:小批量验证后自动触发

* `total_batch_count`：发布批次数

* `batch_interval`：批次间等待时间 (单位: 秒)

* `beta_batch_num`：小批量验证批次的实例数

* `min_available`：发布过程中保障的最小可用实例数。
-1 表示发布过程中保障与当前等量的可用实例；
0 表示发布过程中不保障有服务在线；
n(n>0) 表示发布过程中保障至少有 n 个实例在线

## 更多用法

更多用法参考：[tem帮助文档](https://cloud.tencent.com/document/product/1371/52882)
