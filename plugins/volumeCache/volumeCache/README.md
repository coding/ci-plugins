# Volume Cache

将文件或者文件夹缓存到本地的盘

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: restore-cache
      image: drillster/drone-volume-cache
      volumes:
        - name: cache
          path: /cache
      settings:
        restore: true
        mount:
          - ./node_modules
    - name: rebuild-cache
      image: drillster/drone-volume-cache
      volumes:
        - name: cache
          path: /cache
      settings:
        rebuild: true
        mount:
          - ./node_modules
```

## 参数含义

### Secret Reference

webdav_username, username
: webdav server username

webdav_password, password
: webdav server password

### Parameter Reference

file
: location of the file to upload

destination
: directory to copy the file to

## 更多用法

更多用法参考：[drillster/drone-volume-cache](https://github.com/drillster/drone-volume-cache)
