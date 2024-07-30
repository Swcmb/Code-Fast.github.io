<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 算法库 <algorithm></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 算法库 <code>&lt;algorithm&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;algorithm&gt;</code> 头文件提供了一组用于操作容器（如数组、向量、列表等）的算法。这些算法包括排序、搜索、复制、比较等，它们是编写高效、可重用代码的重要工具。</p>&#13;
&#13;
<p><code>&lt;algorithm&gt;</code> 头文件定义了一组模板函数，这些函数可以应用于任何类型的容器，只要容器支持迭代器。这些算法通常接受两个或更多的迭代器作为参数，表示操作的起始和结束位置。</p>&#13;
<h3>语法</h3>&#13;
<p>大多数 <code>&lt;algorithm&gt;</code> 中的函数都遵循以下基本语法：</p>&#13;
<pre>algorithm_name(container.begin(), container.end(), ...);</pre>&#13;
<p>这里的 <code>container</code> 是一个容器对象，<code>begin()</code> 和 <code>end()</code> 是容器的成员函数，返回指向容器开始和结束的迭代器。</p>&#13;
<h2>实例</h2>&#13;
1. 排序算法&#13;
<p>函数：sort</p><p>&#13;
定义：对容器中的元素进行排序。</p>&#13;
&#13;
<p>语法：</p>&#13;
<pre>&#13;
sort(container.begin(), container.end(), compare_function);</pre>&#13;
&#13;
&#13;
<p>其中 compare_function 是一个可选的比较函数，用于自定义排序方式。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;algorithm&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> numbers <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">5</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">9</span>, <span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">5</span>, <span style="color: #0000dd;">6</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">sort</span><span style="color: #008000;">(</span>numbers.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, numbers.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> num <span style="color: #008080;">:</span> numbers<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
1 2 5 5 6 9 </pre><h3>&#13;
2. 搜索算法</h3>&#13;
<p>函数：find</p><p>&#13;
定义：在容器中查找与给定值匹配的第一个元素。</p><p>&#13;
&#13;
语法：</p>&#13;
<pre>&#13;
auto it = find(container.begin(), container.end(), value);</pre><p>&#13;
如果找到，it 将指向匹配的元素；如果没有找到，it 将等于 container.end()。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;algorithm&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> numbers <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">auto</span> it <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">find</span><span style="color: #008000;">(</span>numbers.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, numbers.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, <span style="color: #0000dd;">3</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>it <span style="color: #000040;">!</span><span style="color: #000080;">=</span> numbers.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Found: "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #000040;">*</span>it <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Value not found."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Found: 3</pre>&#13;
<h3>3. 复制算法</h3><p>&#13;
函数：copy</p><p>&#13;
定义：将一个范围内的元素复制到另一个容器或数组。</p>&#13;
<p>&#13;
语法：</p>&#13;
<pre>&#13;
copy(source_begin, source_end, destination_begin);</pre>&#13;
<p>实例：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;algorithm&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> source <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> destination<span style="color: #008000;">[</span><span style="color: #0000dd;">5</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">copy</span><span style="color: #008000;">(</span>source.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, source.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, destination<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> destination<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
1 2 3 4 5 </pre><h3>&#13;
4. 比较算法</h3><p>&#13;
函数：equal</p><p>&#13;
定义：比较两个容器或两个范围内的元素是否相等。</p>&#13;
<p>&#13;
语法：</p>&#13;
<pre>&#13;
bool result = equal(first1, last1, first2);&#13;
&#13;
或&#13;
&#13;
bool result = equal(first1, last1, first2, compare_function);</pre>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;algorithm&gt;</span><br/>
<span style="color: #060;">#include &lt;vector&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v1 <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">vector</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> v2 <span style="color: #000080;">=</span> <span style="color: #008000;">{</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">2</span>, <span style="color: #0000dd;">3</span>, <span style="color: #0000dd;">4</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">bool</span> are_equal <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">equal</span><span style="color: #008000;">(</span>v1.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v1.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>, v2.<span style="color: #007788;">begin</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #008000;">(</span>are_equal <span style="color: #008080;">?</span> <span style="color: #a11;">"Vectors are equal."</span> <span style="color: #008080;">:</span> <span style="color: #a11;">"Vectors are not equal."</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Vectors are equal.</pre>&#13;
&#13;
<p><code>&lt;algorithm&gt;</code> 是 C++ 标准库中一个非常强大的工具，它提供了大量通用的算法，可以极大地简化编程</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>