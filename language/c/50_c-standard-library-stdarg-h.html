<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <stdarg.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;stdarg.h&gt;</span></h1>&#13;
&#13;
<p><code>&lt;stdarg.h&gt;</code> 是 C 标准库中的一个头文件，提供了一组宏，用于访问可变数量的参数。</p>&#13;
<p><b>stdarg.h</b> 头文件定义了一个变量类型 <b>va_list</b> 和三个宏，这三个宏可用于在参数个数未知（即参数个数可变）时获取函数中的参数。</p>&#13;
<p>可变参数的函数通在参数列表的末尾是使用省略号 <span class="marked">...</span> 定义的。</p>&#13;
&#13;
<h2>库变量</h2>&#13;
<p>下面是头文件 stdarg.h 中定义的变量类型：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">序号</th><th>变量 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>va_list </b><br/>这是一个适用于 <b>va_start()、va_arg()</b> 和 <b>va_end()</b> 这三个宏存储信息的类型。用于存储可变参数信息的类型。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库宏</h2>&#13;
<p>下面是头文件 stdarg.h 中定义的宏：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-macro-va_start.html">void va_start(va_list ap, last_arg)</a><br/>这个宏初始化 <b>ap</b> 变量，它与 <b>va_arg</b> 和 <b>va_end</b> 宏是一起使用的。<b>last_arg</b> 是最后一个传递给函数的已知的固定参数，即省略号之前的参数。</td></tr>&#13;
<tr><td>2</td><td><a href="c-macro-va_arg.html">type va_arg(va_list ap, type)</a><br/>这个宏检索函数参数列表中类型为 <b>type</b> 的下一个参数。</td></tr>&#13;
<tr><td>3</td><td><a href="c-macro-va_end.html">void va_end(va_list ap)</a><br/>这个宏允许使用了 <b>va_start</b> 宏的带有可变参数的函数返回。如果在从函数返回之前没有调用 <b>va_end</b>，则结果为未定义。</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>以下是一个使用 <code>&lt;stdarg.h&gt;</code> 实现可变参数函数的示例。该函数计算所有参数的总和：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;stdarg.h&gt;</span><br/>
<br/>
<span style="color: #666666; font-style: italic;">// 计算可变参数的和</span><br/>
<span style="color: #993333;">int</span> sum<span style="color: #000;">(</span><span style="color: #993333;">int</span> count<span style="color: #339933;">,</span> ...<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #993333;">int</span> total <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
    va_list args<span style="color: #339933;">;</span><br/>
    <br/>
    <span style="color: #666666; font-style: italic;">// 初始化 args 以访问可变参数</span><br/>
    <span style="color: #000066;">va_start</span><span style="color: #000;">(</span>args<span style="color: #339933;">,</span> count<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <br/>
    <span style="color: #666666; font-style: italic;">// 逐个访问可变参数</span><br/>
    <span style="color: #708;">for</span> <span style="color: #000;">(</span><span style="color: #993333;">int</span> i <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span> i <span style="color: #339933;">&lt;</span> count<span style="color: #339933;">;</span> i<span style="color: #339933;">++</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        total <span style="color: #339933;">+=</span> <span style="color: #000066;">va_arg</span><span style="color: #000;">(</span>args<span style="color: #339933;">,</span> <span style="color: #993333;">int</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
    <br/>
    <span style="color: #666666; font-style: italic;">// 清理 args</span><br/>
    <span style="color: #000066;">va_end</span><span style="color: #000;">(</span>args<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <br/>
    <span style="color: #708;">return</span> total<span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Sum of 1, 2, 3: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> sum<span style="color: #000;">(</span><span style="color: #164;">3</span><span style="color: #339933;">,</span> <span style="color: #164;">1</span><span style="color: #339933;">,</span> <span style="color: #164;">2</span><span style="color: #339933;">,</span> <span style="color: #164;">3</span><span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 输出 6</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Sum of 4, 5, 6, 7: %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> sum<span style="color: #000;">(</span><span style="color: #164;">4</span><span style="color: #339933;">,</span> <span style="color: #164;">4</span><span style="color: #339933;">,</span> <span style="color: #164;">5</span><span style="color: #339933;">,</span> <span style="color: #164;">6</span><span style="color: #339933;">,</span> <span style="color: #164;">7</span><span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 输出 22</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
<p>输出结果:</p>&#13;
<pre>Sum of 1, 2, 3: 6&#13;
Sum of 4, 5, 6, 7: 22</pre>&#13;
<h3>&#13;
解析</h3>&#13;
<ul><li><code>va_list args;</code>：声明一个 <code>va_list</code> 变量，用于访问可变参数。</li><li><code>va_start(args, count);</code>：初始化 <code>args</code> 以遍历可变参数列表，从 <code>count</code> 之后的第一个参数开始。</li><li><code>total += va_arg(args, int);</code>：获取可变参数列表中的下一个参数，并将其累加到 <code>total</code> 中。参数类型为 <code>int</code>。</li><li><code>va_end(args);</code>：清理 <code>args</code>。</li></ul>&#13;
<h3>注意事项</h3><ul><li>可变参数列表中的每个参数类型必须明确，且必须一致地传递给 <code>va_arg</code>。</li><li>使用 <code>va_start</code> 后，必须使用 <code>va_end</code> 清理 <code>va_list</code> 变量。</li><li><code>va_start</code>、<code>va_arg</code> 和 <code>va_end</code> 宏在一个函数中应成对使用，以避免未定义行为。</li></ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>