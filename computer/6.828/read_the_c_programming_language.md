# 《The C Programming Language》学习笔记

## 第五章：指针和数组

1. 单目运算符的优先级均为2，且结合方向为自右向左。
```
*ip++;  // 将指针ip的值加1，然后获取指针ip所指向的数据的值
(*ip)++;  // 将指针ip所指向的数据的值加1
```

2. 当计算`a[i]`时，C编译器会立即将其转换为`*(a+i)`。也就是说，C语言中数组下标表达式和指针加偏移是等价的。

3. 数组名和指针的一个区别：指针是变量，可以进行赋值和加减运算；数组名不是变量，不能进行赋值和加减运算。

4. `p[-1], p[-2]`在语法上是合法的，只要保证元素存在，后向索引数组也是可以的。

5. 指向同一个数组（包括数组最后一个元素的下一个元素）的两个指针可以进行大小比较，而对没有指向同一个数组的两个指针进行大小比较的行为是undefined的。

6. 指针的合法操作：同类指针赋值、指针加减某个整数、指向同一数组的两个指针相减或比较大小、将指针赋值为0或与0比较；指针的非法操作：两个指针相加、相乘、相除，以及指针与浮点数相加减等。

7. `char *pmsg = "now is the time"；`是将一个指向字符数组的指针赋值给pmsg，而不是字符串拷贝。C语言不提供任何对整个字符串作为一个单元进行处理的操作符。

8. 注意通过字符串指针修改字符串内容的行为是undefined的：
```
char amsg[] = "now is the time";  // an array
char *pmsg = "now is the time";   // a pointer
```