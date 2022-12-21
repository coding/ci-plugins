# NPM Auth

通过在本地生成.npmrc文件验证公有和私有NPM仓库

## 在 Coding-CI 上使用

```yml
master:
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
: The NPM username.

npm_password
: The NPM password.

npm_email
: The NPM email.

username
: The NPM username. Required.

password
: The NPM password. Required.

email
: The NPM email. Required.

registry
: The NPM registry. Defaults to the default NPM registry.

scope
: Scope of the NPM authentication. Optional.

path
: Output path of the generated `.npmrc` file. Defaults to `./`.

## 更多用法

更多用法参考：[robertstettner/drone-npm-auth](https://github.com/robertstettner/drone-npm-auth)
