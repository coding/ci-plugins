# download

下载构建所需文件的插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: download  
      image: plugins/download
      settings:
        source: https://github.com/drone/drone-cli/releases/download/v0.8.5/drone_linux_amd64.tar.gz
```

## 参数含义

source
: 下载的源URL。

destination
: 下载目标路径。

username
: basic auth 的用户名。

password
: basic auth 的密码。

skip_verify
: 跳过 SSL 校验。

md5
: MD5格式的校验和。

sha256
: SHA256格式的校验和。

## 更多用法

更多用法参考：[drone-plugins/drone-download](https://github.com/drone-plugins/drone-download)。
