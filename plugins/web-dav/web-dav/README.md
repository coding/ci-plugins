# WebDAV

推送构建制品到任何WebDAV服务器

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: upload_debug
      image: vividboarder/drone-webdav
      settings:
        file: com.vividboarder.otbeta/build/outputs/apk/com.vividboarder.otbeta-debug.apk
        destination: https://my.nextcloud.com/remote.php/dav/files/vividboarder/Android/Apks/
        username: admin
        password: password
```

## 参数含义

file
: 上传文件的位置

destination
: 要复制的文件的文件夹

## 更多用法

更多用法参考：[vividboarder/drone-webdav](https://github.com/vividboarder/drone-webdav)
