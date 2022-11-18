# plugins for Coding-CI

## Contributing

Q: 我有一个好插件，希望大家都可以用上，应该如何贡献到镜像插件市场中？

A: 恭喜你，找对地方了，这篇文章就是解释这个问题的！

## Step by step

### 前提

1. 已经制作好了插件。
1. 有 Git 操作的相关经验。

### Step 0

fork 本项目，在 `plugins` 目录下创建插件子目录，比如 `plugins/example/plugin`

### Step 1

添加插件的 Meta 信息`plugin-meta.json` 到子目录中，字段如下：

```json
{
  "name": "npm",
  "description": "发布 NPM 包到仓库，支持官方仓库和私有仓库",
  "tags": [ "publish", "npm" ],
  "mark": "社区",
  "images": "https://hub.docker.com/r/plugins/npm/tags",
  "source": "https://github.com/drone-plugins/drone-npm",
  "bugs": "https://github.com/drone-plugins/drone-npm/issues",
  "logo": "logo.svg"
}
```

- `name`: 插件名称，需要全英文，单词之间以中划线`-`分隔。
- `description`: 插件描述，简单介绍插件作用。
- `tags`: 标签，是一个字符串数组，填写前可以先参照已有的标签填写，若没有合适的，可以自创。
- `mark`: 角标。目前只可填 `官方`、`社区` 两种。
- `images`: 插件镜像地址。
- `source`: 源码地址。
- `bugs`: 问题反馈地址。
- `logo`: logo 图片相对地址。如果没有，可以不填。图片最好为正方形，尺寸大于 100 x 100 即可。

### Step 2

添加 logo README.md 等必要文件到插件 Meta 信息所在目录。

### Step 3

提交修改，发起 PR 等待自动检查工具通过和人工审核。
