# Marathon

部署应用到Marathon集群的插件

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
: The Marathon server URL. defaults to `http://marathon.mesos:8080`

marathonfile
: The Marathon configuration file. defaults to `marathon.json`.

trigger_restart
: Force a restart of the application. defaults to `false`.

values
: Map of values to replace in the `marathonfile`, above.  Optional.

## 更多用法

更多用法参考：[expansioncap/drone-marathon](https://github.com/expansioncap/drone-marathon)
