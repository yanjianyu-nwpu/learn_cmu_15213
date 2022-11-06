# Linking

cc1 .c文件->汇编文件 .i

as 把汇编文件翻译成二进制文件 

## What do linker do

### 1 symbol resolution 符号解析

局部变量分配再栈中，不会再过程中被外部引用，所以不是符号定义

### 1.1 符号链接的类型

- Global symbols 模块内部定义的全局符号

- External Symbols 外部定义的全局符号

- Local symbols 本模块的局部符号

.symtab 记录符号表信息，是一个结构数据

每个表项结构如下 

![](C:\Users\yanjianyu\AppData\Roaming\marktext\images\2022-11-01-09-17-10-image.png)

会将解析的符号定义存储在目标文件中

在符号表里是 一个一个数组， 记录符号的名称，大小和位置

每个一个使用的地方都是 符号引用

## 2 relocation

把符号引用和符号定义链接

进入可执行文件之后可以在系统上执行

重定向在目标模块中的地址 只是记录在模块中的偏移量  对于数据也是如此

## 3 文件类型

### 3.1 .o

重定向目标文件 .o 文件   汇编文件 assembler

relocatedable object file 

### 3.2 可执行文件 a.out 文件

包含代能被直接复制到内存的表

### 3.3 分享文件.SO

### 3.4 generic name 通用名



## 4 GCC方案

- -Wall 可以发现静态一些警告分享

- -wl 命令传递 ld 连接器命令 其中 --wrap命令=foo 将 symbol替换成 ——wrap_symbol
  
  ```
  int fool(void);
  int  __wrap_foo(){
      
  }
  int bra(void){
      return foo();
  }
  ```
  
  `$ gcc wrap_foo.c main.c -Wl,--wrap=foo`
  
  结果如下，由于 `main` 和 `foo` 在同一个编译单元，`main` 调用的依然是 `foo` 本身。`bar` 中则被替换成了 `__warp_foo`。

## 用处

这个选项有什么场景使用呢？像单元测试框架 `cmocka` 函数打桩的实现原理就使用了这个特性。
