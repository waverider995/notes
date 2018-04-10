## 虚函数

* 定义为虚函数是为了让基类的指针可以调用子类的函数。虚函数只能借助指针或者引用来达到多态的效果

```c++
class Base
{
    virtual func(){};
}
class Derived : public base
{
    void func(){
        cout << "in child" << endl;
    }
}
void main()
{
    Base *a = new Derived();
    a->func();  // 这里调用Derived的func
}
```

## 纯虚函数
* 纯虚函数是在基类中声明的虚函数，它在基类中没有定义，但要求任何派生类都要定义自己的实现方法。在基类中实现纯虚函数的方法是在函数原型后加“=0”
```c++
virtual void func() = 0;
```
* 编译器要求在派生类中必须予以重写以实现多态性。同时含有纯虚拟函数的类称为抽象类，它不能生成对象。

* 定义纯虚函数的目的在于，使派生类仅仅只是继承函数的接口。

<br>

## 虚析构函数
为了能够正确地调用对象的析构函数，一般需要把顶层类的析构函数定义为虚函数

```c++
class Base
{
public:
    Base(){};
    virtual ~Base(){};
}
class Derived : public Base
{
public:
    Derived(){};
    ~Derived(){};
}

void main()
{
    Base *a = new Derived();
    delete a; 
    // 动态绑定，会先调用Derived的析构函数再调用Base的析构函数
}

```