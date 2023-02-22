# SonarQube

SonarQube 扫描插件。

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: code-analysis
    image: aosapps/drone-sonar-plugin
    settings:
        sonar_host:
          from_secret: sonar_host
        sonar_token:
          from_secret: sonar_token
```

## 参数含义

host
: 目标主机名或 IP。

port
: 目标主机 ssh 端口。

username
: 目标主机用户账户。

password
: 目标主机用户密码。

key
: 用户私钥明文。

key_path
: 用户私钥路径。

envs
: 在脚本部分提供的自定义 secrets。

script
: 在远端执行命令。

script_stop
: 第一次失败后停止脚本。

timeout
: ssh连接建立超时时间。

command_timeout
：命令执行超时时间。

proxy_host
: 代理主机名或 IP。

proxy_port
: 代理主机ssh端口。

proxy_username
: 代理主机用户账户。

proxy_password
: 代理主机用户密码。

proxy_key
: 代理私钥明文。

proxy_key_path
: 代理私钥路径。

## 更多用法

更多用法参考：[aosapps/drone-sonar-plugin](https://github.com/aosapps/drone-sonar-plugin)。
