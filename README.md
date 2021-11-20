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
[How to reverse forward a forward list?](https://www.youtube.com/watch?v=PQIHq0vfADI&ab_channel=CodeWhoop)

## List
[Method splice has a linear complexity when we want to splice a part of another list, because we need to recalculate a new size](https://en.cppreference.com/w/cpp/container/list/splice)

## GCC Compile Flags
-Wpedantic (-pedantic) - checks that the code complies with the ISO C ++ standard, reports on the use of prohibited extensions, on the presence of extra semicolons, lack of line breaks at the end of the file, and other useful things

-Werror - warning = error

-Wall - turn on basic warnings

-Wextra - turn on extra warnings

-Wshadow - warn whenever a local variable or type declaration shadows another variable

-Wnon-virtual-dtor - tells the compiler to issue a warning when a class appears to be polymorphic, yet it declares a non-virtual one

[More information](https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html)

## Pointers
### Pointers with const modidfcator
1. Just a pointer
```cpp
int a = 4;
int b = 1;
int *p = &a;
*p = 3;
p = &b;
*p = 2;
//there is no error
```
2. Pointer to const object
```cpp
int a = 4;
int b = 1;
const int *p = &a; //it's equal to int const* p = &a;
//*p = 2; - this operation is unavailable because p is a pointer to const int
p = &b; // works fine
```
3. Const pointer to non const object
```cpp
int a = 4;
int b = 1;
int *const p = &a;
*p = 2; //works fine
//++p; - this operation is unavailable because p is a const pointer to int
```
4. Const pointer to const object
```cpp
int a = 4;
int b = 1;
const int *const p = &a;
/*
++p;
p = &b;
these operations are unavailable because p is a const pointer to const int
*/
```
