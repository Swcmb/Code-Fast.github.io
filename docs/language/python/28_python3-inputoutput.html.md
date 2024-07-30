<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 输入和输出</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 输入和输出</h1>&#13;
&#13;
<p>在前面几个章节中，我们其实已经接触了 Python 的输入输出的功能。本章节我们将具体介绍 Python 的输入输出。</p>&#13;
<h2>&#13;
&#13;
<hr/>&#13;
<h2>输出格式美化</h2>&#13;
</h2><p>&#13;
Python两种输出值的方式: 表达式语句和 print() 函数。&#13;
</p><p>第三种方式是使用文件对象的 write() 方法，标准输出文件可以用 sys.stdout 引用。</p>&#13;
&#13;
<p>如果你希望输出的形式更加多样，可以使用 str.format() 函数来格式化输出值。</p>&#13;
<p>如果你希望将输出的值转成字符串，可以使用 repr() 或 str() 函数来实现。</p>&#13;
<ul><li>&#13;
<b>str()：</b> 函数返回一个用户易读的表达形式。 </li><li>&#13;
<b>repr()：</b> 产生一个解释器易读的表达形式。</li></ul>&#13;
<h3>&#13;
例如&#13;
</h3>&#13;
&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> s <span style="color: Gray;">=</span> <span style="color: #a11;">'Hello, Runoob'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">str</span><span style="color: Olive;">(</span>s<span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'Hello, Runoob'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">repr</span><span style="color: Olive;">(</span>s<span style="color: Olive;">)</span><br/>
<span style="color: #a11;">"'Hello, Runoob'"</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">str</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span>/<span style="color: Maroon;">7</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'0.14285714285714285'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> x <span style="color: Gray;">=</span> <span style="color: Maroon;">10</span> * <span style="color: Maroon;">3.25</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> y <span style="color: Gray;">=</span> <span style="color: Maroon;">200</span> * <span style="color: Maroon;">200</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> s <span style="color: Gray;">=</span> <span style="color: #a11;">'x 的值为： '</span> + <span style="color: #05a;">repr</span><span style="color: Olive;">(</span>x<span style="color: Olive;">)</span> + <span style="color: #a11;">',  y 的值为：'</span> + <span style="color: #05a;">repr</span><span style="color: Olive;">(</span>y<span style="color: Olive;">)</span> + <span style="color: #a11;">'...'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>s<span style="color: Olive;">)</span><br/>
x 的值为： <span style="color: Maroon;">32.5</span><span style="color: Gray;">,</span>  y 的值为：<span style="color: Maroon;">40000</span>...<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a50">#  repr() 函数可以转义字符串中的特殊字符</span><br/>
... <span style="color: #05a;">hello</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'hello, runoob<span style="color: #000099; font-weight: bold;">\n</span>'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> hellos <span style="color: Gray;">=</span> <span style="color: #05a;">repr</span><span style="color: Olive;">(</span>hello<span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>hellos<span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'hello, runoob<span style="color: #000099; font-weight: bold;">\n</span>'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a50"># repr() 的参数可以是 Python 的任何对象</span><br/>
... <span style="color: #05a;">repr</span><span style="color: Olive;">(</span><span style="color: Olive;">(</span>x<span style="color: Gray;">,</span> y<span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">"(32.5, 40000, ('Google', 'Runoob'))"</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
这里有两种方式输出一个平方与立方的表:&#13;
</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #05a;">repr</span><span style="color: Olive;">(</span>x<span style="color: Olive;">)</span>.<span style="color: #05a;">rjust</span><span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: #05a;">repr</span><span style="color: Olive;">(</span>x*x<span style="color: Olive;">)</span>.<span style="color: #05a;">rjust</span><span style="color: Olive;">(</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> end<span style="color: Gray;">=</span><span style="color: #a11;">' '</span><span style="color: Olive;">)</span><br/>
...     <span style="color: #a50"># 注意前一行 'end' 的使用</span><br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #05a;">repr</span><span style="color: Olive;">(</span>x*x*x<span style="color: Olive;">)</span>.<span style="color: #05a;">rjust</span><span style="color: Olive;">(</span><span style="color: Maroon;">4</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
...<br/>
 <span style="color: Maroon;">1</span>   <span style="color: Maroon;">1</span>    <span style="color: Maroon;">1</span><br/>
 <span style="color: Maroon;">2</span>   <span style="color: Maroon;">4</span>    <span style="color: Maroon;">8</span><br/>
 <span style="color: Maroon;">3</span>   <span style="color: Maroon;">9</span>   <span style="color: Maroon;">27</span><br/>
 <span style="color: Maroon;">4</span>  <span style="color: Maroon;">16</span>   <span style="color: Maroon;">64</span><br/>
 <span style="color: Maroon;">5</span>  <span style="color: Maroon;">25</span>  <span style="color: Maroon;">125</span><br/>
 <span style="color: Maroon;">6</span>  <span style="color: Maroon;">36</span>  <span style="color: Maroon;">216</span><br/>
 <span style="color: Maroon;">7</span>  <span style="color: Maroon;">49</span>  <span style="color: Maroon;">343</span><br/>
 <span style="color: Maroon;">8</span>  <span style="color: Maroon;">64</span>  <span style="color: Maroon;">512</span><br/>
 <span style="color: Maroon;">9</span>  <span style="color: Maroon;">81</span>  <span style="color: Maroon;">729</span><br/>
<span style="color: Maroon;">10</span> <span style="color: Maroon;">100</span> <span style="color: Maroon;">1000</span><br/>
<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{0:2d} {1:3d} {2:4d}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>x<span style="color: Gray;">,</span> x*x<span style="color: Gray;">,</span> x*x*x<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
...<br/>
 <span style="color: Maroon;">1</span>   <span style="color: Maroon;">1</span>    <span style="color: Maroon;">1</span><br/>
 <span style="color: Maroon;">2</span>   <span style="color: Maroon;">4</span>    <span style="color: Maroon;">8</span><br/>
 <span style="color: Maroon;">3</span>   <span style="color: Maroon;">9</span>   <span style="color: Maroon;">27</span><br/>
 <span style="color: Maroon;">4</span>  <span style="color: Maroon;">16</span>   <span style="color: Maroon;">64</span><br/>
 <span style="color: Maroon;">5</span>  <span style="color: Maroon;">25</span>  <span style="color: Maroon;">125</span><br/>
 <span style="color: Maroon;">6</span>  <span style="color: Maroon;">36</span>  <span style="color: Maroon;">216</span><br/>
 <span style="color: Maroon;">7</span>  <span style="color: Maroon;">49</span>  <span style="color: Maroon;">343</span><br/>
 <span style="color: Maroon;">8</span>  <span style="color: Maroon;">64</span>  <span style="color: Maroon;">512</span><br/>
 <span style="color: Maroon;">9</span>  <span style="color: Maroon;">81</span>  <span style="color: Maroon;">729</span><br/>
<span style="color: Maroon;">10</span> <span style="color: Maroon;">100</span> <span style="color: Maroon;">1000</span><br/>
</div></div>&#13;
&#13;
<p><b>注意：</b>在第一个例子中, 每列间的空格由 print() 添加。</p>&#13;
<p>&#13;
这个例子展示了字符串对象的 rjust() 方法, 它可以将字符串靠右, 并在左边填充空格。</p><p>&#13;
还有类似的方法, 如 ljust() 和 center()。 这些方法并不会写任何东西, 它们仅仅返回新的字符串。</p>&#13;
<p>&#13;
另一个方法 zfill(), 它会在数字的左边填充 0，如下所示：</p>&#13;
&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'12'</span>.<span style="color: #05a;">zfill</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'00012'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'-3.14'</span>.<span style="color: #05a;">zfill</span><span style="color: Olive;">(</span><span style="color: Maroon;">7</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'-003.14'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'3.14159265359'</span>.<span style="color: #05a;">zfill</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'3.14159265359'</span><br/>
</div></div>&#13;
&#13;
<p>str.format() 的基本使用如下:</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{}网址： "{}!"'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #a11;">'菜鸟教程'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'www.runoob.com'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
菜鸟教程网址： <span style="color: #a11;">"www.runoob.com!"</span><br/>
</div></div>&#13;
&#13;
<p>括号及其里面的字符 (称作格式化字段) 将会被 format() 中的参数替换。 </p>&#13;
<p>在括号中的数字用于指向传入对象在 format() 中的位置，如下所示：</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{0} 和 {1}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
Google 和 Runoob<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{1} 和 {0}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
Runoob 和 Google<br/>
</div></div>&#13;
&#13;
<p>&#13;
如果在 format() 中使用了关键字参数, 那么它们的值会指向使用该名字的参数。</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{name}网址： {site}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>name<span style="color: Gray;">=</span><span style="color: #a11;">'菜鸟教程'</span><span style="color: Gray;">,</span> <span style="color: #05a;">site</span><span style="color: Gray;">=</span><span style="color: #a11;">'www.runoob.com'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
菜鸟教程网址： www.<span style="color: #05a;">runoob</span>.<span style="color: #05a;">com</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
位置及关键字参数可以任意的结合:&#13;
</p>&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'站点列表 {0}, {1}, 和 {other}。'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span><span style="color: Gray;">,</span> other<span style="color: Gray;">=</span><span style="color: #a11;">'Taobao'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
站点列表 Google<span style="color: Gray;">,</span> Runoob<span style="color: Gray;">,</span> 和 Taobao。<br/>
</div></div>&#13;
&#13;
<p> <span class="marked">!a</span>  (使用 <strong>ascii()</strong>),  <span class="marked">!s</span>  (使用 <strong>str()</strong>) 和  <span class="marked">!r</span>  (使用<strong> repr()</strong>) 可以用于在格式化某个值之前对其进行转化:</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">math</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'常量 PI 的值近似为： {}。'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #05a;">math</span>.<span style="color: #05a;">pi</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
常量 PI 的值近似为： <span style="color: Maroon;">3.141592653589793</span>。<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'常量 PI 的值近似为： {!r}。'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #05a;">math</span>.<span style="color: #05a;">pi</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
常量 PI 的值近似为： <span style="color: Maroon;">3.141592653589793</span>。<br/>
</div></div>&#13;
&#13;
<p>可选项  <span class="marked">:</span>  和格式标识符可以跟着字段名。 这就允许对值进行更好的格式化。 下面的例子将 Pi 保留到小数点后三位：&#13;
</p>&#13;
&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">math</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'常量 PI 的值近似为 {0:.3f}。'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span><span style="color: #05a;">math</span>.<span style="color: #05a;">pi</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
常量 PI 的值近似为 <span style="color: Maroon;">3.142</span>。<br/>
</div></div>&#13;
&#13;
<p>&#13;
在  <span class="marked">:</span> 后传入一个整数, 可以保证该域至少有这么多的宽度。 用于美化表格时很有用。&#13;
</p>&#13;
&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> table <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">3</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> name<span style="color: Gray;">,</span> number <span style="color: Green;font-weight:bold;">in</span> table.<span style="color: #05a;">items</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'{0:10} ==&gt; {1:10d}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>name<span style="color: Gray;">,</span> number<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
... <br/>
<span style="color: #05a;">Google</span>     <span style="color: Gray;">==&gt;</span>          <span style="color: Maroon;">1</span><br/>
Runoob     <span style="color: Gray;">==&gt;</span>          <span style="color: Maroon;">2</span><br/>
Taobao     <span style="color: Gray;">==&gt;</span>          <span style="color: Maroon;">3</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
如果你有一个很长的格式化字符串, 而你不想将它们分开, 那么在格式化时通过变量名而非位置会是很好的事情。&#13;
</p>&#13;
 <p>最简单的就是传入一个字典, 然后使用方括号  <span class="marked">[]</span> 来访问键值 :</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> table <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">3</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'Runoob: {0[Runoob]:d}; Google: {0[Google]:d}; Taobao: {0[Taobao]:d}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>table<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
Runoob: <span style="color: Maroon;">2</span><span style="color: Gray;">;</span> Google: <span style="color: Maroon;">1</span><span style="color: Gray;">;</span> Taobao: <span style="color: Maroon;">3</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
也可以通过在 table 变量前使用  <span class="marked">**</span>  来实现相同的功能：</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> table <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">3</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'Runoob: {Runoob:d}; Google: {Google:d}; Taobao: {Taobao:d}'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>**table<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
Runoob: <span style="color: Maroon;">2</span><span style="color: Gray;">;</span> Google: <span style="color: Maroon;">1</span><span style="color: Gray;">;</span> Taobao: <span style="color: Maroon;">3</span><br/>
</div></div>&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>旧式字符串格式化</h2>&#13;
<p>&#13;
<span class="marked">%</span> 操作符也可以实现字符串格式化。 它将左边的参数作为类似 <strong>sprintf()</strong> 式的格式化字符串, 而将右边的代入, 然后返回格式化后的字符串. 例如:&#13;
</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">math</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'常量 PI 的值近似为：%5.3f。'</span> % <span style="color: #05a;">math</span>.<span style="color: #05a;">pi</span><span style="color: Olive;">)</span><br/>
常量 PI 的值近似为：<span style="color: Maroon;">3.142</span>。<br/>
</div></div>&#13;
&#13;
<p>&#13;
因为 str.format() 是比较新的函数， 大多数的 Python 代码仍然使用 % 操作符。但是因为这种旧式的格式化最终会从该语言中移除, 应该更多的使用 str.format().&#13;
</p>&#13;
<hr/>&#13;
<h2>读取键盘输入</h2>&#13;
<p>&#13;
Python 提供了 <a href="https://www.runoob.com/python3/python3-func-input.html" rel="noopener" target="_blank">input() 内置函数</a>从标准输入读入一行文本，默认的标准输入是键盘。</p>&#13;
&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> <span style="color: Teal;">input</span><span style="color: Olive;">(</span><span style="color: #a11;">"请输入："</span><span style="color: Olive;">)</span><span style="color: Gray;">;</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"你输入的内容是: "</span><span style="color: Gray;">,</span> <span style="color: Teal;">str</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
这会产生如下的对应着输入的结果：&#13;
</p>&#13;
<pre>&#13;
请输入：菜鸟教程&#13;
你输入的内容是:  菜鸟教程&#13;
</pre>&#13;
&#13;
&#13;
<hr/>&#13;
<h2>读和写文件&#13;
</h2>&#13;
<p>&#13;
open() 将会返回一个 file 对象，基本语法格式如下: &#13;
</p>&#13;
<pre>&#13;
open(filename, mode)&#13;
</pre>&#13;
<ul> <li>filename：包含了你要访问的文件名称的字符串值。</li> &#13;
<li>mode：决定了打开文件的模式：只读，写入，追加等。所有可取值见如下的完全列表。这个参数是非强制的，默认文件访问模式为只读(r)。</li> </ul>&#13;
<p>不同模式打开文件的完全列表：</p>&#13;
<table class="reference"> <tbody><tr><th style="width:10%">模式</th><th>描述</th></tr> <tr><td>r</td><td>以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。</td></tr> <tr><td>rb</td><td>以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。</td></tr> <tr><td>r+</td><td>打开一个文件用于读写。文件指针将会放在文件的开头。</td></tr> <tr><td>rb+</td><td>以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。</td></tr> <tr><td>w</td><td>打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr> <tr><td>wb</td><td>以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr> <tr><td>w+</td><td>打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr> <tr><td>wb+</td><td>以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr> <tr><td>a</td><td>打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。</td></tr> <tr><td>ab</td><td>以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。</td></tr> <tr><td>a+</td><td>打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。</td></tr> <tr><td>ab+</td><td>以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。</td></tr> </tbody></table>&#13;
<p>下图很好的总结了这几种模式：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/11/2112205-861c05b2bdbc9c28.png"/></p>&#13;
<table class="reference">&#13;
<thead>&#13;
<tr>&#13;
<th style="text-align:center">模式</th>&#13;
<th style="text-align:center">r</th>&#13;
<th style="text-align:center">r+</th>&#13;
<th style="text-align:center">w</th>&#13;
<th style="text-align:center">w+</th>&#13;
<th style="text-align:center">a</th>&#13;
<th style="text-align:center">a+</th>&#13;
</tr>&#13;
</thead>&#13;
<tbody>&#13;
<tr>&#13;
<td style="text-align:center">读</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
</tr>&#13;
<tr>&#13;
<td style="text-align:center">写</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
</tr>&#13;
<tr>&#13;
<td style="text-align:center">创建</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
</tr>&#13;
<tr>&#13;
<td style="text-align:center">覆盖</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
</tr>&#13;
<tr>&#13;
<td style="text-align:center">指针在开始</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
</tr>&#13;
<tr>&#13;
<td style="text-align:center">指针在结尾</td>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center"/>&#13;
<td style="text-align:center">+</td>&#13;
<td style="text-align:center">+</td>&#13;
</tr>&#13;
</tbody>&#13;
</table>&#13;
<p>以下实例将字符串写入到文件 foo.txt 中：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"w"</span><span style="color: Olive;">)</span><br/>
<br/>
f.<span style="color: #05a;">write</span><span style="color: Olive;">(</span> <span style="color: #a11;">"Python 是一个非常好的语言。<span style="color: #000099; font-weight: bold;">\n</span>是的，的确非常好!!<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
&#13;
<ul>&#13;
<li>&#13;
第一个参数为要打开的文件名。 &#13;
</li>&#13;
<li>第二个参数描述文件如何使用的字符。 mode 可以是 'r' 如果文件只读, 'w' 只用于写 (如果存在同名文件则将被删除), 和 'a' 用于追加文件内容; 所写的任何数据都会被自动增加到末尾. 'r+' 同时用于读写。 mode 参数是可选的; 'r' 将是默认值。&#13;
</li>&#13;
</ul><p>&#13;
此时打开文件 foo.txt,显示如下：</p>&#13;
<pre>&#13;
$ cat /tmp/foo.txt &#13;
Python 是一个非常好的语言。&#13;
是的，的确非常好!!&#13;
</pre>&#13;
<hr/>&#13;
<h2>文件对象的方法</h2>&#13;
<p>&#13;
本节中剩下的例子假设已经创建了一个称为 f 的文件对象。&#13;
</p>&#13;
<h3>f.read()</h3>&#13;
<p>&#13;
为了读取一个文件的内容，调用 f.read(size), 这将读取一定数目的数据, 然后作为字符串或字节对象返回。</p>&#13;
<p>size 是一个可选的数字类型的参数。 当 size 被忽略了或者为负, 那么该文件的所有内容都将被读取并且返回。</p>&#13;
<p>以下实例假定文件 foo.txt 已存在（上面实例中已创建）：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"r"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> f.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
Python 是一个非常好的语言。&#13;
是的，的确非常好!!&#13;
</pre>&#13;
<h3>f.readline()</h3>&#13;
<p>&#13;
f.readline() 会从文件中读取单独的一行。换行符为 '\n'。f.readline() 如果返回一个空字符串, 说明已经已经读取到最后一行。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"r"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> f.<span style="color: #05a;">readline</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
Python 是一个非常好的语言。&#13;
</pre>&#13;
<h3>f.readlines()</h3>&#13;
<p>&#13;
f.readlines() 将返回该文件中包含的所有行。&#13;
</p>&#13;
<p> 如果设置可选参数 sizehint, 则读取指定长度的字节, 并且将这些字节按行分割。&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"r"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> f.<span style="color: #05a;">readlines</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
['Python 是一个非常好的语言。\n', '是的，的确非常好!!\n']&#13;
</pre>&#13;
<p>&#13;
另一种方式是迭代一个文件对象然后读取每行:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"r"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">for</span> line <span style="color: Green;font-weight:bold;">in</span> f:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>line<span style="color: Gray;">,</span> end<span style="color: Gray;">=</span><span style="color: #a11;">''</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
Python 是一个非常好的语言。&#13;
是的，的确非常好!!&#13;
</pre>&#13;
<p>&#13;
这个方法很简单, 但是并没有提供一个很好的控制。 因为两者的处理机制不同, 最好不要混用。&#13;
</p>&#13;
<h3>f.write()</h3>&#13;
<p>&#13;
f.write(string) 将 string 写入到文件中, 然后返回写入的字符数。&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"w"</span><span style="color: Olive;">)</span><br/>
<br/>
num <span style="color: Gray;">=</span> f.<span style="color: #05a;">write</span><span style="color: Olive;">(</span> <span style="color: #a11;">"Python 是一个非常好的语言。<span style="color: #000099; font-weight: bold;">\n</span>是的，的确非常好!!<span style="color: #000099; font-weight: bold;">\n</span>"</span> <span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>num<span style="color: Olive;">)</span><br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
29&#13;
</pre>&#13;
<p>&#13;
如果要写入一些不是字符串的东西, 那么将需要先进行转换:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 打开一个文件</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"/tmp/foo1.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"w"</span><span style="color: Olive;">)</span><br/>
<br/>
value <span style="color: Gray;">=</span> <span style="color: Olive;">(</span><span style="color: #a11;">'www.runoob.com'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">14</span><span style="color: Olive;">)</span><br/>
s <span style="color: Gray;">=</span> <span style="color: Teal;">str</span><span style="color: Olive;">(</span>value<span style="color: Olive;">)</span><br/>
f.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>s<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭打开的文件</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序，打开 foo1.txt 文件：</p>&#13;
<pre>&#13;
$ cat /tmp/foo1.txt &#13;
('www.runoob.com', 14)&#13;
</pre>&#13;
<h3>f.tell()</h3>&#13;
<p>&#13;
f.tell() 用于返回文件当前的读/写位置（即文件指针的位置）。文件指针表示从文件开头开始的字节数偏移量。f.tell() 返回一个整数，表示文件指针的当前位置。&#13;
</p>&#13;
<h3>f.seek()</h3>&#13;
<p>如果要改变文件指针当前的位置, 可以使用 f.seek(offset, from_what) 函数。</p>&#13;
<p>f.seek(offset, whence)  用于移动文件指针到指定位置。</p>&#13;
<p>&#13;
offset 表示相对于 whence 参数的偏移量，from_what 的值, 如果是 0 表示开头, 如果是 1 表示当前位置, 2 表示文件的结尾，例如：</p>&#13;
&#13;
<ul>&#13;
<li>&#13;
seek(x,0) ： 从起始位置即文件首行首字符开始移动 x 个字符</li><li>&#13;
seek(x,1) ： 表示从当前位置往后移动x个字符</li><li>&#13;
seek(-x,2)：表示从文件的结尾往前移动x个字符&#13;
</li></ul>&#13;
<p>&#13;
from_what 值为默认为0，即文件开头。下面给出一个完整的例子：</p>&#13;
&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">'/tmp/foo.txt'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'rb+'</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>b<span style="color: #a11;">'0123456789abcdef'</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">16</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">seek</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span><span style="color: Olive;">)</span>     <span style="color: #a50"># 移动到文件的第六个字节</span><br/>
<span style="color: Maroon;">5</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
b<span style="color: #a11;">'5'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">seek</span><span style="color: Olive;">(</span>-<span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span> <span style="color: #a50"># 移动到文件的倒数第三字节</span><br/>
<span style="color: Maroon;">13</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
b<span style="color: #a11;">'d'</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
</p><h3>f.close()</h3><p>&#13;
在文本文件中 (那些打开文件的模式下没有 b 的), 只会相对于文件起始位置进行定位。</p>&#13;
<p>&#13;
当你处理完一个文件后, 调用 f.close() 来关闭文件并释放系统的资源，如果尝试再调用该文件，则会抛出异常。</p>&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
Traceback <span style="color: Olive;">(</span>most recent call last<span style="color: Olive;">)</span>:<br/>
  File <span style="color: #a11;">"&lt;stdin&gt;"</span><span style="color: Gray;">,</span> line <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Green;font-weight:bold;">in</span> ?<br/>
<span style="color: Teal;">ValueError</span>: I/O operation on closed <span style="color: Teal;">file</span><br/>
</div></div>&#13;
<p>&#13;
当处理一个文件对象时, 使用 with 关键字是非常好的方式。在结束后, 它会帮你正确的关闭文件。 而且写起来也比 try - finally 语句块要简短:</p>&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">with</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">'/tmp/foo.txt'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'r'</span><span style="color: Olive;">)</span> <span style="color: Green;font-weight:bold;">as</span> f:<br/>
...     <span style="color: #05a;">read_data</span> <span style="color: Gray;">=</span> f.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> f.<span style="color: #05a;">closed</span><br/>
<span style="color: Teal;">True</span><br/>
</div></div><p>&#13;
文件对象还有其他方法, 如 isatty() 和 trucate(), 但这些通常比较少用。</p>&#13;
&#13;
<hr/><h2>pickle 模块&#13;
</h2>&#13;
<p>&#13;
python的pickle模块实现了基本的数据序列和反序列化。</p>&#13;
<p>通过pickle模块的序列化操作我们能够将程序中运行的对象信息保存到文件中去，永久存储。</p>&#13;
<p>通过pickle模块的反序列化操作，我们能够从文件中创建上一次程序保存的对象。&#13;
</p>&#13;
<p>基本接口：&#13;
</p>&#13;
<pre>&#13;
pickle.dump(obj, file, [,protocol])&#13;
</pre>&#13;
<p>&#13;
有了 pickle 这个对象, 就能对 file 以读取的形式打开:&#13;
</p>&#13;
<pre>&#13;
x = pickle.load(file)&#13;
</pre>&#13;
<p><b>注解：</b>从 file 中读取一个字符串，并将它重构为原来的python对象。</p>&#13;
<p><b>file:</b> 类文件对象，有read()和readline()接口。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例 1</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">pickle</span><br/>
<br/>
<span style="color: #a50"># 使用pickle模块将数据对象保存到文件</span><br/>
data1 <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'a'</span>: <span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2.0</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span>+6j<span style="color: Olive;">]</span><span style="color: Gray;">,</span><br/>
         <span style="color: #a11;">'b'</span>: <span style="color: Olive;">(</span><span style="color: #a11;">'string'</span><span style="color: Gray;">,</span> u<span style="color: #a11;">'Unicode string'</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span><br/>
         <span style="color: #a11;">'c'</span>: <span style="color: Teal;">None</span><span style="color: Olive;">}</span><br/>
<br/>
selfref_list <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Olive;">]</span><br/>
selfref_list.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>selfref_list<span style="color: Olive;">)</span><br/>
<br/>
output <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">'data.pkl'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'wb'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># Pickle dictionary using protocol 0.</span><br/>
<span style="color: #05a;">pickle</span>.<span style="color: #05a;">dump</span><span style="color: Olive;">(</span>data1<span style="color: Gray;">,</span> output<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># Pickle the list using the highest protocol available.</span><br/>
<span style="color: #05a;">pickle</span>.<span style="color: #05a;">dump</span><span style="color: Olive;">(</span>selfref_list<span style="color: Gray;">,</span> output<span style="color: Gray;">,</span> -<span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
<br/>
output.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例 2</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">pprint</span><span style="color: Gray;">,</span> <span style="color: #05a;">pickle</span><br/>
<br/>
<span style="color: #a50">#使用pickle模块从文件中重构python对象</span><br/>
pkl_file <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">'data.pkl'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'rb'</span><span style="color: Olive;">)</span><br/>
<br/>
data1 <span style="color: Gray;">=</span> <span style="color: #05a;">pickle</span>.<span style="color: #05a;">load</span><span style="color: Olive;">(</span>pkl_file<span style="color: Olive;">)</span><br/>
<span style="color: #05a;">pprint</span>.<span style="color: #05a;">pprint</span><span style="color: Olive;">(</span>data1<span style="color: Olive;">)</span><br/>
<br/>
data2 <span style="color: Gray;">=</span> <span style="color: #05a;">pickle</span>.<span style="color: #05a;">load</span><span style="color: Olive;">(</span>pkl_file<span style="color: Olive;">)</span><br/>
<span style="color: #05a;">pprint</span>.<span style="color: #05a;">pprint</span><span style="color: Olive;">(</span>data2<span style="color: Olive;">)</span><br/>
<br/>
pkl_file.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>