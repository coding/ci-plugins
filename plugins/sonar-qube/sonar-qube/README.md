# SonarQube

SonarQube 扫描插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: sonar-analysis
    image: aosapps/drone-sonar-plugin
    settings:
      sonar_host: your-sonar-host
      sonar_token: your-sonar-token
```

## 参数含义

sonar_host: sonar 服务所在域名

sonar_token: sonar 服务授权 token

## 更多用法

更多用法参考：[aosapps/drone-sonar-plugin](https://github.com/aosapps/drone-sonar-plugin)。
