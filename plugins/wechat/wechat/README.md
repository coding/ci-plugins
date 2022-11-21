# wechat

微信发消息插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: send wecat notifications
      image: lizheming/drone-wechat
      settings:
        corpid: 
          from_secret: wechat_corpid
        corp_secret:
          from_secret: wechat_corp_secret
        agent_id: 
          from_secret: agent_id
        to_user: 111
        to_party: 112
        to_tag: ${DRONE_REPO_NAME}
        msg_url: ${DRONE_BUILD_LINK}
        safe: 1
        btn_txt: more
        title: ${DRONE_REPO_NAME}
        message: >
          {%if success %}
            build {{build.number}} succeeded. Good job.
          {% else %}
            build {{build.number}} failed. Fix me please.
          {% endif %}
```

## 参数含义

- `PLUGIN_CORPID`: 企业Id
- `WECHAT_CORPID`: `PLUGIN_CORPID` 别名
- `PLUGIN_CORP_SECRET`: 管理组的凭证密钥
- `WECHAT_CORP_SECRET`: `PLUGIN_CORP_SECRET` 别名
- `PLUGIN_AGENT_ID`: 企业应用的id，整型。可在应用的设置页面查看
- `WECHAT_AGENT_ID`: `PLUGIN_AGENT_ID` 别名
- `PLUGIN_TO_PARTY`: 部门ID列表，多个接收者用‘|’分隔，最多支持100个。
- `WECHAT_TO_PARTY`: `PLUGIN_TO_PARTY` 别名
- `PLUGIN_TO_USER`: 成员ID列表（消息接收者，多个接收者用‘|’分隔，最多支持1000个）。特殊情况：指定为@all，则向该企业应用的全部成员发送
- `WECHAT_TO_USER`: `PLUGIN_TO_USER` 别名
- `PLUGIN_TO_TAG`: 标签ID列表，多个接收者用‘|’分隔，最多支持100个。当touser为@all时忽略本参数
- `WECHAT_TO_TAG`: `PLUGIN_TO_TAG` 别名
- `PLUGIN_SAFE`:  表示是否是保密消息，0表示否，1表示是，默认0
- `PLUGIN_MSG_URL`: 点击后跳转的链接。
- `PLUGIN_BTN_TEXT`: 按钮文字。 默认为“详情”， 不超过4个文字，超过自动截断。
- `PLUGIN_TITLE`: 消息卡片标题
- `PLUGIN_MESSAGE`: 消息卡片正文，支持 Markdown。

## 更多用法

更多用法参考：[lizheming/drone-wechat](https://github.com/lizheming/drone-wechat)
