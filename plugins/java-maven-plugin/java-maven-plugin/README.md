# java-maven-plugin

通过Apache Maven构建Java应用的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: build-java-app
      image: docker.io/kameshsampath/drone-java-maven-plugin:v1.0.0
```

## 参数含义

context_dir
: 执行 Maven 目标的上下文目录。

goals
: 要运行的一系列 Maven 目标。默认值：`-DskipTests clean install`

maven_modules
: 在多模块 maven 项目的情况下要构建的 maven 模块数组

maven_mirror_url
: Maven 仓库镜像地址

server_user
: maven 存储库管理器服务器的用户名

server_password
: maven 存储库管理器服务器的密码

proxy_user
: 代理服务器的用户名

proxy_password
: 代理服务器的密码

proxy_port
: 代理服务器的端口号

proxy_host
: 代理服务器主机

proxy_non_proxy_hosts
: 一组非代理服务器主机

proxy_protocol
: 代理协议，即 http 或 https

## 更多用法

更多用法参考：[kameshsampath/drone-java-maven-plugin](https://github.com/kameshsampath/drone-java-maven-plugin)
