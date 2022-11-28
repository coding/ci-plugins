# Jenkins

触发Jenkins Jobs的插件

## 在 Coding-CI 上使用

```yml
master:
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
: jenkins server base url.

user
: jenkins user account

token
: jenkins user token

job
: jenkins job name

## 更多用法

更多用法参考：[appleboy/drone-jenkins](https://github.com/appleboy/drone-jenkins)
