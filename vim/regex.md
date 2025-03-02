to match all digits:
```regex
[0-9]
```

From: 42 \
To: 42,<space>
```regex
'<,'>s/\([0-9],\)/\1 /g
```

From: \[a\]\[b\] \
To: \[b\]\[a\]
```regex
'<,'>s/\(\[i\]\)\(\[[0-9]\]\)/\2\1/g
```

From: a/b/c \
To: b/a/c
```regex
'<,'>s/\(\[i\]\)\(\[[0-9]\]\)/\2\1/g
```

From: ABCDF abcdf (abcdf) \
To: abcdf
```regex
%s/.*(\(\w\+\)).*/\1/g
```


From:                      To:
[1,3],[3,0,1],[2],[0]       {1,3},
                            {3,0,1},
                            {2},
                            {0},
```regex
'<,'>s/\[\([^]]*\)\],*/{\1},\r/g
```

From                         To:
word1, word2, word3          word1
                             word2
                             word3
