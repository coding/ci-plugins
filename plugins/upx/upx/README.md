# UPX

UPX 压缩插件。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: upx
      image: cnbattle/drone-upx
      settings:
        level: 9 //default 5
        save_file: ./executable_upx_file
        original_file: ./executable_original_file
```

## 参数含义

level
: 压缩级别，取值在1到9之间，越大越好。

original_file
: 待处理的原始文件。

save_file
: 保存压缩文件的路径和文件名。

## 更多用法

更多用法参考：[cnbattle/drone-upx](https://github.com/cnbattle/drone-upx)。
