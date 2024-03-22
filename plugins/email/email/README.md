# email

通过 email 发送构建消息的插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: notify
      image: drillster/drone-email
      settings:
        host: smtp.some-server.com
        username: foo
        password: bar
        from: drone@your-domain.com
```

## 参数

from
: 从此地址发送通知。

host
: SMTP服务器主机。

port
: SMTP服务器主机 `587`。

username
: SMTP 用户名。

password
: SMTP 密码。

skip_verify
: 跳过证书验证，默认为 `false`。

recipients
: 发送此邮件的收件人列表。

recipients_file
: 用于加载其他收件人的文件名。

recipients_only
: 不将邮件发送给提交作者，而只发送给收件人，默认为 `false`。

subject
: subject 行模版。

body
: 电子邮件正文模板。

attachment
: 附加到已发送邮件的可选文件。

## 更多用法

更多用法参考：[drillster/drone-email](https://github.com/drillster/drone-email)。
