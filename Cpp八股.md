<!--
 * @Author: Vanish
 * @Date: 2024-10-19 10:51:44
 * @LastEditTime: 2024-10-19 11:41:47
 * Also View: http://vanishing.cc
 * Copyright@ https://creativecommons.org/licenses/by/4.0/deed.zh-hans
-->
# 1.malloc,free,new,delete 的区别

## 答案

在C/C++中，malloc和free是标准库函数，用于手动管理内存，而new和delete是C++运算符，提供更高级的内存管理。new会自动计算所需内存、返回对象类型指针，并在分配失败时抛出异常，还会调用构造函数；而malloc则需手动计算内存、返回void*指针，并在分配失败时返回NULL。释放内存时，delete会调用析构函数，而free则不会.


## 背景

- malloc,free 是C/C++的标准库函数，用来分配和释放内存。
- new,delete 是C++的运算符，用来分配和释放内存。

## 差别

- new 自动计算需要分配内存大小,malloc需要手动计算
- new 返回对象类型指针,mallock返回void* 需要手动类型转换
- new 分配失败抛出异常,malloc分配失败返回NULL
- new 调用构造函数,malloc需要手动调用构造函数
- new 在free store(自由存储区)上分配内存,malloc在堆上分配内存
- delete 需要对象类型指针,free需要void* 
- delete 调用析构函数,malloc需要手动调用析构函数

## 知识补充

- new的步骤
  - operator new
  - 申请足够的内存
  - 调用构造函数,初始化成员变量
- delete的步骤
  - 调用析构函数
  - operator delete
  - 释放内存

## 相关问题

- malloc是怎么分配空间的?
- malloc分配的是物理内存还是虚拟内存?
- malloc调用后是否立刻得到物理内存?
- free(p)如何知道该释放多大空间?

# 2.简述多态实现原理



