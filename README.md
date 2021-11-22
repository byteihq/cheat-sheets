## Content
* [Container's operations complexity](https://github.com/byteihq/cheat-sheets#containers-operations-complexity)
* [Vector](https://github.com/byteihq/cheat-sheets#vector)
  + [Implementation](https://github.com/byteihq/cheat-sheets#implementation)
* [Deque](https://github.com/byteihq/cheat-sheets#deque)
  + [Idea](https://github.com/byteihq/cheat-sheets#idea)
* [Stack](https://github.com/byteihq/cheat-sheets#stack)
  + [Idea](https://github.com/byteihq/cheat-sheets#idea-1)
  + [Notes](https://github.com/byteihq/cheat-sheets#notes)
* [Queue](https://github.com/byteihq/cheat-sheets#queue)
* [Priority Queue](https://github.com/byteihq/cheat-sheets#priority-queue)
* [Forward_List](https://github.com/byteihq/cheat-sheets#forward_list)
  + [Idea](https://github.com/byteihq/cheat-sheets#idea-1)
  + [Notes](https://github.com/byteihq/cheat-sheets#notes)
* [List](https://github.com/byteihq/cheat-sheets#list)
  + [Idea](https://github.com/byteihq/cheat-sheets#idea-2)
  + [Notes](https://github.com/byteihq/cheat-sheets#notes-1) 
* [GCC Compile Flags](https://github.com/byteihq/cheat-sheets#gcc-compile-flags)
* [Pointers](https://github.com/byteihq/cheat-sheets#pointers)
  + [Pointers with const modidfcator](https://github.com/byteihq/cheat-sheets#pointers-with-const-modidfcator)
  + [Pointers arithmetic](https://github.com/byteihq/cheat-sheets#pointers-arithmetic)
  + [Smart Pointers](https://github.com/byteihq/cheat-sheets#smart-pointers)
* [Diamond inheritance problem](https://github.com/byteihq/cheat-sheets#diamond-inheritance-problem)
  + [Case](https://github.com/byteihq/cheat-sheets#case)
  + [Possible solution](https://github.com/byteihq/cheat-sheets#possible-solution)
  + [Notes](https://github.com/byteihq/cheat-sheets#notes-3)
 * [Polymorphism](https://github.com/byteihq/cheat-sheets/blob/main/README.md#polymorphism)
  + [Static](https://github.com/byteihq/cheat-sheets/blob/main/README.md#static)
  + [Dynamic](https://github.com/byteihq/cheat-sheets/blob/main/README.md#dynamic)
    - [Case 1](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-1)
    - [Case 2](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-2)
    - [Case 3](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-3)
    - [Case 4](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-4)
    - [Case 5](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-5)
    - [Case 6](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-6)
  + [Key word override](https://github.com/byteihq/cheat-sheets/blob/main/README.md#key-word-override)
    - [Case 1](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-1-1)
    - [Case 2](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-2-1)
  + [Key word final](https://github.com/byteihq/cheat-sheets/blob/main/README.md#key-word-final)
    - [Case 1](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-1-2)
    - [Case 2](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-2-2)    
* [Hunter](https://github.com/byteihq/cheat-sheets#hunter)
  + [Install](https://github.com/byteihq/cheat-sheets#install)

## Container's operations complexity

| Container | indexing [] | push_back | insert | erase | find |
|-----------|-------------|-----------|--------|-------|------|
|  [vector](https://en.cppreference.com/w/cpp/container/vector)   | O(1)        | O(1) amort| O(N)   | O(N)  |  none|
| [deque](https://en.cppreference.com/w/cpp/container/deque) | O(1) | O(1) amort | O(N) | O(N) | none |
|[list](https://en.cppreference.com/w/cpp/container/list) / [forward_list](https://en.cppreference.com/w/cpp/container/forward_list)| none | O(1) | O(1) | O(1) | none |
|[set](https://en.cppreference.com/w/cpp/container/set) / [map](https://en.cppreference.com/w/cpp/container/map)| O(logN) |none|O(logN)|O(logN)|O(logN)|
|[unordered_set](https://en.cppreference.com/w/cpp/container/unordered_set) / [unordered_map](https://en.cppreference.com/w/cpp/container/unordered_map)| Q(1) mean | none | O(1) mean| O(1) mean| O(1) mean|

## Vector
### [Implementation](https://github.com/byteihq/Vector)

## Deque
### [Idea](https://github.com/byteihq/Deque)

## Stack
### Idea
```cpp
template<typename T>
class Stack {
private:
    struct Node {
        T value_;
        Node* next_;
    };
    Node* head_;
};
```
```cpp
template<typename T>
class Stack {
private:
    T* data;
    size_t head;
};
```
### Notes
_Stack is a LIFO data structure. It has methods push (by default it calls deque.push_back()) and pop (by default it calls deque.pop_back())_

## Queue
_Similar to stack, but it's a FIFO data structure. Also has methods push (by default it calls deque.push_back()) and pop (by default it calls deque.pop_front())_

## Priority Queue
_Similar to queue but it has logarithmic insertion and extraction, because of it stores objects in an orderly fashion, it allows to get the largest object for the constant time_

## Forward_List
### Idea
```cpp
template<typename T>
class ForwardList {
private:
    struct Node {
        T value_;
        Node* next_;
    };
    Node* head_;
};
```
### Notes
[How to reverse a forward list?](https://www.youtube.com/watch?v=PQIHq0vfADI&ab_channel=CodeWhoop)

## List
### Idea
```cpp
template<typename T>
class List {
private:
    struct Node {
        T value_;
        Node* next_;
        Node* prev_;
    };
    Node* head_;
};
```
### Notes
[Method splice has a linear complexity when we want to splice a part of another list, because we need to recalculate a new size](https://en.cppreference.com/w/cpp/container/list/splice)

## GCC Compile Flags
1. **-Wpedantic (-pedantic)** - checks that the code complies with the ISO C ++ standard, reports on the use of prohibited extensions, on the presence of extra semicolons, lack of line breaks at the end of the file, and other useful things
2. **-Werror** - warning = error
3. **-Wall** - turn on basic warnings
4. **-Wextra** - turn on extra warnings
5. **-Wshadow** - warn whenever a local variable or type declaration shadows another variable
6. **-Wnon-virtual-dtor** - tells the compiler to issue a warning when a class appears to be polymorphic, yet it declares a non-virtual one

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
### Pointers arithmetic
```cpp
int8_t i8;
int64_t i64;
int8_t *p8 = &i8;
int64_t *p64 = &i64;

p8 += 10; //shift by 10 * sizeof(int8_t) bytes = 10 bytes
p64 += 10; //shift by 10 * sizeof(int64_t) bytes = 80 bytes;
```
### Smart Pointers
1. [Scooped Ptr](https://cs.brown.edu/~jwicks/boost/libs/smart_ptr/scoped_ptr.htm) - **uncopyable, unmovable**
2. [Weak Ptr](https://en.cppreference.com/w/cpp/memory/weak_ptr) - **std::weak_ptr models temporary ownership: when an object needs to be accessed only if it exists, and it may be deleted at any time by someone else, std::weak_ptr is used to track the object, and it is converted to std::shared_ptr to assume temporary ownership. It has _expired_ method to check whether the referenced object was already deleted**
3. [Unique Ptr](https://en.cppreference.com/w/cpp/memory/unique_ptr) - **uncopyable, movable**
4. [Shared Ptr](https://en.cppreference.com/w/cpp/memory/shared_ptr) - **copyable, movable (also has atomic reference counter)**

## Diamond inheritance problem
### Case
```cpp
struct A {
    int a;
};

struct B : public A {
    int b;
};

struct C : public A {
    int c;
};

struct D : public B, public C {
    int d;
};

int main() {
    D d;
    d.a;
}
```
_Result - CE_

_Location of objects in memory - ( a )( b )( a )( c )( d )_
### Possible solution
```cpp
struct A {
    int a;
};

struct B : public virtual A {
    int b;
};

struct C : public virtual A {
    int c;
};

struct D : public B, public C {
    int d;
};

int main() {
    D d;
    d.a;
}
```
_Location of objects in memory - ( b_ptr )( b )( c_ptr )( c )( d )( a )_

### Notes
1. If we'll inherit virtually only one time, it won't solve this problem
```cpp
struct A {
    int a;
};

struct B : public A {
    int b;
};

struct C : public virtual A {
    int c;
};

struct D : public B, public C {
    int d;
};

int main() {
    D d;
    d.a;
}
```
_Location of objects in memory - ( a )( b )( c_ptr )( c )( d )( a )_

2. Virtual inherit in the also won't solve the problem.
```cpp
struct A {
    int a;
};

struct B : public A {
    int b;
};

struct C : public A {
    int c;
};

struct D : public virtual B, public virtual C {
    int d;
};

int main() {
    D d;
    d.a;
}
```
_Location of objects in memory - ( d_ptr )->( b_ptr && c_ptr )( d )( a )( b )( a )( c )_

3. Kill this guy
```cpp
struct A {
    int a;
};

struct B : public A {
    int b;
};

struct D : public B, public A {
    int d;
};

int main() {
    D d;
    d.a;
}
```
_Location of objects in memory - ( a )( b )( a )( d )_
## Polymorphism
### Static
```cpp
struct A {
    void f() { std::cout << "A"; }
};

struct B : public A {
    void f() { std::cout << "B"; }
};

int main() {
    A a;
    a.f();
    B b;
    b.f();
    b.A::f();
}
```
_Output - ABA_

_Which method should be called is only decided at compile time_
### Dynamic
_Which method should be called is decided at runtime_
#### Case 1
```cpp
struct A {
    void f() { std::cout << "A"; }
};

struct B : public A {
    void f() { std::cout << "B"; }
};

int main() {
    B b;
    A& ar = b;
    ar.f();
}
```
_Output - A_
#### Case 2
```cpp
struct A {
    virtual void f() { std::cout << "A"; }
};

struct B : public A {
    void f() { std::cout << "B"; }
};

int main() {
    B b;
    A& ar = b;
    ar.f();
}
```
_Output - B_

_The same output will be if we'll write **virtual** before f() in B_
#### Case 3
```cpp
struct A {
    virtual void f() { std::cout << "A"; }
};

struct B : public A {
    void f() const { std::cout << "B"; }
};

int main() {
    B b;
    A& ar = b;
    ar.f();
}
```
_Output - A_
#### Case 4
```cpp
struct A {
    virtual void f() { std::cout << "A"; }
};

struct B : public A {
    void f() { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - CE_
#### Case 5
```cpp
struct A {
    virtual void f() const { std::cout << "A"; }
};

struct B : public A {
    void f() { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - A_
#### Case 6
```cpp
struct A {
    virtual void f() const { std::cout << "A"; }
};

struct B : public A {
    void f() const { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - B_
### Key word _override_
_Indicates that the function has been overridden, required by code-style_
#### Case 1
```cpp
struct A {
    virtual void f() const { std::cout << "A"; }
};

struct B : public A {
    void f() const override { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - B_
#### Case 2
```cpp
struct A {
    virtual void f() const { std::cout << "A"; }
};

struct B : public A {
    void f() override { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - CE_
### Key word _final_
_Disallows further overrides_
#### Case 1
```cpp
struct A {
    virtual void f() const { std::cout << "A"; }
};

struct B : public A {
    void f() const override final { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - B_
#### Case 2
```cpp
struct A {
    virtual void f() const final { std::cout << "A"; }
};

struct B : public A {
    void f() const override { std::cout << "B"; }
};

int main() {
    B b;
    const A& ar = b;
    ar.f();
}
```
_Output - CE_
## Hunter
### Install
```sh
wget https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake -O cmake/HunterGate.cmake
```
