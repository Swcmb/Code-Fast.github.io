<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <exception></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;exception&gt;</code></h1>&#13;
&#13;
<p>在 C++ 编程中，异常处理是一种重要的错误处理机制，它允许程序在遇到错误时，能够优雅地处理这些错误，而不是让程序崩溃。</p>&#13;
<p>在 C++ 中，异常处理通常使用 try、catch 和 throw 关键字来实现。标准库中提供了 std::exception 类及其派生类来处理异常。</p>&#13;
<p>C++ 标准库中的 <code>&lt;exception&gt;</code> 头文件提供了一套异常处理的基础设施，包括异常类、异常处理机制等。</p>&#13;
&#13;
<p>异常是程序运行时发生的一个事件，它中断了正常的指令流程。在C++中，异常可以是任何类型的对象，但通常是一个异常类的对象。C++标准库定义了一些基本的异常类，如 <code>std::exception</code>、<code>std::bad_alloc</code>、<code>std::bad_cast</code> 等。</p>&#13;
<p>&#13;
你可以通过定义自己的异常类来扩展异常处理功能，或者使用标准库中已有的异常类来处理常见的异常情况。</p>&#13;
<h3>语法</h3>&#13;
<p><strong>抛出异常</strong></p><p>&#13;
在 C++ 中，使用 throw 关键字来抛出一个异常，语法如下：</p>&#13;
<pre>&#13;
throw exception_object;</pre>&#13;
<p><strong>捕获异常</strong></p><p>&#13;
使用 try 和 catch 关键字来捕获和处理异常，语法如下：</p>&#13;
&#13;
<pre>try {&#13;
    // 可能抛出异常的代码&#13;
} catch (exception_type e) {&#13;
    // 处理异常的代码&#13;
}</pre><p>&#13;
可以指定捕获的异常类型，也可以使用通用的 catch 块捕获所有类型的异常:</p>&#13;
<pre>try {&#13;
    // 可能会抛出异常的代码&#13;
} catch (const std::exception&amp; e) {&#13;
    // 处理 std::exception 及其派生类的异常&#13;
} catch (...) {&#13;
    // 处理所有其他类型的异常&#13;
}</pre>&#13;
<p>&#13;
<strong>std::exception</strong></p><p> std::exception 是 C++ 标准库中定义的基类，用于所有标准异常类的基础。它定义了一些虚函数，如 what()，用于返回异常信息的 C 风格字符串。</p>&#13;
<pre>&#13;
class exception {&#13;
public:&#13;
    virtual const char* what() const noexcept;&#13;
};</pre>&#13;
<p><strong>标准异常类</strong></p><p>C++ 标准库提供了多个派生自 std::exception 的异常类，如 std::runtime_error、std::logic_error 等，用于表示常见的异常情况。你可以根据具体的异常情况选择合适的类来使用。</p>&#13;
<pre>&#13;
throw std::runtime_error("Runtime error occurred");&#13;
throw std::logic_error("Logic error occurred");</pre>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;exception&gt;</code> 头文件的简单示例，演示了如何抛出和捕获异常。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;exception&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> MyException <span style="color: #008080;">:</span> <span style="color: #05a;">public</span> std<span style="color: #008080;">::</span><span style="color: #007788;">exception</span> <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">const</span> <span style="color: #05a;">char</span><span style="color: #000040;">*</span> what<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #05a;">const</span> <span style="color: #05a;">throw</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">return</span> <span style="color: #a11;">"My custom exception"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #666666;">// 模拟一个错误情况</span><br/>
        <span style="color: #05a;">bool</span> error_condition <span style="color: #000080;">=</span> <span style="color: #05a;">true</span><span style="color: #008080;">;</span><br/>
        <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>error_condition<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
            <span style="color: #05a;">throw</span> MyException<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        <span style="color: #008000;">}</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">exception</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught an exception: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>Caught an exception: My custom exception</pre>&#13;
<h2>异常类</h2>&#13;
<p>在 C++ 中，标准库提供了一些常用的异常类，它们都继承自 <code>std::exception</code>，并且可以通过 <code>#include &lt;stdexcept&gt;</code> 引入使用。</p><p>以下是一些常见的 C++ 异常类及其主要用途：</p>&#13;
&#13;
<ul>&#13;
    <li>&#13;
        <p><strong>std::exception</strong>: 所有标准异常类的基类，定义了异常的基本接口。它有一个虚函数 <code>what()</code>，用于返回异常信息的 C 风格字符串。</p>&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::runtime_error</strong>: 表示运行时错误，通常是由于程序逻辑问题导致的异常，例如无效的参数、无法打开文件等。</p>&#13;
        <pre>throw std::runtime_error("Runtime error occurred");</pre>&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::logic_error</strong>: 表示逻辑错误，通常是由于程序逻辑错误导致的异常，例如逻辑断言失败、索引越界等。</p>&#13;
      <pre> throw std::logic_error("Logic error occurred");</pre>&#13;
&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::invalid_argument</strong>: 表示传递给函数的参数无效。</p>&#13;
       <pre>throw std::invalid_argument("Invalid argument");</pre>&#13;
&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::out_of_range</strong>: 表示访问超出有效范围的对象，如数组、容器等。</p>&#13;
        <pre>throw std::invalid_argument("Invalid argument");&#13;
</pre>&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::overflow_error</strong> 和 <strong>std::underflow_error</strong>: 表示数值计算时出现溢出或下溢。</p>&#13;
        <pre>throw std::out_of_range("Out of range");&#13;
</pre>&#13;
    </li>&#13;
    <li>&#13;
        <p><strong>std::bad_alloc</strong>: 表示内存分配失败。</p>&#13;
        <pre>throw std::overflow_error("Overflow occurred");&#13;
throw std::underflow_error("Underflow occurred");&#13;
</pre>&#13;
    </li>&#13;
</ul>&#13;
<h2>注意事项</h2>&#13;
<ul>&#13;
<li>异常不应该用于正常的控制流，它们应该只用于处理异常情况。</li>&#13;
<li>异常处理可能会影响程序的性能，因此应该谨慎使用。</li>&#13;
<li>确保在 <code>catch</code> 块中处理所有可能的异常类型，以避免程序在未处理的异常中崩溃。</li>&#13;
</ul>&#13;
<p>通过使用 <code>&lt;exception&gt;</code> 头文件，C++ 程序员可以更有效地处理程序中的错误情况，提高程序的健壮性和可靠性。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>