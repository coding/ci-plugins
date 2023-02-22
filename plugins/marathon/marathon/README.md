# Marathon

部署应用到 Marathon 集群的插件。

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: marathon
      image: e20co/drone-marathon
      settings:
        server: http://marathon.mesos:8080
```

## 参数含义

server
: Marathon服务器地址. 默认为 `http://marathon.mesos:8080`。

marathonfile
: Marathon配置文件. 默认为 `marathon.json`。

trigger_restart
: 强制重启应用. 默认为 `false`。

values
: 上面 `marathonfile` 的值映射，可选。

## 更多用法

更多用法参考：[expansioncap/drone-marathon](https://github.com/expansioncap/drone-marathon)。
