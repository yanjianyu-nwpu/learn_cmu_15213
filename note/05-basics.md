# Basics



## 1 note

简单汇编基础

- %取寄存器名字，后面是寄存器的名字

- push 把值放到某个寄存器

- mov 移动寄存器

- call 调用某个函数

- ret 返回

- pop 出栈

- lea load effective address 装入有效地址 
  
  - lea eax，【addr】
  
  - 把表达式addr的值放入eax寄存器

rsp是栈指针寄存器



计算符号

- addq 加

- subq 减

- imulq 乘

- salq shift左7移

- shrq 右移

- xorq 异或

- andq 与

- orq 或



比较符号

- sete 是否等于

- setne 是否不等于

- sets 反！

- setg 大于

- setg 大于等于

- setl 小于

- setle 小于等于

- seta 无符号数的大于
  
  - setb 无符号数的小于    



跳转操作

- jmp 1  无条件跳转

- je 等于0

## 2 小技巧

gdb 可以反编译 二进制文件 可执行文件 得到相应的汇编文件

## 附

assembly 汇编
