1. Use / to search for an occurrence
2. Press Enter
3. Press cgn
4. Provide a new phrase
5. Press Esc
6. Spam . to repeat replacement or n to jump between occurrences


```sh
find . -type f -exec sed -i 's/foo/bar/g'
```

or each word in a file same as a word under cursor
:%s/<C-r><C-w>/foo/gc
