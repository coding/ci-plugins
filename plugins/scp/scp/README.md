# SCP

通过ssh复制文件或者代码

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: scp files
      image: appleboy/drone-scp
      settings:
        host: example.com
        username: foo
        password: bar
        port: 22
        target: /var/www/deploy/${DRONE_REPO_OWNER}/${DRONE_REPO_NAME}
        source: release.tar.gz
```

## 参数含义

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

passphrase
: The purpose of the passphrase is usually to encrypt the private key.

target
: folder path of target host

source
: source lists you want to copy

rm
: remove target folder before copy files and artifacts

timeout
: Timeout is the maximum amount of time for the ssh connection to establish, default is 30 seconds.

command_timeout
: Command timeout is the maximum amount of time for the execute commands, default is 10 minutes.

strip_components
: remove the specified number of leading path elements

tar_tmp_path
: temporary path for tar file on the dest host

tar_exec
: alternative `tar` executable to on the dest host

overwrite
: use `--overwrite` flag with tar

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

proxy_passphrase
: The purpose of the passphrase is usually to encrypt the private key.

### Template Reference

repo.owner
: repository owner

repo.name
: repository name

build.status
: build status type enumeration, either `success` or `failure`

build.event
: build event type enumeration, one of `push`, `pull_request`, `tag`, `deployment`

build.number
: build number

build.commit
: git sha for current commit

build.branch
: git branch for current commit

build.tag
: git tag for current commit

build.ref
: git ref for current commit

build.author
: git author for current commit

build.link
: link the the build results in drone

## 更多用法

更多用法参考：[appleboy/drone-scp](https://github.com/appleboy/drone-scp)
