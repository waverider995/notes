## 静态成员变量和函数
* 静态成员被所有对象公有


* 不能通过类名来调用类的非静态成员函数
```c++
class A
{
public:
    void init(){}
    static void func(){}
};
void main()
{
    A::init(); // wrong
    A::func(); // ok
}
```

* 静态成员函数不能引用非静态成员

静态成员函数属于整个类，在实例化对象之前就已经分配空间。非静态成员必须在类实例化对象后才有内存空间

```c++
class A
{
public:
    void init(){}
    static void output()
    {
        cout << m_x;
    }
private:
    int m_x;
}
void main()
{
    A a;
    a.output(); // error
}
```


