# void*泛型

## 泛型编程

泛型编程是一种编程方法，旨在编写可适用于**不同数据类型的通用代码**，从而提高代码的重用性和可维护性，减少代码冗余。



## 泛型技术

### void*指针

1. void*是一种通用指针，可以指向任意类型的内存地址，及可以用任意类型的指针对void指针赋值，不需强制类型转换，但要将void指针赋给其他类型指针，则需**强制类型转换**。

2. 使用时应格外留意内存大小，类型转换。常用sizeof求得内存大小，mallocsize，memcpy指定内存大小与赋值。

3. 实例：

   实现两个元素的交换

 ~~~c
 int swap(void *p1,void *p2,int size)
 {
     void *temp;
     if(temp = malloc(size) == NULL)
         return -1;
     memcpy(temp,p1,size);
     memcpy(p1,p2,size);
     memcpy(p2,temp,size);
     free(temp);
     return 0;
 }
 ~~~

### 宏定义实现泛型

