# Capistrano

通过Capistrano部署应用插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: deploy production
      image: glaszig/drone-capistrano:2.7.4
      settings:
        tasks: production deploy deploy:restart
        private_key:
          from_secret: production_private_key
        public_key:
          from_secret: production_public_key
      environment:
        BUNDLE_PATH: vendor/bundle
      when:
        ref:
          - refs/tags/production-*
```

## 参数含义

capistrano_private_key
: Private SSH deploy key

capistrano_public_key
: Public SSH deploy key

tasks
: The Capistrano tasks to run

## 更多用法

更多用法参考：[glaszig/drone-capistrano](https://github.com/glaszig/drone-capistrano)
