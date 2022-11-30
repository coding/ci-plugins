# Webhook

通过webhook发送构建状态通知

## 在 Coding-CI 上使用

```yml
master:
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
: Payload gets sent to this list of URLs

username
: Username for basic auth

password
: Password for basic auth

method
: HTTP submission method, defaults to POST

content_type
: Content type, defaults to application/json

template
: Custom template for webhook

headers
: Map of custom headers

skip_verify
: Skip SSL verification

debug
: Enable debug information

## 更多用法

更多用法参考：[drone-plugins/drone-webhook](https://github.com/drone-plugins/drone-webhook)
