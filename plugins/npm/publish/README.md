# npm

`npm publish`，支持官方仓库和私有仓库。

## 输入

- `username`: `string` 用户名
- `password`: `string` 密码
- `token`: `string` token方式鉴权
- `email`: `string` 邮箱
- `registry`: `string` registry，默认：`https://registry.npmjs.org`
- `folder`: `string` 要发布的目录，默认当前目录。
- `fail_on_version_conflict`: `boolean` 版本存在时报错退出
- `tag`: `boolean` NPM publish tag `--tag`
- `access`: `string` NPM scoped package access `--access`

## 在 Coding-CI 上使用

### 发布到私有仓库

```yaml
master:
  push:
  - stages:
    - name: npm publish
      image: plugins/npm
      imports: https://your-git.com/xxx/npm-token.yml
      settings:
        username: $NPM_USER
        password: $NPM_PASS
        email: $NPM_EMAIL
        registry: https://your-npm-registry.com/
        folder: ./
        fail_on_version_conflict: true
```

`package.json` 文件需要声明相同的 `registry`，以通过 npm 校验

```json
{
    "name": "xxx",
    "version": "xxx",
    "publishConfig": {
        "registry": "https://your-npm-registry.com/"
    }
}
```

### 发布到 npm 官方仓库

```yaml
master:
  push:
  - stages:
    - name: npm publish
      image: plugins/npm
      imports: https://your-git.com/xxx/npm-token.yml
      settings:
        username: $NPM_USER
        password: $NPM_PASS
        email: $NPM_EMAIL
        folder: ./
        fail_on_version_conflict: true
```
