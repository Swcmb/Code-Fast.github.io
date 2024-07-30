<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python 推导式</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python 推导式</h1>&#13;
&#13;
<p>Python 推导式是一种独特的数据处理方式，可以从一个数据序列构建另一个新的数据序列的结构体。</p>&#13;
<p>&#13;
Python 推导式是一种强大且简洁的语法，适用于生成列表、字典、集合和生成器。</p><p>在使用推导式时，需要注意可读性，尽量保持表达式简洁，以免影响代码的可读性和可维护性。</p>&#13;
<p>Python 支持各种数据结构的推导式：</p>&#13;
&#13;
<ul>&#13;
  <li>列表(list)推导式</li>&#13;
  <li>字典(dict)推导式</li>&#13;
  <li>集合(set)推导式</li>&#13;
  <li>元组(tuple)推导式</li>&#13;
  </ul>&#13;
&#13;
<h2>列表推导式</h2>&#13;
<p>列表推导式格式为：</p>&#13;
<pre>[表达式 for 变量 in 列表] &#13;
[out_exp_res for out_exp in input_list]&#13;
&#13;
或者 &#13;
&#13;
[表达式 for 变量 in 列表 if 条件]&#13;
[out_exp_res for out_exp in input_list if condition]</pre>&#13;
&#13;
&#13;
<ul>&#13;
  <li>out_exp_res：列表生成元素表达式，可以是有返回值的函数。</li>&#13;
  <li>for out_exp in input_list：迭代 input_list 将 out_exp 传入到 out_exp_res 表达式中。</li>&#13;
  <li>if condition：条件语句，可以过滤列表中不符合条件的值。</li></ul>&#13;
&#13;
<p>过滤掉长度小于或等于3的字符串列表，并将剩下的转换成大写字母：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> names <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'Bob'</span><span style="color: Gray;">,</span><span style="color: #a11;">'Tom'</span><span style="color: Gray;">,</span><span style="color: #a11;">'alice'</span><span style="color: Gray;">,</span><span style="color: #a11;">'Jerry'</span><span style="color: Gray;">,</span><span style="color: #a11;">'Wendy'</span><span style="color: Gray;">,</span><span style="color: #a11;">'Smith'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> new_names <span style="color: Gray;">=</span> <span style="color: Olive;">[</span>name.<span style="color: #05a;">upper</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Green;font-weight:bold;">for</span> name <span style="color: Green;font-weight:bold;">in</span> names <span style="color: Green;font-weight:bold;">if</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>name<span style="color: Olive;">)</span><span style="color: Gray;">&gt;</span><span style="color: Maroon;">3</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>new_names<span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'ALICE'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'JERRY'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'WENDY'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'SMITH'</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>&#13;
计算 30 以内可以被 3 整除的整数：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> multiples <span style="color: Gray;">=</span> <span style="color: Olive;">[</span>i <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">30</span><span style="color: Olive;">)</span> <span style="color: Green;font-weight:bold;">if</span> i % <span style="color: Maroon;">3</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>multiples<span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Gray;">,</span> <span style="color: Maroon;">15</span><span style="color: Gray;">,</span> <span style="color: Maroon;">18</span><span style="color: Gray;">,</span> <span style="color: Maroon;">21</span><span style="color: Gray;">,</span> <span style="color: Maroon;">24</span><span style="color: Gray;">,</span> <span style="color: Maroon;">27</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<h2>字典推导式</h2>&#13;
&#13;
&#13;
<p>字典推导基本格式：</p>&#13;
<pre>{ key_expr: value_expr for value in collection }&#13;
&#13;
或&#13;
&#13;
{ key_expr: value_expr for value in collection if condition }</pre>&#13;
&#13;
<p>使用字符串及其长度创建字典：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
listdemo <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'Google'</span><span style="color: Gray;">,</span><span style="color: #a11;">'Runoob'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span><span style="color: Olive;">]</span><br/>
<span style="color: #a50"># 将列表中各字符串值为键，各字符串的长度为值，组成键值对</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> newdict <span style="color: Gray;">=</span> <span style="color: Olive;">{</span>key:<span style="color: Teal;">len</span><span style="color: Olive;">(</span>key<span style="color: Olive;">)</span> <span style="color: Green;font-weight:bold;">for</span> key <span style="color: Green;font-weight:bold;">in</span> listdemo<span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> newdict<br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'Google'</span>: <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Runoob'</span>: <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: #a11;">'Taobao'</span>: <span style="color: Maroon;">6</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
&#13;
<p>提供三个数字，以三个数字为键，三个数字的平方为值来创建字典：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> dic <span style="color: Gray;">=</span> <span style="color: Olive;">{</span>x: x**<span style="color: Maroon;">2</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">)</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> dic<br/>
<span style="color: Olive;">{</span><span style="color: Maroon;">2</span>: <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span>: <span style="color: Maroon;">16</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span>: <span style="color: Maroon;">36</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">type</span><span style="color: Olive;">(</span>dic<span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&lt;</span><span style="color: Green;font-weight:bold;">class</span> <span style="color: #a11;">'dict'</span><span style="color: Gray;">&gt;</span><br/>
</div></div>&#13;
<h2>集合推导式</h2>&#13;
<p>集合推导式基本格式：</p>&#13;
&#13;
<pre>{ expression for item in Sequence }&#13;
或&#13;
{ expression for item in Sequence if conditional }</pre>&#13;
<p>计算数字 1,2,3 的平方数：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> setnew <span style="color: Gray;">=</span> <span style="color: Olive;">{</span>i**<span style="color: Maroon;">2</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> setnew<br/>
<span style="color: Olive;">{</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
&#13;
<p>判断不是 abc 的字母并输出：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">{</span>x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: #a11;">'abracadabra'</span> <span style="color: Green;font-weight:bold;">if</span> x <span style="color: Green;font-weight:bold;">not</span> <span style="color: Green;font-weight:bold;">in</span> <span style="color: #a11;">'abc'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'d'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'r'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">type</span><span style="color: Olive;">(</span>a<span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&lt;</span><span style="color: Green;font-weight:bold;">class</span> <span style="color: #a11;">'set'</span><span style="color: Gray;">&gt;</span><br/>
</div></div>&#13;
&#13;
<h2>元组推导式（生成器表达式）</h2><p>&#13;
元组推导式可以利用 range 区间、元组、列表、字典和集合等数据类型，快速生成一个满足指定需求的元组。</p>&#13;
&#13;
<p>元组推导式基本格式：</p>&#13;
<pre>(expression for item in Sequence )&#13;
或&#13;
(expression for item in Sequence if conditional )</pre>&#13;
&#13;
<p>元组推导式和列表推导式的用法也完全相同，只是元组推导式是用 <span class="marked">()</span> 圆括号将各部分括起来，而列表推导式用的是中括号 <span class="marked">[]</span>，另外元组推导式返回的结果是一个生成器对象。</p>&#13;
&#13;
<p>例如，我们可以使用下面的代码生成一个包含数字 1~9 的元组：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">(</span>x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span><span style="color: Maroon;">10</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Gray;">&lt;</span>generator <span style="color: Teal;">object</span> <span style="color: Gray;">&lt;</span>genexpr<span style="color: Gray;">&gt;</span> at <span style="color: Maroon;">0x7faf6ee20a50</span><span style="color: Gray;">&gt;</span>  <span style="color: #a50"># 返回的是生成器对象</span><br/>
<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">tuple</span><span style="color: Olive;">(</span>a<span style="color: Olive;">)</span>       <span style="color: #a50"># 使用 tuple() 函数，可以直接将生成器对象转换成元组</span><br/>
<span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Olive;">)</span><br/>
</div></div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>