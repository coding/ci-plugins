# gpgsign

通过GunPG给制品加密的插件

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: sign  
      image: plugins/gpgsign
      settings:
        key: your-base64-encoded-private-key
        passphrase: p455w0rd
        files:
          - dist/*

```

## 参数含义

key
: Private GnuPG key, optionally base64 encoded

passphrase
: Passphrase to unlock private key

detach_sign
: Generate a detach-sign signature

clear_sign
: Generate a clear-sign signature

files, file
: List of globs to match files

excludes, exclude
: List of patterns to exclude files

## 更多用法

更多用法参考：[drone-plugins/drone-gpgsign](https://github.com/drone-plugins/drone-gpgsign)
