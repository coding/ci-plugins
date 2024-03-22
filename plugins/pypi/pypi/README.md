# PyPI

发布 python 包。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: pypi_publish
      image: plugins/pypi
      settings:
        username: john
        password: secret
```

## 参数含义

username
: 用于 pypi 包发布的用户名。

password
: ：用于 pypi 包发布的密码。

repository
: 要发布的仓库地址。

distributions
: 要发布的分法类型列表。

setupfile
: 工作空间根目录到要使用的 setup.py 文件的相对路径。

skip_build
: 跳过构建，只从 `dist/*` 上传预构建文件。

## 更多用法

更多用法参考：[drone-plugins/drone-pypi](https://github.com/drone-plugins/drone-pypi)。
