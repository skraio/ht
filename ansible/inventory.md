Check what variables are being loaded:
```bash
➜  ansible git:(INT-5015) ✗ ansible-inventory --list | jq ._meta.hostvars

{
  "repo": {
    "ansible_host": "192.168.65.13",
    "ansible_password": "password",
    "ansible_python_interpreter": "/usr/bin/python3",
    "ansible_user": "user"
  }
}
```


Check groups belonging
```bash
➜  ansible git:(INT-5015) ✗ ansible-inventory --graph

@all:
  |--@ungrouped:
  |--@repository:
  |  |--repo
```

Print the inventory_hostname variable
```bash
ansible all -m debug -a "var=inventory_hostname"
```
