# PyPI

发布python包

## 在 Coding-CI 上使用

```yml
master:
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
: Username to be used for the pypi publish.

password
: Password for the pypi publish.

repository
: The URL of the repository to be published to.

distributions
: List of distribution types to publish.

setupfile
: The relative path from the workspace root to the setup.py file to be used.

skip_build
: Skip the build and only upload pre-build files from `dist/*`

## 更多用法

更多用法参考：[drone-plugins/drone-pypi](https://github.com/drone-plugins/drone-pypi)
