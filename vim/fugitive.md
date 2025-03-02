:Git log %

:tab G log

O

:Gdiff

cvc

Folds the diff under each modified filename
```vim
:set foldmethod=syntax
```
zo zc - open/close

Browsing through the history of a file
```vim
:0Gclog
```

```vim
:G difftool hash1 hash2
:Gvdiffsplit!
```

```vim
:G difftool -y hash1 hash2
```

coo
```vim
:G difftool -y HEAD~1 --
```

```vim
:G difftool -y HEAD~1 % --
```

vim.keymap.set("n", "<leader>Gdf", "<cmd>Gvdiffsplit!<cr>")

vim.keymap.set("n", "<leader>Gdh", "<cmd>G difftool -y HEAD~1<cr>")
