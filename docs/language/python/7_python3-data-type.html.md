<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 基本数据类型</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 基本数据类型</h1>&#13;
<p>&#13;
Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。</p>&#13;
<p>在 Python 中，变量就是变量，它没有类型，我们所说的"类型"是变量所指的内存中对象的类型。</p>&#13;
<p>等号（=）用来给变量赋值。</p><p>&#13;
等号（=）运算符左边是一个变量名,等号（=）运算符右边是存储在变量中的值。例如：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
counter <span style="color: Gray;">=</span> <span style="color: Maroon;">100</span>          <span style="color: #a50"># 整型变量</span><br/>
miles   <span style="color: Gray;">=</span> <span style="color: Maroon;">1000.0</span>       <span style="color: #a50"># 浮点型变量</span><br/>
name    <span style="color: Gray;">=</span> <span style="color: #a11;">"runoob"</span>     <span style="color: #a50"># 字符串</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>counter<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>miles<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>name<span style="color: Olive;">)</span><br/>
&#13;
</div><br/>&#13;
<a target="_blank" href="/try/runcode.php?filename=basic_data_type1&amp;type=python3" class="showbtn" rel="noopener noreferrer">运行实例 »</a>&#13;
</div>&#13;
<p>执行以上程序会输出如下结果：</p>&#13;
<pre>&#13;
100&#13;
1000.0&#13;
runoob&#13;
</pre>&#13;
<h3>多个变量赋值</h3>&#13;
<p>&#13;
Python允许你同时为多个变量赋值。例如：</p>&#13;
<pre>&#13;
a = b = c = 1&#13;
</pre>&#13;
<p>&#13;
以上实例，创建一个整型对象，值为 1，从后向前赋值，三个变量被赋予相同的数值。&#13;
</p><p>&#13;
您也可以为多个对象指定多个变量。例如：</p><pre>&#13;
a, b, c = 1, 2, "runoob"</pre><p>&#13;
以上实例，两个整型对象 1 和 2 的分配给变量 a 和 b，字符串对象 "runoob" 分配给变量 c。</p>&#13;
<hr/>&#13;
<h2>标准数据类型</h2>&#13;
<p>Python3 中常见的数据类型有：&#13;
</p>&#13;
<ul>&#13;
<li>Number（数字）</li>&#13;
<li>String（字符串）</li>&#13;
<li> bool（布尔类型）</li>&#13;
&#13;
<li>List（列表）</li>&#13;
<li>Tuple（元组）</li>&#13;
<li>Set（集合）</li>&#13;
<li>Dictionary（字典）</li>&#13;
</ul>&#13;
<p>Python3 的六个标准数据类型中：</p><ul><li>&#13;
<strong>不可变数据（3 个）：</strong>Number（数字）、String（字符串）、Tuple（元组）；</li><li>&#13;
<strong>可变数据（3 个）：</strong>List（列表）、Dictionary（字典）、Set（集合）。&#13;
</li></ul>&#13;
<p>此外还有一些高级的数据类型，如: 字节数组类型(bytes)。</p>&#13;
&#13;
<hr/>&#13;
<h2>Number（数字）</h2>&#13;
<p>Python3 支持 <b>int、float、bool、complex（复数）</b>。&#13;
</p>&#13;
<p>在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。</p>&#13;
<p>像大多数语言一样，数值类型的赋值和计算都是很直观的。</p>&#13;
<p>内置的 type() 函数可以用来查询变量所指的对象类型。</p>&#13;
<pre>&#13;
&gt;&gt;&gt; a, b, c, d = 20, 5.5, True, 4+3j&#13;
&gt;&gt;&gt; print(type(a), type(b), type(c), type(d))&#13;
&lt;class 'int'&gt; &lt;class 'float'&gt; &lt;class 'bool'&gt; &lt;class 'complex'&gt;&#13;
</pre>&#13;
&#13;
<p>此外还可以用 isinstance 来判断：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Maroon;">111</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">isinstance</span><span style="color: Olive;">(</span>a<span style="color: Gray;">,</span> <span style="color: Teal;">int</span><span style="color: Olive;">)</span><br/>
<span style="color: Teal;">True</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <br/>
&#13;
</div>&#13;
</div>&#13;
<p>&#13;
isinstance 和 type 的区别在于：</p>&#13;
<ul><li>&#13;
type()不会认为子类是一种父类类型。</li><li>&#13;
isinstance()会认为子类是一种父类类型。</li></ul>&#13;
<pre>&#13;
&gt;&gt;&gt; class A:&#13;
...     pass&#13;
... &#13;
&gt;&gt;&gt; class B(A):&#13;
...     pass&#13;
... &#13;
&gt;&gt;&gt; isinstance(A(), A)&#13;
True&#13;
&gt;&gt;&gt; type(A()) == A &#13;
True&#13;
&gt;&gt;&gt; isinstance(B(), A)&#13;
True&#13;
&gt;&gt;&gt; type(B()) == A&#13;
False&#13;
</pre>&#13;
&#13;
&#13;
<blockquote>&#13;
<p><b>注意：</b>Python3 中，bool 是 int 的子类，True 和 False 可以和数字相加， <span class="marked">True==1、False==0</span> 会返回 <strong>True</strong>，但可以通过 <span class="marked">is</span> 来判断类型。</p>&#13;
<pre>&#13;
&gt;&gt;&gt; issubclass(bool, int) &#13;
True&#13;
&gt;&gt;&gt; True==1&#13;
True&#13;
&gt;&gt;&gt; False==0&#13;
True&#13;
&gt;&gt;&gt; True+1&#13;
2&#13;
&gt;&gt;&gt; False+1&#13;
1&#13;
&gt;&gt;&gt; 1 is True&#13;
False&#13;
&gt;&gt;&gt; 0 is False&#13;
False&#13;
</pre>&#13;
<p>在 Python2 中是没有布尔型的，它用数字 0 表示 False，用 1 表示 True。</p>&#13;
</blockquote>&#13;
<p>当你指定一个值时，Number 对象就会被创建：</p>&#13;
<pre>&#13;
var1 = 1&#13;
var2 = 10&#13;
</pre><p>&#13;
您也可以使用del语句删除一些对象引用。</p><p>&#13;
del语句的语法是：</p>&#13;
<pre>&#13;
del var1[,var2[,var3[....,varN]]]&#13;
</pre>&#13;
<p>您可以通过使用del语句删除单个或多个对象。例如：</p>&#13;
<pre>&#13;
del var&#13;
del var_a, var_b</pre>&#13;
<h3>数值运算</h3>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">5</span> + <span style="color: Maroon;">4</span>  <span style="color: #a50"># 加法</span><br/>
<span style="color: Maroon;">9</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">4.3</span> - <span style="color: Maroon;">2</span> <span style="color: #a50"># 减法</span><br/>
<span style="color: Maroon;">2.3</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">3</span> * <span style="color: Maroon;">7</span>  <span style="color: #a50"># 乘法</span><br/>
<span style="color: Maroon;">21</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">2</span> / <span style="color: Maroon;">4</span>  <span style="color: #a50"># 除法，得到一个浮点数</span><br/>
<span style="color: Maroon;">0.5</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">2</span> // <span style="color: Maroon;">4</span> <span style="color: #a50"># 除法，得到一个整数</span><br/>
<span style="color: Maroon;">0</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">17</span> % <span style="color: Maroon;">3</span> <span style="color: #a50"># 取余 </span><br/>
<span style="color: Maroon;">2</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Maroon;">2</span> ** <span style="color: Maroon;">5</span> <span style="color: #a50"># 乘方</span><br/>
<span style="color: Maroon;">32</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p><b>注意：</b></p>&#13;
<ul>&#13;
<li>1、Python可以同时为多个变量赋值，如a, b = 1, 2。</li><li>&#13;
2、一个变量可以通过赋值指向不同类型的对象。</li><li>&#13;
3、数值的除法包含两个运算符：<span class="marked">/</span> 返回一个浮点数，<span class="marked">//</span> 返回一个整数。</li><li>&#13;
4、在混合计算时，Python会把整型转换成为浮点数。&#13;
</li>&#13;
</ul>&#13;
<h3>数值类型实例</h3>&#13;
<table class="reference">&#13;
<tbody><tr><th>int</th><th>float</th><th>complex</th></tr>&#13;
<tr><td>10</td><td>0.0</td><td>3.14j</td></tr>&#13;
<tr><td>100</td><td>15.20</td><td>45.j</td></tr>&#13;
<tr><td>-786</td><td>-21.9</td><td>9.322e-36j</td></tr>&#13;
<tr><td>080</td><td>32.3e+18</td><td>.876j</td></tr>&#13;
<tr><td>-0490</td><td>-90.</td><td>-.6545+0J</td></tr>&#13;
<tr><td>-0x260</td><td>-32.54e100</td><td>3e+26J</td></tr>&#13;
<tr><td>0x69</td><td>70.2E-12</td><td>4.53e-7j</td></tr>&#13;
</tbody></table>&#13;
<p>Python 还支持复数，复数由实数部分和虚数部分构成，可以用 <span class="marked">a + bj</span>，或者 <span class="marked">complex(a,b)</span> 表示， 复数的实部 <strong>a</strong> 和虚部 <strong>b</strong> 都是浮点型。</p>&#13;
<hr/>&#13;
<h2>String（字符串）</h2>&#13;
<p>Python中的字符串用单引号 <span class="marked">'</span> 或双引号 <span class="marked">"</span> 括起来，同时使用反斜杠 <span class="marked">\</span> 转义特殊字符。</p>&#13;
<p>字符串的截取的语法格式如下：</p> <pre>变量[头下标:尾下标]</pre><p>索引值以 0 为开始值，-1 为从末尾的开始位置。</p>&#13;
<p><img decoding="async" src="https://static.jyshare.com/wp-content/uploads/123456-20200923-1.svg"/></p>&#13;
<p>加号  <span class="marked">+</span>  是字符串的连接符， 星号  <span class="marked">*</span>  表示复制当前字符串，与之结合的数字为复制的次数。实例如下：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'Runoob'</span>  <span style="color: #a50"># 定义一个字符串变量</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">)</span>           <span style="color: #a50"># 打印整个字符串</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span>:-<span style="color: Maroon;">1</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>     <span style="color: #a50"># 打印字符串第一个到倒数第二个字符（不包含倒数第一个字符）</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>        <span style="color: #a50"># 打印字符串的第一个字符</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Maroon;">5</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>      <span style="color: #a50"># 打印字符串第三到第五个字符（包含第五个字符）</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Olive;">]</span><span style="color: Olive;">)</span>       <span style="color: #a50"># 打印字符串从第三个字符开始到末尾</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span> * <span style="color: Maroon;">2</span><span style="color: Olive;">)</span>       <span style="color: #a50"># 打印字符串两次</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">str</span> + <span style="color: #a11;">"TEST"</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 打印字符串和"TEST"拼接在一起</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>执行以上程序会输出如下结果：</p>&#13;
<pre>&#13;
Runoob&#13;
Runoo&#13;
R&#13;
noo&#13;
noob&#13;
RunoobRunoob&#13;
RunoobTEST&#13;
</pre>&#13;
<p>Python 使用反斜杠 <span class="marked">\</span> 转义特殊字符，如果你不想让反斜杠发生转义，可以在字符串前面添加一个 <span class="marked">r</span>，表示原始字符串：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'Ru<span style="color: #000099; font-weight: bold;">\n</span>oob'</span><span style="color: Olive;">)</span><br/>
Ru<br/>
oob<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>r<span style="color: #a11;">'Ru<span style="color: #000099; font-weight: bold;">\n</span>oob'</span><span style="color: Olive;">)</span><br/>
Ru\noob<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <br/>
</div></div>&#13;
&#13;
<p>&#13;
另外，反斜杠(\)可以作为续行符，表示下一行是上一行的延续。也可以使用 <b>"""..."""</b> 或者 <b>'''...'''</b> 跨越多行。&#13;
</p>&#13;
&#13;
&#13;
<p>注意，Python 没有单独的字符类型，一个字符就是长度为1的字符串。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> word <span style="color: Gray;">=</span> <span style="color: #a11;">'Python'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>word<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> word<span style="color: Olive;">[</span><span style="color: Maroon;">5</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
P n<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>word<span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> word<span style="color: Olive;">[</span>-<span style="color: Maroon;">6</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
n P<br/>
&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
<p>与 C 字符串不同的是，Python 字符串不能被改变。向一个索引位置赋值，比如 <span class="marked">word[0] = 'm'</span> 会导致错误。&#13;
</p>&#13;
<p>&#13;
<b>注意：</b></p>&#13;
<ul>&#13;
<li>&#13;
1、反斜杠可以用来转义，使用r可以让反斜杠不发生转义。</li><li>&#13;
2、字符串可以用+运算符连接在一起，用*运算符重复。</li><li>&#13;
3、Python中的字符串有两种索引方式，从左往右以0开始，从右往左以-1开始。</li><li>&#13;
4、Python中的字符串不能改变。</li></ul><hr/>&#13;
<h2>bool（布尔类型）</h2>&#13;
<p>布尔类型即 True 或 False。</p><p>在 Python 中，True 和 False 都是关键字，表示布尔值。</p>&#13;
<p>布尔类型可以用来控制程序的流程，比如判断某个条件是否成立，或者在某个条件满足时执行某段代码。</p>&#13;
<p>布尔类型特点：</p>&#13;
<ul><li><p>布尔类型只有两个值：True 和 False。</p></li>&#13;
<li><p>bool 是 int 的子类，因此布尔值可以被看作整数来使用，其中 True 等价于 1。</p></li>&#13;
<li><p>布尔类型可以和其他数据类型进行比较，比如数字、字符串等。在比较时，Python 会将 True 视为 1，False 视为 0。</p></li><li><p>布尔类型可以和逻辑运算符一起使用，包括 and、or 和 not。这些运算符可以用来组合多个布尔表达式，生成一个新的布尔值。</p></li><li><p>布尔类型也可以被转换成其他数据类型，比如整数、浮点数和字符串。在转换时，True 会被转换成 1，False 会被转换成 0。</p></li>&#13;
<li>可以使用 <code>bool()</code> 函数将其他类型的值转换为布尔值。以下值在转换为布尔值时为 <code>False</code>：<code>None</code>、<code>False</code>、零 (<code>0</code>、<code>0.0</code>、<code>0j</code>)、空序列（如 <code>''</code>、<code>()</code>、<code>[]</code>）和空映射（如 <code>{}</code>）。其他所有值转换为布尔值时均为 <code>True</code>。</li>&#13;
</ul>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50"># 布尔类型的值和类型</span><br/>
a <span style="color: Gray;">=</span> <span style="color: Teal;">True</span><br/>
b <span style="color: Gray;">=</span> <span style="color: Teal;">False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">type</span><span style="color: Olive;">(</span>a<span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># &lt;class 'bool'&gt;</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">type</span><span style="color: Olive;">(</span>b<span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># &lt;class 'bool'&gt;</span><br/>
<br/>
<span style="color: #a50"># 布尔类型的整数表现</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">int</span><span style="color: Olive;">(</span><span style="color: Teal;">True</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 1</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">int</span><span style="color: Olive;">(</span><span style="color: Teal;">False</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 0</span><br/>
<br/>
<span style="color: #a50"># 使用 bool() 函数进行转换</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: Maroon;">0</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>         <span style="color: #a50"># False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: Maroon;">42</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>        <span style="color: #a50"># True</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: #a11;">''</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>        <span style="color: #a50"># False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: #a11;">'Python'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># True</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>        <span style="color: #a50"># False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">bool</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span> <span style="color: #a50"># True</span><br/>
<br/>
<span style="color: #a50"># 布尔逻辑运算</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">True</span> <span style="color: Green;font-weight:bold;">and</span> <span style="color: Teal;">False</span><span style="color: Olive;">)</span>  <span style="color: #a50"># False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Teal;">True</span> <span style="color: Green;font-weight:bold;">or</span> <span style="color: Teal;">False</span><span style="color: Olive;">)</span>   <span style="color: #a50"># True</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">True</span><span style="color: Olive;">)</span>        <span style="color: #a50"># False</span><br/>
<br/>
<span style="color: #a50"># 布尔比较运算</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span> <span style="color: Gray;">&gt;</span> <span style="color: Maroon;">3</span><span style="color: Olive;">)</span>  <span style="color: #a50"># True</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Maroon;">2</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span> <span style="color: #a50"># True</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Maroon;">7</span> <span style="color: Gray;">&lt;</span> <span style="color: Maroon;">4</span><span style="color: Olive;">)</span>  <span style="color: #a50"># False</span><br/>
<br/>
<span style="color: #a50"># 布尔值在控制流中的应用</span><br/>
<span style="color: Green;font-weight:bold;">if</span> <span style="color: Teal;">True</span>:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"This will always print"</span><span style="color: Olive;">)</span><br/>
    <br/>
<span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">False</span>:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"This will also always print"</span><span style="color: Olive;">)</span><br/>
    <br/>
x <span style="color: Gray;">=</span> <span style="color: Maroon;">10</span><br/>
<span style="color: Green;font-weight:bold;">if</span> x:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"x is non-zero and thus True in a boolean context"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p><strong>注意:</strong> 在 Python 中，所有非零的数字和非空的字符串、列表、元组等数据类型都被视为 True，只有 <strong>0、空字符串、空列表、空元组</strong>等被视为 False。因此，在进行布尔类型转换时，需要注意数据类型的真假性。</p>&#13;
<hr/>&#13;
<h2>List（列表）</h2>&#13;
<p>List（列表） 是 Python 中使用最频繁的数据类型。</p>&#13;
<p>列表可以完成大多数集合类的数据结构实现。列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）。</p>&#13;
<p>列表是写在方括号 <span class="marked">[]</span> 之间、用逗号分隔开的元素列表。</p>&#13;
<p>&#13;
和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。&#13;
</p>&#13;
<p>列表截取的语法格式如下：</p> <pre>变量[头下标:尾下标]</pre><p>索引值以 <span class="marked">0</span> 为开始值，<span class="marked">-1</span> 为从末尾的开始位置。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/08/list_slicing1_new1.png"/></p>&#13;
<p>加号 <span class="marked">+</span> 是列表连接运算符，星号 <span class="marked">*</span> 是重复操作。如下实例：&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Teal;">list</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span> <span style="color: #a11;">'abcd'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">786</span> <span style="color: Gray;">,</span> <span style="color: Maroon;">2.23</span><span style="color: Gray;">,</span> <span style="color: #a11;">'runoob'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">70.2</span> <span style="color: Olive;">]</span>  <span style="color: #a50"># 定义一个列表</span><br/>
tinylist <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">123</span><span style="color: Gray;">,</span> <span style="color: #a11;">'runoob'</span><span style="color: Olive;">]</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">list</span><span style="color: Olive;">)</span>            <span style="color: #a50"># 打印整个列表</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">list</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>         <span style="color: #a50"># 打印列表的第一个元素</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">list</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span>:<span style="color: Maroon;">3</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>       <span style="color: #a50"># 打印列表第二到第四个元素（不包含第四个元素）</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">list</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Olive;">]</span><span style="color: Olive;">)</span>        <span style="color: #a50"># 打印列表从第三个元素开始到末尾</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>tinylist * <span style="color: Maroon;">2</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 打印tinylist列表两次</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">list</span> + tinylist<span style="color: Olive;">)</span>  <span style="color: #a50"># 打印两个列表拼接在一起的结果</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
['abcd', 786, 2.23, 'runoob', 70.2]&#13;
abcd&#13;
[786, 2.23]&#13;
[2.23, 'runoob', 70.2]&#13;
[123, 'runoob', 123, 'runoob']&#13;
['abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob']&#13;
</pre>&#13;
&#13;
<p>与Python字符串不一样的是，列表中的元素是可以改变的：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Maroon;">9</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Maroon;">5</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">13</span><span style="color: Gray;">,</span> <span style="color: Maroon;">14</span><span style="color: Gray;">,</span> <span style="color: Maroon;">15</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">9</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">13</span><span style="color: Gray;">,</span> <span style="color: Maroon;">14</span><span style="color: Gray;">,</span> <span style="color: Maroon;">15</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Maroon;">5</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span>   <span style="color: #a50"># 将对应的元素值设置为 [] </span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">9</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">]</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>List 内置了有很多方法，例如 append()、pop() 等等，这在后面会讲到。</p>&#13;
<p><b>注意：</b></p>&#13;
<ul><li>&#13;
1、列表写在方括号之间，元素用逗号隔开。</li><li>&#13;
2、和字符串一样，列表可以被索引和切片。</li><li>&#13;
3、列表可以使用 <span class="marked">+</span> 操作符进行拼接。</li><li>&#13;
4、列表中的元素是可以改变的。</li>&#13;
</ul>&#13;
<p>Python 列表截取可以接收第三个参数，参数作用是截取的步长，以下实例在索引 1 到索引 4 的位置并设置为步长为 2（间隔一个位置）来截取字符串：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/08/py-dict-1.png"/></p>&#13;
&#13;
<p>如果第三个参数为负数表示逆向读取，以下实例用于翻转字符串：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">def</span> reverseWords<span style="color: Olive;">(</span><span style="color: Teal;">input</span><span style="color: Olive;">)</span>: <br/>
      <br/>
    <span style="color: #a50"># 通过空格将字符串分隔符，把各个单词分隔为列表</span><br/>
    inputWords <span style="color: Gray;">=</span> <span style="color: Teal;">input</span>.<span style="color: #05a;">split</span><span style="color: Olive;">(</span><span style="color: #a11;">" "</span><span style="color: Olive;">)</span> <br/>
  <br/>
    <span style="color: #a50"># 翻转字符串</span><br/>
    <span style="color: #a50"># 假设列表 list = [1,2,3,4],  </span><br/>
    <span style="color: #a50"># list[0]=1, list[1]=2 ，而 -1 表示最后一个元素 list[-1]=4 ( 与 list[3]=4 一样) </span><br/>
    <span style="color: #a50"># inputWords[-1::-1] 有三个参数</span><br/>
    <span style="color: #a50"># 第一个参数 -1 表示最后一个元素</span><br/>
    <span style="color: #a50"># 第二个参数为空，表示移动到列表末尾</span><br/>
    <span style="color: #a50"># 第三个参数为步长，-1 表示逆向</span><br/>
    inputWords<span style="color: Gray;">=</span>inputWords<span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span>::-<span style="color: Maroon;">1</span><span style="color: Olive;">]</span> <br/>
  <br/>
    <span style="color: #a50"># 重新组合字符串</span><br/>
    output <span style="color: Gray;">=</span> <span style="color: #a11;">' '</span>.<span style="color: #05a;">join</span><span style="color: Olive;">(</span>inputWords<span style="color: Olive;">)</span> <br/>
      <br/>
    <span style="color: Green;font-weight:bold;">return</span> output <br/>
  <br/>
<span style="color: Green;font-weight:bold;">if</span> __name__ <span style="color: Gray;">==</span> <span style="color: #a11;">"__main__"</span>: <br/>
    <span style="color: Teal;">input</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'I like runoob'</span><br/>
    rw <span style="color: Gray;">=</span> reverseWords<span style="color: Olive;">(</span><span style="color: Teal;">input</span><span style="color: Olive;">)</span> <br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>rw<span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>输出结果为：</p>&#13;
<pre>runoob like I</pre>&#13;
<hr/><h2>Tuple（元组）</h2>&#13;
<p>元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 <span class="marked">()</span> 里，元素之间用逗号隔开。&#13;
</p><p>元组中的元素类型也可以不相同：&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Teal;">tuple</span> <span style="color: Gray;">=</span> <span style="color: Olive;">(</span> <span style="color: #a11;">'abcd'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">786</span> <span style="color: Gray;">,</span> <span style="color: Maroon;">2.23</span><span style="color: Gray;">,</span> <span style="color: #a11;">'runoob'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">70.2</span>  <span style="color: Olive;">)</span><br/>
tinytuple <span style="color: Gray;">=</span> <span style="color: Olive;">(</span><span style="color: Maroon;">123</span><span style="color: Gray;">,</span> <span style="color: #a11;">'runoob'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">tuple</span><span style="color: Olive;">)</span>             <span style="color: #a50"># 输出完整元组</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">tuple</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>          <span style="color: #a50"># 输出元组的第一个元素</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">tuple</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span>:<span style="color: Maroon;">3</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>        <span style="color: #a50"># 输出从第二个元素开始到第三个元素</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">tuple</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Olive;">]</span><span style="color: Olive;">)</span>         <span style="color: #a50"># 输出从第三个元素开始的所有元素</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>tinytuple * <span style="color: Maroon;">2</span><span style="color: Olive;">)</span>     <span style="color: #a50"># 输出两次元组</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">tuple</span> + tinytuple<span style="color: Olive;">)</span> <span style="color: #a50"># 连接元组</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
('abcd', 786, 2.23, 'runoob', 70.2)&#13;
abcd&#13;
(786, 2.23)&#13;
(2.23, 'runoob', 70.2)&#13;
(123, 'runoob', 123, 'runoob')&#13;
('abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob')&#13;
</pre>&#13;
<p>元组与字符串类似，可以被索引且下标索引从0开始，-1 为从末尾开始的位置。也可以进行截取（看上面，这里不再赘述）。</p>&#13;
<p>其实，可以把字符串看作一种特殊的元组。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> tup <span style="color: Gray;">=</span> <span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>tup<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">1</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>tup<span style="color: Olive;">[</span><span style="color: Maroon;">1</span>:<span style="color: Maroon;">5</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tup<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Maroon;">11</span>  <span style="color: #a50"># 修改元组元素的操作是非法的</span><br/>
Traceback <span style="color: Olive;">(</span>most recent call last<span style="color: Olive;">)</span>:<br/>
  File <span style="color: #a11;">"&lt;stdin&gt;"</span><span style="color: Gray;">,</span> line <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Green;font-weight:bold;">in</span> <span style="color: Gray;">&lt;</span>module<span style="color: Gray;">&gt;</span><br/>
<span style="color: Teal;">TypeError</span>: <span style="color: #a11;">'tuple'</span> <span style="color: Teal;">object</span> does <span style="color: Green;font-weight:bold;">not</span> support item assignment<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <br/>
&#13;
</div>&#13;
</div>&#13;
<p>虽然tuple的元素不可改变，但它可以包含可变的对象，比如list列表。&#13;
</p><p>&#13;
构造包含 0 个或 1 个元素的元组比较特殊，所以有一些额外的语法规则：&#13;
</p>&#13;
<pre>&#13;
tup1 = ()    # 空元组&#13;
tup2 = (20,) # 一个元素，需要在元素后添加逗号&#13;
</pre>&#13;
<p>如果你想创建只有一个元素的元组，需要注意在元素后面添加一个逗号，以区分它是一个元组而不是一个普通的值，这是因为在没有逗号的情况下，Python会将括号解释为数学运算中的括号，而不是元组的表示。</p>&#13;
<p>如果不添加逗号，如下所示，它将被解释为一个普通的值而不是元组：</p>&#13;
<pre>not_a_tuple = (42)</pre><p>这样的话，not_a_tuple 将是整数类型而不是元组类型。</p>&#13;
<p>string、list 和 tuple 都属于 sequence（序列）。</p>&#13;
<p><b>注意：</b></p>&#13;
<ul><li>&#13;
1、与字符串一样，元组的元素不能修改。</li><li>&#13;
2、元组也可以被索引和切片，方法一样。</li><li>&#13;
3、注意构造包含 0 或 1 个元素的元组的特殊语法规则。</li><li>&#13;
4、元组也可以使用 <span class="marked">+</span> 操作符进行拼接。</li></ul>&#13;
<hr/><h2>Set（集合）</h2>&#13;
<p>&#13;
Python 中的集合（Set）是一种无序、可变的数据类型，用于存储唯一的元素。</p>&#13;
<p>集合中的元素不会重复，并且可以进行交集、并集、差集等常见的集合操作。</p>&#13;
<p>&#13;
在 Python 中，集合使用大括号 <span class="marked">{}</span> 表示，元素之间用逗号 <span class="marked">,</span> 分隔。</p>&#13;
<p>另外，也可以使用 <span class="marked">set()</span> 函数创建集合。</p><p><strong>注意：</strong>创建一个空集合必须用<span class="marked"> set()</span> 而不是 <span class="marked">{ }</span>，因为 <span class="marked">{ }</span> 是用来创建一个空字典。&#13;
</p>&#13;
<p>创建格式：</p>&#13;
<pre>parame = {value01,value02,...}&#13;
或者&#13;
set(value)</pre>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
sites <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Facebook'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Zhihu'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Baidu'</span><span style="color: Olive;">}</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>sites<span style="color: Olive;">)</span>   <span style="color: #a50"># 输出集合，重复的元素被自动去掉</span><br/>
<br/>
<span style="color: #a50"># 成员测试</span><br/>
<span style="color: Green;font-weight:bold;">if</span> <span style="color: #a11;">'Runoob'</span> <span style="color: Green;font-weight:bold;">in</span> sites :<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'Runoob 在集合中'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">else</span> :<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'Runoob 不在集合中'</span><span style="color: Olive;">)</span><br/>
<br/>
<br/>
<span style="color: #a50"># set可以进行集合运算</span><br/>
a <span style="color: Gray;">=</span> <span style="color: Teal;">set</span><span style="color: Olive;">(</span><span style="color: #a11;">'abracadabra'</span><span style="color: Olive;">)</span><br/>
b <span style="color: Gray;">=</span> <span style="color: Teal;">set</span><span style="color: Olive;">(</span><span style="color: #a11;">'alacazam'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a - b<span style="color: Olive;">)</span>     <span style="color: #a50"># a 和 b 的差集</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a | b<span style="color: Olive;">)</span>     <span style="color: #a50"># a 和 b 的并集</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a &amp; b<span style="color: Olive;">)</span>     <span style="color: #a50"># a 和 b 的交集</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a ^ b<span style="color: Olive;">)</span>     <span style="color: #a50"># a 和 b 中不同时存在的元素</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
{'Zhihu', 'Baidu', 'Taobao', 'Runoob', 'Google', 'Facebook'}&#13;
Runoob 在集合中&#13;
{'b', 'c', 'a', 'r', 'd'}&#13;
{'r', 'b', 'd'}&#13;
{'b', 'c', 'a', 'z', 'm', 'r', 'l', 'd'}&#13;
{'c', 'a'}&#13;
{'z', 'b', 'm', 'r', 'l', 'd'}&#13;
</pre>&#13;
<hr/><h2>Dictionary（字典）</h2>&#13;
<p>&#13;
字典（dictionary）是Python中另一个非常有用的内置数据类型。</p>&#13;
<p>列表是有序的对象集合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。</p>&#13;
<p>字典是一种映射类型，字典用 <span class="marked">{ }</span> 标识，它是一个无序的 <b>键(key) : 值(value)</b> 的集合。</p>&#13;
<p>键(key)必须使用不可变类型。</p>&#13;
<p>在同一个字典中，键(key)必须是唯一的。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Teal;">dict</span> <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: Olive;">}</span><br/>
<span style="color: Teal;">dict</span><span style="color: Olive;">[</span><span style="color: #a11;">'one'</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: #a11;">"1 - 菜鸟教程"</span><br/>
<span style="color: Teal;">dict</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Olive;">]</span>     <span style="color: Gray;">=</span> <span style="color: #a11;">"2 - 菜鸟工具"</span><br/>
<br/>
tinydict <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'name'</span>: <span style="color: #a11;">'runoob'</span><span style="color: Gray;">,</span><span style="color: #a11;">'code'</span>:<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'site'</span>: <span style="color: #a11;">'www.runoob.com'</span><span style="color: Olive;">}</span><br/>
<br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">dict</span><span style="color: Olive;">[</span><span style="color: #a11;">'one'</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>       <span style="color: #a50"># 输出键为 'one' 的值</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">dict</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>           <span style="color: #a50"># 输出键为 2 的值</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>tinydict<span style="color: Olive;">)</span>          <span style="color: #a50"># 输出完整的字典</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>tinydict.<span style="color: #05a;">keys</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 输出所有键</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>tinydict.<span style="color: #05a;">values</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span> <span style="color: #a50"># 输出所有值</span><br/>
&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
1 - 菜鸟教程&#13;
2 - 菜鸟工具&#13;
{'name': 'runoob', 'code': 1, 'site': 'www.runoob.com'}&#13;
dict_keys(['name', 'code', 'site'])&#13;
dict_values(['runoob', 1, 'www.runoob.com'])&#13;
</pre>&#13;
<p>构造函数 dict() 可以直接从键值对序列中构建字典如下：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;

<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">dict</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: Olive;">(</span><span style="color: #a11;">'Runoob'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">'Taobao'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Olive;">)</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">3</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">{</span>x: x**<span style="color: Maroon;">2</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">)</span><span style="color: Olive;">}</span><br/>
<span style="color: Olive;">{</span><span style="color: Maroon;">2</span>: <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span>: <span style="color: Maroon;">16</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span>: <span style="color: Maroon;">36</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">dict</span><span style="color: Olive;">(</span>Runoob<span style="color: Gray;">=</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> Google<span style="color: Gray;">=</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> Taobao<span style="color: Gray;">=</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">3</span><span style="color: Olive;">}</span><br/>
&#13;
</div>&#13;
</div>&#13;
&#13;
<p><span class="marked">{x: x**2 for x in (2, 4, 6)}</span> 该代码使用的是字典推导式，更多推导式内容可以参考：<a href="https://www.runoob.com/python3/python-comprehensions.html" rel="noopener" target="_blank">Python 推导式</a>。</p>&#13;
<p>另外，字典类型也有一些内置的函数，例如 clear()、keys()、values() 等。</p>&#13;
<p><b>注意：</b></p>&#13;
<ul><li>&#13;
1、字典是一种映射类型，它的元素是键值对。</li><li>&#13;
2、字典的关键字必须为不可变类型，且不能重复。</li><li>&#13;
3、创建空字典使用 <b>{ }</b>。</li></ul><hr/>&#13;
<h2>bytes 类型</h2>&#13;
&#13;
<p>在 Python3 中，bytes 类型表示的是不可变的二进制序列（byte sequence）。</p><p>与字符串类型不同的是，bytes 类型中的元素是整数值（0 到 255 之间的整数），而不是 Unicode 字符。</p>&#13;
<p>&#13;
bytes 类型通常用于处理二进制数据，比如图像文件、音频文件、视频文件等等。在网络编程中，也经常使用 bytes 类型来传输二进制数据。</p>&#13;
<p>&#13;
创建 bytes 对象的方式有多种，最常见的方式是使用 b 前缀：</p>&#13;
<p>&#13;
此外，也可以使用 bytes() 函数将其他类型的对象转换为 bytes 类型。bytes() 函数的第一个参数是要转换的对象，第二个参数是编码方式，如果省略第二个参数，则默认使用 UTF-8 编码：</p>&#13;
<pre>x = bytes("hello", encoding="utf-8")</pre><p>&#13;
与字符串类型类似，bytes 类型也支持许多操作和方法，如切片、拼接、查找、替换等等。同时，由于 bytes 类型是不可变的，因此在进行修改操作时需要创建一个新的 bytes 对象。例如：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<br/>
x <span style="color: Gray;">=</span> b<span style="color: #a11;">"hello"</span><br/>
y <span style="color: Gray;">=</span> x<span style="color: Olive;">[</span><span style="color: Maroon;">1</span>:<span style="color: Maroon;">3</span><span style="color: Olive;">]</span>  <span style="color: #a50"># 切片操作，得到 b"el"</span><br/>
z <span style="color: Gray;">=</span> x + b<span style="color: #a11;">"world"</span>  <span style="color: #a50"># 拼接操作，得到 b"helloworld"</span><br/>
</div></div>&#13;
<p>需要注意的是，bytes 类型中的元素是整数值，因此在进行比较操作时需要使用相应的整数值。例如：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
x <span style="color: Gray;">=</span> b<span style="color: #a11;">"hello"</span><br/>
<span style="color: Green;font-weight:bold;">if</span> x<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span> <span style="color: Gray;">==</span> <span style="color: Teal;">ord</span><span style="color: Olive;">(</span><span style="color: #a11;">"h"</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"The first element is 'h'"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>其中 ord() 函数用于将字符转换为相应的整数值。</p>&#13;
<hr/>&#13;
<h2>Python数据类型转换</h2>&#13;
<p>&#13;
有时候，我们需要对数据内置的类型进行转换，数据类型的转换，你只需要将数据类型作为函数名即可，在下一章节 <a href="https://www.runoob.com/python3/python3-type-conversion.html" rel="noopener" target="_blank">Python3 数据类型转换</a> 会具体介绍。</p>&#13;
<p>&#13;
以下几个内置的函数可以执行数据类型之间的转换。这些函数返回一个新的对象，表示转换的值。</p>&#13;
<table class="reference">&#13;
<tbody><tr><th>函数</th><th>描述</th></tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-int.html" target="_blank" rel="noopener noreferrer">int(x [,base])</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将x转换为一个整数</p>&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-float.html" target="_blank" rel="noopener noreferrer">float(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将x转换到一个浮点数</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-complex.html" target="_blank" rel="noopener noreferrer">complex(real [,imag])</a></p>&#13;
</td>&#13;
<td>&#13;
<p>创建一个复数</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-str.html" target="_blank" rel="noopener noreferrer">str(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将对象 x 转换为字符串</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-repr.html" target="_blank" rel="noopener noreferrer">repr(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将对象 x 转换为表达式字符串</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-eval.html" target="_blank" rel="noopener noreferrer">eval(str)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>用来计算在字符串中的有效Python表达式,并返回一个对象</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="/python3/python3-func-tuple.html" target="_blank" rel="noopener noreferrer">tuple(s)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将序列 s 转换为一个元组</p>&#13;
&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python3-att-list-list.html" target="_blank" rel="noopener noreferrer">list(s)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>将序列 s 转换为一个列表</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-set.html" target="_blank" rel="noopener noreferrer">set(s)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>转换为可变集合</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-dict.html" target="_blank" rel="noopener noreferrer">dict(d)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>创建一个字典。d 必须是一个 (key, value)元组序列。</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-frozenset.html" target="_blank" rel="noopener noreferrer">frozenset(s)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>转换为不可变集合</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-chr.html" target="_blank" rel="noopener noreferrer">chr(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>  将一个整数转换为一个字符</p>&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-ord.html" target="_blank" rel="noopener noreferrer">ord(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p> 将一个字符转换为它的整数值</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-hex.html" target="_blank" rel="noopener noreferrer">hex(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p>  将一个整数转换为一个十六进制字符串</p>&#13;
</td>&#13;
</tr>&#13;
<tr valign="top">&#13;
<td>&#13;
<p><a href="python-func-oct.html" target="_blank" rel="noopener noreferrer">oct(x)</a></p>&#13;
</td>&#13;
<td>&#13;
<p> 将一个整数转换为一个八进制字符串</p>&#13;
</td>&#13;
</tr>&#13;
</tbody></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>