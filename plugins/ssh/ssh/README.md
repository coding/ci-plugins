# SSH

通过ssh在远端host执行命令

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: ssh
      image: appleboy/drone-ssh
      settings:
        host:
          - example1.com
          - example2.com
        username: ubuntu
        password:
          from_secret: ssh_password
        port: 22
        command_timeout: 2m
        script:
          - echo "Hello World"
```

## 参数含义

ssh_username
: account for target host user

ssh_password
: password for target host user

ssh_passphrase
: The purpose of the passphrase is usually to encrypt the private key.

ssh_key
: plain text of user private key

proxy_ssh_username
: account for user of proxy server

proxy_ssh_password
: password for user of proxy server

proxy_ssh_passphrase
: The purpose of the passphrase is usually to encrypt the private key.

proxy_ssh_key
: plain text of user private key for proxy server

### Parameter Reference

host
: target hostname or IP

port
: ssh port of target host

username
: account for target host user

password
: password for target host user

key
: plain text of user private key

key_path
: key path of user private key

envs
: custom secrets which are made available in the script section

script
: execute commands on a remote server

script_stop
: stop script after first failure

timeout
: Timeout is the maximum amount of time for the ssh connection to establish, default is 30 seconds.

command_timeout
: Command timeout is the maximum amount of time for the execute commands, default is 10 minutes.

proxy_host
: proxy hostname or IP

proxy_port
: ssh port of proxy host

proxy_username
: account for proxy host user

proxy_password
: password for proxy host user

proxy_key
: plain text of proxy private key

proxy_key_path
: key path of proxy private key

## 更多用法

更多用法参考：[appleboy/drone-ssh](https://github.com/appleboy/drone-ssh)
