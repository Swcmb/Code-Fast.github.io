<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 异常处理库  <stdexcept></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 异常处理库  &lt;stdexcept&gt;</h1>&#13;
<p><code>&lt;stdexcept&gt;</code> 是 C++ 标准库中的一个头文件，它定义了一组标准异常类，用于处理程序运行时的错误情况。</p>&#13;
&#13;
<p>异常是程序运行时发生的错误，它们可以被捕获并处理，以避免程序的非正常终止。<code>&lt;stdexcept&gt;</code> 头文件定义了一组从 <code>std::exception</code> 派生的异常类，这些类提供了一种标准的方式来报告和处理错误。</p>&#13;
<h3>语法</h3>&#13;
<p>要使用 <code>&lt;stdexcept&gt;</code> 中的异常类，首先需要包含这个头文件：</p>&#13;
<pre>#include &lt;stdexcept&gt;</pre>&#13;
<p>然后，你可以使用这些异常类来抛出和捕获异常。例如：</p>&#13;
<pre>throw std::runtime_error("An error occurred");</pre>&#13;
<h3>异常类</h3>&#13;
<p><code>&lt;stdexcept&gt;</code> 头文件定义了以下异常类：</p>&#13;
<ul>&#13;
<li><code>std::exception</code>：所有标准异常类的基类。</li>&#13;
<li><code>std::bad_exception</code>：当异常处理过程中发生错误时抛出。</li>&#13;
<li><code>std::bad_alloc</code>：当内存分配失败时抛出。</li>&#13;
<li><code>std::bad_cast</code>：当类型转换失败时抛出。</li>&#13;
<li><code>std::bad_typeid</code>：当 <code>typeid</code> 操作失败时抛出。</li>&#13;
<li><code>std::logic_error</code>：当逻辑错误发生时抛出，例如无效的输入参数。</li>&#13;
<li><code>std::domain_error</code>：当函数调用的参数不在有效范围内时抛出。</li>&#13;
<li><code>std::invalid_argument</code>：当函数调用的参数无效时抛出。</li>&#13;
<li><code>std::length_error</code>：当容器操作因为长度限制而失败时抛出。</li>&#13;
<li><code>std::out_of_range</code>：当访问容器的非法索引时抛出。</li>&#13;
<li><code>std::overflow_error</code>：当算术运算导致溢出时抛出。</li>&#13;
<li><code>std::range_error</code>：当函数返回值不在期望的范围内时抛出。</li>&#13;
<li><code>std::underflow_error</code>：当算术运算导致下溢时抛出。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;stdexcept&gt;</code> 的简单示例，演示了如何抛出和捕获异常：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> riskyFunction<span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>x <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">invalid_argument</span><span style="color: #008000;">(</span><span style="color: #a11;">"Negative value not allowed"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Processing "</span> <span style="color: #000080;">&lt;&lt;</span> x <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        riskyFunction<span style="color: #008000;">(</span><span style="color: #000040;">-</span><span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">invalid_argument</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cerr</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught an exception: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><p>&#13;
输出结果:</p><pre>&#13;
Caught an exception: Negative value not allowed</pre>&#13;
<p>在这个示例中，<code>riskyFunction</code> 函数检查传入的参数是否为负数，如果是，则抛出 <code>std::invalid_argument</code> 异常。在 <code>main</code> 函数中，我们使用 <code>try-catch</code> 块来捕获并处理这个异常。</p>&#13;
<hr/>&#13;
<h2>&#13;
标准异常类</h2><h3>&#13;
std::exception</h3><p>&#13;
std::exception 是所有标准异常类的基类。它提供了一个虚函数 what()，用于返回描述异常的字符串。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;exception&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">exception</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">exception</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught exception: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::logic_error</h3><p>&#13;
std::logic_error 派生自 std::exception，表示程序逻辑错误。它是一个抽象基类，通常由派生类来具体化。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">logic_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Logic error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">logic_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught logic error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::invalid_argument</h3><p>&#13;
std::invalid_argument 派生自 std::logic_error，表示传递了无效的参数。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">invalid_argument</span><span style="color: #008000;">(</span><span style="color: #a11;">"Invalid argument provided"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">invalid_argument</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught invalid argument: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::domain_error</h3><p>&#13;
std::domain_error 派生自 std::logic_error，表示参数超出了有效范围。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">domain_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Domain error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">domain_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught domain error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::length_error</h3><p>&#13;
std::length_error 派生自 std::logic_error，表示长度错误，如在容器操作中超出了最大长度限制。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">length_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Length error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">length_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught length error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::out_of_range</h3><p>&#13;
std::out_of_range 派生自 std::logic_error，表示访问超出了有效范围。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">out_of_range</span><span style="color: #008000;">(</span><span style="color: #a11;">"Out of range error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">out_of_range</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught out of range error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::runtime_error</h3><p>&#13;
std::runtime_error 派生自 std::exception，表示程序运行时错误。它是一个抽象基类，通常由派生类来具体化。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">runtime_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Runtime error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">runtime_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught runtime error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::range_error</h3><p>&#13;
std::range_error 派生自 std::runtime_error，表示计算结果超出了表示范围。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">range_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Range error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">range_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught range error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::overflow_error</h3><p>&#13;
std::overflow_error 派生自 std::runtime_error，表示算术溢出错误。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">overflow_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Overflow error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">overflow_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught overflow error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
std::underflow_error</h3><p>&#13;
std::underflow_error 派生自 std::runtime_error，表示算术下溢错误。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">underflow_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Underflow error occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">underflow_error</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught underflow error: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><h3>&#13;
使用自定义异常类</h3><p>&#13;
除了标准异常类，我们还可以定义自己的异常类，继承自标准异常类。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;stdexcept&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> MyException <span style="color: #008080;">:</span> <span style="color: #05a;">public</span> std<span style="color: #008080;">::</span><span style="color: #007788;">runtime_error</span> <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    MyException<span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">string</span><span style="color: #000040;">&amp;</span> message<span style="color: #008000;">)</span> <span style="color: #008080;">:</span> std<span style="color: #008080;">::</span><span style="color: #007788;">runtime_error</span><span style="color: #008000;">(</span>message<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">throw</span> MyException<span style="color: #008000;">(</span><span style="color: #a11;">"My custom exception occurred"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> MyException<span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught custom exception: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p><code>&lt;stdexcept&gt;</code> 是 C++ 标准库中一个重要的组成部分，它提供了一组标准异常类，使得错误处理更加一致和可预测。通过使用这些异常类，你可以编写更加健壮和易于维护的代码。对于初学者来说，理解异常的基本概念和如何使用 <code>&lt;stdexcept&gt;</code> 中的异常类是非常重要的。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>