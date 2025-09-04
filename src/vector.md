# vector

C++ 的vector的接口

- 访问元素
  - \[\]
  - at
  - front/back
  - data
- 尺寸/容量
  - size
  - capacity
  - reserve
  - shrink_to_fit
- 修改
  - clear
  - insert
  - emplace
  - erase
  - push_back
  - emplace_back
  - pop_back
  - resize
  - swap

## 如何使用vector

## vector的实现

扩容系数: 1.5或者2

## reserve是否会降低性能

除非是每次push_back之前v.reserve(v.size()+1), 正常的一次性reserve对性能没有什么影响.

## 关于迭代器失效

vector的迭代器失效基本符合直觉, 插入元素/删除元素会导致后面位置的迭代器失效. 如果发生了重新分配(capacity改变)会导致迭代器全部失效.

swap会导致end()失效

