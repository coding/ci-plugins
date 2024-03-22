# wechat

微信发消息插件。

## 在 云原生构建I 上使用

```yml
main:
  push:
  - stages:
    - name: send wecat notifications
      image: lizheming/drone-wechat
      settings:
        corpid: wechat_corpid
        corp_secret: wechat_corp_secret
        agent_id: agent_id 
        to_user: 111
        to_party: 112
        to_tag: ${CODING_REPO_NAME}
        msg_url: ${CODING_BUILD_WEB_URL}
        safe: 1
        btn_txt: more
        title: ${CODING_REPO_NAME}
        message: >
          succeeded. Good job.
```

## 参数含义

- `corpid`: 企业Id。
- `corp_secret`: 管理组的凭证密钥。
- `agent_id`: 企业应用的id，整型。可在应用的设置页面查看。
- `to_party`: 部门ID列表，多个接收者用‘|’分隔，最多支持100个。
- `to_user`: 成员ID列表（消息接收者，多个接收者用‘|’分隔，最多支持1000个）。特殊情况：指定为@all，则向该企业应用的全部成员发送。
- `to_tag`: 标签ID列表，多个接收者用‘|’分隔，最多支持100个。当touser为@all时忽略本参数。
- `safe`:  表示是否是保密消息，0表示否，1表示是，默认0。
- `msg_url`: 点击后跳转的链接。
- `btn_text`: 按钮文字。 默认为“详情”， 不超过4个文字，超过自动截断。
- `title`: 消息卡片标题。
- `message`: 消息卡片正文，支持 Markdown。

## 更多用法

更多用法参考：[lizheming/drone-wechat](https://github.com/lizheming/drone-wechat)。

注意：该插件由提供的 message 模板变量，在 Coding-CI 不可用。
