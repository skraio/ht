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

---

To get a list of conflicts int the quickfix list
```
:Git mergetool
```

---

Commit chunks of code

open the preview using the = shortcut that is shown in the video, then visually select the chunk of
code that you want in the commit and press 's'

---

On the left target branch, in the middle working copy and in the right merge branch
```
:G mergetool
:Gvdiffsplit!
```
