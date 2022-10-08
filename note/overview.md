# Overview



## 1 笔记

- 计算机不能真的产生随机数



## 2 技术

- 内存随机访问也会快比如
  
  ```
  void copyij(int ast[2048][048]){
      int i,j;
      for(i=0;i<2048;i++){
          for(j=0;j<2048;j++){
              dst[i][j] = src[i][j]
          }
      }
  }
  ```
  
  入股 i，j for循环改换位置，速度就慢了
  
     一个4.3ms 一个 81.8ms

- 
