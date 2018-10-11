# hello-world
编程学习笔记
c语言
分治法  递归
快速排序法
#include <stdio.h>
void quick_sort(int array[],int left,int right)
{
  int i=left,j=right;
  int temp;
  int pivot;
  pivot=array[(left+right)/2];
  while(i<=j)
  {
    //从左到右找到大于等于基准点的元素
    while(array[i]<pivot)
    {
      i++;
    }
  //从右到左找到小于等于基准点的元素  
  while(array[j]>pivot)
  {
    j++;
  }
  //如果i<=j,则互换
  if(i<=j)
  {
    temp=array[i];
    array[i]=array[j];
    array[j]=temp;
    i++;
    j--;
    }
  }
  if(left<j)
  {
    quick_sort(array,left,j);
  }
  if(i<right)
  {
    quick_sort(array,i,right);
  }
}
int main(void)
{
  int array[]{73,108,111,118,101,70,105,114,104,67,46,99,111,109};
  length=sizeof(array)/sizeof(array[0]);
  quich_sort(array,0,length-1);
  
  printf("排序后的结果是：")；
  for(i=0;i<length;i++)
  {
    printf("%d",array[i]);
  }
  putchar('\n')
  return 0;
}


内存管理函数
 malloc 函数  void *malloc(size_t  size);
 malloc函数向系统申请分配size个字节的内存空间
 #include<stdio.h>
 int main()
 {
  int *ptr;
  ptr=(int *)malloc(sizeof(int));
  if(ptr==null)
  {
    printf("分配内存失败！\n");
    exit(1);
  }
  printf("请输入一个整数:")；
  scanf("%d",ptr);
  printf("你输入的整数是：%d\n")
  return 0;
 }
 malloc  分配的是在推上的  堆要自己释放
 free  函数 释放ptr参数执行的内存空间，该内存空间必须是由 malloc, calloc,  realloc函数申请 否则该函数将导致未定义行为
 
 #include <stdio.h>
 #include <stdio.h>
 int main(void)
 {
    while(1)
    {
      malloc(1024);
    }
    return 0;
 }
 不合理申请空间 是内存的泄露 c语言不具有 内存回收机制 要自己动手分配
 
  #include<stdio.h>
 int main()
 {
  int *ptr;
  int num=123;
  ptr=(int *)malloc(sizeof(int));
  if(ptr==null)
  {
    printf("分配内存失败！\n");
    exit(1);
  }
  printf("请输入一个整数:")；
  scanf("%d",ptr);
  printf("你输入的整数是：%d\n")
  ptr=&num;
  printf("你输入的整数是：%d\n",*ptr);
  free(ptr);
  return 0;
 }
 导致内存泄露  主要有两种情况  一种是隐式内存泄露   一种是丢失内存地址
 malloc 还可以申请一块任意尺寸的内存空间
 #include<stdio.h>
 #inlcude<stdlib.h>
 int main(void)
 {
  int *ptr=null;
  int num,i;
  printf("请输入整数的内存个数  :");
  scanf("%d",&num);
  prt=(int *)malloc(num*sizeof(int));
  for(i=0;i<num;i++)
  {
    printf("请录入第%d个整数："，i+1)；
    scanf("%d",&ptr[i]);
  }
  printf("你录入的整数是：")；
  for(i=0;i<num;i++)
  {
    printf("%d",ptr[i]);
  }
  putchar('\n');
  free(ptr);
  
  return 0;
 }
 mem 开头 的函数 一个高效的处理空间函数
 
 
 #include<stdio.h>
 #include<stdlib.h>
 #include<string.h>
 #define N 10
 int main(void)
 {
  int *ptr=NULL;
  int i;
  ptr=(int*)malloc(N*sezeof(int));
  if(ptr==NULL)
  {
    exit(i);
  }
  memset(ptr,0,N*siezof(int));
  for(i=0;i<N;i++)
  {
    printf("%d",ptr[i]);
  }
  putchar('\n');
  free()
  return 0;
 }
 
 
 calloc  函数 原型 void *calloc(size_t nmemb,size_t size);
 calloc函数在内存中动态地申请nmemb个长度为size的连续内存空间，这些内存空间全被初始化为0
 calloc 是可以初始化的
 
 业务的需求  需要申请 更大的内存空间
 
 #include <stdio.h>
 #include <stdlib.h>
 #include <string.h>
 
 int main(void)
 {
    int   
 }
 
 realloc  重新分配内存空间  库函数 重新分配 地址是会改变的
 
 
 #include<stdio.h>
 #include<stdlib.h>
 int main(void)
 {
    int i,num;
    int count=0;
    int *ptr= NULL;   //注意 这里必须初始化为null
    do
    {
      printf("请输入一个整数（输入-1表示结束）：")；
      scanf("%d",&num);
      count++;
      ptr=(int *)realloc)_ #include<stdio.h>
 int main()
 {
  int *ptr;
  ptr=(int *)malloc(sizeof(int));
  if(ptr==null)
  {
    printf("分配内存失败！\n");
    exit(1);
  }
  printf("请输入一个整数:")；
  scanf("%d",ptr);
  printf("你输入的整数是：%d\n")
  return 0;
 } #include<stdio.h>
 int main()
 {
  int *ptr;
  ptr=(int *)malloc(sizeof(int));
  if(ptr==null)
  {
    printf("分配内存失败！\n");
    exit(1);
  }
  printf("请输入一个整数:")；
  scanf("%d",ptr);
  printf("你输入的整数是：%d\n")
  return 0;
 }
    }
    


#include <stdio.h>
#include<stdlib.h>
int *func(void)
{
  int *ptr=NULL;
  ptr=(int *)malloc(sizeof(int));
  if(ptr==NULL)
  {
    exit(1);
  }
  *ptr=520;
  return ptr;
}
int main(void)
{
  int *ptr=NUll;
  ptr=func();
  printf("%d\n",*ptr);
  free(ptr);
  return 0;
}
    
#include <stdio.h>
#include<stdlib.h>

int main(void)
{
    int *ptr1=NULL;
    int *ptr2=NULL;
    ptr1=(int *)malloc(sizeof(int));
    ptr2=(int *)malloc(sizeof(int));
    printf("sstack:%p到%p\n",&ptr1,&ptr2);
    printf("heap:%p到%p\n",ptr1,ptr2);
    printf(int *)realloc(ptr1,2*siezof(int));
    printf("heap:%p到%p\n",ptr1,ptr2);
    return 0;
    
}
 
 

#include <stdio.h>
inline int square(int x)
inlime int square(int x)
{
  return x*x
}
int main(void)
{
  int i=1;
  while(i<=100)
  {
    printf("%d的平方是%d\n",i-1,square(i++));
  }
}


#inlcude <stdio.h>
#define STR(s) # s
int main(void)
{
  printf("%s\n",STR(FISHC));
  return 0;
}


利用str这个宏  替换 字符串
#include <stdio.h>
#define STR(s) # s
int main (void)
{
  printf(STR(hello          %s num=%d\n),), STR(FIshc),520);
  return 0;
}

##  链接预处理预算符
#include <stdio.h>
#define TOGERHTER(x,y) x##y
int main(void)
{
  printf("%d\n",TOGERTHER(2,50));
  return 0;
}

#include <stdio.h>
#define SHOWLIST(...) printf(# __VA_ARGS__)
int main(void)
{
  SHOWLISST(fishc,520,3.14\n);
  return 0;
  
  结构体声明 一个整体
  
  #include <stdio.h>
  struct Book
  {
    char title[128];
    char author[40];
    float price;
    unsigned int date;
    char publisher[40];
  }book;
  int main(void)
  {
    printf{"请输入书名："}；
    scanf("%s",book.title);
    printf{"请输入作者："}；
    scanf("%s",book.author);
    printf{"请输入售价："}；
    scanf("%f",book.price);
    printf{"请输入出版日期："}；
    scanf("%d",book.date);
    printf{"请输入出版社："}；
    scanf("%s",book.publisher);
    printf("\n====数据录入完毕====")；
    printf("书名:%s\n",book.title);
    printf("作者:%s\n",book.author);
    printf("售价:%.2f\n",book.price);
    printf("出版日期:%s\n",book.date);
    printf("出版社:%s\n",book.publisher);
   
    
    return 0;
  }
}






  #include <stdio.h>
  struct Date
  {
    int year;
    int month;
    int day;
  };
  struct Book
  {
    char title[128];
    char author[40];
    float price;
    unsigned int date;
    char publisher[40];
  }book{
    "我是声"，
    "物业乐乐"，
    48.8，
    {2017,11,11}，
    "清华大学出版社"
  }
  int main(void)
  {
    printf{"请输入书名："}；
    scanf("%s",book.title);
    printf{"请输入作者："}；
    scanf("%s",book.author);
    printf{"请输入售价："}；
    scanf("%f",book.price);
    printf{"请输入出版日期："}；
    scanf("%d",book.date);
    printf{"请输入出版社："}；
    scanf("%s",book.publisher);
    printf("\n====数据录入完毕====")；
    printf("书名:%s\n",book.title);
    printf("作者:%s\n",book.author);
    printf("售价:%.2f\n",book.price);
    printf("出版日期::%d-%d-%d\n",book.date.year,book.date.month,book.date.day);
    printf("出版社:%s\n",book.publisher);
   
    
    return 0;
  }
}



  #include <stdio.h>
  struct Date
  {
    int year;
    int month;
    int day;
  };
  struct Book
  {
    char title[128];
    char author[40];
    float price;
    unsigned int date;
    char publisher[40];
  }book{
    "我是声"，
    "物业乐乐"，
    48.8，
    {2017,11,11}，
    "清华大学出版社"
  }
  int main(void)
  {
    struct Book *pt;
    pt=&book;
    printf{"请输入书名："}；
    scanf("%s",book.title);
    printf{"请输入作者："}；
    scanf("%s",book.author);
    printf{"请输入售价："}；
    scanf("%f",book.price);
    printf{"请输入出版日期："}；
    scanf("%d",book.date);
    printf{"请输入出版社："}；
    scanf("%s",book.publisher);
    printf("\n====数据录入完毕====")；
    printf("书名:%s\n",book.title);
    printf("作者:%s\n",book.author);
    printf("售价:%.2f\n",book.price);
    printf("出版日期::%d-%d-%d\n",book.date.year,book.date.month,book.date.day);
    printf("出版社:%s\n",book.publisher);
   
    
    return 0;
  }
}


#include <stdio.h>
int main(void)
{
  sstruct Test
  {
    int x;
    int y;
  }t1,t2;
  t1.x=3;
  t2.y=4;
  t2=t1;
  printf("t2.x=%d,t2.y=%d\n",t2.x,t2,y);
  return 0;
  
  
  #include <stdio.h>
  struct Date
  {
    int year;
    int month;
    int day;
    
  };
struct Book
{
  char title[128];
  char author[40];
  float price;
  struct Date date;
  char publisher[40];
};
struct Book getInpu(struct Book book);
struct Book getInpu(struct Book book)
{
    printf{"请输入书名："}；
    scanf("%s",book.title);
    printf{"请输入作者："}；
    scanf("%s",book.author);
    printf{"请输入售价："}；
    scanf("%f",&book.price);
    printf{"请输入出版日期："}；
    scanf("%d-%d-%d",&book.date.year,&book.date.month,&book.date.day);
    printf{"请输入出版社："}；
    scanf("%s",book.publisher);
    
    return book;
}
int main(void)
{
  struct Book b1,b2;
  printf("请录入第一本书的信息...\n");
  b1=getINPUT(b1);
  return 0;
}
}
