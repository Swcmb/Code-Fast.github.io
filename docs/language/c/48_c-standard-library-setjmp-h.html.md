<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <setjmp.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;setjmp.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p><b>setjmp.h</b> 头文件定义了宏 <b>setjmp()</b>、函数 <b>longjmp()</b> 和变量类型 <b>jmp_buf</b>，该变量类型会绕过正常的函数调用和返回规则。</p>&#13;
<p><code>&lt;setjmp.h&gt;</code> 是 C 标准库中的一个头文件，提供了一组函数和宏，用于非本地跳转（即从一个函数跳转到另一个之前调用过的函数，而不需要正常的函数返回机制）。这种机制通常用于错误处理、异常处理或者跳出深层嵌套的循环或递归。</p>&#13;
<h2>库变量</h2>&#13;
<p>下面列出了头文件 setjmp.h 中定义的变量：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>变量 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>jmp_buf </b><br/><p><code>jmp_buf</code> 是一个数据类型，用于保存调用环境，包括栈指针、指令指针和寄存器等。在执行 <code>setjmp()</code> 时，这些环境信息会被保存到 <code>jmp_buf</code> 类型的变量中。</p></td></tr>&#13;
</table>&#13;
&#13;
<h2>库宏</h2>&#13;
<p>下面是这个库中定义的唯一的一个宏：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-macro-setjmp.html">int setjmp(jmp_buf environment)</a><br/>这个宏把当前环境保存在变量 <b>environment</b> 中，以便函数 <b>longjmp()</b> 后续使用。如果这个宏直接从宏调用中返回，则它会返回零，但是如果它从 <b>longjmp()</b> 函数调用中返回，则它会返回一个非零值。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库函数</h2>&#13;
<p>下面是头文件 setjmp.h 中定义的唯一的一个函数：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>函数 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-function-longjmp.html">void longjmp(jmp_buf environment, int value)</a><br/>该函数恢复最近一次调用 <b>setjmp()</b> 宏时保存的环境，<b>jmp_buf</b> 参数的设置是由之前调用 setjmp() 生成的。</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>以下示例展示了如何使用 setjmp() 和 longjmp() 实现非本地跳转：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;setjmp.h&gt;</span><br/>
<br/>
jmp_buf env<span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #993333;">void</span> second<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Entering second()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">longjmp</span><span style="color: #000;">(</span>env<span style="color: #339933;">,</span> <span style="color: #164;">1</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"This line will never be executed<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
<br/>
<span style="color: #993333;">void</span> first<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Entering first()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">if</span> <span style="color: #000;">(</span><span style="color: #000066;">setjmp</span><span style="color: #000;">(</span>env<span style="color: #000;">)</span> <span style="color: #339933;">==</span> <span style="color: #164;">0</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Calling second() from first()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
        second<span style="color: #000;">(</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span> <span style="color: #708;">else</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Returned to first() from second() using longjmp<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Exiting first()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Starting main()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    first<span style="color: #000;">(</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Exiting main()<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>运行上述程序将输出类似以下内容：</p>&#13;
<pre>Starting main()&#13;
Entering first()&#13;
Calling second() from first()&#13;
Entering second()&#13;
Returned to first() from second() using longjmp&#13;
Exiting first()&#13;
Exiting main()</pre>&#13;
&#13;
    <h3>代码解析</h3>&#13;
    <ul>&#13;
        <li><code>jmp_buf env</code>：定义一个用于保存环境信息的变量 <code>env</code>。</li>&#13;
        <li><code>first()</code> 函数：调用 <code>setjmp(env)</code> 保存当前环境信息，并根据其返回值决定是否调用 <code>second()</code> 函数。</li>&#13;
        <li><code>second()</code> 函数：调用 <code>longjmp(env, 1)</code>，跳转回 <code>setjmp(env)</code>，并使其返回 1。</li>&#13;
        <li><code>main()</code> 函数：调用 <code>first()</code> 函数。</li>&#13;
    </ul>    <h3>使用场景</h3>&#13;
    <ul>&#13;
        <li><strong>错误处理</strong>：在深层嵌套的函数调用中使用 <code>setjmp()</code> 和 <code>longjmp()</code> 实现错误处理机制。</li>&#13;
        <li><strong>异常处理</strong>：用于实现简单的异常处理。</li>&#13;
        <li><strong>中断控制流</strong>：在某些情况下，可以中断正常的控制流，跳出多层嵌套的循环或函数调用。</li>&#13;
    </ul>&#13;
    <h3>注意事项</h3>&#13;
    <ul>&#13;
        <li>使用 <code>setjmp()</code> 和 <code>longjmp()</code> 需要小心，因为它们会跳过正常的栈展开过程，可能导致资源泄漏（如未释放的内存、未关闭的文件等）。</li>&#13;
        <li>避免在调用 <code>setjmp()</code> 和 <code>longjmp()</code> 之间修改局部变量，因为这可能导致未定义行为。</li>&#13;
        <li>非本地跳转可能使代码难以阅读和调试，因此应谨慎使用。</li>&#13;
    </ul>&#13;
    <h3>总结</h3>&#13;
    <p><code>&lt;setjmp.h&gt;</code> 提供了 <code>setjmp()</code> 和 <code>longjmp()</code> 函数，用于实现非本地跳转。这些函数在错误处理和异常处理中非常有用，但需要谨慎使用以避免潜在的问题。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>