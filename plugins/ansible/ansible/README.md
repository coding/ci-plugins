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
    - name: use ansible
      image: plugins/ansible
      settings:
        private_key: $PRIVATE_KEY
        inventory: hosts.conf
        playbook: playbook.yml
```

```conf
# hosts.conf
[custom]
127.0.0.1
127.0.0.2
127.0.0.3
```

```yml
# playbook.yml
---
- hosts: 
    - custom
  remote_user: root
  vars:
    ansible_ssh_port: 36000
  tasks:
    
    # 执行脚本
    - name: hello
      shell: echo hello
    
    # 复制文件
    - name: copy
      copy:
        src: /dir/from/
        dest: /dir/to/
        owner: root
        group: root
        mode: 0644
```

## 常见问题

### RSA 加密算法提示不支持时

建议使用 3.0 版本，即：`plugins/ansible:3`，示例如下

```yml
master:
  push:
  - stages:
    - name: use ansible
      image: plugins/ansible:3
      settings:
        private_key: $PRIVATE_KEY
        inventory: hosts.conf
        playbook: playbook.yml
```

## 更多用法

参见 [ansible/ansible](https://github.com/ansible/ansible)
