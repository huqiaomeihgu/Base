### 数据库

#### 第一章 绪论

1. 数据结构的定义：（R,D）=（集合，关系）

2. 算法看重两点：

（1）健壮性 

（2）效率

3. 效率：时间复杂度 ,就是语句执行的频度，语句重复执行的次数,这里指的是最坏情况下的时间复杂度
   
       对数（log）<线性(kx)< 二次多元(2x2)<三次及以上多元(x3)<指数（2n）

       (1)T(n)=O(n2);平方

       ```c
       for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
          x ++;
          x = x + 2;
        }
       }
       ```

       (2)T(n)=O(1);

       ```c
       {x++;j=j+1;}
       ```

       (3)T(n)=O(n);

       ```c
       for(int i=0;i<n;i++){
         x++;
         j=j+1;
       }
       ```

       (4)T(n)=O(la*lb);嵌套函数

       ```c
       la = init(a);lb = init(b);
       for(int i=la;i<n;i++){
         x++;
         location(lb,i);//与lb有关
       }
       ```

       (5)T(n)=O(la+lb);嵌套函数

       ```c
       la = init(a);lb = init(b);
       while(i<=la && j <= lb){
        x++;
       }
       //下面两个最多只会执行其中的一个
       while(i<=la){
        y++;
       }
       while(j<=lb){
        z++;
       }
       ```
#### 第二章 线性表

1. 线性表特点

线性表中是一个个的元素，或者一个个的记录

（1） 唯一的第一个元素，唯一的最后一个元素

（2） 每个元素的位置固定

（3） 长度就是元素的个数，可以灵活变化

2. 线性表表示：顺序表示，链式表示

3. 顺序表示及实现

（1）顺序表示指的是：地址连续的存储单元一次存放数据元素

（2）区分：存储地址，存储单元，存储容量

存储地址：地址

存储单元：int型占用4个存储单元

存储容量：占用的存储单元的数量


![pic1](pic/1.png)

（3） 定义存储结构：顺序表
```c
typedef struct
{
	char name[10];
	char tel[10];
	char class1[10];
}elemtype;
typedef  struct
{
	elemtype *data;//相当于结构体数组的首地址
	int length;
	int listsize;
}list;
```

（4）顺序表的操做
 
