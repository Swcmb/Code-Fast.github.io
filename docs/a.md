[TOC]

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

### 单链表的结点定义：

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
        p->next;
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

其原理可以用一个简单的游戏来理解：将两手的掌心对着自己，左手在右手上面， 可以实现将一个具有10 个元素的数组向左循环移动5位，如图所示。![](img\1358339139_6806.jpg)

该算法在时间和空间上都很有效，并且是这么简短和简单，想出错都很难。 Brian Kernighan在Software Tools in Pascal中使用了这个算法在文本编辑器中移动各行。

[Software tools in Pascal by Brian W. Kernighan | 开放图书馆 (openlibrary.org)](https://openlibrary.org/books/OL4258115M/Software_tools_in_Pascal)

作为一个规律，一个好的算法是反复努力和重新修正的结果，即使足够幸运地得到了一个貌似完美的算法思想， 我们也应该尝试着改进它。 

## 习题

# 第三章
