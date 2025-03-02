# Array
```c
bool compare(int a, int b) {
    return a > b;
}

int main() {
    int arr[] = {5, 2, 9, 1, 6};

    int n = sizeof(arr) / sizeof(arr[0]);
    std::sort(arr, arr + n, compare);
}
```

# Vector of Pairs
```c
bool compare(const std::pair<int,int>& a, const std::pair<int, int>& b) {
    return a.first > b.first;
}

void solve() {
    int n; std::cin >> n;
    std::vector<std::pair<int, int>> a(n);
    for (int i = 0; i < n; i++) {
        std::cin >> a[i].first;
        a[i].second = i;
    }
    std::sort(a.begin(), a.end(), compare);
}
```

# Vector
```c
void solve() {
    std::sort(a.begin(), a.end());
    std::reverse(a.begin(), a.end());
}
```
