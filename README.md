# Ansible Demo

Ansible demo on VirtualBox (use Vagrant)

| host         | addr            | app     |
| ------------ | --------------- | ------- |
| demo-ansible | 192.168.244.130 | Ansible |
| demo-lb01    | 192.168.244.131 | HAProxy |
| demo-www01   | 192.168.244.132 | Apache  |
| demo-www02   | 192.168.244.133 | Apache  |

## demo

### create VMs

```console
$ cd vagrant
$ vagrant up
```

### login

```console
$ vagrant ssh ansible
```

### execute ansible

```console
[vagrant@demo-ansible ~]$ cd /ansible-demo/
[vagrant@demo-ansible ansible-demo]$ ls
ansible.cfg  inventory.ini  playbook.yml  templates
[vagrant@demo-ansible ansible-demo]$ ansible-playbook -i inventory.ini playbook.yml 
```

### access to http server

http://192.168.244.131/

## reference

- [社内勉強会ネタ：2週間で完全にマスターしたAnsible入門まとめ](https://qiita.com/zaki-lknr/items/3ac4c7e105609a7f0bf9)
- [Ansible検証環境に特化したVagrantを使ったVM構築 - 複数VM・VM間ssh公開鍵認証設定・共有フォルダ](https://qiita.com/zaki-lknr/items/cdf4eac2d2f2020ac7be)
