# Wechat for Work

通过企业微信发送构建状态通知

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: wechat
      image: clem109/drone-wechat
      settings:
        corpid: corpid
        corp_secret: secret
        agent_id: 1234567
        title: ${DRONE_REPO_NAME}
        description: "Build Number: ${DRONE_BUILD_NUMBER} failed. ${DRONE_COMMIT_AUTHOR} please fix. Check the results here: ${DRONE_BUILD_LINK} "
        msg_url: ${DRONE_BUILD_LINK}
        btn_txt: btn
```

## 参数含义

* `corpid` - The corpid for authorization
* `corp_secret` - The corp secret for authorization
* `agent_id` - The agent id to send the message
* `to_party` - The party ids to send the message
* `to_user` - The user ids to send the message to
* `to_tag` - The tag ids to send the message to
* `title` - Title of the card
* `description` - Text description of the card
* `msg_url` - The agent id to send the message
* `btntxt` - The text for the button on the card

## 更多用法

更多用法参考：[clem109/drone-wechat](https://github.com/clem109/drone-wechat)
