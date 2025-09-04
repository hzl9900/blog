# stl1weekend

link: <https://github.com/parallel101/stl1weekend>

视频教程速度较慢, 记得自行加速.

## `std::Function`

function 可以存储函数指针, lambda, 仿函数等.

最简单的需求, 传一个无参数的函数指针

需要传递参数怎么办? 参数类型转为void* 传入, 在函数内部转回去. 这就是类型擦除.

需要传递多个参数怎么办? 把参数打包为一个结构体, 再转为void* 类型擦除.

实现闭包: 把结构体成员改为指针或者引用.

实现仿函数: 重载函数调用运算符

lambda的实现实际上就是匿名结构体.

## `std::unique_ptr`

传入一个删除器作为参数

内部保存一个裸指针和一个删除器(如果删除器为空, 可以实现空类优化)

make_unique的实现, 把unique_ptr的初始化和new封装在一起.

## `std::array`

实现array只需要按照标准的要求写就可以了. 注意要特殊处理长度为0的array.

## `std::vector`

包含数据指针, size, capacity, 和分配器(可能的空基类优化). 分配器默认是无状态的.

编写vector代码的时候需要手动控制存储分配/解分配和对象构造/析构

allocator提供allocate/deallocate 和 construct/destory
分别是对operator new 和placement new 的包装

麻烦的地方在于扩容时保证异常安全

使用move_if_noexcept, 如果移动不抛出异常或者可以复制构造, 返回T&&, 否则返回T&&

## `std::list`

实现双向链表

## `std::optional`

tag类, union惰性初始化, 万能引用, 完美转发

## `std::map`

红黑树

## `std::shared_ptr`

使用引用计数实现多个指针共享资源. 需要额外创建一个管理块

enable_shared_from_this

# `std::variant`
