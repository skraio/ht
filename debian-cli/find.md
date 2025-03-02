Find softlinks
```bash
find / -type l -lname "/path" 2>/dev/null
```

Find hardlinks
```bash
find / -inum <inode> 2>/dev/null
```

Find unique files that contain word status
```bash
vim -p $(find . -type f -name "*.sql" | xargs grep -il status)
```


```bash
user@ceph4:~$ sudo find / -type d -perm -3000 2>/dev/null
/var/log/ceph
user@ceph4:~$ sudo ls -lah `!!`
```

```bash
root@machine:/# find / -type f -name "*html*" 2>/dev/null
/usr/share/nginx/html/index.html
/usr/share/nginx/html/50x.html
```
