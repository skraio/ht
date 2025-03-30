```bash
git config --global user.name "Имя Фамилия"
git config --global user.email "Ваш email"
git config --global color.ui true
```

Unset key
```bash
git config --global --unset user.name
```

Get the last out value
```bash
git config --get user.name
```

List keys
```bash
git config --list | grep user
```

Remove key(all duplicates)
```bash
git config --unset-all user.name
```
