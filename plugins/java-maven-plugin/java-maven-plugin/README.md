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
: The context directory to execute the maven goals.

goals
: An array of maven goals to run.Defaults: `-DskipTests clean install`.

maven_modules
: An array of maven modules to be built incase of a multi module maven project.

maven_mirror_url
: The Maven repository mirror url.

server_user
: The username for the maven repository manager server.

server_password
: The password for the maven repository manager server.

proxy_user
: The username for the proxy server.

proxy_password
: The password for the proxy server.

proxy_port
: Port number for the proxy server.

proxy_host
: Proxy server Host.

proxy_non_proxy_hosts
: An array of non proxy server hosts.

proxy_protocol
: Protocol for the proxy ie http or https.

## 更多用法

更多用法参考：[kameshsampath/drone-java-maven-plugin](https://github.com/kameshsampath/drone-java-maven-plugin)
