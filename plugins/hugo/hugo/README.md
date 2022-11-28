# Hugo

通过Hugo自动创建静态web页面的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: build
      image: plugins/hugo
      settings:
        hugo_version: 0.55
        validate: true
```

## 参数含义

buildDrafts
: Include content marked as draft

buildExpired
: include expired content

buildFuture
: include content with publishdate in the future

config
: config file (default is path/config.yaml|json|toml)

content
: filesystem path to content directory

layout
: filesystem path to layout directory

output
: filesystem path to write files to

source
: filesystem path to read files relative from

theme
: theme to use (located in /themes/THEMENAME/)

url
: hostname (and path) to the root

validate
: validate config file before generation

## 更多用法

更多用法参考：[drone-plugins/drone-hugo](https://github.com/drone-plugins/drone-hugo)
