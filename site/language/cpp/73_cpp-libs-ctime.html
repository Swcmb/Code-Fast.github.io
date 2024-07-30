<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <ctime></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;ctime&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库提供了丰富的功能，其中 <code>&lt;ctime&gt;</code> 是处理时间和日期的标准库之一。它提供了一组函数，用于获取当前时间、日期以及执行时间相关的计算。</p>&#13;
&#13;
<p><code>&lt;ctime&gt;</code> 库定义了一组与时间相关的函数和类型，这些函数和类型允许程序员在程序中处理时间。它包括：</p>&#13;
<ul>&#13;
<li><code>time_t</code>：表示时间的类型，通常是一个长整型。</li>&#13;
<li><code>tm</code>：一个结构体，用于表示时间的各个部分，如年、月、日、小时等。</li>&#13;
<li>一系列函数，如 <code>time()</code>, <code>localtime()</code>, <code>gmtime()</code>, <code>strftime()</code> 等。</li>&#13;
</ul>&#13;
<h2>语法</h2>&#13;
<p>以下是 <code>&lt;ctime&gt;</code> 库中一些常用函数的基本语法：</p>&#13;
<ul>&#13;
<li>&#13;
<p>获取当前时间（以秒为单位，从1970年1月1日开始计算）：</p>&#13;
<pre>time_t t = time(NULL);</pre>&#13;
</li>&#13;
<li>&#13;
<p>将 <code>time_t</code> 类型的时间转换为 <code>tm</code> 结构体：</p>&#13;
<pre>struct tm *tm = localtime(&amp;t);</pre>&#13;
</li>&#13;
<li>&#13;
<p>将 <code>time_t</code> 类型的时间转换为协调世界时（UTC）的 <code>tm</code> 结构体：</p>&#13;
<pre>struct tm *tm_utc = gmtime(&amp;t);</pre>&#13;
</li>&#13;
<li>&#13;
<p>格式化时间：</p>&#13;
<pre>char buffer[80];&#13;
strftime(buffer, 80, "%Y-%m-%d %H:%M:%S", tm);</pre>&#13;
</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;ctime&gt;</code> 库的简单示例，展示如何获取当前时间并格式化输出。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;ctime&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<span style="color: #060;">#include &lt;sstream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 获取当前时间</span><br/>
    <span style="color: #05a;">time_t</span> now <span style="color: #000080;">=</span> <span style="color: #05a;">time</span><span style="color: #008000;">(</span><span style="color: #05a;">NULL</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 将当前时间转换为本地时间</span><br/>
    <span style="color: #05a;">struct</span> <span style="color: #05a;">tm</span> <span style="color: #000040;">*</span>local_tm <span style="color: #000080;">=</span> <span style="color: #05a;">localtime</span><span style="color: #008000;">(</span><span style="color: #000040;">&amp;</span>now<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 使用 strftime 格式化时间</span><br/>
    <span style="color: #05a;">char</span> buffer<span style="color: #008000;">[</span><span style="color: #0000dd;">80</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">strftime</span><span style="color: #008000;">(</span>buffer, <span style="color: #0000dd;">80</span>, <span style="color: #a11;">"%Y-%m-%d %H:%M:%S"</span>, local_tm<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出当前时间</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Current local time: "</span> <span style="color: #000080;">&lt;&lt;</span> buffer <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 将当前时间转换为UTC时间</span><br/>
    <span style="color: #05a;">struct</span> <span style="color: #05a;">tm</span> <span style="color: #000040;">*</span>utc_tm <span style="color: #000080;">=</span> <span style="color: #05a;">gmtime</span><span style="color: #008000;">(</span><span style="color: #000040;">&amp;</span>now<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 格式化UTC时间</span><br/>
    <span style="color: #05a;">strftime</span><span style="color: #008000;">(</span>buffer, <span style="color: #0000dd;">80</span>, <span style="color: #a11;">"%Y-%m-%d %H:%M:%S"</span>, utc_tm<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出UTC时间</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Current UTC time: "</span> <span style="color: #000080;">&lt;&lt;</span> buffer <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>运行上述程序，你将看到类似以下的输出（具体时间取决于你运行程序的时间）：</p>&#13;
<pre>&#13;
Current local time: 2023-04-01 12:34:56&#13;
Current UTC time: 2023-04-01 12:34:56</pre>&#13;
<p>请注意，由于时区差异，本地时间和UTC时间可能相同，也可能不同。</p>&#13;
&#13;
<p><code>&lt;ctime&gt;</code> 库是 C++ 中处理时间和日期的重要工具。通过上述示例，我们可以看到如何使用 <code>&lt;ctime&gt;</code> 库来获取和格式化当前时间。这在开发需要时间信息的应用程序时非常有用，例如日志记录、定时任务等。希望这篇文章能帮助初学者更好地理解和使用 <code>&lt;ctime&gt;</code> 库。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>