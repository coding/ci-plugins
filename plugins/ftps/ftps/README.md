# ftps

通过ftps上传制品的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: deploy
      image: cschlosser/drone-ftps
      env: 
        FTP_PASSWORD: xxx
        FTP_USERNAME: xxx
      settings:
        hostname: example.com:21
        secrets: [ ftp_username, ftp_password ]
```

## 参数

hostname
: FTP主机，包括端口

clean_dir
: 如果设置为true，将在文件传输之前清理目标目录

chmod
: 如果设置为true，将在文件传输后执行```chmod```。

verify
: 如果设置为true，则强制SSL证书验证，否则无验证（默认为true）

secure
: 如果设置为true，则强制FTPS，否则使用普通FTP（默认为true）

dest_dir
: 将文件放在远程服务器上的位置（默认/）

src_dir
: 用于上传的本地目录（默认值./）

exclude
: egrep-like模式匹配从上传的文件中排除文件（默认无）

include
: egrep类模式匹配要上传的文件（默认为无）

## 更多用法

更多用法参考：[cschlosser/drone-ftps](https://github.com/cschlosser/drone-ftps)
