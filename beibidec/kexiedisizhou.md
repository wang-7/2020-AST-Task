# 张恩灿科协第二周task

**2、**
**局部变量是在函数内定义的变量，只在本函数范围类有效。  
而全局变量是在函数外定义的变量，从定义变量的位置到本源文件结束都有效。**  
**3、** 

- **return语句用在函数末尾。**  
  **return语句的一个作用就是从函数中返回一个值，**  
  **另一个作用是终止（退出）执行函数。**
- **函数是C语言的主要组成部分。**  
  **函数的定义包含一个函数头（function head，或称为声明符（declarator））和一个函数块。  
  函数头指定了函数的名称、返回值的类型以及参数的类型和名称（如果有参数的话）。  
  函数块中的语句明确了该函数要做的事。  
  “名称”指函数名，而“类型”包含至少一个类型修饰符，用来定义函数返回值的类型。返回值的类型可以是 void 或者任何对象类型（数组除外）  
  函数类型指定了其返回值的类型。**
- **返回值是一个函数的处理结果,  
  使用函数返回值需调用这个函数，调用的结果即为函数的返回值**  
  **区别（以下是在网上查找的一些资料，还没完全理解）：**  

 **（1）：传递引用给函数与传递指针的效果是一样的。**  
 **这时，被调函数的形参就成为原来主调函数中的实参变量或对象的一个别名来使用，  
 所以在被调函数中对形参变量的操作就是对其相应的目标对象(在主调函数中)的操作。**  
**（2）：使用引用传递函数的参数，在内存中并没有产生实参的副本，它是直接对实参操作;  
而使用一般变量传递函数的参数，当发生函数调用时，需要给形参分配存储单元，  
形参变量是实参变量的副本;  
如果传递的是对象，还将调用拷贝构造函数。  
因此，当参数传递的数据较大时，用引用比用一般变量传递参数的效率和所占空间都好。**  
**（3）：使用指针作为函数的参数虽然也能达到与使用引用的效果，但是,  
在被调函数中同样要给形参分配存储单元，且需要重复使用"*指针变量名"的形式进行运算，  
这很容易产生错误且程序的阅读性较差;另一方面，在主调函数的调用点处，  
必须用变量的地址作为实参。而引用更容易使用，更清晰。  **

**结合资料我自己的理解：传地址实际传递的是实参的一个拷贝，对拷贝进行的操作不影响实参，但可通过改变地址改变实参的值，即通过对地址的操作改变变量；传引用是直接对对象进行操作。  **

**二者在函数格式与功能上不同。  **

- **递归即函数直接或间接调用自己**

**P1001的三种方法的原代码（都已通过洛谷测试）都已截图上交，不知道符不符合要求。**  

**科协第三周Task**

___


## 基础任务一

**一维数组的定义方式为：[存储类型]数据类型 数组名 [常量表达式] 
二维数组的定义方式为：[存储类型]数据类型 数组名[下标][下标] 
字符数组的定义方式为：char a[ ]**

## 基础任务二

**在程序设计中，为了处理方便，把具有相同类型的若干变量按有序 
的形式组织起来。  这些按序排列的同类数据元素的集合称为数组。
以C语言中的一维数组为例，一维数组的定义方式为： 
类型说明符 数组名 [常量表达式];
其中，类型说明符是任一种基本数据类型或构造数据类型。 
数组的类型实际上是指数组元素的取值类型。
其实，从变量的角度看，每个数组元素（相当于变量） 
具有的属性：数组元素名、数据类型、值、内存地址中， 
能每个元素都相同的也只能是数据类型。**

**提高任务**

**一、结果为POINT
ER
ST
EW       *c[]是一个指针数组， 后一个也为指针数组，最后一个则为指向第二个指针数组的指针。++cpp即向前方移动一个数据,移动后指向的是c+2而c+2指向的又是POINT。剩下几个不明白。**

**二、结果为0000000000100020
0000000000100001
0000000000100004      程序中p+0x1指指针变量里的地址移动一个单元。  **

**而这个程序中结构体的大小为20字节，即偏移二十给字节。  **

**(unsigned long)p + 0x1则涉及强制转换，将指针变量p保存的值强制转换成无符号的长整数型。所以这个表达式实际是一个无符号整数加上一个整数。  **

**(unsigned int*)p + 0x1则把p指向的对象换成无符号整型，而无符号整数一个单位长4个字节。  **



**三、结果为4
2000000       &a是整个数组的首地址,&a+1实际上偏离了一个数组的大小即a[4]，ptr1[-1]则又向后偏移了一个int 的大小即a[3]等于4。把a强制类型转换成int之后就编变成 数值 00000000 了，不在有地址的任何附加属性，对其进行+1 操作也是纯粹数学上的加1 变成00000001此时又强制类型转换成(int*) 那么此时指向的内存内容是 00 00 00 02 00 00 00
对其取内容（以%x的方式取，取4个字节） 取出来 是00 00 00 02 ，这个按16进制解释出来就是 2000000**

**此次科协作业在网上查找了很多资料，但任有不少不懂的地方。部分答案为结合网上资料与自己的理解所写。**