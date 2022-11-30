# Artifactory

发布文件或者制品到制品库插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: artifactory
      image: athieriot/drone-artifactory
      settings:
        url: http://arti.company.com
        username: admin
        password: password
        pom: pom.xml
        files:
          - target/*.jar
          - target/*.war
```

## 参数含义

* `url` - Artifactory URL (Includes scheme)
* `username` - Artifactory username, default to blank
* `password` - Artifactory password, default to blank
* `pom` - An optional pom.xml path were to read project details
* `group_id` - Project group id, default to value from Pom file
* `artifact_id` - Project artifact id, default to value from Pom file
* `version` - Artifact version, default to value from Pom file
* `repo_key` - Target repository key, default to 'libs-snapshot-local' if version contains 'snapshot', 'libs-release-local' otherwise
* `files` - List of files to deploy
* `force_upload` - Force upload if a file already exists

## 更多用法

更多用法参考：[athieriot/drone-artifactory](https://github.com/athieriot/drone-artifactory)
