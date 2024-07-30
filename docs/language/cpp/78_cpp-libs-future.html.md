<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <future></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;future&gt;</code></h1>&#13;
&#13;
<p>C++11 引入了 <code>&lt;future&gt;</code> 头文件，它提供了一种异步编程的机制，允许程序在等待某个操作完成时继续执行其他任务。<code>&lt;future&gt;</code> 库是 C++ 标准库中并发编程的一部分，它允许程序员以一种更简洁和安全的方式处理异步操作。</p>&#13;
&#13;
<p><code>&lt;future&gt;</code> 库中定义了几个关键的类型：</p>&#13;
<ul>&#13;
<li><code>std::future</code>：表示异步操作的结果，可以查询操作的状态，获取结果或等待操作完成。</li>&#13;
<li><code>std::promise</code>：用于与 <code>std::future</code> 配对，用于设置异步操作的结果。</li>&#13;
<li><code>std::packaged_task</code>：封装一个函数或可调用对象，使其可以作为异步任务执行。</li>&#13;
</ul>&#13;
&#13;
<h3>std::promise</h3>&#13;
<p><code>std::promise</code> 用于设置异步操作的结果。它与 <code>std::future</code> 配对使用。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">promise</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> prom<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> fut <span style="color: #000080;">=</span> prom.<span style="color: #007788;">get_future</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 在另一个线程中设置结果</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t<span style="color: #008000;">(</span><span style="color: #008000;">[</span>prom<span style="color: #008000;">]</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        prom.<span style="color: #007788;">set_value</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 等待结果</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Future value: "</span> <span style="color: #000080;">&lt;&lt;</span> fut.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    t.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Future value: 10</pre>&#13;
<h3>std::packaged_task</h3>&#13;
<p><code>std::packaged_task</code> 封装一个函数或可调用对象，使其可以作为异步任务执行。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<span style="color: #060;">#include &lt;cmath&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> compute_square_root<span style="color: #008000;">(</span><span style="color: #05a;">double</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">return</span> std<span style="color: #008080;">::</span><span style="color: #05a;">sqrt</span><span style="color: #008000;">(</span>x<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">packaged_task</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">double</span><span style="color: #008000;">(</span><span style="color: #05a;">double</span><span style="color: #008000;">)</span><span style="color: #000080;">&gt;</span> task<span style="color: #008000;">(</span>compute_square_root<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">double</span><span style="color: #000080;">&gt;</span> result <span style="color: #000080;">=</span> task.<span style="color: #007788;">get_future</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> th<span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">move</span><span style="color: #008000;">(</span>task<span style="color: #008000;">)</span>, <span style="color:#800080;">9.0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Result: "</span> <span style="color: #000080;">&lt;&lt;</span> result.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    th.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Result: 3</pre>&#13;
<h3>std::async</h3>&#13;
<p><code>std::async</code> 是一个方便的函数，用于启动异步任务。它可以立即返回一个 <code>std::future</code> 对象。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> fut <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">async</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">launch</span><span style="color: #008080;">::</span><span style="color: #007788;">async</span>, <span style="color: #008000;">[</span><span style="color: #008000;">]</span><span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">return</span> x <span style="color: #000040;">*</span> x<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Result: "</span> <span style="color: #000080;">&lt;&lt;</span> fut.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Result: 25</pre>&#13;
<h2>异常处理</h2>&#13;
<p>当异步操作抛出异常时，<code>std::future</code> 会捕获这个异常，并且可以通过调用 <code>.get()</code> 方法来重新抛出它。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> throw_exception<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">throw</span> std<span style="color: #008080;">::</span><span style="color: #007788;">runtime_error</span><span style="color: #008000;">(</span><span style="color: #a11;">"Exception thrown"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">void</span><span style="color: #000080;">&gt;</span> fut <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">async</span><span style="color: #008000;">(</span>throw_exception<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">try</span> <span style="color: #008000;">{</span><br/>
        fut.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">catch</span> <span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">exception</span><span style="color: #000040;">&amp;</span> e<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Caught exception: "</span> <span style="color: #000080;">&lt;&lt;</span> e.<span style="color: #007788;">what</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Caught exception: Exception thrown</pre>&#13;
<p><code>&lt;future&gt;</code> 库为 C++ 程序员提供了一种简单而强大的异步编程方式。通过使用 <code>std::promise</code>、<code>std::packaged_task</code> 和 <code>std::async</code>，我们可以轻松地在 C++ 程序中实现并发和异步操作。同时，异常处理机制也确保了程序的健壮性。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>