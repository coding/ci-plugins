# Ansible

Ansible 可以向指定的IP执行任务，完成对 VM 集群的的自动化管理。

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

## 更多用法

参见 [ansible/ansible](https://github.com/ansible/ansible)
