# download

下载构建所需文件的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: download  
      image: plugins/download
      settings:
        source: https://github.com/drone/drone-cli/releases/download/v0.8.5/drone_linux_amd64.tar.gz
```

## 参数含义

source
: Source URL for the download

destination
: Destination for the download

username
: Username for basic auth

password
: Password for basic auth

skip_verify
: Skip SSL verification

md5
: Checksum in MD5 format

sha256
: Checksum in SHA256 format

## 更多用法

更多用法参考：[drone-plugins/drone-download](https://github.com/drone-plugins/drone-download)
