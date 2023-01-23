## Inheritance
### Public Inheritance
1. B expands A
2. B is a special case of A
[Circle-Ellipse-Problem](https://en.wikipedia.org/wiki/Circle%E2%80%93ellipse_problem)
#### The Liskov Substitution Principle
_If  for each object o1 of type S there is an object o2 of type T such that for all
programs P defined in terms of T, the behavior of P is unchanged when o1 is
substituted for o2 then S is a subtype of T._
#### Slice problem
```cpp
struct A {
    int _a;

    A(int a) : _a(a) {}
};

struct B : public A {
    int _b;

    B(int b) : A(b / 2), _b(b) {}
};

int main() {
    B b1{10};
    B b2{8};

    A &a_ref = b1;
    a_ref = b2;
    std::cout << b1._a << ' ' << b1._b;
    return 0;
}
```
_Output - 4 10_
### (down / up)cast with non-virtual inheritance
```cpp
struct Padding {
    int x, y;

    virtual ~Padding() = default;
};

struct A {
    int _a;

    explicit A(int a) : _a(a) {}

    virtual ~A() = default;
};

struct B {
    int _b;

    explicit B(int b) : _b(b) {}

    virtual ~B() = default;
};

struct C: Padding, A, B {
    int _c;

    explicit C(int c): A(c * 2), B(c * 3), _c(c) {}
};

int main() {
    C *pc = new C(4);
    std::cout << std::hex << pc << ' ' << std::dec << pc->_c << std::endl;

    auto *pa = static_cast<A *>(pc);
    std::cout << std::hex << pa << ' ' << std::dec << pa->_a << std::endl;

    auto *pb = static_cast<B *>(pc);
    std::cout << std::hex << pb << ' ' << std::dec << pb->_b << std::endl;

    pc = static_cast<C *>(pa);
    std::cout << std::hex << pc << ' ' << std::dec << pc->_c << std::endl;

    pc = static_cast<C *>(pb);
    std::cout << std::hex << pc << ' ' << std::dec << pc->_c << std::endl;
    return 0;
}
```
### Diamond inheritance problem
#### Case
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
#### Possible solution
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
#### Notes
```cpp
struct A {
    int _a;

    A(int a) : _a(a) {}
};

struct B : public virtual A {
    int _b;

    B(int b): A(3 * b), _b(2 * b) {}
};

struct C : public virtual A {
    int _c;

    C(int c): A(4 * c), _c(3 * c) {}
};

struct D : public B, public C {
    D(int d): A(d / 2), B(d), C(d) {}
};

int main() {
    D d(4); // _a = 2; _a = 12; _a = 16 ???
    std::cout << d._a;
}
```
_Output - 2_
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

class B : public A {
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

### How to live now?
1. Virtual destructor
2. Final class
3. Stateless -> EBCO
4. Protected destructor

### PVC
```cpp
struct A {
    A() {
        ff();
    }

    void ff() {
        f();
    }

    virtual void f() = 0;

    virtual ~A() {};
};

struct B: public A {
    void f() override { std::cout << "B.f()"; }
};


int main() {
    B b;
    return 0;
}
```
### Static linking
```cpp
struct A {
    virtual void f(int a = 100) { std::cout << a << std::endl; }

    virtual void g() { std::cout << 100 << std::endl; }

    virtual ~A() {}
};

struct B: public A {
    void f(int a = 200) override { std::cout << a << std::endl; }

    virtual void g() override { std::cout << 200 << std::endl; }
};

int main() {
    A *a = new B;
    a->f();
    a->g();
    delete a;
    return 0;
}
```
_Output - 100 200_
### NVI
```cpp
struct A {
    void f(int a = 100) { fImpl(a); }

    virtual void fImpl(int a) { std::cout << a << std::endl; }

    virtual void g() { std::cout << 100 << std::endl; }

    virtual ~A() {}
};

struct B: public A {
    void fImpl(int a) override { std::cout << 2 * a << std::endl; }

    virtual void g() override { std::cout << 200 << std::endl; }
};

int main() {
    A *a = new B;
    a->f();
    a->g();
    delete a;
    return 0;
}
```
_Output - 200 200_
