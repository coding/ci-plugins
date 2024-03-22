# markdownlint-cli2

linting Markdown files with the markdownlint。

## 在 Docker 上使用

```shell
docker run -w /myfolder -v $(pwd):/myfolder  davidanson/markdownlint-cli2 docs/**/*.md

docker run -w /myfolder -v $(pwd):/myfolder  davidanson/markdownlint-cli2 --fix docs/**/*.md
```

尝试自动修复检查过程中发现的问题

```shell
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) \
  --entrypoint="markdownlint-cli2-fix" \
  davidanson/markdownlint-cli2 "**/*.md" "#node_modules"
```

## 在 云原生构建 上使用

```yaml
# .cnb.yml
main:
  pull_request:
  - stages:
    - name: do markdownlint
      image: davidanson/markdownlint-cli2
      commands: 
      - markdownlint-cli2 **/*.md 
```

## 在 Coding-CI 上使用

```yaml
# .coding-ci.yml
master:
  merge_request:
  - stages:
    - name: do markdownlint
      image: davidanson/markdownlint-cli2
      commands: 
      - markdownlint-cli2 **/*.md 
```

## 排除指定目录

```yaml
stages:
- name: do markdownlint
  image: davidanson/markdownlint-cli2
  commands: 
  - markdownlint-cli2 "**/*.md" "#node_modules"
```
