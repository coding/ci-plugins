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

## 参数

* capistran_private_key：专用SSH部署密钥

* capistrano_public_key：公共SSH部署密钥

* tasks：要运行的Capistrano任务

## 更多用法

更多用法参考：[glaszig/drone-capistrano](https://github.com/glaszig/drone-capistrano)
