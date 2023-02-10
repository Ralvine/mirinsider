---
tags:
 - 后端开发
hide: 
 - tags
comments: true
---
# C++ 基础
<div class="badges">
<span class="badge badge1">后端开发</span>
</div>

## 学习概况
!!! abstract ""
    正在施工

!!! quote "资料"
    - [翁恺 C++](https://www.bilibili.com/video/BV1dE41167hJ/?spm_id_from=333.337.search-card.all.click&vd_source=e81e93bc6892fd0d7e19b265d26a2b3a)

## 面向对象 (Object-Oriented)
### 基本原理

- object=entity (实体): attributes+services (属性+服务)
- 数据 (静态/动态): visible/invisible
- 映射: 问题域 -> 解决域
- 和面向过程的区别
  - 描述事情发生的流程/存在实体导向解决
  - C++: Struct -> Class (Private+Public) 给结构体提供操作 (operator)
- Design+Implementations (算法的设计+编写)

### 面向对象编程

- Objects: 实体, 收发消息: Data+Method (数据+方法)
  - Receivers: 接收者自行决定如何操作
  - Messages (消息) 对 Receiver 的作用
    - 改变状态
    - 返回结果
- Class: 对 Object 实例的抽象
  - 类定义对象的属性 所有对象都有一种类型
  - 一切都是对象
  - 程序是一系列通过彼此收发消息实现做什么的对象
  - 接口: 同类对象可以接受相同消息 (Ex. 灯泡)
  - 函数
- Encapsulation (封装)

### 编译

- 编译预处理`#include`
  - 编译器将会自动将被引用的库/文件代码前置
  - `"xx.h"` 当前目录
  - `<xx.h>` 系统目录
  - `<xx>`=`"xx.h"`
- 一个.cpp文件即一个编译单元

### 头文件

- Declarations (声明)
- Definitions (定义)
- 头文件中的宏定义 `#define _H_ `
  - 避免导入头文件时重复定义

## 类的设计 (Class)

- 解析符 `::`

### Ex: Ticket Machine

- TicketMachine.h

```c++
#ifndef TICKETMACHINE_H_
#define TICKETMACHINE_H_

class TicketMachine {
public:
    TicketMachine();
    virtual ~TicketMachine();
    void showPrompt();
    void insertMoney(int money);
    void showBalance();
    void printTicket();
    void showTotal();
private:
    const int PRICE;
    int balance;
    int total;
};
#endif
```

- TicketMachine.cpp

```c++
#include "TicketMachine.h"
#include <iostream>

TicketMachine::TicketMachine() {
}

TicketMachine::~TicketMachine() {
}

void TicketMachine:: showPrompt() {
    std::cout << "something." << std::endl;
}

void TicketMachine:: insertMoney(int money) {
    balance += money;
}
```

### g++
`g++ a.cpp`

- --save-temps
- -Wall 输出所有Warning