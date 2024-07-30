<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <assert.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;assert.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p>C 标准库的 <b>assert.h</b>头文件提供了一个名为 <b>assert</b> 的宏，它可用于验证程序做出的假设，并在假设为假时输出诊断消息。</p><p>&#13;
assert.h 标准库主要用于在程序运行时进行断言断言是一种用于测试假设的手段，通常用于调试阶段，以便在程序出现不符合预期的状态时立即发现问题。</p>&#13;
<p><code>&lt;assert.h&gt;</code> 提供的断言机制是 C 语言中一个有用的工具，帮助开发人员在早期发现和修复程序中的错误。</p>&#13;
<p>已定义的宏 <b>assert</b> 指向另一个宏 <b>NDEBUG</b>，宏 <b>NDEBUG</b> 不是 &lt;assert.h&gt; 的一部分。如果已在引用 &lt;assert.h&gt; 的源文件中定义 NDEBUG 为宏名称，则 <b>assert</b> 宏的定义如下：</p>&#13;
<pre>&#13;
assert(expression)&#13;
</pre>&#13;
<p>assert 宏用于测试表达式 expression 是否为真。如果 expression 为假（即结果为 0），assert 会输出一条错误信息并终止程序的执行。这个错误信息包括以下内容：</p>&#13;
<ul><li>触发断言失败的表达式</li><li>源文件名</li><li>行号</li></ul><p>&#13;
在发布版本中，可以通过定义 NDEBUG 来禁用所有的 assert 断言。例如：</p>&#13;
&#13;
<pre>#define NDEBUG&#13;
#include &lt;assert.h&gt;</pre>&#13;
<p>一旦定义了 NDEBUG，assert 宏将被预处理为一个空语句，不会有任何运行时开销。</p>&#13;
<p>以下是一个简单的示例，演示了 assert 的基本用法：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #060;">#include &lt;assert.h&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> test_positive<span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">assert</span><span style="color: #008000;">(</span>x <span style="color: #000080;">&gt;</span> <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> b <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">3</span><span style="color: #008080;">;</span><br/>
<br/>
    test_positive<span style="color: #008000;">(</span>a<span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 这个断言通过</span><br/>
    test_positive<span style="color: #008000;">(</span>b<span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 这个断言失败，程序终止</span><br/>
<br/>
    <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"This line will not be executed if an assertion fails.<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>在上面的例子中，当调用 test_positive(b) 时，由于 b 是一个负数，断言 x &gt; 0 将失败，程序会输出类似如下的信息并终止：</p>&#13;
<pre>&#13;
Assertion failed: (x &gt; 0), file example.c, line 6</pre>&#13;
<h3>断言的作用</h3>&#13;
<ul><li><strong>调试</strong>：在开发阶段，通过断言可以快速发现程序中的逻辑错误或假设不成立的情况。</li><li><strong>文档</strong>：断言可以作为文档的一部分，描述函数的前置条件和后置条件。</li><li><strong>防御性编程</strong>：虽然不建议在生产代码中使用断言来进行参数检查，但在某些情况下，断言可以作为最后的防线。</li></ul>&#13;
&#13;
<h3>注意事项</h3>&#13;
<ul><li><strong>性能</strong>：在性能敏感的代码中，断言可能会增加额外的开销，尤其是在大量调用的情况下。因此，发布版本中通常会禁用断言。</li><li><strong>错误处理</strong>：断言不应该用于处理可以预期并且可以恢复的错误情况。断言更多地用于捕获程序员的错误。</li></ul>&#13;
<h2>库宏</h2>&#13;
<p>下面列出了头文件 assert.h 中定义的唯一的函数：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">序号</th><th>函数 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-macro-assert.html">void assert(int expression)</a><br/>这实际上是一个宏，不是一个函数，可用于在 C 程序中添加诊断。</td></tr>&#13;
</table>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>