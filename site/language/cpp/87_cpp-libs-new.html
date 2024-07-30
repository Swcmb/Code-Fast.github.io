<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 内存管理库 <new></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 内存管理库 <code>&lt;new&gt;</code></h1>&#13;
&#13;
<p>C++ 是一种功能强大的编程语言，它提供了丰富的标准库来帮助开发者更高效地编写代码。</p><p>在 C++ 中，<code>&lt;new&gt;</code> 是一个非常重要的头文件，它包含了用于动态内存分配的函数和异常类型。</p><p>动态内存分配允许程序在运行时请求内存，这在处理不确定大小的数据结构时非常有用。</p>&#13;
&#13;
<p><code>&lt;new&gt;</code> 头文件定义了以下几个关键组件：</p>&#13;
<ul>&#13;
<li><code>new</code> 运算符：用于动态分配内存。</li>&#13;
<li><code>delete</code> 运算符：用于释放动态分配的内存。</li>&#13;
<li><code>nothrow</code> 运算符：用于在内存分配失败时不抛出异常。</li>&#13;
<li><code>std::bad_alloc</code> 异常：当内存分配失败时抛出。</li>&#13;
</ul>&#13;
<h2>语法</h2>&#13;
<h3>使用 <code>new</code> 运算符</h3>&#13;
<p><code>new</code> 运算符用于在堆上分配内存。其基本语法如下：</p>&#13;
<pre>&lt;code class="language-cpp"&gt;pointer new (type [, initializer]);&lt;/code&gt;</pre>&#13;
<ul>&#13;
<li><code>pointer</code> 是指向分配的内存的指针。</li>&#13;
<li><code>type</code> 是要分配的对象的类型。</li>&#13;
<li><code>initializer</code> 是一个可选的初始化表达式。</li>&#13;
</ul>&#13;
<h3>使用 <code>delete</code> 运算符</h3>&#13;
<p><code>delete</code> 运算符用于释放之前使用 <code>new</code> 分配的内存。其基本语法如下：</p>&#13;
<pre>&lt;code class="language-cpp"&gt;delete pointer;&lt;/code&gt;</pre>&#13;
<ul>&#13;
<li><code>pointer</code> 是之前使用 <code>new</code> 分配的内存的指针。</li>&#13;
</ul>&#13;
<h2>实例</h2><p>&#13;
动态分配单个对象:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;new&gt; // 包含 &lt;new&gt; 头文件</span><br/>
<br/>
<span style="color: #05a;">class</span> MyClass <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">int</span> value<span style="color: #008080;">;</span><br/>
    MyClass<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008080;">:</span> value<span style="color: #008000;">(</span><span style="color: #0000dd;">0</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    MyClass<span style="color: #000040;">*</span> myObject <span style="color: #000080;">=</span> <span style="color: #05a;">new</span> MyClass<span style="color: #008080;">;</span> <span style="color: #666666;">// 分配一个 MyClass 对象</span><br/>
    myObject<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>value <span style="color: #000080;">=</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用点操作符访问成员</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Value: "</span> <span style="color: #000080;">&lt;&lt;</span> myObject<span style="color: #000040;">-</span><span style="color: #000080;">&gt;</span>value <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">delete</span> myObject<span style="color: #008080;">;</span> <span style="color: #666666;">// 释放内存</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Value: 10</pre>&#13;
<p>动态分配数组:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;new&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span><span style="color: #000040;">*</span> myArray <span style="color: #000080;">=</span> <span style="color: #05a;">new</span> <span style="color: #05a;">int</span><span style="color: #008000;">[</span><span style="color: #0000dd;">10</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 分配一个包含10个整数的数组</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        myArray<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">=</span> i <span style="color: #000040;">*</span> <span style="color: #0000dd;">2</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 初始化数组</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Array["</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"]: "</span> <span style="color: #000080;">&lt;&lt;</span> myArray<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">delete</span><span style="color: #008000;">[</span><span style="color: #008000;">]</span> myArray<span style="color: #008080;">;</span> <span style="color: #666666;">// 释放数组内存</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
&#13;
<pre>Array[0]: 0&#13;
Array[1]: 2&#13;
Array[2]: 4&#13;
Array[3]: 6&#13;
Array[4]: 8&#13;
Array[5]: 10&#13;
Array[6]: 12&#13;
Array[7]: 14&#13;
Array[8]: 16&#13;
Array[9]: 18</pre><p>&#13;
使用 nothrow 避免异常:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;new&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span><span style="color: #000040;">*</span> myArray <span style="color: #000080;">=</span> <span style="color: #05a;">new</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">nothrow</span><span style="color: #008000;">)</span> <span style="color: #05a;">int</span><span style="color: #008000;">[</span><span style="color: #0000dd;">10000000</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 尝试分配一个大数组</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span><span style="color: #000040;">!</span>myArray<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Memory allocation failed."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Memory allocation succeeded."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
        <span style="color: #05a;">delete</span><span style="color: #008000;">[</span><span style="color: #008000;">]</span> myArray<span style="color: #008080;">;</span> <span style="color: #666666;">// 释放内存</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
&#13;
<pre>Memory allocation failed. // 或者 Memory allocation succeeded. 取决于系统内存情况</pre>&#13;
<h3>异常处理</h3><p>&#13;
当使用 new 运算符分配内存失败时，C++ 会抛出一个 std::bad_alloc 异常。</p><p>开发者可以通过 try-catch 块来捕获并处理这个异常。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;new&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">int</span><span style="color: #000040;">*</span> myArray <span style="color: #000080;">=</span> <span style="color: #05a;">new</span> <span style="color: #05a;">int</span><span style="color: #008000;">[</span><span style="color: #0000dd;">10000000</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 尝试分配一个大数组</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Memory allocation succeeded."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
        <span style="color: #05a;">delete</span><span style="color: #008000;">[</span><span style="color: #008000;">]</span> myArray<span style="color: #008080;">;</span> <span style="color: #666666;">// 释放内存</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">bad_alloc</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Exception caught: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Exception caught: std::bad_alloc // 如果内存分配失败</pre>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>