## Container's operations complexity

| Container | indexing [] | push_back | insert | erase | find |
|-----------|-------------|-----------|--------|-------|------|
|  vector   | O(1)        | O(1) amort| O(N)   | O(N)  |  none|
| deque | O(1) | O(1) amort | O(N) | O(N) | none |
|list / forward_list| none | O(1) | O(1) | O(1) | none |
|set / map| O(logN) |none|O(logN)|O(logN)|O(logN)|
|unordered_set / unordered_map| Q(1) mean | none | O(1) mean| O(1) mean| O(1) mean|

## Hunter
### Install
```sh
wget https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake -O cmake/HunterGate.cmake
```

## Forward_List
[How to reverse forward list?](https://www.youtube.com/watch?v=PQIHq0vfADI&ab_channel=CodeWhoop)

## List
Method splice has a linear complexity when we want to splice a part of another list, because we need to recalculate a new size.
