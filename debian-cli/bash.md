Replace spaces with dashes
```bash
for file in *.md; do mv "$file" "${file// /-}"; done
```
