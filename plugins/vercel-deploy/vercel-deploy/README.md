# Vercel Deploy

部署应用到 Vercel。

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
  - name: deploy
    image: docker.io/kameshsampath/drone-vercel-deploy
    settings:
      log_level: debug
      # valid values are production, development, preview
      vercel_env: production
      vercel_token:
        from_secret: vercel_token
      vercel_org_id:
        from_secret: vercel_org_id
      vercel_project_id:
        from_secret: vercel_project_id
      vercel_project_create: true
      vercel_environment:
        - NEXT_PUBLIC_FOO=BAR
        - NEXT_PUBLIC_XMAS=25 Dec
```

## 参数含义

vercel_token
: 使用的 Vercel 令牌。

vercel_org_id
: 用于 Vercel 部署的组织 ID。

vercel_project_id
: Vercel 项目名称或 ID。

log_level
:  如果设置为允许调试，则启用脚本调试。

## 更多用法

更多用法参考：[kameshsampath/drone-vercel-deploy](https://github.com/kameshsampath/drone-vercel-deploy)。
