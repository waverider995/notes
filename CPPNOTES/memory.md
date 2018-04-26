## C++ 的智能指针

### unique_ptr

### shared_ptr
支持多个 shared_ptr 指向同一个对象，并记录(reference counting)

一旦某个对象的引用计数变为0，这个对象就会被自动删除

#### 循环引用
```c++
#include <iostream>  
#include <memory>  

using std::shared_ptr;

class B;
class A{
private:
    shared_ptr<B> p_b_;
public:
    set(shared_ptr<B> p){
        p_b_ = p;
    }
};
class B{
private:
    shared_ptr<A> p_a_;
public:
    set(shared_ptr<A> p){
        p_a_ = p;
    }
}
int main()
{
    shared_ptr<A> a;
    shared_ptr<B> b;
    if (a && b) {
        a->set(b);
        b->set(a);
    }
    return 0;
}
```

### weak_ptr

weak_ptr 是一种不控制对象生命周期的智能指针, 它指向一个 shared_ptr 管理的对象. 进行该对象的内存管理的是那个强引用的 shared_ptr. weak_ptr只是提供了对管理对象的一个访问手段

　　weak_ptr 设计的目的是为配合 shared_ptr 而引入的一种智能指针来协助 shared_ptr 工作, 它只可以从一个 shared_ptr 或另一个 weak_ptr 对象构造, 它的构造和析构不会引起引用记数的增加或减少

#### 成员函数

* expired : 检测对象是否已经释放
* lock : 获取所管理对象的强引用(shared_ptr)， 如果 expired 为 true，返回 nullptr

#### 避免循环引用造成的内存泄露


