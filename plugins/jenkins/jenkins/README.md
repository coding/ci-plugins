# Jenkins

触发 Jenkins Jobs 的插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: trigger jenkins job
      image: appleboy/drone-jenkins
      settings:
        url: http://example.com
        user: appleboy
        token: xxxxxxxxxx
        job: drone-jenkins-plugin-job
```

## 参数含义

url
: jenkins 服务地址。

user
: jenkins 用户账号。

token
: jenkins 用户 token。

job
: jenkins job 名称。

## 更多用法

更多用法参考：[appleboy/drone-jenkins](https://github.com/appleboy/drone-jenkins)。
