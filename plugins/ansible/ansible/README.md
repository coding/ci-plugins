# Ansible

Ansible can help you demonstrate value, connect teams,
and deliver efficiencies for your organization.

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
