## 2.2 STL基本概念

Standard Template Library

分为容器(container)、算法、迭代器(iterator)

容器和算法通过迭代器连接。

## 2.3 STL六大组件

- 容器：各种数据结构，如vector, list,deque,set,map
- 算法:sort, find, copy,for_each等
- 迭代器：连接算法和容器
- 仿函数：行为类似函数，可以作为算法的某种策略
- 适配器：用来修饰容器，仿函数的东西
- 空间适配器：负责空间的配置和管理



## 2.4 STL中容器、算法、迭代器

容器

- 关联式容器 ：二叉树结构，元素没有严格顺序关系。

- 序列式容器：强调值的排序，每个元素都有固定的位置。

算法

- 质变算法：过程中会更改区间内的元素的内容.拷贝，替换，删除
- 非质变算法：不会更改区间内的元素的内容.查找，计数，遍历等。。。

## 2.5容器、迭代器、算法初步入门

####  2.5.1vector存放数据类型



```cpp
三种遍历方式
 
//
for_each(v.begin(),v.end(),myprint;
         
//
for(vector<int>::iterator it = v.begin();it!=v.end();it++)
         cout<<*it<<endl;
```

#### 2.5.1 vector存放自定义数据类型





#### 3.1.3 string赋值操作



功能描述：

- 给string字符串赋值

赋值的函数原型

- string& operator = (const char* s);
- string& operator = (const string & s);
- string& operator = (char c);
- string& assign(const char *s);
- string& assign(const char *s, int n);       把字符串的前n个赋值过来
- string& assign(const string &s);      

```cpp
void test()
{
  string str1;
  
  str1 = "abc";
  
  string str2;
  
  str2 = str1;
  
  string str3;
  
  str3.assign("hell0");
  
  string str4;
  
  str4.assign("helll;", 3);
  
  
}
```





#### 3.1.4 字符串拼接



函数原型

- string & operator   += (const char * str);
- string &operator +=(const char c);
- string &operator +=(const string& str);
- string& append(const char *s);
- string & append(const string &s);

```cpp
```



#### 3.1.5 string查找和替换



功能描述：

- 查找：查询指定字符串是否存在
- 替换：在指定位置替换字符串

函数原型

- int find(const string & str,  int pos = 0); //返回下标， 没有就返回-1
- int rfind(const string &str, int pos = n-1);      //从右往左查询
- string& replace(int pos ,int n,const string& str); // 替换从pos开始的n个字符为str

```cpp
void test()
{
  string str1 = "abcde";
  
  cout<<str1.find("de")<<endl;;
  
  
  cout<<str1.rfind("de")<<endl;
  // rfind 是从右往左查找
  
}
```



```cpp
void test02()
{
  string str1 = "abcdfe";
  
  str1.replace(1,3,"1111");
  
  // str1 = "a1111fe";   //全部替换成字符串
}
```

#### 3.1.6 string字符串比较

函数原型

- int compare(const string &s) const;
- int compare(const char *s) const;

相等返回0

大于返回1

小于返回-1 



```cpp
void test()
{
  str1 = "ab";
  str2 = "aa";
  
  cout<<str1.compare(str2);  //输出1
}
```





#### 3.1.7 string字符存取



- char &operator[](int n);  //通过【】取字符(下标)
- char &at(int n);        // 通过at方法取字符

```cpp
void test01()
{
  string str = "hell0";
  
  cout<< str[0];
  
  cout<<str.at(0);
  
  str.at(0) = 'x'; //也可以更改
  
  
}
```





#### 3.1.8

#### 3.1.9 string 子串



函数原型

- string substr(int pos = 0,int n = pos) const;



```cpp
void test()
{
  string str1 = "abcdef";
  
  string str2 = str1.substr(1,3);
  
  //此时str为 “bcd”
}

void test01()
{
  string email = "zhangjh@qq.com";
  
  int pos = email.find("@");
  
  string name = email.substr(0,pos);
  
  cout<<name<<endl;
}
```



### 3.2 vector



#### 3.2.1 vector 基本概念



动态扩展：

并不是原空间后面接续新空间，而是找更大的内存空间，拷贝至新空间，释放原空间。



<img src="/Users/zhangjinghao/Library/Application Support/typora-user-images/截屏2022-01-06 下午12.14.26.png" alt="截屏2022-01-06 下午12.14.26" style="zoom: 50%;" />





#### 3.2.2 vector构造函数

函数原型

- vector<T> v 
- vector(v.begin(),v.end());
- vector(n,elem);
- vector(const vector &vec);

#### 3.2.3 vector赋值操作

函数原型

- vector& operator = (const vector &vec);
- assign(begin,end);

```cpp
void test01(){
  
  vector<int> v1;
  for(int i=0;i<10;i++)
  {
    v1.push_back(i);
  }
  
  vector<int> v2 = v1 ;  // 第一种直接赋值方式
  
  vector<int>v3;
  
  v3.assgin(v1.begin(),v1.begin()+3);  //第二种赋值方式
  
}

void print(vector<int> &v)
{
  for(vector<int>::iterator it= v.begin();it!=v.end();it++)
    cout<<*it<<endl;
}
```



#### 3.2.4 vector容量和大小



函数原型

- empty()
- capacity()
- size()
- resize(int n)

```cpp
void test01()
{
  vector<int> v1;
  
}








```

