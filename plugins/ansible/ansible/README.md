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

## 在 云原生构建 上使用

```yml
main:
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

### SSH-KEY 生成

使用 椭圆曲线(推荐) 算法生成密钥对

```shell
ssh-keygen -t ed25519 -f ./ssh-key
```

公钥内容追加到目标机器的 `/root/.ssh/authorized_keys` 文件中

### RSA 加密算法提示不支持时

因为最新版本的 openssl 已弱化对 `RSA` 的支持，遇到不支持的情况时，可降级为 3.0 版本解决，

即：`plugins/ansible:3`，示例如下

```yml
main:
  push:
  - stages:
    - name: use ansible
      image: plugins/ansible:3
      settings:
        private_key: $PRIVATE_KEY
        inventory: hosts.conf
        playbook: playbook.yml
```

## 隐藏明文凭证

可通过 imports 动态注入凭证，达到隐藏明文凭证的目标

```yml
main:
  push:
  - stages:
    - name: use ansible
      image: plugins/ansible
      imports: https://your-git.com/xxx/xxx/ssh-key.yml
      settings:
        private_key: $PRIVATE_KEY
        inventory: hosts.conf
        playbook: playbook.yml
```

```yml
# ssh-key.yml
PRIVATE_KEY: |
  xxxxxx
  xxxxxx
PUBLIC_KEY: |
  xxxxxx
  xxxxxx
```

## 更多用法

参见 [ansible/ansible](https://github.com/ansible/ansible)
