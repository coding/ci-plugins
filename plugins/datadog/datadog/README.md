# Datadog

发送 events 和 metrics 到 Datadog

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: count-pipeline
      image: masci/drone-datadog
      # https://xxx/secret.yaml中存放变量DATADOG_API_KEY
      imports: https://xxx/secret.yaml
      settings:
        api_key: $DATADOGAPIKEY
        metrics:
          - type: "count"
            name: "masci.pipelines.count"
            value: 1.0
            tags: ["project:${CODING_PROJECT_NAME}", "branch:${CODING_BRANCH}"]
```

## 参数

* `api_key`：用于发送 metrics 和 events 的 Datadog API密钥

* `dry_run`：当设置为`true`时，插件只计算 metrics 和 events，而不计算向 Datadog 入口发送任何信息

* `metrics`：要发送到 Datadog 的度量列表

* `events`：要发送到 Datadog 的事件列表。事件必须具有 `title` 和 `text`

* `alert_type`默认为`info`

## 更多用法

更多用法参考：[masci/drone-datadog](https://github.com/masci/drone-datadog)
