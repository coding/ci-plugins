# gpgsign

通过 GunPG 给制品加密的插件。

## 在 云原生构建 上使用

```yml
main:
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

## 参数

key
: 私有GnuPG密钥，可选base64编码。

passphrase
: 用于解锁私钥的passphrase。

detach_sign
: 生成 detach-sign 签名。

clear_sign
: 生成 clear-sign 签名。

files, file
: 要匹配文件的globs列表。

excludes, exclude
: 要排除文件的pattern列表。

## 更多用法

更多用法参考：[drone-plugins/drone-gpgsign](https://github.com/drone-plugins/drone-gpgsign)
