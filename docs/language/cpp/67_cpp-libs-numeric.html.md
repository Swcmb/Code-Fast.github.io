<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <numeric></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;numeric&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;numeric&gt;</code> 头文件提供了一组用于数值计算的函数模板，这些函数可以对容器中的元素进行各种数值操作，如求和、乘积、最小值、最大值等。这些函数模板非常强大，可以应用于任何类型的容器，包括数组、向量、列表等。</p>&#13;
&#13;
<p>在使用 <code>&lt;numeric&gt;</code> 头文件中的函数之前，需要在你的 C++ 程序中包含这个头文件：</p>&#13;
<pre>#include &lt;numeric&gt;</pre>&#13;
<h2>常用函数</h2>&#13;
<h3>1. <code>accumulate</code></h3>&#13;
<p><code>accumulate</code> 函数用于计算容器中所有元素的总和。它接受三个参数：容器的开始迭代器、结束迭代器和初始值。</p>&#13;
<p><strong>语法</strong>:</p>&#13;
<pre>template &lt;InputIterator Iter, class T&gt;&#13;
T accumulate(Iter first, Iter last, T init);</pre>&#13;
<p><strong>实例</strong>:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> sum <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">accumulate</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Sum: "</span> <span style="color: #000080;">&lt;&lt;</span> sum <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: Sum: 15</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>2. <code>inner_product</code></h3>&#13;
<p><code>inner_product</code> 函数用于计算两个容器中对应元素乘积的总和。</p>&#13;
<p><strong>语法</strong>:</p>&#13;
<pre>template &lt;InputIterator1 Iter1, InputIterator2 Iter2, class T&gt;&#13;
T inner_product(Iter1 first1, Iter1 last1, Iter2 first2, T init);</pre>&#13;
<p><strong>实例</strong>:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v1 <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v2 <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span>, <span style="color: #0000dd;">6</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> product_sum <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">inner_product</span><span style="color: #008000;">(</span>v1.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v1.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v2.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Product Sum: "</span> <span style="color: #000080;">&lt;&lt;</span> product_sum <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: Product Sum: 32</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>3. <code>partial_sum</code></h3>&#13;
<p><code>partial_sum</code> 函数用于计算容器中元素的部分和，并将结果存储在另一个容器中。</p>&#13;
<p><strong>语法</strong>:</p>&#13;
<pre>template &lt;InputIterator InIter, OutputIterator OutIter&gt;&#13;
OutIter partial_sum(InIter first, InIter last, OutIter result);</pre>&#13;
<p><strong>实例</strong>:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> result<span style="color: #008000;">(</span>v.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">partial_sum</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, result.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #008080;">:</span> result<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 1 3 6 10</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>4. <code>adjacent_difference</code></h3>&#13;
<p><code>adjacent_difference</code> 函数用于计算容器中相邻元素的差值，并将结果存储在另一个容器中。</p>&#13;
<p><strong>语法</strong>:</p>&#13;
<pre>template &lt;InputIterator InIter, OutputIterator OutIter&gt;&#13;
OutIter adjacent_difference(InIter first, InIter last, OutIter result);</pre>&#13;
<p><strong>实例</strong>:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> result<span style="color: #008000;">(</span>v.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000040;">-</span> <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">adjacent_difference</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, result.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #008080;">:</span> result<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 1 1 1</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>5. std::gcd</h3>&#13;
<p>使用 std::gcd 计算两个整数的最大公约数：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">48</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">18</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> result <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">gcd</span><span style="color: #008000;">(</span>a, b<span style="color: #008000;">)</span><span style="color: #008080;">;</span>  <span style="color: #666666;">// 计算 48 和 18 的最大公约数</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"GCD: "</span> <span style="color: #000080;">&lt;&lt;</span> result <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span>  <span style="color: #666666;">// 输出 6</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>6. std::lcm</h3>&#13;
<p>使用 std::lcm 计算两个整数的最小公倍数：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">48</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">18</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> result <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">lcm</span><span style="color: #008000;">(</span>a, b<span style="color: #008000;">)</span><span style="color: #008080;">;</span>  <span style="color: #666666;">// 计算 48 和 18 的最小公倍数</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"LCM: "</span> <span style="color: #000080;">&lt;&lt;</span> result <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span>  <span style="color: #666666;">// 输出 144</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>7. std::iota</h3>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;  // 包含 numeric 头文件</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v<span style="color: #008000;">(</span><span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 创建一个包含5个元素的向量</span><br/>
<br/>
    <span style="color: #666666;">// 使用 std::iota 填充向量，起始值为1</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">iota</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">begin</span><span style="color: #008000;">(</span>v<span style="color: #008000;">)</span>, std<span style="color: #008080;">::</span><span style="color: #007788;">end</span><span style="color: #008000;">(</span>v<span style="color: #008000;">)</span>, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出填充后的向量</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #008080;">:</span> v<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 1 2 3 4 5</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>&#13;
使用 std::iota 填充范围内的序列值。</p>&#13;
<pre>template&lt;class ForwardIt, class T&gt;&#13;
void iota(ForwardIt first, ForwardIt last, T value);</pre>&#13;
<h3>8.查找最大值与最小值</h3>&#13;
<p><code>min_element</code> 和 <code>max_element</code> 函数用于找到容器中的最大值和最小值。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;numeric&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;algorithm&gt; // 为了使用 std::min_element 和 std::max_element</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 定义一个包含整数的向量</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">5</span>, <span style="color: #0000dd;">9</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 计算最小值和最大值</span><br/>
    <span style="color: #05a;">int</span> min_val <span style="color: #000080;">=</span> <span style="color: #000040;">*</span>std<span style="color: #008080;">::</span><span style="color: #007788;">min_element</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> max_val <span style="color: #000080;">=</span> <span style="color: #000040;">*</span>std<span style="color: #008080;">::</span><span style="color: #007788;">max_element</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 计算总和</span><br/>
    <span style="color: #05a;">int</span> sum_val <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">accumulate</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 计算平均值</span><br/>
    <span style="color: #05a;">double</span> avg_val <span style="color: #000080;">=</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">double</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>sum_val<span style="color: #008000;">)</span> <span style="color: #000040;">/</span> v.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出结果</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Min: "</span> <span style="color: #000080;">&lt;&lt;</span> min_val <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Max: "</span> <span style="color: #000080;">&lt;&lt;</span> max_val <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Sum: "</span> <span style="color: #000080;">&lt;&lt;</span> sum_val <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Average: "</span> <span style="color: #000080;">&lt;&lt;</span> avg_val <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><p>输出结果为：</p>&#13;
<pre>Min: 1&#13;
Max: 9&#13;
Sum: 23&#13;
Average: 3.83333</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>