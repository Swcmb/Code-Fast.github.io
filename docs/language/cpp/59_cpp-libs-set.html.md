<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 容器类 <set></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 容器类 <code>&lt;set&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;set&gt;</code> 是一个关联容器，它存储了一组唯一的元素，并按照一定的顺序进行排序。</p><p><code>&lt;set&gt;</code> 提供了高效的元素查找、插入和删除操作。它是基于红黑树实现的，因此具有对数时间复杂度的查找、插入和删除性能。</p>&#13;
&#13;
<p><code>&lt;set&gt;</code> 容器中存储的元素类型必须满足以下条件：</p>&#13;
<ul>&#13;
<li>元素类型必须可以比较大小。</li>&#13;
<li>元素类型必须可以被复制和赋值。</li>&#13;
</ul>&#13;
<h3>语法</h3>&#13;
<p>包含头文件:</p>&#13;
<pre>#include &lt;set&gt;</pre>&#13;
<p>声明 set 容器</p>&#13;
<pre>std::set&lt;元素类型&gt; 容器名;</pre>&#13;
<h3>常用操作</h3>&#13;
<ul>&#13;
<li><code>insert(元素)</code>: 插入一个元素。</li>&#13;
<li><code>erase(元素)</code>: 删除一个元素。</li>&#13;
<li><code>find(元素)</code>: 查找一个元素。</li>&#13;
<li><code>size()</code>: 返回容器中元素的数量。</li>&#13;
<li><code>empty()</code>: 检查容器是否为空。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;set&gt;</code> 的简单示例，包括元素的插入、查找、删除和输出结果。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;set&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 声明一个整型 set 容器</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">set</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> mySet<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 插入元素</span><br/>
    mySet.<span style="color: #007788;">insert</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    mySet.<span style="color: #007788;">insert</span><span style="color: #008000;">(</span><span style="color: #0000dd;">20</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    mySet.<span style="color: #007788;">insert</span><span style="color: #008000;">(</span><span style="color: #0000dd;">30</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    mySet.<span style="color: #007788;">insert</span><span style="color: #008000;">(</span><span style="color: #0000dd;">40</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出 set 中的元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Set contains: "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> num <span style="color: #008080;">:</span> mySet<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 查找元素</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>mySet.<span style="color: #007788;">find</span><span style="color: #008000;">(</span><span style="color: #0000dd;">20</span><span style="color: #008000;">)</span> <span style="color: #000040;">!</span><span style="color: #000080;">=</span> mySet.<span style="color: #007788;">end</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"20 is in the set."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"20 is not in the set."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 删除元素</span><br/>
    mySet.<span style="color: #007788;">erase</span><span style="color: #008000;">(</span><span style="color: #0000dd;">20</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 再次输出 set 中的元素</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"After erasing 20, set contains: "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> num <span style="color: #008080;">:</span> mySet<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 检查 set 是否为空</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>mySet.<span style="color: #007788;">empty</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"The set is empty."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"The set is not empty."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 输出 set 中元素的数量</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"The set contains "</span> <span style="color: #000080;">&lt;&lt;</span> mySet.<span style="color: #007788;">size</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" elements."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果:</p>&#13;
<pre>Set contains: 10 20 30 40 &#13;
20 is in the set.&#13;
After erasing 20, set contains: 10 30 40 &#13;
The set is not empty.&#13;
The set contains 3 elements.</pre>&#13;
<h2>总结</h2>&#13;
<p><code>&lt;set&gt;</code> 是 C++ 标准库中一个非常有用的容器，特别适合需要快速查找、插入和删除操作的场景。通过上述示例，初学者可以对 <code>&lt;set&gt;</code> 的基本用法有一个清晰的了解。在实际开发中，合理利用 <code>&lt;set&gt;</code> 可以提高程序的效率和可读性。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>