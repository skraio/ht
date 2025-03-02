Для подключения по RDP к ВМ через Remmina, установить на ВМ:
```bash
sudo apt install xrdp
```

```bash
sudo systemctl enable xrdp
sudo systemctl start xrdp
```


```bash
user@sandbox:~$ sudo netstat -tuln | grep 3389
tcp        0      0 0.0.0.0:3389            0.0.0.0:*               LISTEN
user@sandbox:~$
user@sandbox:~$
user@sandbox:~$ sudo systemctl restart xrdp
user@sandbox:~$ sudo ufw allow 3389/tcp
Rules updated
Rules updated (v6)
user@sandbox:~$ sudo firewall-cmd --add-port=3389/tcp --permanent
success
user@sandbox:~$ sudo firewall-cmd --reload

success
```
