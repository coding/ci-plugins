# NPM Auth

通过在本地生成 .npmrc 文件验证公有和私有 NPM 仓库。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: npm-auth
      image: robertstettner/drone-npm-auth
      settings:
        username: joebloggs
        password: mypass
        email: jb@me.com
```

## 参数含义

npm_username
: NPM 用户名。

npm_password
: NPM 密码。

npm_email
: NPM 邮件。

username
: NPM 用户名，必选。

password
: NPM 密码，必选。

email
: NPM 邮件，必选。

registry
: NPM 注册表。

scope
:  NPM authentication 范围，可选。

path
: 生成的 .npmrc 文件的输出路径，默认为 `./`。

## 更多用法

更多用法参考：[robertstettner/drone-npm-auth](https://github.com/robertstettner/drone-npm-auth)。
