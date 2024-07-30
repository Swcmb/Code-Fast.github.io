<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <functional></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;functional&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;functional&gt;</code> 头文件提供了一组函数模板，这些模板允许我们使用函数对象（function objects）作为参数传递给算法，或者作为算法的返回值。函数对象是那些重载了 <code>operator()</code> 的对象，它们可以像普通函数一样被调用。</p>&#13;
&#13;
<p>在 C++ 中，函数对象是一种特殊的类，它重载了 <code>operator()</code> 来允许对象像函数一样被调用。这使得我们可以将行为作为对象传递，增加了代码的灵活性和可重用性。</p>&#13;
<h2>语法</h2>&#13;
<p>要使用 <code>&lt;functional&gt;</code> 头文件中的功能，你需要在你的 C++ 程序中包含这个头文件：</p>&#13;
<pre>#include &lt;functional&gt;</pre>&#13;
<h2>常用函数对象</h2>&#13;
<p><code>&lt;functional&gt;</code> 头文件中定义了一些常用的函数对象，包括：</p>&#13;
<ul>&#13;
<li><code>std::function</code>：一个通用的多态函数封装器。</li>&#13;
<li><code>std::bind</code>：用于绑定函数的参数。</li>&#13;
<li><code>std::plus</code>、<code>std::minus</code>、<code>std::multiplies</code>、<code>std::divides</code>、<code>std::modulus</code>：基本的算术操作。</li>&#13;
<li><code>std::equal_to</code>、<code>std::not_equal_to</code>、<code>std::greater</code>、<code>std::less</code>、<code>std::greater_equal</code>、<code>std::less_equal</code>：比较操作。</li>&#13;
<li><code>std::unary_negate</code>、<code>std::binary_negate</code>：逻辑否定操作。</li>&#13;
<li><code>std::logical_and</code>、<code>std::logical_or</code>、<code>std::logical_not</code>：逻辑操作。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>使用 <code>std::function</code></h3>&#13;
<p><code>std::function</code> 是一个模板类，可以存储、调用和复制任何可调用对象，比如函数、lambda 表达式或函数对象。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;functional&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> greet<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello, World!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">function</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">void</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #000080;">&gt;</span> f <span style="color: #000080;">=</span> greet<span style="color: #008080;">;</span> <span style="color: #666666;">// 使用函数</span><br/>
    f<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: Hello, World!</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">function</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">void</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #000080;">&gt;</span> lambda <span style="color: #000080;">=</span> <span style="color: #008000;">[</span><span style="color: #008000;">]</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello, Lambda!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    lambda<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: Hello, Lambda!</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>使用 <code>std::bind</code></h3>&#13;
<p><code>std::bind</code> 允许我们创建一个可调用对象，它在调用时会将给定的参数绑定到一个函数或函数对象。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;functional&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> add<span style="color: #008000;">(</span><span style="color: #05a;">int</span> a, <span style="color: #05a;">int</span> b<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">return</span> a <span style="color: #000040;">+</span> b<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">auto</span> bound_add <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">bind</span><span style="color: #008000;">(</span>add, <span style="color: #0000dd;">5</span>, std<span style="color: #008080;">::</span><span style="color: #007788;">placeholders</span><span style="color: #008080;">::</span>_1<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> bound_add<span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 15</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>在这个例子中，<code>std::placeholders::_1</code> 是一个占位符，它在调用 <code>bound_add</code> 时会被实际的参数替换。</p>&#13;
<h3>使用比较函数对象</h3>&#13;
<p>比较函数对象可以用于算法，比如 <code>std::sort</code>。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;algorithm&gt;</span><br/>
<span style="color: #060;">#include &lt;functional&gt;</span><br/>
<br/>
<span style="color: #05a;">bool</span> compare<span style="color: #008000;">(</span><span style="color: #05a;">int</span> a, <span style="color: #05a;">int</span> b<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">return</span> a <span style="color: #000080;">&lt;</span> b<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">5</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">9</span>, <span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">4</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">sort</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, compare<span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用自定义比较函数</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #008080;">:</span> v<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 1 3 4 5 9</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">sort</span><span style="color: #008000;">(</span>v.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, std<span style="color: #008080;">::</span><span style="color: #007788;">less</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 使用标准库比较函数对象</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #008080;">:</span> v<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> i <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出: 1 3 4 5 9</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><code>&lt;functional&gt;</code> 头文件是 C++ 标准库中一个非常强大的部分，它提供了丰富的函数对象和工具，使得我们可以编写更灵活、更可重用的代码。通过使用函数对象，我们可以将行为作为参数传递，或者将它们存储在容器中，从而实现更高级的编程技术。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>