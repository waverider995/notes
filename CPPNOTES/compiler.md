## Prefer consts，enums，and inlines to #defines

## extern 关键字
c++ 支持函数重载，被 c++ 编译的函数在库中的名字与 C 语言不同。extern "C" 解决名字匹配问题

## 内联函数
* 编译优化，减小调用函数的额外开销
* inline 必须与函数定义体放在一起才能使函数成为内联，仅将 inline 放在函数声明前面不起任何作用
* 定义在类声明之中的成员函数将自动地成为内联函数