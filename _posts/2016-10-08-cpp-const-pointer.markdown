---  
layout: post  
title:  "C++ 常量指针 和 指针常量"  
date:   2016-10-08 15:00:39 +0800  
---

### const 修饰普通变量以下写法是等价的:  
`const int val = 100;`  
`int const val = 100;`  

### const 修饰指针时一般有三种写法:  
1. `const int *val;`  
2. `int * const val;`  
3. `const int * const val;`  


第一种: 常量指针, 即指针 val 指向的内容不可变.  
`int i=10; `  
`int j=20;`  
`const int *p= &i;`  
`*p = 20; //error`  
`p=&j; //right`  

第二种: 指针常量, 即指针 val 本身地址不可变.  
`int i=10;`  
`int j=20;`  
`int * const p=&1;`  
`p=&j;  //error`  
`*p=5; //right`  

第三种是1和2的综合, 即指针 val 本身地址不可变, 同时指向的内容也不可变.  