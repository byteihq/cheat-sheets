## Thread
**A thread of execution (also known as a thread) is a single flow of control within a program**

## Memory
**A memory Location is either an object of scalar type or a maxiaml sequence of adjacent bit-fileds all having nonzero width**

## Data race
**Two expression evaluations conflict if one of them modifies a memory location and the other one reads or modifies the same memory location**

**The execution of a program contains a data race if it contains two potentially concurrent conflicting actions, at least one of which is not atomic, and neither happens before the other, except for the special case for signal handlers. Any such data race results in UB**

## Mutex
**std::mutex вводят оотношение happens-before между доступами**
### Интерфейс
- lock() - захватить мьютекс. Попытка вызвать повторно в том же потоке - UB
- try_lock() - захватил ?
- unlock() - отпустить мьютекс. Попытка разблокировать не захваченный мьютекс - UB

## RAII Mutex = lock_guard
```cpp
std::lock_guard<std::mutex> lk(m, std::adopt_lock); // only unlock in destructor 
```
```cpp
std::lock(m1, m2);
std::lock_guard<std::mutex> lk1(m1, std::adopt_lock);
std::lock_guard<std::mutex> lk2(m2, std::adopt_lock);
```
```cpp
// since CPP17
std::scoped_lock s1(m1, m2); 
```
