<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <iomanip></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 &lt;iomanip&gt;</h1>&#13;
&#13;
<p><code>&lt;iomanip&gt;</code> 是 C++ 标准库中的一个头文件，它提供了对输入/输出流的格式化操作。</p><p><code>iomanip</code> 库中的函数允许开发者控制输出格式，如设置小数点后的位数、设置宽度、对齐方式等。</p>&#13;
&#13;
<p><code>iomanip</code> 是 Input/Output Manipulators 的缩写，它提供了一组操作符，用于控制 C++ 标准库中的输入/输出流的格式。</p>&#13;
<h3>语法</h3>&#13;
<p><code>iomanip</code> 库中的函数通常与 <code>&lt;&lt;</code> 和 <code>&gt;&gt;</code> 操作符一起使用，以实现对输出流的控制。以下是一些常用的 <code>iomanip</code> 函数：</p>&#13;
<ul>&#13;
<li><code>setw(int)</code></li>&#13;
<li><code>setprecision(int)</code></li>&#13;
<li><code>fixed</code></li>&#13;
<li><code>scientific</code></li>&#13;
<li><code>setiosflags(ios_base::fmtflags)</code></li>&#13;
<li><code>resetiosflags(ios_base::fmtflags)</code></li>&#13;
<li><code>setfill(char)</code></li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>1. 设置宽度</h3>&#13;
<p>使用 <code>setw</code> 可以设置输出的宽度。如果输出内容的字符数少于设置的宽度，剩余部分将用空格填充。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setw</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>输出结果:</strong></p>&#13;
<pre>Hello</pre>&#13;
<h3>2. 设置精度</h3>&#13;
<p>使用 <code>setprecision</code> 可以设置浮点数的小数点后的位数。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">double</span> pi <span style="color: #000080;">=</span> <span style="color:#800080;">3.14159265358979323846</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setprecision</span><span style="color: #008000;">(</span><span style="color: #0000dd;">2</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> pi <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>输出结果:</strong></p>&#13;
<pre>3.14</pre>&#13;
<h3>3. 固定小数点和科学计数法</h3>&#13;
<p><code>fixed</code> 和 <code>scientific</code> 可以控制浮点数的输出格式。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">double</span> num <span style="color: #000080;">=</span> <span style="color:#800080;">123456789.0</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Fixed: "</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">fixed</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Scientific: "</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">scientific</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>输出结果:</strong></p>&#13;
<pre>Fixed: 123456789.000000&#13;
Scientific: 1.23456789e+08</pre>&#13;
<h3>4. 设置填充字符</h3>&#13;
<p>使用 <code>setfill</code> 可以设置填充字符，通常与 <code>setw</code> 一起使用。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setfill</span><span style="color: #008000;">(</span><span style="color: #a11;">'*'</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setw</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"World"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>输出结果:</strong></p>&#13;
<pre>*****World</pre>&#13;
<h3>5. 设置和重置格式标志</h3>&#13;
<p><code>setiosflags</code> 和 <code>resetiosflags</code> 可以设置或重置流的格式标志。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setiosflags</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">ios</span><span style="color: #008080;">::</span><span style="color: #007788;">uppercase</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">hex</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #0000dd;">255</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">resetiosflags</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">ios</span><span style="color: #008080;">::</span><span style="color: #007788;">uppercase</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">hex</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #0000dd;">255</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>输出结果:</strong></p>&#13;
<pre>FF&#13;
ff</pre>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>