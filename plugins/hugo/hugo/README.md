# Hugo

通过 Hugo 自动创建静态 web 页面的插件。

## 在 云原生构建 上使用

```yml
main:
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
: 包括标记为草稿的内容。

buildExpired
: 包括过期的内容。

buildFuture
: 包含未来发布日期的内容。

config
: 配置文件（默认路径/config.yaml|json|toml）。

content
: 内容目录的文件系统路径。

layout
: 设计目录的文件系统路径。

output
: 写入文件的文件系统路径。

source
: 读取文件的文件系统路径。

theme
: 要使用的主题（位于/themes/THEMENAME/）。

url
: 根目录的主机名（和路径）。

validate
: 生成之前验证配置文件。

## 更多用法

更多用法参考：[drone-plugins/drone-hugo](https://github.com/drone-plugins/drone-hugo)。
