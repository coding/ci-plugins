# Artifactory

发布文件或者制品到制品库。

## 在 云原生构建 上使用

```yml
main:
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

## 参数

* `url`-项目url（包括scheme）。

* `username`-制品库用户名，默认为空。

* `password`-制品库密码，默认为空。

* `pom`-用于读取项目详细信息的可选的pom.xml路径。

* `group_id`-项目组id，默认为Pom文件中的值。

* `artifact_id`-项目项目id，默认为Pom文件中的值。

* `version`-制品版本，默认为Pom文件中的值。

* `repo_key`-目标存储库密钥。

* `files`-要部署的文件列表。

* `force_upload`-如果文件已存在，则强制上传。

## 更多用法

更多用法参考：[athieriot/drone-artifactory](https://github.com/athieriot/drone-artifactory)。
