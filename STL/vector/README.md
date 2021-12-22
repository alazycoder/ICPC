# vector

熟练使用vector相关的STL，能大幅提升codeforces的A、B题的解决速度。

## Capacity

### resize

```c++
void resize (size_type n);
void resize (size_type n, const value_type& val);
```
注意：
* resize如果提供val参数，只是用val去填充新加入的元素，**不会影响已有的元素**。
* resize如果不提供val参数，则用该元素类型的初始值去填充新加入的元素，**不会影响已有的元素**。

```c++
#include <iostream>
#include <vector>

int main ()
{
  std::vector<int> my_vector;

  // set some initial content:
  for (int i=1; i<10; i++)
    my_vector.push_back(i);

  my_vector.resize(5);
  my_vector.resize(8, 100);
  my_vector.resize(12);

  std::cout << "my_vector contains:";
  for (int i=0; i<my_vector.size(); i++)
    std::cout << ' ' << my_vector[i];
  std::cout << '\n';
  //my_vector contains: 1 2 3 4 5 100 100 100 0 0 0 0
  return 0;
}
 Edit & Run

```

## Element access

### front

```c++
      reference front();
const_reference front() const;
```

获取第一个元素的引用。注意：
* 返回的是第一个元素的**引用**
* 不要与vector::begin混淆，vector::begin返回的是迭代器，vector::front返回的是元素的引用

```c++
#include <iostream>
#include <vector>

int main ()
{
  std::vector<int> my_vector;

  my_vector.push_back(78);
  my_vector.push_back(16);

  // now front equals 78, and back 16

  my_vector.front() -= my_vector.back();

  std::cout << "my_vector.front() is now " << my_vector.front() << '\n';
  
  // output: my_vector.front() is now 62
  
  return 0;
}
```

### back

获取最后一个元素的引用。注意：
* 返回的是最后一个元素的**引用**
* 不要与vector::end混淆，vector::end返回的是迭代器，vector::back返回的是元素的引用
