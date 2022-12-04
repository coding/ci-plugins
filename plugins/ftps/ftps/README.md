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

## 参数含义

### Env Reference

FTP_PASSWORD
: password used to login to the FTP server with the specified user

FTP_USERNAME
: Username used to login to the FTP server

### Parameter Reference

hostname
: FTP host including the port

clean_dir
: if set to true destination directory would be cleaned before file transfer.

chmod
: if set to true ```chmod``` would be executed after file transferred.

verify
: if set to true the SSL certificate validation is enforced,
 otherwise no validation (default true)

secure
: if set to true FTPS is enforced, otherwise plain FTP is used (default true)

dest_dir
: where to put the files on the remote server (default /)

src_dir
: which local directory should be used for the upload (default ./)

exclude
: egrep like pattern matching to exclude files from uploading (default none)

include
: egrep like pattern matching to include files to upload (default none)

## 更多用法

更多用法参考：[cschlosser/drone-ftps](https://github.com/cschlosser/drone-ftps)
