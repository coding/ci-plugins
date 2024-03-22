# yaml2json

将 yaml 转换为 json 格式。

## 在 云原生构建 上使用

```yml
main:
  push:
  - stages:
    - name: yaml2json
      image: simplealpine/yaml2json
      settints:
         args: data.yaml

```

data.yaml:

```yml
people: 
    - 
      name: yyy
      age: 18
    - 
      name: zzz
      age: 19
```

## 参数含义

args: yaml文件

## 更多用法

在docker中使用：
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) simplealpine/yaml2json test.yaml
