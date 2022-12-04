# Vercel Deploy

部署应用到Vercel

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
  - name: deploy
    image: docker.io/kameshsampath/drone-vercel-deploy
    pull: never
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

* `vercel_token`: The Vercel Token to use
* `vercel_org_id`: The organization id to use with Vercel deployment
* `vercel_project_id` The Vercel Project Name or ID.
* `log_level`:  If set to debug enable scripting debug

## 更多用法

更多用法参考：[kameshsampath/drone-vercel-deploy](https://github.com/kameshsampath/drone-vercel-deploy)
