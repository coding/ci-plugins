# downstream

下载构建所需文件的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: trigger  
      image: plugins/downstream
      settings:
        server: https://drone.example.com
        token: eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
        fork: true
        repositories:
          - octocat/Hello-World
          - octocat/Spoon-Knife
```

## 参数含义

token
: drone server auth token

server
: drone server url

repositories
: trigger builds for the repository list, you can mention branch using @<branch>

fork
: trigger new build numbers if true, else rebuild

wait
: wait for any currently running builds to finish if true, else fails

timeout
: how long to wait on any currently running builds defaults to 60 seconds

params
: supports params in KEY=value format as well as loading of params from godotenv files.

deploy
: Trigger a deployment (promote build), value is the environment/target for the new build

last_successful
: Trigger the last successful build for the branch specified in repositories

## 更多用法

更多用法参考：[drone-plugins/drone-downstream](https://github.com/drone-plugins/drone-downstream)
