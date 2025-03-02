Time complexity of std::sort() is O(n logn)

## Two Vectors
```c
void parallelSortTwoVectors() {
    int n = 5;

    std::vector<int> a;
    for (int i = 0; i < n; i++) {
        int aa; std::cin >> aa;
        a.push_back(aa);
    }

    std::vector<int> b;
    for (int i = 0; i < n; i++) {
        int bb; std::cin >> bb;
        b.push_back(bb);
    }

    std::vector<size_t> indices(a.size());
    // time O(n)
    std::iota(indices.begin(), indices.end(), 0);

    // time O(n logn)
    std::sort(indices.begin(), indices.end(), [&](size_t i, size_t j) {
        return b[i] < b[j];
    });

    std::vector<int> sorted_a;
    std::vector<int> sorted_b;

    for (size_t i : indices) {
        sorted_a.push_back(a[i]);
        sorted_b.push_back(b[i]);
    }
}
```

## One Vector of Pairs
```c
void sortPairsInVector() {
    int n = 5;

    std::vector<std::pair<int, int>> a;
    for (int i = 0; i < n; i++) {
        std::cin >> a[i].first;
    }
    for (int i = 0; i < n; i++) {
        std::cin >> a[i].second;
    }

    std::sort(a.begin(), a.end());
}
```

## Array of Pairs
```c
void sortPairsInArray() {
    int n = 5;

    std::pair<int, int> a[n];
    for (int i = 0; i < n; i++) {
        std::cin >> a[i].first;
    }
    for (int i = 0; i < n; i++) {
        std::cin >> a[i].second;
    }

    std::sort(a, a + n);
}
```
