# Datadog

发送events和metrics到Datadog

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: count-pipeline
      image: masci/drone-datadog
      settings:
        api_key:
          from_secret: datadog_api_key
        metrics:
          - type: "count"
            name: "masci.pipelines.count"
            value: 1.0
            tags: ["project:${DRONE_REPO_NAME}", "branch:${DRONE_BRANCH}"]
```

## 参数

* `api_key`：用于发送metrics和events的Datadog API密钥。

* `dry_run`：当设置为`true`时，插件只计算metrics和events，而不计算向Datadog入口发送任何信息。

* `metrics`：要发送到Datadog的度量列表。

* `events`：要发送到Datadog的事件列表。事件必须具有`title`和`text`；

* `alert_type`默认为`info`。

## 更多用法

更多用法参考：[masci/drone-datadog](https://github.com/masci/drone-datadog)
