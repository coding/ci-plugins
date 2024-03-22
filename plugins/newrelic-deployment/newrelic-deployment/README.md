# Newrelic Deployment

将部署报告记录到 dashboard。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: newrelic
      image: cityfurniture/drone-newrelic-deployment
      settings:
        api_key: <your-api-key>
        app_name: <your-app-name>
```

## 参数含义

app_id
: Newrelic APP ID。

api_key
: Newrelic API Key，在生成前验证配置文件。

## 更多用法

更多用法参考：[cityfurniture/newrelic-deployment](https://github.com/cityfurniture/newrelic-deployment)。
