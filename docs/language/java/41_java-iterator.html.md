<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java Iterator（迭代器）</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java Iterator（迭代器）</h1><p><a href="java-collections.html"><img decoding="async" class="navup" src="/images/up.gif" alt="Java 集合框架"/> Java 集合框架</a></p>&#13;
<p>&#13;
Java迭代器（Iterator）是 Java 集合框架中的一种机制，是一种用于遍历集合（如列表、集合和映射等）的接口。</p><p>它提供了一种统一的方式来访问集合中的元素，而不需要了解底层集合的具体实现细节。</p>&#13;
<p>&#13;
Java Iterator（迭代器）不是一个集合，它是一种用于访问集合的方法，可用于迭代   <a href="https://www.runoob.com/java/java-arraylist.html" rel="noopener noreferrer" target="_blank">ArrayList</a> 和 <a href="https://www.runoob.com/java/java-hashset.html" rel="noopener noreferrer" target="_blank">HashSet</a> 等集合。</p>&#13;
<p>Iterator 是 Java 迭代器最简单的实现，ListIterator 是 Collection API 中的接口， 它扩展了 Iterator 接口。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2020/07/ListIterator-Class-Diagram.jpg"/></p>&#13;
<p>&#13;
迭代器接口定义了几个方法，最常用的是以下三个：</p>&#13;
<ul>&#13;
&#13;
&#13;
	<li><p><strong>next()</strong> - 返回迭代器的下一个元素，并将迭代器的指针移到下一个位置。</p></li>&#13;
&#13;
&#13;
	<li><p><strong>hasNext()</strong> -  用于判断集合中是否还有下一个元素可以访问。</p></li>&#13;
&#13;
	<li><p><strong>remove()</strong> - 从集合中删除迭代器最后访问的元素（可选操作）。</p></li></ul>&#13;
&#13;
&#13;
&#13;
&#13;
<p>Iterator 类位于 java.util 包中，使用前需要引入它，语法格式如下：</p>&#13;
&#13;
<pre>import java.util.Iterator; // 引入 Iterator 类</pre>&#13;
&#13;
<p>通过使用迭代器，我们可以逐个访问集合中的元素，而不需要使用传统的 for 循环或索引。这种方式更加简洁和灵活，并且适用于各种类型的集合。</p>&#13;
&#13;
&#13;
<h3>获取一个迭代器</h3>&#13;
&#13;
<p>集合想获取一个迭代器可以使用 iterator() 方法:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #666666; font-style: italic;">// 引入 ArrayList 和 Iterator 类</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.ArrayList</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.Iterator</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 创建集合</span><br/>
        ArrayList<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span> sites <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> ArrayList<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Google"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Runoob"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Taobao"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Zhihu"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 获取迭代器</span><br/>
        Iterator<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span> it <span style="color: #339933;">=</span> sites.<span style="color: #006633;">iterator</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 输出集合中的第一个元素</span><br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>it.<span style="color: #006633;">next</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>执行以上代码，输出结果如下：</p>&#13;
&#13;
<pre>Google</pre>&#13;
&#13;
<p>使用迭代器遍历集合时，如果在遍历过程中对集合进行了修改（例如添加或删除元素），可能会导致 ConcurrentModificationException 异常，为了避免这个问题，可以使用迭代器自身的 <strong>remove()</strong> 方法进行删除操作。</p>&#13;
<h3>循环集合元素</h3><p>&#13;
让迭代器 it 逐个返回集合中所有元素最简单的方法是使用 while 循环：</p>&#13;
&#13;
<pre>while(it.hasNext()) {&#13;
    System.out.println(it.next());&#13;
}</pre>&#13;
&#13;
<p>以下输出集合 sites 中的所有元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #666666; font-style: italic;">// 引入 ArrayList 和 Iterator 类</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.ArrayList</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.Iterator</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 创建集合</span><br/>
        ArrayList<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span> sites <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> ArrayList<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Google"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Runoob"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Taobao"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        sites.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Zhihu"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 获取迭代器</span><br/>
        Iterator<span style="color: #339933;">&lt;</span>String<span style="color: #339933;">&gt;</span> it <span style="color: #339933;">=</span> sites.<span style="color: #006633;">iterator</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<br/>
        <span style="color: #666666; font-style: italic;">// 输出集合中的所有元素</span><br/>
        <span style="color: #000000; font-weight: bold;">while</span><span style="color: #009900;">(</span>it.<span style="color: #006633;">hasNext</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>it.<span style="color: #006633;">next</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #009900;">}</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
执行以上代码，输出结果如下：</p>&#13;
&#13;
<pre>Google&#13;
Runoob&#13;
Taobao&#13;
Zhihu</pre>&#13;
<p>&#13;
删除元素</p>&#13;
&#13;
<p>要删除集合中的元素可以使用 remove() 方法。</p>&#13;
<p>以下实例我们删除集合中小于 10 的元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #666666; font-style: italic;">// 引入 ArrayList 和 Iterator 类</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.ArrayList</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.Iterator</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
        ArrayList<span style="color: #339933;">&lt;</span>Integer<span style="color: #339933;">&gt;</span> numbers <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> ArrayList<span style="color: #339933;">&lt;</span>Integer<span style="color: #339933;">&gt;</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        numbers.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">12</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        numbers.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">8</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        numbers.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">2</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        numbers.<span style="color: #006633;">add</span><span style="color: #009900;">(</span><span style="color: #cc66cc;">23</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        Iterator<span style="color: #339933;">&lt;</span>Integer<span style="color: #339933;">&gt;</span> it <span style="color: #339933;">=</span> numbers.<span style="color: #006633;">iterator</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #000000; font-weight: bold;">while</span><span style="color: #009900;">(</span>it.<span style="color: #006633;">hasNext</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">Integer</span> i <span style="color: #339933;">=</span> it.<span style="color: #006633;">next</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #000000; font-weight: bold;">if</span><span style="color: #009900;">(</span>i <span style="color: #339933;">&lt;</span> <span style="color: #cc66cc;">10</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span>  <br/>
                it.<span style="color: #006633;">remove</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span>  <span style="color: #666666; font-style: italic;">// 删除小于 10 的元素</span><br/>
            <span style="color: #009900;">}</span><br/>
        <span style="color: #009900;">}</span><br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>numbers<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>执行以上代码，输出结果如下：</p>&#13;
<pre>[12, 23]</pre>&#13;
&#13;
&#13;
<p><strong>注意：</strong>Java 迭代器是一种单向遍历机制，即只能从前往后遍历集合中的元素，不能往回遍历。同时，在使用迭代器遍历集合时，不能直接修改集合中的元素，而是需要使用迭代器的 remove() 方法来删除当前元素。</p>&#13;
<p><a href="java-collections.html"><img decoding="async" class="navup" src="/images/up.gif" alt="Java 集合框架"/> Java 集合框架</a></p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>