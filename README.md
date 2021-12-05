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
* [HashTable](https://github.com/byteihq/cheat-sheets#hashtable)
  + [Idea](https://github.com/byteihq/cheat-sheets#idea-4) 
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
      - [Shoot yourself in the leg](https://github.com/byteihq/cheat-sheets/blob/main/README.md#shoot-yourself-in-the-leg)
    + [Key word override](https://github.com/byteihq/cheat-sheets/blob/main/README.md#key-word-override)
      - [Case 1](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-1-1)
      - [Case 2](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-2-1)
    + [Key word final](https://github.com/byteihq/cheat-sheets/blob/main/README.md#key-word-final)
      - [Case 1](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-1-2)
      - [Case 2](https://github.com/byteihq/cheat-sheets/blob/main/README.md#case-2-2)
    + [Vtables](https://github.com/byteihq/cheat-sheets/blob/main/README.md#vtables)
      - [Example](https://github.com/byteihq/cheat-sheets/blob/main/README.md#example) 
* [Design Patterns](https://github.com/byteihq/cheat-sheets/blob/main/README.md#design-patterns)
  + [Factory Method](https://github.com/byteihq/cheat-sheets/blob/main/README.md#factory-method)
    - [Example](https://github.com/byteihq/cheat-sheets/blob/main/README.md#example)
    - [Notes](https://github.com/byteihq/cheat-sheets/blob/main/README.md#notes-4)
  + [Singleton](https://github.com/byteihq/cheat-sheets/blob/main/README.md#singleton)
    - [Example](https://github.com/byteihq/cheat-sheets/blob/main/README.md#example-by-scott-meyers)
    - [Notes](https://github.com/byteihq/cheat-sheets/blob/main/README.md#notes-5)
  + [Observer](https://github.com/byteihq/cheat-sheets/blob/main/README.md#observer)
    - [Example](https://github.com/byteihq/cheat-sheets/blob/main/README.md#example-1) 
    - [Notes](https://github.com/byteihq/cheat-sheets/blob/main/README.md#notes-6)
  + [Adapter](https://github.com/byteihq/cheat-sheets/blob/main/README.md#adapter)
    - [Example](https://github.com/byteihq/cheat-sheets/blob/main/README.md#example-2)
    - [Notes](https://github.com/byteihq/cheat-sheets/blob/main/README.md#notes-7)
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

## HashTable
### [Idea](https://github.com/byteihq/HashTable/blob/main/README.md)

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
#### Shoot yourself in the leg
```cpp
class A {
public:
    virtual void f() {
        std::cout << "A";
    }
};

class B : public A{
private:
    void f() override {
        std::cout << "B";
    }
};

int main() {
    A* a = new B();
    a->f();
    delete a;
    return 0;
}
```
_Output - B_

![](https://sun9-61.userapi.com/impg/AQ9Z2xGxRNt8PNujNTxYU_kFFmfzwVWzF3NxLg/M7gDMXMygqc.jpg?size=510x587&quality=96&sign=9810b2a2294fa9df41d4948adcc86f89&type=album)
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
### Vtables
#### Example
```cpp
struct A1 {};

struct A2 {
    int a;
};

struct A3 {
    int a;
    void f() {}
};

struct A4 {
    int a;
    virtual void f() {}
};

int main() {
    std::cout << sizeof(A1) << ' ' << sizeof(A2) << ' ' << sizeof(A3) << ' ' << sizeof(A4);
    return 0;
}
```
_Output - 1 4 4 16_

**A4 - ( v_ptr ) -> ( typeinfo_ptr [RTTI](https://ru.wikipedia.org/wiki/%D0%94%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F_%D1%82%D0%B8%D0%BF%D0%B0_%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85) )( &f() ) ( a ). 8 + 4 = 12 = 16 (due to alignment)**
## Design Patterns
### Factory Method
#### Example
```cpp
class Product {
private:
    size_t cost_;
    size_t weight_;
public:
    virtual ~Product() {}

    virtual Product* create() = 0;

    size_t cost() const { return cost_; }
    
    size_t weight() const { return weight_; }
};

class Bread : public Product {
public:
    Product* create() override {
        return new Bread;
    }
};

class Milk : public Product {
public:
    Product* create() override {
        return new Milk;
    }
};
```
#### Notes
A factory method defines a method that should be used instead of calling a **new** one to create product objects. Subclasses can override this method to change the type of products they create.
### Singleton
#### Example (by Scott Meyers)
```cpp
class Singleton {
private:
  Singleton() {}
  Singleton(const Singleton&) = delete;
  Singleton& operator=(Singleton&) = delete;
public:
  static Singleton& getInstance() {
    static Singleton instance;
    return instance;
  }
};
```
#### Notes
It's very simple to implement a single clumsy Singleton - you just need to hide the constructor and provide a static creating method. **The same class behaves incorrectly in a multithreaded environment**. Multiple threads can simultaneously call the Singleton's getter method and create multiple instances of the object at once.
### Observer
#### Example
```cpp
class Handler {
public:
    class HandlerObserver {
    public:
        virtual void Update() const = 0;
    };

    void AddObserver(const HandlerObserver &observer);

    void DeleteObserver(const HandlerObserver &observer);

    void DoSmth();

private:
    void NotifyAll();

    std::vector<const HandlerObserver *> observers_;
};

void Handler::AddObserver(const HandlerObserver &observer) {
    observers_.push_back(&observer);
}

void Handler::DeleteObserver(const HandlerObserver &observer) {
    auto it = std::remove(observers_.begin(), observers_.end(), &observer);
    observers_.erase(it, observers_.end());
}

void Handler::DoSmth() {
    // some code
    NotifyAll();
    // other code
}

void Handler::NotifyAll() {
    for (const auto &observer: observers_) {
        observer->Update();
    }
}

class Observer : public Handler::HandlerObserver {
public:
    void Update() const override;
};

void Observer::Update() const {
    // notification
}
```
#### Notes
Observer is a behavioral design pattern that creates a subscription mechanism that allows one object to watch and respond to events occurring in other objects.
### Adapter
#### Example
```cpp
class English {
public:
    virtual std::string sayHello() const {
        return "Hello";
    }
};

class Spanish {
public:
    std::string sayHello() const {
        return "Hola";
    }
};

class Adaptor : public English {
private:
    Spanish *spanish_;

    std::string translateToEnglish(const std::string& msg) {
        // translation
        return translatedMsg;
    }
public:
    Adaptor(Spanish *spanish) : spanish_(spanish) {}

    std::string sayHello() const override {
        auto spanishHello = spanish_->sayHello();
        return translateToEnglish(spanishHello);
    }
};

void EnglishSpeakingPerson(English* eng) {
    // some code
}

int main() {
    Spanish spanish;
    Adaptor adaptor(&spanish);
    EnglishSpeakingPerson(&adaptor);
    return 0;
}
```
#### Notes
The adapter acts as a layer between two objects, converting the calls of one into calls that are understandable to the other.
## ThreadPool
![](https://bmstu-iu8-cpp.github.io/cpp-upper-intermediate/lec_07/res/multitask2.jpg)
### [Implementation](https://github.com/progschj/ThreadPool)
### Notes
A thread pool is a set of a fixed number of threads that are created when the application starts. Threads then sit and wait for requests coming to them, usually through a semaphore-driven queue. When a request is made and at least one thread is waiting, the thread wakes up, services the request, and returns to waiting on the semaphore. If no threads are available, requests are queued until one of them is available. Thread pools are generally a more efficient way to manage resources than just starting a new thread for each request. However, some architectures allow new threads to be created and added to the pool as the application runs, depending on the load on the request.
## Hunter
### Install
```sh
wget https://raw.githubusercontent.com/cpp-pm/gate/master/cmake/HunterGate.cmake -O cmake/HunterGate.cmake
```
