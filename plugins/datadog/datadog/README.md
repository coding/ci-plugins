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

## 参数含义

api_key
: The Datadog API key that'll be used to send metrics and events.

dry_run
: When set to `true`, the plugin only computes metrics and events without sending anything to the
Datadog intake. When the plugin runs in dry mode, it doesn't require an `api_key` to be set,
useful for testing.

metrics
: A list of metrics to be sent to Datadog. A metric must have a `name` and a `value`;
`type` defaults to `gauge`; `tags` and `hostname` are optional.

events
: A list of events to be sent to Datadog. An event must have a `title` and a `text`;
`alert_type` defaults to `info`.

## 更多用法

更多用法参考：[masci/drone-datadog](https://github.com/masci/drone-datadog)
