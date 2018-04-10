## 常量
```c++
const double PI = 3.14159;
```


## 输入参数
```c++
void func(const int &a);
```

## 常量返回值
* 如果给以“指针传递”方式的函数返回值加const 修饰，那么函数返回值（即指针）的内容不能被修改，该返回值只能被赋给加const 修饰的同类型指针
```c++
const char * GetString(void);
const char *str = GetString();
```

## 常量成员函数
* 成员函数后加 const， 此函数权限为只读，不能修改成员变量
* 如果一个对象为 const， 那么它只有权限调用 const函数