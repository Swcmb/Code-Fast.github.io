---
title: 数据结构（cpp实现）
date: 2024-10-30 20:56:55
tags: 数据结构
---


# 第一章

## 七桥问题

七桥问题是一个经典的图论问题，它是由数学家欧拉在18世纪提出的。问题的背景是哥尼斯堡（今俄罗斯的加里宁格勒）的一个地区，该地区被普雷格尔河分成四个区域，并由七座桥连接。问题是：是否有可能从某个区域出发，不重复地走过所有七座桥，并且回到起点。
我们可以这样求解七桥问题：

1. 首先，我们需要确定每个顶点（即每个城区）相关联的边数（即桥的数量）。
2. 然后，我们根据以下规则进行判定：
   - 如果所有顶点相关联的边数都是偶数，则存在欧拉回路。
   - 如果有超过两个顶点相关联的边数是奇数，则不存在欧拉回路。
   - 如果恰好有两个顶点相关联的边数是奇数，则不存在欧拉回路，但存在一条从这两个顶点之一出发的欧拉路径（不会回到起点）。
   对于七桥问题，我们可以将四个区域视为四个顶点，七座桥视为连接这些顶点的边。通过计算每个顶点相关联的边数，我们可以得到以下结果：
- 两个区域（顶点）各有三座桥相连，因此这两个区域相关联的边数是奇数。
- 另外两个区域（顶点）各有两座桥相连，因此这两个区域相关联的边数是偶数。
根据判定规则，因为有超过两个顶点相关联的边数是奇数（具体来说，有两个顶点），所以七桥问题中不存在欧拉回路。同时，也不存在从这两个顶点之一出发的欧拉路径，因为路径要求不重复地走过所有边，而这是不可能的。
因此，结论是：在七桥问题中，不可能找到一条不重复地走过所有七座桥的路径，并且返回起点。

```c++
#include<iostream>
using namespace std;
const int MaxSize=4;
class EulerCircuit {
public:
    EulerCircuit(int a[][MaxSize],int n);
    int oddVertexNum();
private:
    int mat[MaxSize][MaxSize];
    int vertexNum;
};
EulerCircuit::EulerCircuit(int a[][MaxSize],int n){
    for(int i=0;i<n;i++){
        for(int j=0;j<n;j++){
            mat[i][j]=a[i][j];
        }
    }
    vertexNum=n;
}
int EulerCircuit::oddVertexNum(){
    int count=0,i,j,degree;
    for(i=0;i<vertexNum;i++){
        degree=0;
        for(j=0;j<vertexNum;j++){ // 这里应该是 j++ 而不是 i++
            degree=degree+mat[i][j];
        }
        if(degree%2!=0){
            count++;
        }
    }
    return count;
}
int main(){
    int a[4][MaxSize]={
        {0,1,2,2},
        {1,0,1,1},
        {2,1,0,0},
        {2,1,0,0}
    };
    EulerCircuit G{a,4};
    int num=G.oddVertexNum();
    if(num>=2){
        cout<<num<<"个地方通奇数桥，不存在欧拉回路";
    }
    else{
        cout<<"存在欧拉回路";
    }
    return 0;
}
```

## 欧几里得算法

欧几里得算法用自然语言描述如下：

步骤1：将m除以n得到余数r

步骤2：若r等于0，则n为最大公约数，算法结束；否则执行步骤3

步骤3：将n的值放在m中，将r的值放在n中，重新执行步骤1

```c++
#include <iostream>
using namespace std;
int ComFactor(int m,int n) {
    int r=m%n;
    while (r!=0) {
        m=n;
        n=r;
        r=m%n;
    }
    return n;
}
int main() {
    cout<<"最大公约数是"<<ComFactor(35,25)<<endl;
    return 0;
}
```

# 第二章

## 线性表的定义

线性表简称表，是n个数据元素的有限序列，线性表中数据元素的个数称为线性表的长度，长度等于零的线性表称为空表，一个非空表通常记为：
$$
L=(a1,a2,...,an)
$$
其中，ai称为数据元素，下角标i表示该元素在线性表中的位置或序号，称元素ai位于表的第i个位置，或称是ai是表中的第i的元素。a1称为表头元素，an称为表尾元素，任意一对相邻的数据元素a（i-1）和ai（1<i<=n）之间存在序偶关系<a(i-1),ai>，且a(i-1)称为ai的前驱，ai称为a(i-1)的后继。在这个序列中，元素a1无前驱，元素an无后继，其他每个元素有且仅有一个前驱和一个后继

线性表的基本操作包括：

1. **初始化**：创建一个空的线性表。
2. **销毁**：销毁线性表，释放其占用的内存空间。
3. **插入**：在指定位置插入一个元素。
4. **删除**：删除指定位置的元素。
5. **查找**：查找并返回指定元素的位置。
6. **取值**：获取指定位置的元素。
7. **修改**：修改指定位置的元素。
8. **长度**：返回线性表的长度（元素个数）。
9. **判空**：判断线性表是否为空。

## 线性表的顺序存储结构及实现

线性表的顺序存储结构称为顺序表，其基本思想是用一段地址连续的存储单元依次存储线性表的数据元素

设顺序表的每个元素占用c个存储单元，则第i个元素的存储地址为：
$$
Loc(ai)=Loc(a1)+(i-1)*c
$$
顺序表中数据元素的存储地址是其序号的线性函数，只要确定了存储顺序表的起始地址（即基地址），计算任何一个元素的存储地址的时间是相等的，具有这一特点的存储结构称为随机存取结构

通常用一维数组来实现顺序表

```c++
#include <iostream>
using namespace std;
const int MaxSize=100;//根据实际问题具体定义
template <typename DataType>//由于线性表的数据元素类型不确定，所以采用模板机制
class SeqList {
public:
    SeqList();//创建一个空的线性表
    SeqList(DataType a[],int n);//建立长度为n的顺序表
    ~SeqList();//析构函数，销毁线性表，释放其占用的内存空间
    int Length();//求线性表的长度
    DataType Get(int i);//按位查找，查找第i个元素的值
    int Locate(DataType x);//按值查找，查找值为x的元素序号；
    void Insert(int i,DataType x);//插入操作，在第i个位置插入值为x的元素
    DataType Delete(int i);//删除操作，删除第i个元素
    int Empty();//判断线性表是否为空
    void PrintList();//按序号输出各元素
private:
    DataType data[MaxSize];//存放数据元素的数组
    int length;//线性表的长度
};
template<typename DataType>
SeqList<DataType>::SeqList() {
    length=0;
}

template<typename DataType>
SeqList<DataType>::SeqList(DataType a[], int n) {
    if(n>MaxSize)throw"参数非法";
    for(int i=0;i<n;i++) {
        data[i]=a[i];
    }
    length=n;
}

template<typename DataType>
SeqList<DataType>::~SeqList() {}//

template<typename DataType>
int SeqList<DataType>::Empty() {
    return length==0;
}

template<typename DataType>
int SeqList<DataType>::Length() {
    return length;
}

template<typename DataType>
void SeqList<DataType>::PrintList() {
    for(int i=0;i<length;i++) {
        cout<<data[i]<<'\t';
    }
    cout<<endl;
}

template<typename DataType>
DataType SeqList<DataType>::Get(int i) {//时间复杂度为O(1)
    if(i<1||i>length)throw"查找位置非法";
    else {
        return data[i-1];
    }
}

template<typename DataType>
int SeqList<DataType>::Locate(DataType x) {//平均时间性能是O(n)
    for(int i=0;i<length;i++) {
        if(data[i]==x)return i+1;
    }
    return 0;
}

template<typename DataType>
void SeqList<DataType>::Insert(int i, DataType x) {//平均时间性能是O(n)
    if(length==MaxSize)throw"表满，上溢";
    if(i<1||i>length+1)throw"插入位置错误";
    for(int j=length;j>=i;j--) {
        data[j]==data[j-1];
    }
    data[i-1]=x;
    length++;
}

template<typename DataType>
DataType SeqList<DataType>::Delete(int i) {//平均时间性能是O(n)
    DataType x;
    if(length==0)throw"空表 下溢";
    if(i<1||i>length)throw"删除位置错误";
    x=data[i-1];
    for(int j=i;j<length;j++) {
        data[j-1]=data[j];
    }
    length--;
    return x;
}
```

```c++
int main() {
    int r[5]={1,2,3,4,5},i,x;
    SeqList<int>L{r,5};
    cout<<"当前线性表的数据为：";
    L.PrintList();
    try {
        L.Insert(2,8);
        cout<<"执行插入操作后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    cout<<"当前线性表的长度为："<<L.Length()<<endl;
    cout<<"请输入查找的元素值：";
    cin>>x;
    i=L.Locate(x);
    if (0==i)cout<<"查找失败"<<endl;
    else {
        cout<<"元素"<<x<<"的位置为："<<i<<endl;
    }
    try {
        cout<<"请输入查找第几个元素值：";
        cin>>i;
        cout<<"第"<<i<<"个元素值是"<<L.Get(i)<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入要删除的第几个元素";
        cin>>i;
        x=L.Delete(i);
        cout<<"删除的元素是"<<x<<",删除后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    return 0;
}
```

## 线性表的链接存储结构及其实现

单链表是用一组任意的存储单元存放线性表的元素，这组存储单元可以连续也可以不连续，甚至可以零散分布在内存中的任意位置。为了能正确表示元素之间的逻辑关系，每个存储单元在存储数据元素的同时，还必须存储其后继元素所在的地址信息，这个地址信息称为指针。这两部分组成了数据元素的存储映像，称为结点。

### 单链表的结点定义

```c++
template<typename DataType>
struct Node {
    DataType data;
    Node<DataType>* next;
};
```

在使用单链表时，关心的只是数据元素以及数据元素之间的逻辑关系

单链表中每个结点的存储地址存放在其前驱结点的next域中，而第一个结点无前驱，所以设头指针指向第一个元素所在结点，整个单链表的存取必须从头指针开始进行，因而头指针具有标识一个单链表的作用。最后一个元素所在结点的指针域为空。

### 单链表的实现

```c++
#include <iostream>
using namespace std;

template<typename DataType>
struct Node {
    DataType data;
    Node<DataType> *next;
};

template<typename DataType>
class LinkList {
public:
    LinkList();
    LinkList(DataType a[],int n);
    ~LinkList();
    int Length();//求线性表的长度
    DataType Get(int i);//按位查找，查找第i个元素的值
    int Locate(DataType x);//按值查找，查找值为x的元素序号；
    void Insert(int i,DataType x);//插入操作，在第i个位置插入值为x的元素
    DataType Delete(int i);//删除操作，删除第i个元素
    int Empty();//判断线性表是否为空
    void PrintList();//按序号输出各元素
private:
    Node<DataType> *first;
};

template<typename DataType>
LinkList<DataType>::LinkList() {
    first=new Node<DataType>;
    first->next=nullptr;
    /* nullptr是一个字面常量，表示空指针
       它用于初始化指针变量或将其赋值给指针变量，
       以确保指针不指向任何有效的内存地址 */
}

template<typename DataType>
int LinkList<DataType>::Empty() {
    return first->next==nullptr;
}

template<typename DataType>
void LinkList<DataType>::PrintList() {//时间复杂度为O(n)
    //设置工作指针p依次指向各节点
    //p后移不能写作p++
    Node<DataType> *p=first->next;
    while (p!=nullptr) {
        cout<<p->data<<" ";
        p=p->next;//工作指针后移
    }
    cout<<endl;
}

template<typename DataType>
int LinkList<DataType>::Length() {
    Node<DataType> *p=first->next;
    int count=0;
    while (p!=nullptr) {
        p=p->next;//工作指针后移
        count++;
    }
    return count;
}

template<typename DataType>
DataType LinkList<DataType>::Get(int i) {
    Node<DataType> *p=first->next;
    int count=1;
    while (p!=nullptr && count<i) {
        p=p->next;//工作指针后移
        count++;
    }
    if(p==nullptr)throw "查找位置错误" ;
    else {
        return p->data;
    }
    //平均时间性能为O(n),单链表是顺序存取结构
}

template<typename DataType>
int LinkList<DataType>::Locate(DataType x) {
    Node<DataType> *p=first->next;
    int count=1;
    while (p!=nullptr) {
        if(p->data==x) {
            return count;
        }
        p=p->next;
        count++;
    }
    return 0;
    //平均时间性能为O(n)
}

template<typename DataType>
void LinkList<DataType>::Insert(int i, DataType x) {//时间复杂度为O(n)
    Node<DataType> *p=first,*s=nullptr;
    int count=0;
    while (p!=nullptr && count<i-1) {
        p=p->next;
        count++;
    }
    if(p==nullptr)throw"插入位置错误";
    else {
        s=new Node<DataType>;
        s->data=x;
        s->next=p->next;
        p->next=s;
    }
}

template<typename DataType>
LinkList<DataType>::LinkList(DataType a[], int n) {
    //头插法
    first=new Node<DataType>;
    first->next=nullptr;
    for(int i=0;i<n;i++) {
        Node<DataType> *s=nullptr;
        s=new Node<DataType>;
        s->data=a[i];
        s->next=first->next;
        first->next=s;
    }
    //尾插法
    // first=new Node<DataType>;
    // Node<DataType> *r=first,*s=nullptr;
    // for(int i=0;i<n;i++) {
    //     s=new Node<DataType>;
    //     s->data=a[i];
    //     r->next=s;
    //     r=s;
    // }
    // r->next=nullptr;
}

template<typename DataType>
DataType LinkList<DataType>::Delete(int i) {
    DataType x;
    Node<DataType> *p=first,*q=nullptr;
    int count=0;
    while (p!=nullptr && count<i-1) {
        p=p->next;
        count++;
    }
    if(p==nullptr || p->next==nullptr)throw "删除位置错误" ;
    else {
        q=p->next;
        x=q->data;
        p->next=q->next;
        delete q;
        return x;
    }
}

template<typename DataType>
LinkList<DataType>::~LinkList() {
    Node<DataType> *p=first;
    while (first!=nullptr) {
        first=first->next;
        delete p;
        p=first;
    }
}
```

```c++
int main() {
    int r[5]={1,2,3,4,5},i,x;
    LinkList<int> L{r,5};
    cout<<"当前线性表的数据为：";
    L.PrintList();
    try {
        L.Insert(2,8);
        cout<<"执行插入操作后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    cout<<"当前线性表的长度为："<<L.Length()<<endl;
    cout<<"请输入查找的元素值：";
    cin>>x;
    i=L.Locate(x);
    if (0==i)cout<<"查找失败"<<endl;
    else {
        cout<<"元素"<<x<<"的位置为："<<i<<endl;
    }
    try {
        cout<<"请输入查找第几个元素值：";
        cin>>i;
        cout<<"第"<<i<<"个元素值是"<<L.Get(i)<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入要删除的第几个元素";
        cin>>i;
        x=L.Delete(i);
        cout<<"删除的元素是"<<x<<",删除后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    return 0;
}
```

## 双链表

在单链表的每个结点中再设置一个指向其前驱结点的指针域，这样就形成了双链表

### 双链表的结点结构定义：

```c++
template<typename Datatype>
struct DulNode {
    Datatype data;
    DulNode<Datatype> *prior,*next;
};
```

在双链表中求表长等操作与单链表基本相同，下面讨论插入和删除操作

```c++
#include <iostream>
using namespace std;

template<typename Datatype>
struct DulNode {
    Datatype data;
    DulNode<Datatype> *prior,*next;
};

template<typename DataType>
class DulLinkList {
public:
    DulLinkList();
    DulLinkList(DataType a[],int n);
    ~DulLinkList();
    int Length();//求线性表的长度
    DataType Get(int i);//按位查找，查找第i个元素的值
    int Locate(DataType x);//按值查找，查找值为x的元素序号；
    void Insert(int i,DataType x);//插入操作，在第i个位置插入值为x的元素
    DataType Delete(int i);//删除操作，删除第i个元素
    int Empty();//判断线性表是否为空
    void PrintList();//按序号输出各元素
private:
    DulNode<DataType> *first;
};

template<typename DataType>
DulLinkList<DataType>::DulLinkList() {
    first=new DulNode<DataType>;
    first->next=nullptr;
    first->prior=nullptr;
    /* nullptr是一个字面常量，表示空指针
       它用于初始化指针变量或将其赋值给指针变量，
       以确保指针不指向任何有效的内存地址 */
}

template<typename DataType>
int DulLinkList<DataType>::Empty() {
    return first->next==nullptr;
}

template<typename DataType>
void DulLinkList<DataType>::PrintList() {//时间复杂度为O(n)
    //设置工作指针p依次指向各节点
    //p后移不能写作p++
    DulNode<DataType> *p=first->next;
    while (p!=nullptr) {
        cout<<p->data<<" ";
        p=p->next;//工作指针后移
    }
    cout<<endl;
}

template<typename DataType>
int DulLinkList<DataType>::Length() {
    DulNode<DataType> *p=first->next;
    int count=0;
    while (p!=nullptr) {
        p=p->next;//工作指针后移
        count++;
    }
    return count;
}

template<typename DataType>
DataType DulLinkList<DataType>::Get(int i) {
    DulNode<DataType> *p=first->next;
    int count=1;
    while (p!=nullptr && count<i) {
        p=p->next;//工作指针后移
        count++;
    }
    if(p==nullptr)throw "查找位置错误" ;
    else {
        return p->data;
    }
    //平均时间性能为O(n),单链表是顺序存取结构
}

template<typename DataType>
int DulLinkList<DataType>::Locate(DataType x) {
    DulNode<DataType> *p=first->next;
    int count=1;
    while (p!=nullptr) {
        if(p->data==x) {
            return count;
        }
        p=p->next;
        count++;
    }
    return 0;
    //平均时间性能为O(n)
}

template<typename DataType>
void DulLinkList<DataType>::Insert(int i, DataType x) {//时间复杂度为O(n)
    DulNode<DataType> *p=first,*s=nullptr;
    int count=0;
    while (p!=nullptr && count<i-1) {
        p=p->next;
        count++;
    }
    if(p==nullptr)throw"插入位置错误";
    else {
        s=new DulNode<DataType>;
        s->data=x;
        //与单链表不同之处//这里
        s->prior=p;
        s->next=p->next;
        p->next->prior=s;
        p->next=s;
    }
}

template<typename DataType>
DulLinkList<DataType>::DulLinkList(DataType a[], int n) {
    //头插法
    first=new DulNode<DataType>;
    first->next=nullptr;
    for(int i=0;i<n;i++) {
        DulNode<DataType> *s=nullptr;
        s=new DulNode<DataType>;
        s->data=a[i];
        s->next=first->next;
        first->next=s;
    }
    //尾插法
    // first=new DulNode<DataType>;
    // DulNode<DataType> *r=first,*s=nullptr;
    // for(int i=0;i<n;i++) {
    //     s=new DulNode<DataType>;
    //     s->data=a[i];
    //     r->next=s;
    //     r=s;
    // }
    // r->next=nullptr;
}

template<typename DataType>
DataType DulLinkList<DataType>::Delete(int i) {//这里
    DulNode<DataType> *p = first;
    DulNode<DataType> *q;
    int count = 0;
    while (p != nullptr && count < i - 1) {
        p = p->next;
        count++;
    }

    if (p == nullptr || p->next == nullptr) {
        throw std::runtime_error("删除位置错误");
    } else {
        q = p->next; // Save the node to be deleted
        p->next = q->next; // Update next of the previous node
        q->next->prior = p; // Update prior of the next node
        DataType x = q->data; // Save data to return
        delete q; 
        return x; 
    }
}

template<typename DataType>
DulLinkList<DataType>::~DulLinkList() {
    DulNode<DataType> *p=first;
    while (first!=nullptr) {
        first=first->next;
        delete p;
        p=first;
    }
}
```

```c++
int main() {
    int r[5]={1,2,3,4,5},i,x;
    DulLinkList<int> L{r,5};
    cout<<"当前线性表的数据为：";
    L.PrintList();
    try {
        L.Insert(2,8);
        cout<<"执行插入操作后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    cout<<"当前线性表的长度为："<<L.Length()<<endl;
    cout<<"请输入查找的元素值：";
    cin>>x;
    i=L.Locate(x);
    if (0==i)cout<<"查找失败"<<endl;
    else {
        cout<<"元素"<<x<<"的位置为："<<i<<endl;
    }
    try {
        cout<<"请输入查找第几个元素值：";
        cin>>i;
        cout<<"第"<<i<<"个元素值是"<<L.Get(i)<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入要删除的第几个元素";
        cin>>i;
        x=L.Delete(i);
        cout<<"删除的元素是"<<x<<",删除后数据为：";
        L.PrintList();
    }catch (char *str){cout<<str<<endl;}
    return 0;
}
```

## 循环链表

在单链表中，如果将终端结点的指针由空指针改为指向头结点，就使得整个单链表形成一个环，这种头尾相接的单链表称为循环单链表。实际应用中多采用尾指针指示的循环单链表

在双链表中，如果将终端结点的后继指针由空指针改为指向头结点，将头结点的前驱指针由空指针改为指向终端结点，就使得整个双链表形成一个环，这种头尾相接的单链表称为循环双链表

循环链表中没有明显的尾端，可能会使循环链表的处理操作进入死循环，通常判断用作循环变量的工作指针是否等于某一特定指针（如头指针或尾指针），以判定工作指针是否扫描了整个链表，例如可以用循环条件  `p!=first`  判断工作指针是否扫描了整个链表

## 顺序表和链表的比较

### 1.时间性能比较

所谓时间性能是指基某种存储结构的基本操作（即算法）的时间复杂度。

**随机访问**
- **顺序表**：能够直接定位到任意位置，实现快速访问，时间复杂度为 O(1)。
- **链表**：必须从头部开始遍历至目标位置，平均时间复杂度为 O(n)。

**插入与删除**
- **链表**：一旦拥有指向目标位置的指针，插入或删除操作无需移动其他元素，时间复杂度为 O(1)。
- **顺序表**：插入或删除元素需要调整后续所有元素的位置，平均时间复杂度为 O(n)，尤其是当元素数量大或每个元素占用较大存储空间时，移动元素的成本显著增加。

**一般来说**

- 当线性表的主要操作是**频繁查找**且**插入和删除较少**，或操作依赖于**数据元素的绝对位置**时，**顺序表**是更优的选择。
- 若线性表中**频繁执行插入和删除操作**，**链表**则提供更好的性能。

### 2.空间性能比较

所谓空间性能是指某种存储结构所占用的存储空间的大小。

- **存储特性**
  - **顺序表**: 每个结点仅包含数据元素，存储密度高，空间利用率好。
  - **链表**: 结点包含数据元素和指针，指针增加结构开销，降低存储密度。
- **空间分配**
  - **顺序表**: 需预分配固定大小空间，可能造成浪费（分配过多）或上溢（分配不足）。
  - **链表**: 动态分配，元素数量不受限，只要系统有可用内存。
- **适用场景**
  - **顺序表**: 适合已知大致长度的线性表，以优化空间效率。
  - **链表**: 更适用于元素数量变化大或未知的情况。

## 扩展与提高

### 线性表的静态链表存储

静态链表用数组来表示链表。由于是利用数组定义的链表，属于静态存储分配，因此叫静态链表。最常用的是静态单链表。

avail是空闲链表（全部由空闲数组单元组成的单链表）头指针，first是静态链表头指针，为了运算方便通常静态链表也带头指针。

**静态链表的数组元素定义：**

```c++
template <typename DateType>
struct SNode {
    DateType data;
    int next;//指针域(也称游标),注意不是指针类型
};
```

**静态链表的定义：**

```c++
const int MaxSize=100;
template <typename DataType>
class StaList {
public:
    StaList();
    StaList(DataType a[],int n);
    ~StaList();
    //与单链表成员函数相同
    int Length();//求线性表的长度
    DataType Get(int i);//按位查找，查找第i个元素的值
    int Locate(DataType x);//按值查找，查找值为x的元素序号；
    void Insert(int i,DataType x);//插入操作，在第i个位置插入值为x的元素
    DataType Delete(int i);//删除操作，删除第i个元素
    int Empty();//判断线性表是否为空
    void PrintList();//按序号输出各元素
private:
    SNode<DataType> SList[MaxSize];
    int first,avail;
};
```

静态链表采用静态存储分配，因此析构函数为空，求表长等操作的实现基本与单链表相同，下面讨论**插入和删除**操作

在静态链表中进行插入操作，首先从空闲链的最前端摘下一个结点，将该结点插入静态链表中，假设新结点插在结点p的后面，则修改指针的操作为：

```c++
s=avail;
avail=SList[avail].next;
SList[s].data=x;
SList[s].next=SList[p].next;
SList[p].next=s;
```

在静态链表中进行删除操作，首先将被删除结点从静态链表中摘下，再插入空闲链的最前端，假设要删除结点p的后继结点，则修改指针的操作为：

```
q=SList[p].next;
SList[p].next=SList[q].next;
SList[q].next=avail;
avail=q;
```

### 顺序表的动态分配方式

顺序表的动态分配方式是在程序执行过程中通过动态存储分配，一旦数组空间占满，另外再分配一块更大的存储空间，用来替换原来的存储空间，从而达到扩充数组空间的目的

```c++
const int InitSize=100;//顺序表的初始长度
const int IncreSize=10;//顺序表存储空间每次扩展的长度
template <typename DataType>
class SeqList {
public:
    //与顺序表的静态分配相同
    SeqList();
    SeqList(DataType a[],int n);
    ~SeqList();
    //与单链表成员函数相同
    int Length();//求线性表的长度
    DataType Get(int i);//按位查找，查找第i个元素的值
    int Locate(DataType x);//按值查找，查找值为x的元素序号；
    void Insert(int i,DataType x);//插入操作，在第i个位置插入值为x的元素
    DataType Delete(int i);//删除操作，删除第i个元素
    int Empty();//判断线性表是否为空
    void PrintList();//按序号输出各元素
private:
    DataType *data;//动态申请数组空间的首地址
    int maxSize;//当前数组空间的最大长度
    int length;//线性表的长度
};
```

在顺序表的动态分配方式下，求线性表的长度等操作与顺序表的静态分配方式相同，下面讨论其他基本操作的实现

#### 无参构造函数——初始化顺序表：

```c++
template<typename DataType>
SeqList<DataType>::SeqList() {
    data=new DataType[InitSize];
    maxSize=InitSize;
    length=0;
}
```

#### 有参构造函数——建立顺序表：

建立一个长度为*n*的顺序表需要申请长度大于n的存储空间，一般是当前线性表长度两倍的存储空间：

```c++
template<typename DataType>
SeqList<DataType>::SeqList(DataType a[], int n) {
    data=new DataType[2*n];
    maxSize=2*n;
    for(int i=0;i<n;i++) {
        data[i]=a[i];
    }
    length=n;
}
```

#### 析构函数——销毁顺序表

```c++
template<typename DataType>
SeqList<DataType>::~SeqList() {
    delete[] data;
}
```

#### 插入操作

```c++
// 在序列的第i个位置插入元素x
template<typename DataType>
void SeqList<DataType>::Insert(int i, DataType x) {
    // 检查插入位置是否合法
    if(i<1||i>length+1)throw"插入位置错误!";
    // 检查序列是否已满
    if(length==maxSize) {
        // 发生上溢,扩充存储空间
        DataType *oldData=data;
        maxSize+=IncreSize;
        data=new DataType[maxSize];
        // 将旧数据复制到新数组
        for(int j=0;j<length;j++) {
            data[j]=oldData[j];
        }
        // 释放旧数组的内存
        delete[] oldData;
    }
    // 为新元素腾出空间
    for(int j=length;j>=i;j--) {
        data[j]=data[j-1];
    }
    // 插入新元素
    data[i-1]=x;
    // 更新序列长度
    length++;
}
```

## 应用示例

### 约瑟夫环问题

由于约瑟夫环问题本身具有循环性质，考虑采用循环单链表。求解约瑟夫环的问题的基本思路是：设置一个计数器count和工作指针p，当计数器累加到m时删除结点p。为了统一对链表中任意结点进行计数和删除操作，循环单链表不带头结点；为了便于删除操作设两个工作指针pre和p，指针pre指向p的前驱结点；为了使计数器从1开始奇数，采用尾指针指示的循环单链表，将指针pre初始化为指向终端结点，将指针p初始化为开始结点。

```c++
#include <iostream>
using namespace std;
struct Node {//约瑟夫环的结点定义
    int data;
    struct Node *next;
};
class JosephRing {
public:
    JosephRing(int n);//构造函数，初始化n个结点的循环单链表
    ~JosephRing();//析构函数，类似单链表的析构函数
    void Joseph(int m);//为m，打印出环的顺序
private:
    Node *rear;
};
JosephRing::~JosephRing() {
    
}
JosephRing::JosephRing(int n) {
    Node *s=nullptr;
    rear=new Node;
    rear->data=1;rear->next=rear;//建立长度为1的循环单链表
    for(int i=2;i<=n;i++) {//依次插入数据域为2、3...n的结点
        s=new Node;
        s->data=i;
        s->next=rear->next;//将结点s插入尾结点rear的后面
        rear->next=s;
        rear=s;
    }
}
void JosephRing::Joseph(int m) {
    Node *pre=rear,*p=rear->next;
    int count=1;
    cout<<"出环的顺序是:";
    while (p->next!=p) {
        if(count<m) {
            pre=p;p=p->next;
            count++;
        }
        else {
            cout<<p->data<<"\t";
            pre->next=p->next;//将p摘链
            delete p;
            p=pre->next;//工作指针p后移，但pre不动
            count=1;
        }
    }
    cout<<p->data<<"\t";
    delete p;
}
int main() {
    int n,m;
    cout<<"请输入约瑟夫环的长度：";
    cin>>n;
    cout<<"请输入密码：";
    cin>>m;
    JosephRing R{n};
    R.Joseph(m);
    return 0;
}
```

### 一元多项式求和

若相加的某两项的指数不等，则两项应分别加在结果中，将引起线性表的插入；若某两项的指数相等，则系数相加，若相加结果为零，将引起线性表的删除。由于在线性表的合并过程中需要频繁地执行插入和删除操作，因此考虑采取单链表存储。

在表示一元多项式的单链表中，每一个非零项对应单链表中的一个结点，且单链表应按指数递增有序排列。

其中，coef 为系数域，存放非零项的系数；exp为指数域，存放非零项的指数；next 为指针域，存放指向下一结点的指针。

下面分析一元多项式求和的执行过程。

设单链表A和B分别存储两个多项式，求和结果存储在单链表 A 中，设两个工作指针p和q分别指向两个单链表的开始结点。

两个多项式求和实质上是对结点p的指数域和结点q的指数域进行比较，有下列三种情况：

① 若p一>exp 小于q一>exp，则结点p应为结果链表中的一个结点，将指针p后移

② 若p->exp大于q一＞exp，则结点q应为结果中的一个结点，将q插入到第一个单链表中结点P之前，并将指针q指向单链表B中的下一个结点。为此，在单链表A 中应该设置两个工作指针 pre 和p，使得pre 指向p的前驱结点。

③ 若p->exp等于q->exp，则p与q所指为同类项，将q的系数加到p的系数上。若相加结果不为0，则将指针P后移，并删除结点q，为此，在单链表B中应该设置两个工作指针 qre 和q，使得gre 指向q的前驱结点；若相加结果为0，则表明结果中无此项，删除结点p和结点 q，并将指针p 和指针q分别后移。

```c++
#include <iostream>
using namespace std;
struct Node {
    int coef,exp;
    Node *next;
};
class Polynomial {
public:
    Polynomial();
    Polynomial(const Polynomial &B);//拷贝构造函数
    /*拷贝构造函数是C++中一种特殊的构造函数，用于创建一个对象作为已存在对象的副本
    这种构造函数的名称与类名相同，形式参数只有一个，即该类的引用类型的对象.
    通常，这个形参会被声明为const，以确保在构造过程中不会修改原对象.
    拷贝构造函数的主要应用场景包括，当一个对象作为值传递的参数传递给函数，
    或者函数返回一个对象时，都需要调用到拷贝构造函数*/
    ~Polynomial();
    Polynomial operator+(Polynomial &B);//重载运算符,多项式相加
    void Print();
private:
    Node *first;//一元多项式单链表的头指针
};

Polynomial::Polynomial() {
    Node *r=nullptr,*s=nullptr;
    int coef,exp;
    first=new Node;//申请头结点
    r=first;//尾插法建立单链表
    cout<<"请输入系数和指数";
    cin>>coef>>exp;
    while (coef!=0) {//循环结束的条件是输入系数为0
        s=new Node;
        s->coef=coef;s->exp=exp;
        r->next=s;r=s;//将结点s插入单链表的尾部
        cout<<"请输入系数和指数";
        cin>>coef>>exp;
    }
    r->next=nullptr;
    cout<<"\n\n";
}
Polynomial::Polynomial(const Polynomial &B) {
    first=B.first;
}
Polynomial::~Polynomial() {

}
Polynomial Polynomial::operator+(Polynomial &B) {
    Node *pre=first,*p=pre->next;//工作指针pre和p初始化
    Node *qre=B.first,*q=qre->next;//工作指针qre和q初始化
    Node *qtemp=nullptr;
    while (p!=nullptr && q!=nullptr) {
        if(p->exp < q->exp) {//第1种情况
            pre=p;p=p->next;
        }
        else if(p->exp > q->exp) {//第2种情况
            qtemp=q->next;
            pre->next=q;//将结点q插入到结点p之前
            q->next=p;
            pre=q;
            q=qtemp;
            qre->next=q;
        }
        else {//第3种情况
            p->coef=p->coef+q->coef;
            if(p->coef==0) {//系数相加为0,则删除结点p
                pre->next=p->next;
                delete p;
                p=pre->next;
            }
            else {
                pre=p;
                p=p->next;
            }
            qre->next=q->next;//第3种情况都要删除结点q
            delete q;
            q=qre->next;
        }
    }
    if(q!=nullptr) {
        pre->next=q;//将结点q链接到第一个单链表的后面
    }
    return *this;
}

void Polynomial::Print() {
    Node *p=first->next;
    if(p!=nullptr) {//输出第一项
        cout<<p->coef<<"x^"<<p->exp;
    }
    p=p->next;
    while (p!=nullptr) {
        if(p->coef>0) {
            cout<<"+"<<p->coef<<"x^"<<p->exp;
        }
        else {
            cout<<p->coef<<"x^"<<p->exp;
        }
        p=p->next;
    }
    cout<<"\n";
}

int main() {
    Polynomial A{},B{};
    A.Print();
    B.Print();
    A=A+B;//运算符重载，对象赋值调用拷贝构造函数
    cout<<"结果是：";
    A.Print();
    return 0;
}
```



```
请输入系数和指数7 0
请输入系数和指数12 3
请输入系数和指数-2 8
请输入系数和指数5 12
请输入系数和指数0 0


请输入系数和指数4 1
请输入系数和指数6 3
请输入系数和指数2 8
请输入系数和指数5 20
请输入系数和指数7 28
请输入系数和指数0 0


7x^0+12x^3-2x^8+5x^12
4x^1+6x^3+2x^8+5x^20+7x^28
结果是：7x^0+4x^1+18x^3+5x^12+5x^20+7x^28

进程已结束，退出代码为 0
```



## 思想火花

 **实验问题：**

  将一个具有n个元素的数组向左循环移动i个位置。

> [!NOTE]
>
> 如图1 数组元素循环左移1位：
>
> ![数组元素循环左移1位](img\1485495-20190604181312769-273893486.png)
>
> 将一个具有n个元素的数组向左循环移动i个位置，**意味着将数组的前i个元素移动到数组的末尾，而原数组中的其余元素则相应地向左移动**

 有许多应用程序会调用这个问题的算法，例如在文本编辑器中移动行的操作，磁盘整理时交换两个不同大小的相邻内存块等。所以，这个问题的算法要求有较高的时间和空间性能。 

**基本要求：**

  ⑴在原数组中实现循环右移，不另外申请空间；

  ⑵时间性能尽可能好；

   ⑶分析算法的时间复杂度。

 要在不另申请空间的情况下，保证算法的时间性能尽可能好，如果先设计一个函数将数组向左移动一位，然后再调用该算法i次，是一些人通常想到的方法，但显然这个算法的时间性能不是最好的。要在有限的资源中解决这个问题，似乎比较困难，是否存在这种既不另申请存储空间，又能够达到最好时间性能的完美算法呢。

  **求解步骤：**

1）可以通过下面的方法解决这个问题：先将数组中的前i个元素存放在一个临时数组中，再将余下的n-i个元素左移i个位置， 最后将前i个元素从临时数组复制回原数组中后面的位置。但是这个算法使用了i个额外的存储单元，使得空间性能降低。

2）如上所述，先设计一个函数将数组向左循环移动一个位置，然后再调用该算法i次， 显然，这个算法的时间性能不好。 

 3）现在我们换一个角度看这个问题： 将这个问题看作是把数组ab转换成数组ba（a代表数组的前i个元素，b代表数组中余下的n-i个元素）， 先将a逆置得到ar b，再将b逆置得到ar br，最后将整个ar br逆置得到(ar br)r=ba。
> [!NOTE]
>
> **数组元素逆置是指将数组中的元素按照相反的顺序重新排列，即第一个元素和最后一个元素交换，第二个元素和倒数第二个元素交换，以此类推，直到所有元素都逆序排列完毕**。

设Reverse函数执行将数组元素逆置的操作， 对abcdefgh向左循环移动3个位置的过程如下：
```
Reverse(0, i-1); //得到cbadefgh(逆置abc)
Reverse(i, n-1); //得到cbahgfed(逆置defgh)
Reverse(0, n-1); //得到defghabc(逆置cbahgfed)
```

其原理可以用一个简单的游戏来理解：将两手的掌心对着自己，左手在右手上面， 可以实现将一个具有10 个元素的数组向左循环移动5位，如图所示。

![](img\1358339139_6806.jpg)

```c++
#include <iostream>
using namespace std;
void reverseArr(int A[],int start,int rear){
    for(int i=start,j=rear;i<j;i++,j--) {
        int t=A[i];
        A[i]=A[j];
        A[j]=t;
    }
}
void leftCir(int A[],int n,int k){
    if(k<=0 || k>=n)
        cout<<"ERROR"<<endl;
    else{
        reverseArr(A,0,k-1);
        reverseArr(A,k,n-1);
        reverseArr(A,0,n-1);
    }
}
void show(int A[],int n){
    for(int i=0;i<n;++i)
        cout<<A[i]<<" ";
    cout<<endl;
}
int main()
{
    int n,p;
    cin>>n>>p;
    int a[n];
    for(int i=0;i<n;++i)
        cin>>a[i];
    leftCir(a,n,p);
    show(a,n);
    return 0;
}
```

该算法在时间和空间上都很有效，并且是这么简短和简单，想出错都很难。 Brian Kernighan在Software Tools in Pascal中使用了这个算法在文本编辑器中移动各行。

[Software tools in Pascal by Brian W. Kernighan | 开放图书馆 (openlibrary.org)](https://openlibrary.org/books/OL4258115M/Software_tools_in_Pascal)

> Brian Kernighan 在他的著作 *Software Tools in Pascal* 中，讨论了一个将 n 个元素的数组向左循环移动 i 个位置的算法。原文如下：
>
> "To rotate an array left by i positions, reverse the first i elements, then reverse the remaining n-i elements, and finally reverse the entire array."
>
> 翻译过来大致是：
>
> “要将一个数组向左循环移动 i 个位置，首先反转数组的前 i 个元素，然后反转剩下的 n-i 个元素，最后反转整个数组。”
>
> 这种方法基于三个步骤的反转操作，可以高效地完成数组的左循环移动。

作为一个规律，一个好的算法是反复努力和重新修正的结果，即使足够幸运地得到了一个貌似完美的算法思想， 我们也应该尝试着改进它。 

## 习题



# 第三章

## 栈

栈是限定仅在表的一段进行插入和删除操作的线性表，允许插入和删除的一端称为栈顶，另一端称为栈底，不含任何数据元素的栈称为空栈

> [!NOTE]
>
> 插入元素——入栈、进栈、压栈
>
> 删除元素——出栈、弹栈

栈中元素除了具有线性关系外，还具有***==后进先出==***的特性

栈的顺序存储结构称为顺序栈，本质上是顺序表的简化，唯一需要确定的是用数组的哪一端表示栈底

通常把数组中下标为0的一段作为栈底，同时附设变量top指示栈顶元素在数组中的位置

设存储栈的数组长度为StackSize，则栈空时栈顶位置top=-1；栈满时栈顶位置top=StackSize-1

> [!TIP]
>
> 在有些教程中，将top指向栈中第一个空闲位置，如果这样的话，空栈应该表示为top=0

入栈时，栈顶位置top加1；出栈时，栈顶位置top减1

### 顺序栈的实现

```c++
#include <iostream>
using namespace std;
const int StackSize=10;//
template<typename DataType>
class SeqStack {
public:
    SeqStack();//初始化一个空栈
    ~SeqStack();//析构函数
    void Push(DataType x);//入栈操作，将元素x入栈
    DataType Pop();//出栈操作，将栈顶元素弹出
    DataType GetTop();//取栈顶元素(并不删除)
    int Empty();//判断栈是否为空
private:
    DataType data[StackSize];
    int top;//栈顶元素在数组中的下标
};
template<typename DataType>
SeqStack<DataType>::SeqStack() {
    top=-1;
}
template<typename DataType>
SeqStack<DataType>::~SeqStack() {

}
template<typename DataType>
void SeqStack<DataType>::Push(DataType x) {
    if(top==StackSize-1)throw"上溢";
    data[++top]=x;
    /*即:
    top++;
    s[top] = x;
    */
}
template<typename DataType>
DataType SeqStack<DataType>::Pop() {
    DataType x;
    if(top==-1)throw"下溢";
    x=data[top--];
    /*即:
    x=data[top];
    top--;
    */
    return x;
}
template<typename DataType>
DataType SeqStack<DataType>::GetTop() {
    return data[top];
}
template<typename DataType>
int SeqStack<DataType>::Empty() {
    if(top==-1)return 1;
    else return 0;
}
```

```c++
int main() {
    int x;
    SeqStack<int> S{};
    cout<<"对15和10入栈";
    S.Push(15);S.Push(10);
    cout<<"当前栈顶元素为:"<<S.GetTop()<<endl;
    try {
        x=S.Pop();
        cout<<x<<"出栈"<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入待入栈元素";
        cin>>x;
        S.Push(x);
    }catch (char *str){cout<<str<<endl;}
    if(S.Empty()==1) {
        cout<<"栈为空"<<endl;
    }
    else {
        cout<<"栈非空"<<endl;
    }
    return 0;
}
```

### 栈的链接存储结构及实现

栈的链接存储结构称为链栈，通常用单链表表示，其节点结构与单链表的结点结构相同

```c++
template<typename DataType>
struct Node {
    DataType data;
    Node<DataType>* next;
};
```

因为只能在栈顶执行入栈(插入)和出栈(删除)操作，所以以单链表的头部做栈顶是最方便的，而且没有必要像单链表那样为了运算方便附加头结点

> [!TIP]
>
> 在单链表中，如果我们将头部用作栈顶（top），那么入栈和出栈操作都会非常高效，这是因为单链表的特性允许我们在头部进行 O(1) 时间复杂度的操作。
>
> 具体来说，有以下几点原因：
>
> 1. **插入操作**：当我们需要向栈中添加一个元素时（即入栈操作），我们只需要创建一个新的节点，并让它指向当前的头部（即当前栈顶），然后更新头部指针指向这个新节点。这样的操作不需要遍历整个链表来找到插入位置，因此时间复杂度为 O(1)。
> 2. **删除操作**：当我们需要从栈中移除一个元素时（即出栈操作），我们只需改变头部指针，让它指向原来的头部所指向的下一个节点，并释放原来的头部节点即可。这也同样是一个 O(1) 的操作。
> 3. **访问栈顶元素**：由于头部就是栈顶，访问栈顶元素也仅需要返回头部指针指向的节点的数据，这也是 O(1) 的操作。
>
> 关于是否需要附加头结点（dummy head）的问题，通常情况下，如果单链表只用于实现栈的功能，并且不需要支持其他额外操作（比如查找特定元素等），那么就没有必要设置一个额外的头结点。因为所有的操作都在头部进行，直接将头部视为栈顶已经足够高效了。

时间复杂度 —— O(1)

```c++
#include <iostream>
using namespace std;
template<typename DataType>
struct Node {
    DataType data;
    Node<DataType>* next;
};
template<typename DataType>
class LinkStack {
public:
    LinkStack();
    ~LinkStack();
    void Push(DataType x);//入栈操作，将元素x入栈
    DataType Pop();//出栈操作，将栈顶元素弹出
    DataType GetTop();//取栈顶元素(并不删除)
    int Empty();//判断栈是否为空
private:
    Node<DataType> *top;//栈顶指针即链栈的头指针
};
template<typename DataType>
LinkStack<DataType>::LinkStack() {
    top=nullptr;
}
template<typename DataType>
LinkStack<DataType>::~LinkStack() {

}
template<typename DataType>
void LinkStack<DataType>::Push(DataType x) {
    Node<DataType> *s=nullptr;
    s=new Node<DataType>;
    s->data=x;
    s->next=top;
    top=s;
}
template<typename DataType>
DataType LinkStack<DataType>::Pop() {
    Node<DataType> *p=nullptr;
    DataType x;
    if(top==nullptr)throw"下溢";
    x=top->data;
    p=top;
    top=top->next;
    delete p;
    return x;
}
template<typename DataType>
DataType LinkStack<DataType>::GetTop() {
    return top->data;
}
template<typename DataType>
int LinkStack<DataType>::Empty() {
    if(top==nullptr)return 1;
    else return 0;
}
```

```c++
int main() {
    int x;
    LinkStack<int> S{};
    cout<<"对15和10入栈";
    S.Push(15);S.Push(10);
    cout<<"当前栈顶元素为:"<<S.GetTop()<<endl;
    try {
        x=S.Pop();
        cout<<x<<"出栈"<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入待入栈元素";
        cin>>x;
        S.Push(x);
    }catch (char *str){cout<<str<<endl;}
    if(S.Empty()==1) {
        cout<<"栈为空"<<endl;
    }
    else {
        cout<<"栈非空"<<endl;
    }
    return 0;
}
```

### 顺序栈和链栈的比较

作为一般规律，当栈的使用过程中元素变化较大时，应该采用链栈，反之，应使用顺序栈

### STL中的栈

C++ Stack(堆栈) 是一个容器类的改编，为程序员提供了堆栈的全部功能，--也就是说实现了一个先进后出(FILO)的数据结构。

栈stack的头文件为:

#include <stack>

#### c++ stl栈stack的成员函数介绍

操作   比较和分配堆栈

empty()堆栈为空则返回真

pop()移除栈顶元素(删除)

push()在栈顶增加元素(增加)

size() 返回栈中元素数目

top() 返回栈顶元素，不删除(获取)

##### 1.什么是[stack](https://so.csdn.net/so/search?q=stack&spm=1001.2101.3001.7020)

**1. stack**是一种**容器适配器**，专门用在具有后进先出操作的上下文环境中，其删除只能从容器的一端进行 元素的插入与提取操作。**(后进先出)**

**2. stack**是作为容器适配器被实现的，容器适配器即是对特定类封装作为其底层的容器，并提供一组特定 的成员函数来访问其元素，将特定类作为其底层的，元素特定容器的尾部(即栈顶)被压入和弹出。

**3. stack**的底层容器可以是任何标准的容器类模板或者一些其他特定的容器类，这些容器类应该支持以下

**操作：**

> **empty：判空操作**
>
> **back：获取尾部元素操作**
>
> **push_back：尾部插入元素操作**
>
> **pop_back：尾部删除元素操作**

**4.** 标准容器vector、deque、list均符合这些需求，默认情况下，如果没有为stack指定特定的底层容器， 默认情况下使用deque。

![img](https://i-blog.csdnimg.cn/blog_migrate/667251d46c039b39d506132e9fa06b51.png)

##### 2.容器适配器

**容器适配器（Container Adapters）是 C++ 标准库提供的一种数据结构，它们基于现有的容器类型，提供了特定的接口和功能，以便更方便地实现某些特定的数据结构和算法**。容器适配器本质上是对底层容器的封装，提供了不同的数据访问方式，使它们适用于特定的用途。 

**标准库中提供了三种常用的容器适配器：**

> ***\*stack：栈适配器\**，基于底层容器提供了栈数据结构的操作，如压入（push）、弹出（pop）、查看栈顶元素等。默认底层容器是 deque，但也可以使用其他支持 back() 和 push_back() 操作的容器。**
>
>
> ***\*queue：队列适配器\**，基于底层容器提供了队列数据结构的操作，如入队（push）、出队（pop）、查看队首元素等。默认底层容器是 deque，但也可以使用其他支持 back() 和 push_back() 操作的容器。**
>
>
> ***\*priority_queue：优先队列适配器\**，基于底层容器提供了优先队列数据结构的操作，支持在插入元素时根据优先级进行排序。默认底层容器是 vector，但也可以使用其他支持随机访问和插入操作的容器。**

##### 3.stack的使用

![img](https://i-blog.csdnimg.cn/blog_migrate/8591236db69c7870d8bd8f1c680badcb.png)

这些是C++[标准库](https://so.csdn.net/so/search?q=标准库&spm=1001.2101.3001.7020)中stack类的构造函数声明。stack是一个适配器容器，它可以使用不同的底层容器来实现栈的功能。这些构造函数声明提供了不同的方式来创建和初始化stack对象，可以根据需求选择合适的构造函数。 

> **stack的Construct中除了构造函数，其他什么都没有，它连拷贝构造、析构都没有。这个也跟它是容器适配器有关系，因为它的成员都是自定义类型，编译器默认生成的就够用。**
>
> 
>
> **stack是容器适配器以后，就开始不支持迭代器了。容器支持迭代器，容器适配器不支持迭代器。**
>
> 
>
> **栈随便去遍历反而是不好的，因为要保证后进先出的性质。**
>
> 
>
> **所以取数据得用top，想取下一个数据就得先pop。**

##### [top](https://so.csdn.net/so/search?q=top&spm=1001.2101.3001.7020)

reference top(); 和 const_reference top() const; 是 C++ 标准库中 std::stack 类的成员函数之一。它们用于获取栈顶元素的引用。

reference top();：返回栈顶元素的引用。如果需要修改栈顶元素，可以使用这个版本。

```cpp
#include <iostream>
#include <stack>
 
		stack<int> m;
 
		m.push(42);
		m.push(15);
 
		// 使用 top() 获取栈顶元素
		int topElement = m.top();
		cout << "Top element: " << topElement << endl;
 
		// 修改栈顶元素
		m.top() = 99;
		cout << "New top element: " << m.top() << endl;
 
		return 0;
	
 
}
```

 ![img](https://i-blog.csdnimg.cn/blog_migrate/af9dbb720d78efb612f5c4bb64dbb6ec.png)

后进先出，15先出，然后修改为99，最后出99

##### push

**是 C++ 标准库中 `std::stack` 类的成员函数之一。它们用于将一个新的元素压入栈中。**

**这两个版本的 push 函数允许你在栈顶添加新的元素。如果需要保持传入值的不变性，可以使用第一个版本；如果你想利用移动语义来避免不必要的复制，可以使用第二个版本。**

```cpp
#include<iostream>
#include<stack>
using namespace std;
 
 
	int main() 
	{
		stack<int> m;
 
		m.push(10); // 使用右值，将 10 压入栈中
		m.push(19);
 
		int newElement = 99;
		m.push(newElement); // 使用常量引用，将 newElement 压入栈中
 
		cout << "Stack size: " << m.size() << endl;
 
		while (!m.empty())  // 遍历不能用迭代器，容器适配器不支持迭代器
		{
			cout << m.top() << " "; // 输出栈顶元素
			m.pop(); // 弹出栈顶元素
		}
 
		return 0;
	}
```

![img](https://i-blog.csdnimg.cn/blog_migrate/fe6f4bb4063818fce45d827a5bc7661c.png)

#####  pop

**`void pop();` 是 C++ 标准库中 `stack` 类的成员函数之一。它用于将栈顶元素弹出（删除）。**

**这个函数没有返回值，它只是从栈中移除栈顶元素。在调用 `pop()` 函数之前，需要确保栈不为空，否则会导致未定义行为。**

```cpp
	int main() 
	{
		stack<int> m;
 
		m.push(10); // 使用右值，将 10 压入栈中
		m.push(19);
		m.push(29);
 
		cout << "Stack size: " << m.size() << endl;
 
		m.pop();
 
		cout << "Stack new size: " << m.size() << endl;
 
		return 0;
	}
```

![img](https://i-blog.csdnimg.cn/blog_migrate/84b16ae75feec2ff17399e8a5edab7b8.png)

##### **公共成员函数**：

> push(const T& x)：将传入的元素值 x 添加到底层容器的末尾，实现了入栈操作。
>
>
> pop()：从底层容器的末尾删除一个元素，实现了出栈操作。
>
>
> T& top() 和 const T& top() const：分别返回底层容器的末尾元素的引用（允许修改）和常量引用（只读），实现了查看栈顶元素操作。
>
>
> bool empty() const：返回底层容器是否为空。
>
>
> size_t size() const：返回底层容器中元素的数量。
>
>
> 私有成员变量 _con：这是一个模板类的私有成员变量，用于存储实际的栈元素。其类型是根据模板参数 Container 确定的，在实例化时会被替换为具体的容器类型。

### 实例(o2r函数，用于将整数n转换为基数r的字符串表示)

```c++
#include <iostream>
#include <stack>
using namespace std;

// 定义o2r函数，用于将整数n转换为基数r的字符串表示
void o2r(int n, int r) {
    // 使用栈来存储转换过程中的每一位数字
    stack<char> s;
    // base数组用于将十进制数转换为r进制的字符表示
    char base[] = "0123456789ABCDEF";
    
    // 当n不为0时，继续转换过程
    while (n) {
        // 取n除以r的余数，得到当前位的值，并将其加入栈中
        s.push(base[n % r]);
        // 更新n为n除以r的商，继续下一位的计算
        n = n / r;
    }
    
    // 当栈不为空时，依次取出栈中的元素并输出，完成r进制数的构建
    while (!s.empty()) {
        cout << s.top();
        // 取出栈顶元素后，将其从栈中移除
        s.pop();
    }
    
    // 在输出后换行，以便于阅读
    cout << endl;
}

int main() {
    // 示例：将10进制的255转换为16进制
    cout << "10进制的255转换为16进制：" << endl;
    o2r(255, 16); // 输出: FF

    // 示例：将10进制的100转换为2进制
    cout << "10进制的100转换为2进制：" << endl;
    o2r(100, 2); // 输出: 1100100

    // 示例：将10进制的1234转换为8进制
    cout << "10进制的1234转换为8进制：" << endl;
    o2r(1234, 8); // 输出: 2322

    return 0;
}
```

## 队列

队列是只允许在一端进行插入操作，在另一端进行删除操作的线性表，允许插入(入队、进队)的一端称为队尾，允许删除(出队)的一端称为队头。

队列中的元素除了具有线性关系外，还具有==***先进先出***==的特性

### 队列的顺序存储结构及实现

队列的顺序存储结构称为顺序队列。假设队列有n个元素，顺序队列把队列的所有元素存储在数组的前n个单元。如果把队头元素放在数组中下标为0的一端，则入队操作相当于追加，不需要移动元素，其时间性能为O(1)，但是出队操作的时间性能为O(n)，因为要保证剩下的n-1个元素仍然存储在数组的前n-1个单元，所有元素都要向前移动一个位置。

如果放宽队列的所有元素必须存储在数组的前n个单元这一条件，就可以得到一种更为有效的存储方式。此时入队和出队操作的时间性能都是O(1)，因为没有移动任何元素。需要设置队头、队尾两个位置变量front和rear，入队时rear加1，出队时front加1，并且约定：front指向队头元素的前一个位置，rear指向队尾元素的位置。

> [!NOTE]
>
> 这样约定的目的是方便运算，例如rear-front等于队列的长度。

### 循环队列

在顺序队列中，随着队列的插入和删除操作，整个队列向数组的高端移过去，从而产生了队列的“单向移动性”。当元素被插入到数组中下标最大的位置之后，数组空间就用尽了，尽管此时数组的低端还有空闲空间，这种现象叫做“假溢出”

解决假溢出的方法是将存储队列的数组看成是头尾相接的循环结构，这可以通过取模操作来实现，设存储队列的数组长度为QueueSize，操作语句为rear=(rear+1)%QueueSize

队列的这种头尾相接的顺序存储结构称为循环队列。

队空的条件是front=rear

队满的条件是(rear+1)%QueueSize=front

```c++
#include <iostream>
using namespace std;
const int QueueSize=100;
template <typename DataType>
class CirQueue {
public:
    CirQueue();//构造函数，初始化空队列
    ~CirQueue();//析构函数
    void EnQueue(DataType x);//入队
    DataType DeQueue();//出队
    DataType GetHead();//取队头元素
    int Empty();//判断队列是否为空
private:
    DataType data[QueueSize];//存放队列元素的数组
    int front,rear;//游标，队头和队尾指针
};
template<typename DataType>
CirQueue<DataType>::CirQueue() {
    rear=front=QueueSize-1;
}
template<typename DataType>
CirQueue<DataType>::~CirQueue() {

}
template<typename DataType>
void CirQueue<DataType>::EnQueue(DataType x) {
    if((rear+1)%QueueSize==front)throw"上溢";
    rear=(rear+1)%QueueSize;//队尾指针在循环意义下加1
    data[rear]=x;//在队尾处插入元素
}
template<typename DataType>
DataType CirQueue<DataType>::DeQueue() {
    if(rear==front)throw"下溢";
    front=(front+1)%QueueSize;//队头在循环意义下加1
    return data[front];//返回出队前的队头元素
}
template<typename DataType>
DataType CirQueue<DataType>::GetHead() {
    if(rear==front)throw"下溢";
    return data[(front+1)%QueueSize];
}
template<typename DataType>
int CirQueue<DataType>::Empty() {
    if (rear==front) {
        return 1;
    }
    else {
        return 0;
    }
}
```



```c++
int main() {
    int x;
    CirQueue<int> Q{};
    Q.EnQueue(5);Q.EnQueue(8);
    cout<<"当前队头元素为："<<Q.GetHead()<<endl;
    try {
        x=Q.DeQueue();
        cout<<"执行一次出队操作，出队元素是："<<x<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入入队元素:";
        cin>>x;
        Q.EnQueue(x);
    }catch (char *str){cout<<str<<endl;}
    if(Q.Empty()==1) {
        cout<<"队列为空"<<endl;
    }
    else {
        cout<<"队列非空"<<endl;
    }
    return 0;
}
```

### 队列的链存储结构及实现

队列的链接存储结构称为链队列，通常用单链表表示，其结点结构与单链表的结点结构相同

```c++
template<typename DataType>
struct Node {
    DataType data;
    Node<DataType>* next;
};
```

为了使空队列和非空队列的操作一致，链队列也加上头结点；为了操作上的方便，设置队头指针指向链队列的头结点，队尾指针指向终端结点

```c++
#include <iostream>
using namespace std;
template<typename DataType>
struct Node {
    DataType data;
    Node<DataType>* next;
};
template <typename DataType>
class LinkQueue {
public:
    LinkQueue();//构造函数，初始化空队列
    ~LinkQueue();//析构函数
    void EnQueue(DataType x);//入队
    DataType DeQueue();//出队
    DataType GetHead();//取队头元素
    int Empty();//判断队列是否为空
private:
    Node<DataType> *front,*rear;//队头和队尾指针
};

template<typename DataType>
LinkQueue<DataType>::LinkQueue() {
    Node<DataType> *s=nullptr;
    s=new Node<DataType>;
    s->next=nullptr;
    front=rear=s;//将队头指针和队尾指针都指向头结点s
}
template<typename DataType>
LinkQueue<DataType>::~LinkQueue() {

}
template<typename DataType>
void LinkQueue<DataType>::EnQueue(DataType x) {
    Node<DataType> *s=nullptr;
    s=new Node<DataType>;
    s->data=x;s->next=nullptr;
    rear->next=s;
    rear=s;
}
template<typename DataType>
DataType LinkQueue<DataType>::DeQueue() {
    DataType x;
    Node<DataType> *p=nullptr;
    if(rear==front)throw"下溢";
    p=front->next;x=p->data;
    front->next=p->next;
    if(p->next==nullptr){//出队前队列长度为1
        rear=front;
    }
    delete p;
    return x;
}
template<typename DataType>
DataType LinkQueue<DataType>::GetHead() {
    return front->next->data;
}
template<typename DataType>
int LinkQueue<DataType>::Empty() {
    if(front==rear) {
        return 1;
    }
    else {
        return 0;
    }
}
```

```c++
int main() {
    int x;
    LinkQueue<int> Q{};
    Q.EnQueue(5);Q.EnQueue(8);
    cout<<"当前队头元素为："<<Q.GetHead()<<endl;
    try {
        x=Q.DeQueue();
        cout<<"执行一次出队操作，出队元素是："<<x<<endl;
    }catch (char *str){cout<<str<<endl;}
    try {
        cout<<"请输入入队元素:";
        cin>>x;
        Q.EnQueue(x);
    }catch (char *str){cout<<str<<endl;}
    if(Q.Empty()==1) {
        cout<<"队列为空"<<endl;
    }
    else {
        cout<<"队列非空"<<endl;
    }
    return 0;
}
```

### 循环队列和链队列的比较

循环队列和链队列基本操作的时间复杂度均为O(1)，因此可以比较的只有空间性能。作为一般规律，当队列中元素个数变化较大时，应采用链队列，反之，应该采用循环队列，如果确定不会发生假溢出，也可以采用顺序队列

## 扩展与提高

### 两栈共享空间

在一个程序中，如果同时使用具有相同数据类型的两个顺序栈，最直接的方法是为每个栈开辟一个数组空间，这样做的结果可能出现一个栈的空间已被占满而无法再进行插入操作，同时另一个栈的空间仍有大量剩余而没有得到利用的情况，从而造成存储空间的浪费。

可以充分利用顺序栈单向延伸的特性，使用一个数组来存储两个栈，让一个栈的栈底位于该数组的始端，另一个栈的栈底位于该数组的末端，每个栈从各自的端点向中间延伸。

其中，topl 和 top2分别为栈1 和栈2 的栈顶位置，StackSize 为整个数组空间的大小，栈1的底位于下标为。的一端；栈2的底位于下标为 StackSize一1 的一端。

在两栈共享空间中，由于两个栈相向增长，浪费的数组空间就会减少，同时发生上溢的概率也会减少。**但是，只有当两个栈的空间需求有相反的关系时，这种方法才会奏效，也就是说，最好一个栈增长时另一个栈缩短。**下面给出两栈共享空间的类定义：

```c++
const int StackSize=100;
template <typename DataType>
class BothStack {
public:
    BothStack();//构造函数，将两个栈分别初始化
    ~BothStack();
    void Push(int i,DataType x);//入栈操作，将元素x压入栈i
    DataType Pop(int i);//出栈操作，对栈i执行出栈操作
    DataType GetTop(int i);//取栈i的栈顶元素
    int Empty(int i);//判断栈i是否为空栈
private:
    DataType data[StackSize];//存放两个栈的数组
    int top1,top2;//两个栈的栈顶指针，分别为各自栈顶元素在数组中的下标
};
```

设整型变量i只取1和2两个值。当i=1时，表示对栈1操作；当i=2时，表示对栈2操作

下面讨论两栈共享空间的入栈和出栈操作：

#### 入栈

当存储栈的数组中没用空闲单元时为栈满，此时栈1的栈顶元素和栈2的栈顶元素位于数组中的相邻位置，即top1=top2-1。另外，当新元素插入栈2时，栈顶位置top2不是加一而是减一

```c++
template<typename DataType>
void BothStack<DataType>::Push(int i, DataType x) {
    if(top1==top2-1)throw"上溢";
    if(i==1)data[++top1]=x;
    /*即:
    top1++;
    data[top1] = x;
    */
    if(i==2)data[--top2]=x;
    /*即:
    top2--;
    data[top2] = x;
    */
}
```

#### 出栈

当top1=-1时栈1为空，当top2=StackSize时栈2为空。另外，当从栈2删除元素时，top2不是减一而是加一

```c++
template<typename DataType>
DataType BothStack<DataType>::Pop(int i) {
    if(i==1) {
        if(top1==-1)throw"下溢";
        return data[top1--];
    }
    if(i==2) {
        if(top2==StackSize)throw"下溢";
        return data[top2++];
    }
}
```

#### 完整代码

```c++
#include<iostream>
using namespace std;
const int StackSize=100;
template <typename DataType>
class BothStack {
public:
    BothStack();//构造函数，将两个栈分别初始化
    ~BothStack();
    void Push(int i,DataType x);//入栈操作，将元素x压入栈i
    DataType Pop(int i);//出栈操作，对栈i执行出栈操作
    DataType GetTop(int i);//取栈i的栈顶元素
    int Empty(int i);//判断栈i是否为空栈
private:
    DataType data[StackSize];//存放两个栈的数组
    int top1,top2;//两个栈的栈顶指针，分别为各自栈顶元素在数组中的下标
};
template<typename DataType>
void BothStack<DataType>::Push(int i, DataType x) {
    if(top1==top2-1)throw"上溢";
    if(i==1)data[++top1]=x;
    /*即:
    top1++;
    data[top1] = x;
    */
    if(i==2)data[--top2]=x;
    /*即:
    top2--;
    data[top2] = x;
    */
}
template<typename DataType>
DataType BothStack<DataType>::Pop(int i) {
    if(i==1) {
        if(top1==-1)throw"下溢";
        return data[top1--];
    }
    if(i==2) {
        if(top2==StackSize)throw"下溢";
        return data[top2++];
    }
}
```

### 双端队列

#### 定义

双端队列是队列的扩展，

如果允许在队列的两端进行插人和删除操作，则称为双端队列；

如果允许在两端插入但只允许在一端删除，则称为二进一出队列；

如果只允许在一端插入但允许在两端删除，则称为一进二出队列。

双端队列和普通队列一样，具有人队、出队、取队头元素等基本操作，不同的是必须指明操作的位置，其抽象数据类型定义如下：

```ADT
ADT DoubleQueue
DataModel
	相邻元素具有前驱和后继关系，允许在队列的两端进行插入和删除操作
Operation
	InitQueue
		输入：无
		功能：初始化双端队列
		输出：一个空的双端队列
	DestroyQueue
		输人：无
		功能：队列的销毁
		输出：释放双端队列占用的存储空间
	EnQueueHead
		输入：元素值x
		功能：入队操作，将元素x插人到双端队列的队头输出：如果插入成功，双端队列的队头增加了一个元素
	EnQueueTail
		输人：元素值x
		功能：入队操作，将元素×插入到双端队列的队尾输出：如果插入成功，双端队列的队尾增加了一个元系
	DeQueueHead
		输入：无
		功能：出队操作，删除双端队列的队头元素
		输出：如果删除成功，将队头元素出队
	DeQueueTail
		输人：无
		功能：出队操作，删除双端队列的队尾元素输出：如果删除成功，将队尾元素出队
	GetHead
		输人：无
		功能：读取双端队列的队头元素
		输出：若双端队列不空，返回队头元素
	GetTail
		输人：无
		功能：读取双端队列的队尾元素
		输出：若双端队列不空，返回队尾元素
	Empty
		输人：无
		功能：判空操作，判断双端队列是否为空输出：如果双端队列为空，返回1，否则返回0。
endADT
```

双端队列可以采用循环队列的存储方式，基本算法可以在循环队列的基础上修改而成。不同的是，在队头入队时，先将新元素插人到 front处，再把队头位置 front 在循环意义下减1；在队尾出队时，先将 rear 处的队尾元素暂存，再把队尾位置 rear 在循环意义下减1。

#### 完整代码

```C++
#include <iostream>
#include <stdexcept>

// 定义链表节点
struct Node {
	int data;
	Node* prev;
	Node* next;
	
	Node(int val) : data(val), prev(nullptr), next(nullptr) {}
};

// 双端队列类
class DoubleQueue {
private:
	Node* head;
	Node* tail;
	
public:
	// 构造函数
	DoubleQueue() : head(nullptr), tail(nullptr) {}
	
	// 析构函数
	~DoubleQueue() {
		DestroyQueue();
	}
	
	// 初始化双端队列
	void InitQueue() {
		head = nullptr;
		tail = nullptr;
	}
	
	// 销毁双端队列
	void DestroyQueue() {
		while (head != nullptr) {
			Node* temp = head;
			head = head->next;
			delete temp;
		}
		tail = nullptr;
	}
	
	// 在队头插入元素
	void EnQueueHead(int x) {
		Node* newNode = new Node(x);
		if (head == nullptr) {
			head = tail = newNode;
		} else {
			newNode->next = head;
			head->prev = newNode;
			head = newNode;
		}
	}
	
	// 在队尾插入元素
	void EnQueueTail(int x) {
		Node* newNode = new Node(x);
		if (tail == nullptr) {
			head = tail = newNode;
		} else {
			newNode->prev = tail;
			tail->next = newNode;
			tail = newNode;
		}
	}
	
	// 从队头删除元素
	bool DeQueueHead() {
		if (head == nullptr) return false;
		Node* temp = head;
		head = head->next;
		if (head != nullptr) {
			head->prev = nullptr;
		} else {
			tail = nullptr;
		}
		delete temp;
		return true;
	}
	
	// 从队尾删除元素
	bool DeQueueTail() {
		if (tail == nullptr) return false;
		Node* temp = tail;
		tail = tail->prev;
		if (tail != nullptr) {
			tail->next = nullptr;
		} else {
			head = nullptr;
		}
		delete temp;
		return true;
	}
	
	// 获取队头元素
	int GetHead() const {
		if (head == nullptr) throw std::out_of_range("Queue is empty");
		return head->data;
	}
	
	// 获取队尾元素
	int GetTail() const {
		if (tail == nullptr) throw std::out_of_range("Queue is empty");
		return tail->data;
	}
	
	// 判断双端队列是否为空
	bool Empty() const {
		return head == nullptr;
	}
};

int main() {
	DoubleQueue dq;
	
	// 测试操作
	dq.EnQueueHead(1);
	dq.EnQueueTail(2);
	dq.EnQueueHead(3);
	
	std::cout << "Head: " << dq.GetHead() << ", Tail: " << dq.GetTail() << std::endl; // 应该输出 Head: 3, Tail: 2
	
	dq.DeQueueHead();
	std::cout << "After DeQueueHead, Head: " << dq.GetHead() << std::endl; // 应该输出 Head: 1
	
	dq.DeQueueTail();
	std::cout << "After DeQueueTail, Tail: " << dq.GetHead() << std::endl; // 应该输出 Tail: 1
	
	std::cout << "Is the queue empty? " << (dq.Empty() ? "Yes" : "No") << std::endl; // 应该输出 No
	
	dq.DeQueueHead();
	std::cout << "Is the queue empty after all elements removed? " << (dq.Empty() ? "Yes" : "No") << std::endl; // 应该输出 Yes
	
	return 0;
}
```

## 应用举例

### 括号匹配问题

```c++
#include<iostream>
#include <string>
using namespace std;

class Matcher {
public:
    Matcher(string str);
    ~Matcher();
    int Match();
private:
    string str;
};
Matcher::Matcher(string str) {
    this->str=str;
}
int Matcher::Match() {
    char S[100];
    int i,top=-1;
    for(i=0;str[i]!='\0';i++) {
        if(str[i]==')') {
            if(top>-1)top--;
            else return -1;
        }
        else if(str[i]=='(') {
            S[++top]=str[i];
        }
    }
    if(top==-1) return 0;
    else return 1;
}
Matcher::~Matcher() {

}


int main() {
    string str;
    cout<<"请输入一个算数表达式";
    cin>>str;
    Matcher M{str};
    int k=M.Match();
    if(k==0) {
        cout<<"正确匹配\n";
    }
    else if(k==1) {
        cout<<"多左括号\n";
    }
    else {
        cout<<"多右括号\n";
    }
    return 0;
}
```

### 表达式求值

表达式求值需要根据运算符的优先级来确定计算顺序。因此，在求值过程中需要保存优先级较低的运算符以及没有参与计算的运算对象，并将当前运算符与已经扫描过的、尚未计算的运算符进行比较，以确定哪个运算符以及哪两个运算对象参与计算。这需要两个栈来辅助完成：运算对象栈 OPND 和运算符栈 OPTR。

```c++
#include <iostream>
#include <string>
using namespace std;
class Expression {
public:
    Expression(string str);
    ~Expression();
    int Compute();
private:
    int Comp(char str1,char str2);
    string str;
};
Expression::Expression(string str) {
    this->str=str+"#";
}
Expression::~Expression() {

}
int Expression::Compute() {
    char OPND[100],OPTR[100];
    OPTR[0]='#';
    int top1=-1,top2=0;
    int i,k,x,y,z,op;
    for(i=0;str[i]!='\0';) {
        if(str[i]>=48 && str[i]<=57) {
            OPND[++top1]=str[i++]-48;
        }
        else {
            k=Comp(str[i],OPTR[top2]);
            if(k==1) {
                OPTR[++top2]=str[i++];
            }
            else if(k==-1) {
                y=OPND[top1--];
                x=OPND[top1--];
                op=OPTR[top2--];
                switch (op) {
                    case '+':z=x+y;break;
                    case '-':z=x-y;break;
                    case '*':z=x*y;break;
                    case '/':z=x/y;break;
                    default: break;
                }
                OPND[++top1]=z;
            }
            else {
                top2--;
                i++;
            }
        }
    }
    return OPND[top1];
}
int Expression::Comp(char str1, char str2) {
    switch (str1) {
        case '+':case '-':
            if(str2=='(' || str2=='#') return 1;
            else return -1;
            break;
        case '*':case '/':
            if(str2=='*' || str2=='/') return -1;
            else return 1;
            break;
        case '(':return -1;break;
        case ')':
            if(str2=='(') return 0;else return -1;
            break;
        case '#':
            if(str2=='#') return 0;else return -1;
            break;
        default:
            break;
    }
}
int main() {
    string str;
    cout<<"请输入一个表达式"<<endl;
    cin>>str;
    Expression E{str};
    int result=E.Compute();
    cout<<"表达式的值是"<<result<<endl;
    return 0;
}
```

## 习题

# 第四章

## 字符串

给定两个字符串S，T，在主串S中寻找子串T的过程称为模式匹配，T称为模式。如果匹配成功，返回T在S中的位置；如果匹配失败，返回0。

### BF算法

BF算法的基本思想是蛮力匹配，即从主串S的第一个字符开始和模式T的第一个字符进行比较。若相等，则继续比较两者的后续字符；否则，从主串S的第二个字符开始和模式T的第一个字符进行比较，重复上述过程，直至S或T中所有字符比较完毕。若T中的字符全部比较完毕，则匹配成功，返回本趟匹配的开始位置；否则匹配失败，返回0.

```c++
int BF(char S[],char T[]){
	int start=0;
	int i=0,j=0;
	while((S[i]!='\0') && (T[i]!='\0')){
		if(S[i]==T[i]){
			i++;j++;
		}
		else{
			start++;
			i=start;j=0;
		}
	}
	if(T[j]=='\0'){
		return start+1;
	}
	else{
		return 0;
	}
}
```

最坏情况下的时间复杂度是O(n*m)（设主串S长度为n，模式T长度为m）

### KMP算法

【最浅显易懂的 KMP 算法讲解】 https://www.bilibili.com/video/BV1AY4y157yL/?share_source=copy_web&vd_source=440c7ec5d64e62c0d02675282b15de02
【【天勤考研】KMP算法易懂版】 https://www.bilibili.com/video/BV1jb411V78H/?share_source=copy_web&vd_source=440c7ec5d64e62c0d02675282b15de02
【KMP算法之求next数组代码讲解】 https://www.bilibili.com/video/BV16X4y137qw/?share_source=copy_web&vd_source=440c7ec5d64e62c0d02675282b15de02

## 多维数组



## 矩阵压缩存储
