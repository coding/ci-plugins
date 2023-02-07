# Ansible

Ansible可以帮助您展示价值，连接团队，并为您的组织带来效率。

## 在 Docker 上使用

```shell
docker run --rm \
  -e PLUGIN_PRIVATE_KEY="$(cat ~/.ssh/id_rsa)" \
  -e PLUGIN_PLAYBOOK="deployment/playbook.yml" \
  -e PLUGIN_INVENTORY="deployment/hosts.yml" \
  -v $(pwd):$(pwd) \
  -w $(pwd) \
  plugins/ansible
```

## 在 Coding-CI 上使用

```yml
master:
  push:
  - stages:
    - name: use 
      image: plugins/ansible
      settings:
        private_key: $PRIVATE_KEY
        playbook: deployment/playbook.yml
        inventory: deployment/hosts.yml
```
