# Webhook

通过 webhook 发送构建状态通知。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: send
      image: plugins/webhook
      settings:
        username: myusername
        password: mypassword
        urls: https://your.webhook/...
        content_type: application/json
        template: |
          {
            "owner": "{{ repo.owner }}",
            "repo": "{{ repo.name }}",
            "status": "{{ build.status }}",
          }
```

## 参数含义

urls
: 要发送的地址列表。

username
: basic auth 用户名。

password
: basic auth 密码。

method
: HTTP 请求方式，默认 POST。

content_type
: 内容类型，默认为 application/json。

template
: webhook自定义模版。

headers
: 自定义header映射。

skip_verify
: 跳过SSL verification。

debug
: 启用调试信息。

## 更多用法

更多用法参考：[drone-plugins/drone-webhook](https://github.com/drone-plugins/drone-webhook)。
