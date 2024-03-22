# Wechat for Work

通过企业微信发送构建状态通知。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: wechat
      image: clem109/drone-wechat
      settings:
        corpid: corpid
        corp_secret: secret
        agent_id: 1234567
        title: ${CODING_REPO_NAME}
        description: "hello"
        msg_url: ${CODING_BUILD_WEB_URL}
        btn_txt: btn
```

## 参数含义

* `corpid` - 授权的 corpid。
* `corp_secret` - 授权的corp secret。
* `agent_id` - 发送消息的代理 ID。
* `to_party` - 发送消息的组织 ID。
* `to_user` - 要将消息发送到的用户 ID。
* `to_tag` - 要将消息发送到的tag ID。
* `title` - 消息的标题。
* `description` - 消息的文字描述。
* `msg_url` - 发送消息的代理 ID。
* `btntxt` - 消息按钮上的文本。

## 更多用法

更多用法参考：[clem109/drone-wechat](https://github.com/clem109/drone-wechat)。
