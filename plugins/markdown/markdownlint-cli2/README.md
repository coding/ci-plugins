# markdownlint-cli2

linting Markdown files with the markdownlint。

## 在 Docker 上使用

```shell
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) davidanson/markdownlint-cli2 **/*.md
```

尝试自动修复检查过程中发现的问题

```shell
docker run --rm -it -v $(pwd):$(pwd) -w $(pwd) \
  --entrypoint="markdownlint-cli2-fix" \
  davidanson/markdownlint-cli2 "**/*.md" "#node_modules"
```

## 在 Coding-CI 上使用

```yaml
main:
  merge_request:
  - stages:
    - name: do markdownlint
      image: davidanson/markdownlint-cli2
      commands: 
      - markdownlint-cli2 **/*.md 
```

排除指定目录

```yaml
main:
  merge_request:
  - stages:
    - name: do markdownlint
      image: davidanson/markdownlint-cli2
      commands: 
      - markdownlint-cli2 "**/*.md" "#node_modules"
```
