# grafana-annotation

在Grafana中创建注解的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: annotate
      image: fdeschenes/drone-grafana-annotation
      settings:
        api_key: xxxxx
        image: fdeschenes/drone-grafana-annotation
        tags:
          - deploy
          - production
        text: "Deployed"
        url: https://grafana.example.com

```

## 参数含义

api_key
: api key

tags
: tag 列表

text
: 描述

url
: 服务器 url

## 更多用法

更多用法参考：[fdeschenes/drone-grafana-annotation](https://github.com/fdeschenes/drone-grafana-annotation)
