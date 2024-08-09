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

