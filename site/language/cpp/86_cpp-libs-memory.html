<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 内存管理库 <memory></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 内存管理库 <code>&lt;memory&gt;</code></h1>&#13;
&#13;
<p><code>&lt;memory&gt;</code> 是 C++ 标准库中的一个头文件，它包含了用于动态内存管理的模板和函数。</p>&#13;
&#13;
<p>在 C++ 中，内存管理是一个重要的概念。动态内存管理允许程序在运行时分配和释放内存，这在处理不确定大小的数据结构时非常有用。然而，不正确的内存管理可能导致内存泄漏、野指针等问题。</p><p><code>&lt;memory&gt;</code> 头文件提供了智能指针等工具，帮助开发者更安全地管理动态内存。</p>&#13;
<h3>智能指针</h3>&#13;
<p>智能指针是 <code>&lt;memory&gt;</code> 头文件中的核心内容。它们是 C++11 引入的特性，用于自动管理动态分配的内存。智能指针的主要类型有：</p>&#13;
<ul>&#13;
<li><code>std::unique_ptr</code>：独占所有权的智能指针，同一时间只能有一个 <code>unique_ptr</code> 指向特定内存。</li>&#13;
<li><code>std::shared_ptr</code>：共享所有权的智能指针，多个 <code>shared_ptr</code> 可以指向同一内存，内存在最后一个 <code>shared_ptr</code> 被销毁时释放。</li>&#13;
<li><code>std::weak_ptr</code>：弱引用智能指针，用于与 <code>shared_ptr</code> 配合使用，避免循环引用导致的内存泄漏。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>使用 <code>std::unique_ptr</code></h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;memory&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> MyClass <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">void</span> doSomething<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Doing something"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">unique_ptr</span><span style="color: #000080;">&lt;</span>MyClass<span style="color: #000080;">&gt;</span> myPtr<span style="color: #008000;">(</span><span style="color: #05a;">new</span> MyClass<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    myPtr<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>doSomething<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用智能指针调用成员函数</span><br/>
<br/>
    <span style="color: #666666;">// 当 main 函数结束时，myPtr 被销毁，自动释放 MyClass 对象的内存</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>Doing something</pre>&#13;
<h3>使用 <code>std::shared_ptr</code></h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;memory&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> MyClass <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">void</span> doSomething<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Doing something"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">shared_ptr</span><span style="color: #000080;">&lt;</span>MyClass<span style="color: #000080;">&gt;</span> myPtr1<span style="color: #008000;">(</span><span style="color: #05a;">new</span> MyClass<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">shared_ptr</span><span style="color: #000080;">&lt;</span>MyClass<span style="color: #000080;">&gt;</span> myPtr2 <span style="color: #000080;">=</span> myPtr1<span style="color: #008080;">;</span><br/>
<br/>
    myPtr1<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>doSomething<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用 myPtr1 调用成员函数</span><br/>
    myPtr2<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>doSomething<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用 myPtr2 调用成员函数</span><br/>
<br/>
    <span style="color: #666666;">// 当 myPtr1 和 myPtr2 都被销毁时，MyClass 对象的内存才会被释放</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>Doing something&#13;
Doing something</pre>&#13;
<h3>使用 <code>std::weak_ptr</code></h3>&#13;
<p><code>std::weak_ptr</code> 通常不单独使用，而是与 <code>std::shared_ptr</code> 结合使用，以解决循环引用问题。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;memory&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> Node <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">shared_ptr</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span> next<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">weak_ptr</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span> prev<span style="color: #008080;">;</span><br/>
<br/>
    Node<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008080;">:</span> next<span style="color: #008000;">(</span>nullptr<span style="color: #008000;">)</span>, prev<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">shared_ptr</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span> node1 <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">make_shared</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">shared_ptr</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span> node2 <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">make_shared</span><span style="color: #000080;">&lt;</span>Node<span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    node1<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>next <span style="color: #000080;">=</span> node2<span style="color: #008080;">;</span><br/>
    node2<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>prev <span style="color: #000080;">=</span> node1<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 循环引用，但使用 weak_ptr 避免了内存泄漏</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>在这个例子中，<code>node1</code> 和 <code>node2</code> 形成了循环引用。由于 <code>prev</code> 是 <code>weak_ptr</code>，当 <code>node1</code> 和 <code>node2</code> 的 <code>shared_ptr</code> 被销毁时，它们指向的内存也会被正确释放。</p>&#13;
&#13;
<h2>分配器</h2><p>&#13;
分配器是 &lt;memory&gt; 中的另一重要部分。</p><p>分配器用于为容器分配内存，标准库的所有容器都使用分配器来处理内存分配。</p>&#13;
&#13;
<h3>std::allocator</h3><p>&#13;
std::allocator 是标准分配器，提供了基本的内存分配和释放功能。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;memory&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">allocator</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> alloc<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span><span style="color: #000040;">*</span> p <span style="color: #000080;">=</span> alloc.<span style="color: #007788;">allocate</span><span style="color: #008000;">(</span><span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 分配内存</span><br/>
    alloc.<span style="color: #007788;">construct</span><span style="color: #008000;">(</span>p, <span style="color: #0000dd;">42</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 构造对象</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #000040;">*</span>p <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    alloc.<span style="color: #007788;">destroy</span><span style="color: #008000;">(</span>p<span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 销毁对象</span><br/>
    alloc.<span style="color: #007788;">deallocate</span><span style="color: #008000;">(</span>p, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 释放内存</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h2>其他内存管理工具</h2><h3>&#13;
std::align</h3><p>&#13;
std::align 用于调整指针的对齐方式，以确保所分配内存满足特定对齐要求。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;memory&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    alignas<span style="color: #008000;">(</span><span style="color: #0000dd;">16</span><span style="color: #008000;">)</span> <span style="color: #05a;">char</span> buffer<span style="color: #008000;">[</span><span style="color: #0000dd;">64</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">void</span><span style="color: #000040;">*</span> p <span style="color: #000080;">=</span> buffer<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">size_t</span> space <span style="color: #000080;">=</span> <span style="color: #05a;">sizeof</span><span style="color: #008000;">(</span>buffer<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">void</span><span style="color: #000040;">*</span> aligned_ptr <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">align</span><span style="color: #008000;">(</span><span style="color: #0000dd;">16</span>, <span style="color: #05a;">sizeof</span><span style="color: #008000;">(</span><span style="color: #05a;">int</span><span style="color: #008000;">)</span>, p, space<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>aligned_ptr<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Memory aligned<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Memory alignment failed<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p><code>&lt;memory&gt;</code> 头文件是 C++ 标准库中处理动态内存管理的重要部分。</p><p>通过使用智能指针，如 <code>unique_ptr</code>、<code>shared_ptr</code> 和 <code>weak_ptr</code>，开发者可以更安全、更有效地管理内存，避免常见的内存管理错误。希望这篇文章能帮助初学者更好地理解和使用 C++ 的 <code>&lt;memory&gt;</code> 头文件。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>