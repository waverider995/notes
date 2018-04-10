## Vector

* 初始化
```c++
vector<int> a(10)
vector<int> a(10, 1)
vector<int> a(b)
vector<int> a(b.begin(), b.begin()+3)
```
* 操作
```c++
vec.assign(b.begin(), b.begin()+3)
vec.back()
vec.front()
vec.clear()
vec.empty()
vec.pop_back() //删除最后一个元素
vec.erase(a.begin()+1, a.begin()+3) //不包含最后一个
vec.insert(a.begin()+1, 5) //在此位置前面插入5
vec.insert(a.begin()+1, 3，5) //3个5
vec.insert(a.begin()+1, b.begin()+3, b.begin()+6)
vec.capacity()
vec.resize(10) //多删少补，数值随机
vec.resize(10,2) // 补2
vec.reserve(100) //扩容，避免内存多次扩容
vec.swap(b)
```
* 算法
```c++
#include<algorithm>
sort(vec.begin(), vec.end())
reserve(vec.begin(), vec.end())
copy(a.begin(), a.end(), b.begin()+1) // 把a复制到b，包括b+1的位置，覆盖
find(a.begin(), a.end(), key) //返回位置
```