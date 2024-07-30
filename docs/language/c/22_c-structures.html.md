<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 结构体</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C <span class="color_h1">结构体</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>C 数组允许定义可存储相同类型数据项的变量，<b>结构</b>是 C 编程中另一种用户自定义的可用的数据类型，它允许您存储不同类型的数据项。</p>&#13;
<p>结构体中的数据成员可以是基本数据类型（如 int、float、char 等），也可以是其他结构体类型、指针类型等。</p>&#13;
<p>结构用于表示一条记录，假设您想要跟踪图书馆中书本的动态，您可能需要跟踪每本书的下列属性：</p>&#13;
<ul class="list">&#13;
<li>Title</li>&#13;
<li>Author</li>&#13;
<li>Subject</li>&#13;
<li>Book ID</li>&#13;
</ul>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">定义结构</h2>&#13;
<p>结构体定义由关键字 <span class="marked">struct</span> 和结构体名组成，结构体名可以根据需要自行定义。</p><p>struct 语句定义了一个包含多个成员的新的数据类型，struct 语句的格式如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;

<span style="color: #05a;">struct</span> tag <span style="color: #008000;">{</span> <br/>
    member<span style="color: #000040;">-</span>list<br/>
    member<span style="color: #000040;">-</span>list <br/>
    member<span style="color: #000040;">-</span>list  <br/>
    ...<br/>
<span style="color: #008000;">}</span> variable<span style="color: #000040;">-</span>list <span style="color: #008080;">;</span> <br/>
&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
&#13;
<p><b>tag</b> 是结构体标签。</p>&#13;
<p><b>member-list</b> 是标准的变量定义，比如 <span class="marked">int i;</span> 或者 <span class="marked">float f;</span>，或者其他有效的变量定义。</p>&#13;
<p><b>variable-list</b> 结构变量，定义在结构的末尾，最后一个分号之前，您可以指定一个或多个结构变量。下面是声明 Book 结构的方式：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;

<span style="color: #05a;">struct</span> Books<br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">char</span>  title<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  author<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  subject<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">int</span>   book_id<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span> book<span style="color: #008080;">;</span>  <br/>
&#13;
</div>&#13;
</div>&#13;
<p>在一般情况下，<strong>tag、member-list、variable-list</strong> 这 3 部分至少要出现 2 个。以下为实例：</p>&#13;
&#13;
<div class="example">&#13;
<div class="example_code">&#13;

<span style="color: #666666;">//此声明声明了拥有3个成员的结构体，分别为整型的a，字符型的b和双精度的c</span><br/>
<span style="color: #666666;">//同时又声明了结构体变量s1</span><br/>
<span style="color: #666666;">//这个结构体并没有标明其标签</span><br/>
<span style="color: #05a;">struct</span> <br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">char</span> b<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">double</span> c<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span> s1<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #666666;">//此声明声明了拥有3个成员的结构体，分别为整型的a，字符型的b和双精度的c</span><br/>
<span style="color: #666666;">//结构体的标签被命名为SIMPLE,没有声明变量</span><br/>
<span style="color: #05a;">struct</span> SIMPLE<br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">char</span> b<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">double</span> c<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<span style="color: #666666;">//用SIMPLE标签的结构体，另外声明了变量t1、t2、t3</span><br/>
<span style="color: #05a;">struct</span> SIMPLE t1, t2<span style="color: #008000;">[</span><span style="color: #0000dd;">20</span><span style="color: #008000;">]</span>, <span style="color: #000040;">*</span>t3<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #666666;">//也可以用typedef创建新类型</span><br/>
<span style="color: #05a;">typedef</span> <span style="color: #05a;">struct</span><br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">char</span> b<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">double</span> c<span style="color: #008080;">;</span> <br/>
<span style="color: #008000;">}</span> Simple2<span style="color: #008080;">;</span><br/>
<span style="color: #666666;">//现在可以用Simple2作为类型声明新的结构体变量</span><br/>
Simple2 u1, u2<span style="color: #008000;">[</span><span style="color: #0000dd;">20</span><span style="color: #008000;">]</span>, <span style="color: #000040;">*</span>u3<span style="color: #008080;">;</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>在上面的声明中，第一个和第二声明被编译器当作两个完全不同的类型，即使他们的成员列表是一样的，如果令 t3=&amp;s1，则是非法的。</p>&#13;
&#13;
<p>结构体的成员可以包含其他结构体，也可以包含指向自己结构体类型的指针，而通常这种指针的应用是为了实现一些更高级的数据结构如链表和树等。</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;

<span style="color: #666666;">//此结构体的声明包含了其他的结构体</span><br/>
<span style="color: #05a;">struct</span> COMPLEX<br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">char</span> string<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">struct</span> SIMPLE a<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #666666;">//此结构体的声明包含了指向自己类型的指针</span><br/>
<span style="color: #05a;">struct</span> NODE<br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">char</span> string<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">struct</span> NODE <span style="color: #000040;">*</span>next_node<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>如果两个结构体互相包含，则需要对其中一个结构体进行不完整声明，如下所示：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;

<span style="color: #05a;">struct</span> B<span style="color: #008080;">;</span>    <span style="color: #666666;">//对结构体B进行不完整声明</span><br/>
<br/>
<span style="color: #666666;">//结构体A中包含指向结构体B的指针</span><br/>
<span style="color: #05a;">struct</span> A<br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">struct</span> B <span style="color: #000040;">*</span>partner<span style="color: #008080;">;</span><br/>
    <span style="color: #666666;">//other members;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #666666;">//结构体B中包含指向结构体A的指针，在A声明完后，B也随之进行声明</span><br/>
<span style="color: #05a;">struct</span> B<br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">struct</span> A <span style="color: #000040;">*</span>partner<span style="color: #008080;">;</span><br/>
    <span style="color: #666666;">//other members;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
&#13;
</div>&#13;
</div><hr/>&#13;
<h2>结构体变量的初始化</h2>&#13;
<p>和其它类型变量一样，对结构体变量可以在定义时指定初始值。</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #05a;">struct</span> Books<br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">char</span>  title<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  author<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  subject<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">int</span>   book_id<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span> book <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #a11;">"C 语言"</span>, <span style="color: #a11;">"RUNOOB"</span>, <span style="color: #a11;">"编程语言"</span>, <span style="color: #0000dd;">123456</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"title : %s<span style="color: #000099; font-weight: bold;">\n</span>author: %s<span style="color: #000099; font-weight: bold;">\n</span>subject: %s<span style="color: #000099; font-weight: bold;">\n</span>book_id: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book.<span style="color: #007788;">title</span>, book.<span style="color: #007788;">author</span>, book.<span style="color: #007788;">subject</span>, book.<span style="color: #007788;">book_id</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>执行输出结果为：</p>&#13;
<pre>title : C 语言&#13;
author: RUNOOB&#13;
subject: 编程语言&#13;
book_id: 123456</pre>&#13;
<h2 class="tutheader">访问结构成员</h2>&#13;
<p>为了访问结构的成员，我们使用<b>成员访问运算符（.）</b>。成员访问运算符是结构变量名称和我们要访问的结构成员之间的一个句号。您可以使用 <b>struct</b> 关键字来定义结构类型的变量。下面的实例演示了结构的用法：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #060;">#include &lt;string.h&gt;</span><br/>
 <br/>
<span style="color: #05a;">struct</span> Books<br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">char</span>  title<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  author<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  subject<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">int</span>   book_id<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
 <br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span> <span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">struct</span> Books Book1<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book1，类型为 Books */</span><br/>
   <span style="color: #05a;">struct</span> Books Book2<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book2，类型为 Books */</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* Book1 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">title</span>, <span style="color: #a11;">"C Programming"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Nuha Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"C Programming Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book1.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495407</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* Book2 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">title</span>, <span style="color: #a11;">"Telecom Billing"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Zara Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"Telecom Billing Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book2.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495700</span><span style="color: #008080;">;</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* 输出 Book1 信息 */</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 1 title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book1.<span style="color: #007788;">title</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 1 author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book1.<span style="color: #007788;">author</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 1 subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book1.<span style="color: #007788;">subject</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 1 book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book1.<span style="color: #007788;">book_id</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* 输出 Book2 信息 */</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 2 title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book2.<span style="color: #007788;">title</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 2 author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book2.<span style="color: #007788;">author</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 2 subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book2.<span style="color: #007788;">subject</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book 2 book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, Book2.<span style="color: #007788;">book_id</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Book 1 title : C Programming&#13;
Book 1 author : Nuha Ali&#13;
Book 1 subject : C Programming Tutorial&#13;
Book 1 book_id : 6495407&#13;
Book 2 title : Telecom Billing&#13;
Book 2 author : Zara Ali&#13;
Book 2 subject : Telecom Billing Tutorial&#13;
Book 2 book_id : 6495700&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">结构作为函数参数</h2>&#13;
<p>您可以把结构作为函数参数，传参方式与其他类型的变量或指针类似。您可以使用上面实例中的方式来访问结构变量：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #060;">#include &lt;string.h&gt;</span><br/>
 <br/>
<span style="color: #05a;">struct</span> Books<br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">char</span>  title<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  author<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  subject<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">int</span>   book_id<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #696969;; font-style: italic;">/* 函数声明 */</span><br/>
<span style="color: #05a;">void</span> printBook<span style="color: #008000;">(</span> <span style="color: #05a;">struct</span> Books book <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span> <span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">struct</span> Books Book1<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book1，类型为 Books */</span><br/>
   <span style="color: #05a;">struct</span> Books Book2<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book2，类型为 Books */</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* Book1 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">title</span>, <span style="color: #a11;">"C Programming"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Nuha Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"C Programming Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book1.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495407</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* Book2 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">title</span>, <span style="color: #a11;">"Telecom Billing"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Zara Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"Telecom Billing Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book2.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495700</span><span style="color: #008080;">;</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* 输出 Book1 信息 */</span><br/>
   printBook<span style="color: #008000;">(</span> Book1 <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* 输出 Book2 信息 */</span><br/>
   printBook<span style="color: #008000;">(</span> Book2 <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<span style="color: #05a;">void</span> printBook<span style="color: #008000;">(</span> <span style="color: #05a;">struct</span> Books book <span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book.<span style="color: #007788;">title</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book.<span style="color: #007788;">author</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book.<span style="color: #007788;">subject</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book.<span style="color: #007788;">book_id</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Book title : C Programming&#13;
Book author : Nuha Ali&#13;
Book subject : C Programming Tutorial&#13;
Book book_id : 6495407&#13;
Book title : Telecom Billing&#13;
Book author : Zara Ali&#13;
Book subject : Telecom Billing Tutorial&#13;
Book book_id : 6495700&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">指向结构的指针</h2>&#13;
<p>您可以定义指向结构的指针，方式与定义指向其他类型变量的指针相似，如下所示：</p>&#13;
<pre>&#13;
struct Books *struct_pointer;&#13;
</pre>&#13;
<p>现在，您可以在上述定义的指针变量中存储结构变量的地址。为了查找结构变量的地址，请把 &amp; 运算符放在结构名称的前面，如下所示：</p>&#13;
<pre>&#13;
struct_pointer = &amp;Book1;&#13;
</pre>&#13;
<p>为了使用指向该结构的指针访问结构的成员，您必须使用 -&gt; 运算符，如下所示：</p>&#13;
<pre>&#13;
struct_pointer-&gt;title;&#13;
</pre>&#13;
<p>让我们使用结构指针来重写上面的实例，这将有助于您理解结构指针的概念：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #060;">#include &lt;string.h&gt;</span><br/>
 <br/>
<span style="color: #05a;">struct</span> Books<br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">char</span>  title<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  author<span style="color: #008000;">[</span><span style="color: #0000dd;">50</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">char</span>  subject<span style="color: #008000;">[</span><span style="color: #0000dd;">100</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">int</span>   book_id<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #696969;; font-style: italic;">/* 函数声明 */</span><br/>
<span style="color: #05a;">void</span> printBook<span style="color: #008000;">(</span> <span style="color: #05a;">struct</span> Books <span style="color: #000040;">*</span>book <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span> <span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">struct</span> Books Book1<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book1，类型为 Books */</span><br/>
   <span style="color: #05a;">struct</span> Books Book2<span style="color: #008080;">;</span>        <span style="color: #696969;; font-style: italic;">/* 声明 Book2，类型为 Books */</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* Book1 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">title</span>, <span style="color: #a11;">"C Programming"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Nuha Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book1.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"C Programming Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book1.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495407</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* Book2 详述 */</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">title</span>, <span style="color: #a11;">"Telecom Billing"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">author</span>, <span style="color: #a11;">"Zara Ali"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">strcpy</span><span style="color: #008000;">(</span> Book2.<span style="color: #007788;">subject</span>, <span style="color: #a11;">"Telecom Billing Tutorial"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   Book2.<span style="color: #007788;">book_id</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">6495700</span><span style="color: #008080;">;</span><br/>
 <br/>
   <span style="color: #696969;; font-style: italic;">/* 通过传 Book1 的地址来输出 Book1 信息 */</span><br/>
   printBook<span style="color: #008000;">(</span> <span style="color: #000040;">&amp;</span>Book1 <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #696969;; font-style: italic;">/* 通过传 Book2 的地址来输出 Book2 信息 */</span><br/>
   printBook<span style="color: #008000;">(</span> <span style="color: #000040;">&amp;</span>Book2 <span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
   <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<span style="color: #05a;">void</span> printBook<span style="color: #008000;">(</span> <span style="color: #05a;">struct</span> Books <span style="color: #000040;">*</span>book <span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book title : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>title<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book author : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>author<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book subject : %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>subject<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
   <span style="color: #05a;">printf</span><span style="color: #008000;">(</span> <span style="color: #a11;">"Book book_id : %d<span style="color: #000099; font-weight: bold;">\n</span>"</span>, book<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>book_id<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Book title : C Programming&#13;
Book author : Nuha Ali&#13;
Book subject : C Programming Tutorial&#13;
Book book_id : 6495407&#13;
Book title : Telecom Billing&#13;
Book author : Zara Ali&#13;
Book subject : Telecom Billing Tutorial&#13;
Book book_id : 6495700&#13;
</pre>&#13;
&#13;
<h2>结构体大小的计算</h2><p>&#13;
C 语言中，我们可以使用 <strong>sizeof</strong> 运算符来计算结构体的大小，<strong>sizeof</strong> 返回的是给定类型或变量的字节大小。</p>&#13;
<p>对于结构体，<strong>sizeof</strong> 将返回结构体的总字节数，包括所有成员变量的大小以及可能的填充字节。</p>&#13;
<p>&#13;
以下实例演示了如何计算结构体的大小：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">struct</span> Person <span style="color: #000;">{</span><br/>
    <span style="color: #993333;">char</span> name<span style="color: #000;">[</span><span style="color: #164;">20</span><span style="color: #000;">]</span><span style="color: #339933;">;</span><br/>
    <span style="color: #993333;">int</span> age<span style="color: #339933;">;</span><br/>
    <span style="color: #993333;">float</span> height<span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #993333;">struct</span> Person person<span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"结构体 Person 大小为: %zu 字节<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #993333;">sizeof</span><span style="color: #000;">(</span>person<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>&#13;
以上实例中，我们定义了一个名为 <strong>Person</strong> 的结构体，它包含了一个字符数组 <strong>name</strong>、一个整数 <strong>age</strong> 和一个浮点数 <strong>height</strong>。</p>&#13;
<p>在 <strong>main</strong> 函数中，我们声明了一个 <strong>Person</strong> 类型的变量 <strong>person</strong>，然后使用 <strong>sizeof</strong> 运算符来获取 <strong>person</strong> 结构体的大小。</p><p>&#13;
最后，我们使用 <strong>printf</strong> 函数打印出结构体的大小，输出结果如下：</p>&#13;
<pre>结构体 Person 大小为: 28 字节</pre>&#13;
<p><strong>注意</strong>，结构体的大小可能会受到编译器的优化和对齐规则的影响，编译器可能会在结构体中插入一些额外的填充字节以对齐结构体的成员变量，以提高内存访问效率。因此，结构体的实际大小可能会大于成员变量大小的总和，如果你需要确切地了解结构体的内存布局和对齐方式，可以使用 <span class="marked">offsetof</span> 宏和 <span class="marked">__attribute__((packed))</span> 属性等进一步控制和查询结构体的大小和对齐方式。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>