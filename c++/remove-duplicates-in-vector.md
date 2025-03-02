```c
int main() {
    std::vector<int> arr(n)
    // time O(n)
    arr.erase(std::unique(arr.begin(), arr.end()), arr.end());
}
```
