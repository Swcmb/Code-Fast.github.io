<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <deque></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;deque&gt;</code></h1>&#13;
&#13;
<p>在 C++中，<code>&lt;deque&gt;</code> 是标准模板库（STL）的一部分，它提供了双端队列（double-ended queue）的实现。</p><p>双端队列是一种允许在两端进行插入和删除操作的线性数据结构。</p><p><code>&lt;deque&gt;</code> 的全称是 "double-ended queue"，它在C++中以模板类的形式存在，允许存储任意类型的数据。</p>&#13;
&#13;
<p><code>&lt;deque&gt;</code> 是一个动态数组，它提供了快速的随机访问能力，同时允许在两端进行高效的插入和删除操作。这使得 <code>&lt;deque&gt;</code> 成为处理需要频繁插入和删除元素的场景的理想选择。</p>&#13;
<h3>语法</h3>&#13;
<p>在 C++ 中，使用 <code>&lt;deque&gt;</code> 需要包含头文件 <code>#include &lt;deque&gt;</code>。以下是 <code>&lt;deque&gt;</code> 的基本语法：</p>&#13;
<pre>#include &lt;iostream&gt;&#13;
#include &lt;deque&gt;&#13;
&#13;
int main() {&#13;
    std::deque&lt;int&gt; myDeque; // 创建一个整数类型的双端队列&#13;
    // 接下来可以进行插入、删除等操作&#13;
    return 0;&#13;
}</pre>&#13;
<h2>常用操作</h2><p>下面是 std::deque 容器的一些常用成员函数：</p>&#13;
<table class="reference"><thead><tr><th>函数名称</th><th>功能描述</th></tr></thead><tbody><tr><td><code>deque()</code></td><td>默认构造函数，创建一个空的 <code>deque</code> 容器。</td></tr><tr><td><code>deque(size_type n)</code></td><td>创建一个包含 <code>n</code> 个默认值元素的 <code>deque</code> 容器。</td></tr><tr><td><code>deque(size_type n, const T&amp; value)</code></td><td>创建一个包含 <code>n</code> 个值为 <code>value</code> 的 <code>deque</code> 容器。</td></tr><tr><td><code>deque(initializer_list&lt;T&gt; il)</code></td><td>使用初始化列表 <code>il</code> 构造 <code>deque</code> 容器。</td></tr><tr><td><code>operator=</code></td><td>赋值操作符，赋值给 <code>deque</code> 容器。</td></tr><tr><td><code>assign()</code></td><td>用新值替换 <code>deque</code> 容器中的所有元素。</td></tr><tr><td><code>at(size_type pos)</code></td><td>返回 <code>pos</code> 位置的元素，并进行范围检查。</td></tr><tr><td><code>operator[](size_type pos)</code></td><td>返回 <code>pos</code> 位置的元素，不进行范围检查。</td></tr><tr><td><code>front()</code></td><td>返回第一个元素的引用。</td></tr><tr><td><code>back()</code></td><td>返回最后一个元素的引用。</td></tr><tr><td><code>begin()</code></td><td>返回指向第一个元素的迭代器。</td></tr><tr><td><code>end()</code></td><td>返回指向末尾元素后一位置的迭代器。</td></tr><tr><td><code>rbegin()</code></td><td>返回指向最后一个元素的逆向迭代器。</td></tr><tr><td><code>rend()</code></td><td>返回指向第一个元素之前位置的逆向迭代器。</td></tr><tr><td><code>empty()</code></td><td>检查容器是否为空。</td></tr><tr><td><code>size()</code></td><td>返回容器中的元素个数。</td></tr><tr><td><code>max_size()</code></td><td>返回容器可容纳的最大元素个数。</td></tr><tr><td><code>clear()</code></td><td>清除容器中的所有元素。</td></tr><tr><td><code>insert(iterator pos, const T&amp; value)</code></td><td>在 <code>pos</code> 位置插入 <code>value</code> 元素。</td></tr><tr><td><code>erase(iterator pos)</code></td><td>移除 <code>pos</code> 位置的元素。</td></tr><tr><td><code>push_back(const T&amp; value)</code></td><td>在容器末尾添加 <code>value</code> 元素。</td></tr><tr><td><code>pop_back()</code></td><td>移除容器末尾的元素。</td></tr><tr><td><code>push_front(const T&amp; value)</code></td><td>在容器前端添加 <code>value</code> 元素。</td></tr><tr><td><code>pop_front()</code></td><td>移除容器前端的元素。</td></tr><tr><td><code>resize(size_type count)</code></td><td>调整容器大小为 <code>count</code>，多出部分用默认值填充。</td></tr><tr><td><code>swap(deque&amp; other)</code></td><td>交换两个 <code>deque</code> 容器的内容。</td></tr><tr><td><code>get_allocator()</code></td><td>返回一个用于构造双端队列的分配器对象的副本。</td></tr></tbody></table>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;deque&gt;</code> 的简单示例，包括元素的插入、访问和删除操作。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;deque&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">deque</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> myDeque<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 插入元素</span><br/>
    myDeque.<span style="color: #007788;">push_back</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    myDeque.<span style="color: #007788;">push_back</span><span style="color: #008000;">(</span><span style="color: #0000dd;">20</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    myDeque.<span style="color: #007788;">push_front</span><span style="color: #008000;">(</span><span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 访问元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Deque contains: "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> myDeque.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> myDeque<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 删除元素</span><br/>
    myDeque.<span style="color: #007788;">pop_back</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    myDeque.<span style="color: #007788;">pop_front</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 再次访问元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Deque after popping: "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> myDeque.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> myDeque<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果:</p><pre>&#13;
Deque contains: 5 10 20 &#13;
Deque after popping: 10 </pre>&#13;
&#13;
<p>&#13;
在不知道 deque 长度的时候，可以使用 deque.front() 与 deque.back() 来访问头尾元素：</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;deque&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">deque</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> d<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 向双端队列中添加元素</span><br/>
    d.<span style="color: #007788;">push_back</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    d.<span style="color: #007788;">push_back</span><span style="color: #008000;">(</span><span style="color: #0000dd;">20</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    d.<span style="color: #007788;">push_front</span><span style="color: #008000;">(</span><span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 访问前端元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Front element: "</span> <span style="color: #000080;">&lt;&lt;</span> d.<span style="color: #007788;">front</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 访问后端元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Back element: "</span> <span style="color: #000080;">&lt;&lt;</span> d.<span style="color: #007788;">back</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 修改前端元素</span><br/>
    d.<span style="color: #007788;">front</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">15</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 修改后端元素</span><br/>
    d.<span style="color: #007788;">back</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">25</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 再次访问元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Modified front element: "</span> <span style="color: #000080;">&lt;&lt;</span> d.<span style="color: #007788;">front</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Modified back element: "</span> <span style="color: #000080;">&lt;&lt;</span> d.<span style="color: #007788;">back</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><p>输出结果为：</p>&#13;
<pre>Front element: 5&#13;
Back element: 20&#13;
Modified front element: 15&#13;
Modified back element: 25</pre>&#13;
&#13;
<p>&#13;
&#13;
<strong>注意：</strong>在使用 front() 或 back() 之前，确保双端队列不为空，否则会引发未定义的行为。如果需要检查双端队列是否为空，可以使用 empty() 成员函数。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>