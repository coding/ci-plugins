# UPX

UPX压缩插件

## 在 Coding-CI 上使用

```yml
master:
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
: Compression level, a value between 1 and 9, the bigger the better.

original_file
: An original file to be processed.

save_file
: Save the path and file name of the compressed file.

## 更多用法

更多用法参考：[cnbattle/drone-upx](https://github.com/cnbattle/drone-upx)
