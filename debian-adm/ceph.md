# Ceph

```bash
sudo vim /etc/chrony/chrony.conf

server 192.168.65.2 iburst
```

```bash
chronyc sources
chronyc tracking
```

# Настройка фронтальной машины и развертывание Ceph-кластера

```bash
sudo pdpl-user ceph-adm
```

```bash
$ cat /etc/hosts
127.0.0.1       localhost
192.168.65.9    ceph1
192.168.65.10   ceph2
192.168.65.11   ceph3
192.168.65.3    front1
192.168.65.7    front2
192.168.65.8    front3
192.168.65.4    node

# The following lines are desirable for IPv6 capable hosts
::1     localhost ip6-localhost ip6-loopback
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```

```bash
su - ceph-adm
ssh-keygen
for N in $(seq 1 3); do ssh-copy-id ceph-adm@ceph$N; done
ssh-copy-id ceph-adm@front
ceph-deploy --username ceph-adm install --mon --osd ceph1 ceph2 ceph3 # osd - роль, которая отвечает за хранение данных
```

```bash
for N in $(seq 1 3); do ssh ceph-adm@ceph$N sudo reboot; done
```

```bash
ceph-deploy --username ceph-adm install --mgr ceph1 # установка роли ceph-manager, которая отвечает за графическое управление
```

```bash
ceph-deploy --username ceph-adm new ceph1 ceph2 ceph3
```

запустить только на ceph-1-hostname
```bash
$ ls
''$'\r'   ceph.conf   ceph-deploy-ceph.log   ceph.mon.keyring  ''$'\r''.pub'
$ ceph-deploy --username ceph-adm mon create-initial
```

```bash
ceph-deploy --username ceph-adm mgr create ceph1
```


```bash
ceph-deploy --username ceph-adm osd create --data /dev/sdb ceph1
ceph-deploy --username ceph-adm osd create --data /dev/sdb ceph2
ceph-deploy --username ceph-adm osd create --data /dev/sdb ceph3
```

```bash
ceph-deploy --username ceph-adm install --cli front
ceph-deploy admin front
```

```bash
sudo ceph -s
```

# 4. Настройка службы узла виртуализации для работы с Ceph-кластером


----------------------------------------------------------------------------------------------------

```bash
scp ceph.client.libvirt.keyring ceph-adm@front2:/tmp
scp client.libvirt.key ceph-adm@front2:/tmp
ssh ceph-adm@front2 "sudo mv /tmp/ceph.client.libvirt.keyring /etc/ceph"
ssh ceph-adm@front2 "sudo mv /tmp/client.libvirt.key /var/lib/one"
ssh ceph-adm@front2 "sudo ln -s /var/lib/one/client.libvirt.key /root/client.libvirt.key"
```

----------------------------------------------------------------------------------------------------

# Ceph Dashboard

```bash
$ sudo apt install -y ceph-mgr-dashboard
...
$
$
$ sudo ceph mgr module enable dashboard
$
$
$ sudo ceph dashboard create-self-signed-cert
Self-signed certificate created
$
$
$ vim dashboard-password.txt
$ cat dashboard-password.txt
password
$
$
$ sudo ceph dashboard ac-user-create user1 -i dashboard-password.txt administrator
{"username": "user1", "password": "$2b$12$GK3hJSip4/Wf550LOObvX.yGDydwLr5pPkW4oNPNucOM1jtLf4yqW", "roles": ["administrator"], "name": null, "email": null, "lastUpdate": 1737351164, "enabled": true, "pwdExpirationDate": null, "pwdUpdateRequired": false}
$
$
$ sudo ceph mgr services
{
    "dashboard": "https://192.168.65.9:8443/"
}
```

----------------------------------------------------------------------------------------------------
Ceph mgr up
```
https://docs.ceph.com/en/latest/mgr/administrator/
```
