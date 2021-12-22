# vector

熟练使用vector相关的STL，能大幅提升codeforces的A、B题的解决速度。

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
