<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 数据结构</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 数据结构</h1>&#13;
<p>本章节我们主要结合前面所学的知识点来介绍Python数据结构。</p>&#13;
<hr/>&#13;
<h2>列表</h2>&#13;
<p>Python中列表是可变的，这是它区别于字符串和元组的最重要的特点，一句话概括即：列表可以修改，而字符串和元组不能。&#13;
</p>&#13;
<p>以下是 Python 中列表的方法：</p>&#13;
<table class="reference">&#13;
<tr>&#13;
<th>方法</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr>&#13;
<td>list.append(x)&#13;
</td>&#13;
<td>把一个元素添加到列表的结尾，相当于 a[len(a):] = [x]。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.extend(L)&#13;
</td>&#13;
<td>通过添加指定列表的所有元素来扩充列表，相当于 a[len(a):] = L。 &#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.insert(i, x)&#13;
</td>&#13;
<td>在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。&#13;
</td>&#13;
</tr>&#13;
<tr>&#13;
<td>list.remove(x)&#13;
</td>&#13;
<td>删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.pop([i])&#13;
</td>&#13;
<td>从列表的指定位置移除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被移除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。）&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.clear()&#13;
</td>&#13;
<td>移除列表中的所有项，等于del a[:]。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.index(x)&#13;
</td>&#13;
<td>返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.count(x)&#13;
</td>&#13;
<td>返回 x 在列表中出现的次数。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.sort()&#13;
</td>&#13;
<td>对列表中的元素进行排序。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.reverse()&#13;
</td>&#13;
<td>倒排列表中的元素。&#13;
</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>list.copy()&#13;
</td>&#13;
<td>返回列表的浅复制，等于a[:]。&#13;
</td>&#13;
</tr>&#13;
</table>&#13;
<p>下面示例演示了列表的大部分方法：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>a.<span style="color: #05a;">count</span><span style="color: Olive;">(</span><span style="color: Maroon;">333</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> a.<span style="color: #05a;">count</span><span style="color: Olive;">(</span><span style="color: Maroon;">66.25</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> a.<span style="color: #05a;">count</span><span style="color: Olive;">(</span><span style="color: #a11;">'x'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">2</span> <span style="color: Maroon;">1</span> <span style="color: Maroon;">0</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">insert</span><span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: Maroon;">333</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">index</span><span style="color: Olive;">(</span><span style="color: Maroon;">333</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">1</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">remove</span><span style="color: Olive;">(</span><span style="color: Maroon;">333</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">reverse</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">66.25</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a.<span style="color: #05a;">sort</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<p>注意：类似 insert, remove 或 sort 等修改列表的方法没有返回值。</p>&#13;
<hr/>&#13;
<h2>将列表当做栈使用</h2>&#13;
<p>在 Python 中，可以使用列表（list）来实现栈的功能。栈是一种后进先出（LIFO, Last-In-First-Out）数据结构，意味着最后添加的元素最先被移除。列表提供了一些方法，使其非常适合用于栈操作，特别是 <strong>append()</strong> 和 <strong>pop()</strong> 方法。</p>&#13;
&#13;
<p>&#13;
用 append() 方法可以把一个元素添加到栈顶，用不指定索引的 pop() 方法可以把一个元素从栈顶释放出来。&#13;
</p> &#13;
<h3>栈操作</h3>&#13;
&#13;
<ul><li><strong>压入（Push）</strong>: 将一个元素添加到栈的顶端。</li><li><strong>弹出（Pop）</strong>: 移除并返回栈顶元素。</li><li><strong>查看栈顶元素（Peek/Top）</strong>: 返回栈顶元素而不移除它。</li><li><strong>检查是否为空（IsEmpty）</strong>: 检查栈是否为空。</li><li><strong>获取栈的大小（Size）</strong>: 获取栈中元素的数量。</li></ul>&#13;
&#13;
<p>&#13;
以下是如何在 Python 中使用列表实现这些操作的详细说明：</p>&#13;
<h3>&#13;
1、创建一个空栈</h3>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
stack <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<h3>2、压入（Push）操作</h3><p>&#13;
使用 append() 方法将元素添加到栈的顶端：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
stack.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
stack.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Olive;">)</span><br/>
stack.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>stack<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: [1, 2, 3]</span><br/>
</div></div>&#13;
<h3>3、弹出（Pop）操作</h3><p>&#13;
使用 pop() 方法移除并返回栈顶元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
top_element <span style="color: Gray;">=</span> stack.<span style="color: #05a;">pop</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>top_element<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 3</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>stack<span style="color: Olive;">)</span>        <span style="color: #a50"># 输出: [1, 2]</span><br/>
</div></div>&#13;
<h3>4、查看栈顶元素（Peek/Top）</h3><p>&#13;
直接访问列表的最后一个元素（不移除）：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
top_element <span style="color: Gray;">=</span> stack<span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span><span style="color: Olive;">]</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>top_element<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 2</span><br/>
</div></div>&#13;
<h3>5、检查是否为空（IsEmpty）</h3>&#13;
<p>检查列表是否为空：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
is_empty <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>stack<span style="color: Olive;">)</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>is_empty<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: False</span><br/>
</div></div>&#13;
<h3>6、获取栈的大小（Size）</h3>&#13;
<p>使用 len() 函数获取栈中元素的数量：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
size <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>stack<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>size<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 2</span><br/>
</div></div>&#13;
<h3>实例</h3><p>&#13;
以下是一个完整的实例，展示了如何使用上述操作来实现一个简单的栈：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">class</span> Stack:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> push<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> item<span style="color: Olive;">)</span>:<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span>.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>item<span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> pop<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span>.<span style="color: #05a;">pop</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">else</span>:<br/>
            <span style="color: Green;font-weight:bold;">raise</span> <span style="color: Teal;">IndexError</span><span style="color: Olive;">(</span><span style="color: #a11;">"pop from empty stack"</span><span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> peek<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span><span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span><span style="color: Olive;">]</span><br/>
        <span style="color: Green;font-weight:bold;">else</span>:<br/>
            <span style="color: Green;font-weight:bold;">raise</span> <span style="color: Teal;">IndexError</span><span style="color: Olive;">(</span><span style="color: #a11;">"peek from empty stack"</span><span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> is_empty<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span><span style="color: Olive;">)</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> size<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">stack</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 使用示例</span><br/>
stack <span style="color: Gray;">=</span> Stack<span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
stack.<span style="color: #05a;">push</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
stack.<span style="color: #05a;">push</span><span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Olive;">)</span><br/>
stack.<span style="color: #05a;">push</span><span style="color: Olive;">(</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"栈顶元素:"</span><span style="color: Gray;">,</span> stack.<span style="color: #05a;">peek</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 栈顶元素: 3</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"栈大小:"</span><span style="color: Gray;">,</span> stack.<span style="color: #05a;">size</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 栈大小: 3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"弹出元素:"</span><span style="color: Gray;">,</span> stack.<span style="color: #05a;">pop</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 弹出元素: 3</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"栈是否为空:"</span><span style="color: Gray;">,</span> stack.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 栈是否为空: False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"栈大小:"</span><span style="color: Gray;">,</span> stack.<span style="color: #05a;">size</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 栈大小: 2</span><br/>
</div></div><p>&#13;
以上代码中，我们定义了一个 Stack 类，封装了列表作为底层数据结构，并实现了栈的基本操作。</p>&#13;
<p>&#13;
输出结果如下：</p>&#13;
<pre>栈顶元素: 3&#13;
栈大小: 3&#13;
弹出元素: 3&#13;
栈是否为空: False&#13;
栈大小: 2</pre>&#13;
&#13;
<hr/>&#13;
<h2>将列表当作队列使用</h2><p>&#13;
在 Python 中，列表（list）可以用作队列（queue），但由于列表的特点，直接使用列表来实现队列并不是最优的选择。</p><p>队列是一种先进先出（FIFO, First-In-First-Out）的数据结构，意味着最早添加的元素最先被移除。</p>&#13;
<p>&#13;
使用列表时，如果频繁地在列表的开头插入或删除元素，性能会受到影响，因为这些操作的时间复杂度是 O(n)。为了解决这个问题，Python 提供了 collections.deque，它是双端队列，可以在两端高效地添加和删除元素。</p>&#13;
<h3>&#13;
使用 collections.deque 实现队列</h3>&#13;
<p>&#13;
collections.deque 是 Python 标准库的一部分，非常适合用于实现队列。</p><p>&#13;
以下是使用 deque 实现队列的示例：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">collections</span> <span style="color: Green;font-weight:bold;">import</span> deque<br/>
<br/>
<span style="color: #a50"># 创建一个空队列</span><br/>
queue <span style="color: Gray;">=</span> deque<span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 向队尾添加元素</span><br/>
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'a'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'b'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'c'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列状态:"</span><span style="color: Gray;">,</span> queue<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 队列状态: deque(['a', 'b', 'c'])</span><br/>
<br/>
<span style="color: #a50"># 从队首移除元素</span><br/>
first_element <span style="color: Gray;">=</span> queue.<span style="color: #05a;">popleft</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"移除的元素:"</span><span style="color: Gray;">,</span> first_element<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 移除的元素: a</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列状态:"</span><span style="color: Gray;">,</span> queue<span style="color: Olive;">)</span>            <span style="color: #a50"># 输出: 队列状态: deque(['b', 'c'])</span><br/>
<br/>
<span style="color: #a50"># 查看队首元素（不移除）</span><br/>
front_element <span style="color: Gray;">=</span> queue<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队首元素:"</span><span style="color: Gray;">,</span> front_element<span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 队首元素: b</span><br/>
<br/>
<span style="color: #a50"># 检查队列是否为空</span><br/>
is_empty <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>queue<span style="color: Olive;">)</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列是否为空:"</span><span style="color: Gray;">,</span> is_empty<span style="color: Olive;">)</span>     <span style="color: #a50"># 输出: 队列是否为空: False</span><br/>
<br/>
<span style="color: #a50"># 获取队列大小</span><br/>
size <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>queue<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列大小:"</span><span style="color: Gray;">,</span> size<span style="color: Olive;">)</span>            <span style="color: #a50"># 输出: 队列大小: 2</span><br/>
</div></div>&#13;
```&#13;
&#13;
<h3>使用列表实现队列</h3>&#13;
<p>&#13;
虽然 deque更高效，但如果坚持使用列表来实现队列，也可以这么做。以下是如何使用列表实现队列的示例：</p>&#13;
<p>&#13;
<strong>1. 创建队列</strong></p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
queue <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
<strong>2. 向队尾添加元素</strong></p>&#13;
<p>使用 append() 方法将元素添加到队尾：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'a'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'b'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #a11;">'c'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列状态:"</span><span style="color: Gray;">,</span> queue<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 队列状态: ['a', 'b', 'c']</span><br/>
</div></div>&#13;
<p>&#13;
&#13;
<strong>3. 从队首移除元素</strong></p>&#13;
<p>使用 pop(0) 方法从队首移除元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
first_element <span style="color: Gray;">=</span> queue.<span style="color: #05a;">pop</span><span style="color: Olive;">(</span><span style="color: Maroon;">0</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"移除的元素:"</span><span style="color: Gray;">,</span> first_element<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 移除的元素: a</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列状态:"</span><span style="color: Gray;">,</span> queue<span style="color: Olive;">)</span>            <span style="color: #a50"># 输出: 队列状态: ['b', 'c']</span><br/>
</div></div>&#13;
<p>&#13;
&#13;
<strong>4. 查看队首元素（不移除）</strong></p>&#13;
<p>直接访问列表的第一个元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
front_element <span style="color: Gray;">=</span> queue<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队首元素:"</span><span style="color: Gray;">,</span> front_element<span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 队首元素: b</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
<strong>5. 检查队列是否为空</strong></p>&#13;
<p>检查列表是否为空：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
is_empty <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>queue<span style="color: Olive;">)</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列是否为空:"</span><span style="color: Gray;">,</span> is_empty<span style="color: Olive;">)</span>     <span style="color: #a50"># 输出: 队列是否为空: False</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
<strong>6. 获取队列大小</strong></p>&#13;
<p>使用 len() 函数获取队列的大小：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
size <span style="color: Gray;">=</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span>queue<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列大小:"</span><span style="color: Gray;">,</span> size<span style="color: Olive;">)</span>            <span style="color: #a50"># 输出: 队列大小: 2</span><br/>
</div></div>&#13;
&#13;
<h3>&#13;
实例（使用列表实现队列）</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<br/>
<span style="color: Green;font-weight:bold;">class</span> <span style="color: #05a;">Queue</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> enqueue<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> item<span style="color: Olive;">)</span>:<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span>.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>item<span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> dequeue<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span>.<span style="color: #05a;">pop</span><span style="color: Olive;">(</span><span style="color: Maroon;">0</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">else</span>:<br/>
            <span style="color: Green;font-weight:bold;">raise</span> <span style="color: Teal;">IndexError</span><span style="color: Olive;">(</span><span style="color: #a11;">"dequeue from empty queue"</span><span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> peek<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
        <span style="color: Green;font-weight:bold;">else</span>:<br/>
            <span style="color: Green;font-weight:bold;">raise</span> <span style="color: Teal;">IndexError</span><span style="color: Olive;">(</span><span style="color: #a11;">"peek from empty queue"</span><span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> is_empty<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span><span style="color: Olive;">)</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">0</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">def</span> size<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">return</span> <span style="color: Teal;">len</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">queue</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 使用示例</span><br/>
queue <span style="color: Gray;">=</span> <span style="color: #05a;">Queue</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">enqueue</span><span style="color: Olive;">(</span><span style="color: #a11;">'a'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">enqueue</span><span style="color: Olive;">(</span><span style="color: #a11;">'b'</span><span style="color: Olive;">)</span><br/>
queue.<span style="color: #05a;">enqueue</span><span style="color: Olive;">(</span><span style="color: #a11;">'c'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队首元素:"</span><span style="color: Gray;">,</span> queue.<span style="color: #05a;">peek</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 队首元素: a</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列大小:"</span><span style="color: Gray;">,</span> queue.<span style="color: #05a;">size</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 队列大小: 3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"移除的元素:"</span><span style="color: Gray;">,</span> queue.<span style="color: #05a;">dequeue</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 移除的元素: a</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列是否为空:"</span><span style="color: Gray;">,</span> queue.<span style="color: #05a;">is_empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 输出: 队列是否为空: False</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"队列大小:"</span><span style="color: Gray;">,</span> queue.<span style="color: #05a;">size</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 输出: 队列大小: 2</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
虽然可以使用列表来实现队列，但使用 collections.deque 会更高效和简洁。它提供了 O(1) 时间复杂度的添加和删除操作，非常适合队列这种数据结构。</p>&#13;
&#13;
<hr/>&#13;
<h2>列表推导式</h2>&#13;
<p>列表推导式提供了从序列创建列表的简单途径。通常应用程序将一些操作应用于某个序列的每个元素，用其获得的结果作为生成新列表的元素，或者根据确定的判定条件创建子序列。 &#13;
</p>&#13;
<p>&#13;
每个列表推导式都在 for 之后跟一个表达式，然后有零到多个 for 或 if 子句。返回结果是一个根据表达从其后的 for 和 if 上下文环境中生成出来的列表。如果希望表达式推导出一个元组，就必须使用括号。&#13;
&#13;
</p>&#13;
<p>这里我们将列表中每个数值乘三，获得一个新的列表：</p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> vec <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span>*x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec<span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Gray;">,</span> <span style="color: Maroon;">18</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>现在我们玩一点小花样：</p>&#13;
<div class="example"><div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Olive;">[</span>x<span style="color: Gray;">,</span> x**<span style="color: Maroon;">2</span><span style="color: Olive;">]</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec<span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">16</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">36</span><span style="color: Olive;">]</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
这里我们对序列里每一个元素逐个调用某方法：&#13;
</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> freshfruit <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'  banana'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'  loganberry '</span><span style="color: Gray;">,</span> <span style="color: #a11;">'passion fruit  '</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span>weapon.<span style="color: #05a;">strip</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <span style="color: Green;font-weight:bold;">for</span> weapon <span style="color: Green;font-weight:bold;">in</span> freshfruit<span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'banana'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'loganberry'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'passion fruit'</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<p>我们可以用 if 子句作为过滤器： </p>&#13;
&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span>*x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec <span style="color: Green;font-weight:bold;">if</span> x <span style="color: Gray;">&gt;</span> <span style="color: Maroon;">3</span><span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">12</span><span style="color: Gray;">,</span> <span style="color: Maroon;">18</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span>*x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec <span style="color: Green;font-weight:bold;">if</span> x <span style="color: Gray;">&lt;</span> <span style="color: Maroon;">2</span><span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<p>以下是一些关于循环和其它技巧的演示：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> vec1 <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> vec2 <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">9</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span>x*y <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec1 <span style="color: Green;font-weight:bold;">for</span> y <span style="color: Green;font-weight:bold;">in</span> vec2<span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">18</span><span style="color: Gray;">,</span> <span style="color: Maroon;">16</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">36</span><span style="color: Gray;">,</span> <span style="color: Maroon;">24</span><span style="color: Gray;">,</span> <span style="color: Maroon;">18</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">54</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span>x+y <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> vec1 <span style="color: Green;font-weight:bold;">for</span> y <span style="color: Green;font-weight:bold;">in</span> vec2<span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">3</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span>vec1<span style="color: Olive;">[</span>i<span style="color: Olive;">]</span>*vec2<span style="color: Olive;">[</span>i<span style="color: Olive;">]</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Teal;">len</span><span style="color: Olive;">(</span>vec1<span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Gray;">,</span> -<span style="color: Maroon;">54</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>列表推导式可以使用复杂表达式或嵌套函数：&#13;
</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Teal;">str</span><span style="color: Olive;">(</span><span style="color: Teal;">round</span><span style="color: Olive;">(</span><span style="color: Maroon;">355</span>/<span style="color: Maroon;">113</span><span style="color: Gray;">,</span> i<span style="color: Olive;">)</span><span style="color: Olive;">)</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">)</span><span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'3.1'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'3.14'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'3.142'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'3.1416'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'3.14159'</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<hr/>&#13;
<h2>嵌套列表解析</h2>&#13;
<p>&#13;
Python的列表还可以嵌套。&#13;
</p>&#13;
<p>以下实例展示了3X4的矩阵列表：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> matrix <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><br/>
...     <span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span><br/>
...     <span style="color: Olive;">[</span><span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span><br/>
...     <span style="color: Olive;">[</span><span style="color: Maroon;">9</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span><br/>
... <span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>以下实例将3X4的矩阵列表转换为4X3列表：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">[</span><span style="color: Olive;">[</span>row<span style="color: Olive;">[</span>i<span style="color: Olive;">]</span> <span style="color: Green;font-weight:bold;">for</span> row <span style="color: Green;font-weight:bold;">in</span> matrix<span style="color: Olive;">]</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">4</span><span style="color: Olive;">)</span><span style="color: Olive;">]</span><br/>
<span style="color: Olive;">[</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Olive;">]</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>以上实例也可以使用以下方法来实现：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> transposed <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">4</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: #05a;">transposed</span>.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span>row<span style="color: Olive;">[</span>i<span style="color: Olive;">]</span> <span style="color: Green;font-weight:bold;">for</span> row <span style="color: Green;font-weight:bold;">in</span> matrix<span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> transposed<br/>
<span style="color: Olive;">[</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Olive;">]</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>另外一种实现方法：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> transposed <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">4</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: #a50"># the following 3 lines implement the nested listcomp</span><br/>
...     <span style="color: #05a;">transposed_row</span> <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
...     <span style="color: Green;font-weight:bold;">for</span> row <span style="color: Green;font-weight:bold;">in</span> matrix:<br/>
...         <span style="color: #05a;">transposed_row</span>.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>row<span style="color: Olive;">[</span>i<span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
...     <span style="color: #05a;">transposed</span>.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>transposed_row<span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> transposed<br/>
<span style="color: Olive;">[</span><span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Gray;">,</span> <span style="color: Maroon;">9</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">7</span><span style="color: Gray;">,</span> <span style="color: Maroon;">11</span><span style="color: Olive;">]</span><span style="color: Gray;">,</span> <span style="color: Olive;">[</span><span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">12</span><span style="color: Olive;">]</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<hr/>&#13;
<h2>del 语句</h2>&#13;
<p>&#13;
使用 del 语句可以从一个列表中根据索引来删除一个元素，而不是值来删除元素。这与使用 pop() 返回一个值不同。可以用 del 语句从列表中删除一个切割，或清空整个列表（我们以前介绍的方法是给该切割赋一个空列表）。例如：&#13;
</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">[</span>-<span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">del</span> a<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">333</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">del</span> a<span style="color: Olive;">[</span><span style="color: Maroon;">2</span>:<span style="color: Maroon;">4</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">66.25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1234.5</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">del</span> a<span style="color: Olive;">[</span>:<span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
<p>也可以用 del 删除实体变量： </p>&#13;
<pre>&#13;
&gt;&gt;&gt; del a&#13;
</pre>&#13;
<hr/>&#13;
<h2> 元组和序列 </h2>&#13;
<p>&#13;
元组由若干逗号分隔的值组成，例如：&#13;
</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> t <span style="color: Gray;">=</span> <span style="color: Maroon;">12345</span><span style="color: Gray;">,</span> <span style="color: Maroon;">54321</span><span style="color: Gray;">,</span> <span style="color: #a11;">'hello!'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> t<span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
<span style="color: Maroon;">12345</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> t<br/>
<span style="color: Olive;">(</span><span style="color: Maroon;">12345</span><span style="color: Gray;">,</span> <span style="color: Maroon;">54321</span><span style="color: Gray;">,</span> <span style="color: #a11;">'hello!'</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a50"># Tuples may be nested:</span><br/>
... <span style="color: #05a;">u</span> <span style="color: Gray;">=</span> t<span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> u<br/>
<span style="color: Olive;">(</span><span style="color: Olive;">(</span><span style="color: Maroon;">12345</span><span style="color: Gray;">,</span> <span style="color: Maroon;">54321</span><span style="color: Gray;">,</span> <span style="color: #a11;">'hello!'</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>如你所见，元组在输出时总是有括号的，以便于正确表达嵌套结构。在输入时可能有或没有括号， 不过括号通常是必须的（如果元组是更大的表达式的一部分）。&#13;
</p>&#13;
<hr/>&#13;
<h2>集合</h2>&#13;
<p>集合是一个无序不重复元素的集。基本功能包括关系测试和消除重复元素。</p>&#13;
<p>可以用大括号({})创建集合。注意：如果要创建一个空集合，你必须用 set() 而不是 {} ；后者创建一个空的字典，下一节我们会介绍这个数据结构。</p>&#13;
<p>以下是一个简单的演示：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> basket <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'apple'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'orange'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'apple'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'pear'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'orange'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'banana'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>basket<span style="color: Olive;">)</span>                      <span style="color: #a50"># 删除重复的</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'orange'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'banana'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'pear'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'apple'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'orange'</span> <span style="color: Green;font-weight:bold;">in</span> basket                 <span style="color: #a50"># 检测成员</span><br/>
<span style="color: Teal;">True</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'crabgrass'</span> <span style="color: Green;font-weight:bold;">in</span> basket<br/>
<span style="color: Teal;">False</span><br/>
<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a50"># 以下演示了两个集合的操作</span><br/>
...<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Teal;">set</span><span style="color: Olive;">(</span><span style="color: #a11;">'abracadabra'</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> b <span style="color: Gray;">=</span> <span style="color: Teal;">set</span><span style="color: Olive;">(</span><span style="color: #a11;">'alacazam'</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a                                  <span style="color: #a50"># a 中唯一的字母</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'a'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'r'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'b'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'c'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'d'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a - b                              <span style="color: #a50"># 在 a 中的字母，但不在 b 中</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'r'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'d'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'b'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a | b                              <span style="color: #a50"># 在 a 或 b 中的字母</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'a'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'c'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'r'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'d'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'b'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'m'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'z'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'l'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a &amp; b                              <span style="color: #a50"># 在 a 和 b 中都有的字母</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'a'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'c'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a ^ b                              <span style="color: #a50"># 在 a 或 b 中的字母，但不同时在 a 和 b 中</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'r'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'d'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'b'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'m'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'z'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'l'</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
<p>集合也支持推导式：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> a <span style="color: Gray;">=</span> <span style="color: Olive;">{</span>x <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: #a11;">'abracadabra'</span> <span style="color: Green;font-weight:bold;">if</span> x <span style="color: Green;font-weight:bold;">not</span> <span style="color: Green;font-weight:bold;">in</span> <span style="color: #a11;">'abc'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> a<br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'r'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'d'</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
<hr/>&#13;
<h2>字典</h2>&#13;
<p>另一个非常有用的 Python 内建数据类型是字典。</p>&#13;
<p>序列是以连续的整数为索引，与此不同的是，字典以关键字为索引，关键字可以是任意不可变类型，通常用字符串或数值。</p>&#13;
<p>理解字典的最佳方式是把它看做无序的键=&gt;值对集合。在同一个字典之内，关键字必须是互不相同。</p>&#13;
<p>一对大括号创建一个空的字典：{}。</p>&#13;
<p>这是一个字典运用的简单例子： </p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> tel <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'jack'</span>: <span style="color: Maroon;">4098</span><span style="color: Gray;">,</span> <span style="color: #a11;">'sape'</span>: <span style="color: Maroon;">4139</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tel<span style="color: Olive;">[</span><span style="color: #a11;">'guido'</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Maroon;">4127</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tel<br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'sape'</span>: <span style="color: Maroon;">4139</span><span style="color: Gray;">,</span> <span style="color: #a11;">'guido'</span>: <span style="color: Maroon;">4127</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span>: <span style="color: Maroon;">4098</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tel<span style="color: Olive;">[</span><span style="color: #a11;">'jack'</span><span style="color: Olive;">]</span><br/>
<span style="color: Maroon;">4098</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">del</span> tel<span style="color: Olive;">[</span><span style="color: #a11;">'sape'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tel<span style="color: Olive;">[</span><span style="color: #a11;">'irv'</span><span style="color: Olive;">]</span> <span style="color: Gray;">=</span> <span style="color: Maroon;">4127</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> tel<br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'guido'</span>: <span style="color: Maroon;">4127</span><span style="color: Gray;">,</span> <span style="color: #a11;">'irv'</span>: <span style="color: Maroon;">4127</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span>: <span style="color: Maroon;">4098</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">list</span><span style="color: Olive;">(</span>tel.<span style="color: #05a;">keys</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'irv'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'guido'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">sorted</span><span style="color: Olive;">(</span>tel.<span style="color: #05a;">keys</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'guido'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'irv'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'guido'</span> <span style="color: Green;font-weight:bold;">in</span> tel<br/>
<span style="color: Teal;">True</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #a11;">'jack'</span> <span style="color: Green;font-weight:bold;">not</span> <span style="color: Green;font-weight:bold;">in</span> tel<br/>
<span style="color: Teal;">False</span><br/>
</div></div>&#13;
<p>构造函数 dict() 直接从键值对元组列表中构建字典。如果有固定的模式，列表推导式指定特定的键值对：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">dict</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: Olive;">(</span><span style="color: #a11;">'sape'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4139</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">'guido'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4127</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">'jack'</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4098</span><span style="color: Olive;">)</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'sape'</span>: <span style="color: Maroon;">4139</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span>: <span style="color: Maroon;">4098</span><span style="color: Gray;">,</span> <span style="color: #a11;">'guido'</span>: <span style="color: Maroon;">4127</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
<p>此外，字典推导可以用来创建任意键和值的表达式词典：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Olive;">{</span>x: x**<span style="color: Maroon;">2</span> <span style="color: Green;font-weight:bold;">for</span> x <span style="color: Green;font-weight:bold;">in</span> <span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span><span style="color: Olive;">)</span><span style="color: Olive;">}</span><br/>
<span style="color: Olive;">{</span><span style="color: Maroon;">2</span>: <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span>: <span style="color: Maroon;">16</span><span style="color: Gray;">,</span> <span style="color: Maroon;">6</span>: <span style="color: Maroon;">36</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
<p>如果关键字只是简单的字符串，使用关键字参数指定键值对有时候更方便： </p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Teal;">dict</span><span style="color: Olive;">(</span>sape<span style="color: Gray;">=</span><span style="color: Maroon;">4139</span><span style="color: Gray;">,</span> guido<span style="color: Gray;">=</span><span style="color: Maroon;">4127</span><span style="color: Gray;">,</span> jack<span style="color: Gray;">=</span><span style="color: Maroon;">4098</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">{</span><span style="color: #a11;">'sape'</span>: <span style="color: Maroon;">4139</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jack'</span>: <span style="color: Maroon;">4098</span><span style="color: Gray;">,</span> <span style="color: #a11;">'guido'</span>: <span style="color: Maroon;">4127</span><span style="color: Olive;">}</span><br/>
</div></div>&#13;
<hr/>&#13;
<h2>遍历技巧</h2>&#13;
<p>&#13;
在字典中遍历时，关键字和对应的值可以使用 items() 方法同时解读出来：&#13;
</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> knights <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'gallahad'</span>: <span style="color: #a11;">'the pure'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'robin'</span>: <span style="color: #a11;">'the brave'</span><span style="color: Olive;">}</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> k<span style="color: Gray;">,</span> v <span style="color: Green;font-weight:bold;">in</span> knights.<span style="color: #05a;">items</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>k<span style="color: Gray;">,</span> v<span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: #05a;">gallahad</span> the pure<br/>
robin the brave<br/>
</div></div>&#13;
<p>在序列中遍历时，索引位置和对应值可以使用 enumerate() 函数同时得到：</p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> i<span style="color: Gray;">,</span> v <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">enumerate</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: #a11;">'tic'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'tac'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'toe'</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>i<span style="color: Gray;">,</span> v<span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: Maroon;">0</span> tic<br/>
<span style="color: Maroon;">1</span> tac<br/>
<span style="color: Maroon;">2</span> toe<br/>
</div></div>&#13;
<p>同时遍历两个或更多的序列，可以使用 zip() 组合： </p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> questions <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'name'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'quest'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'favorite color'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> answers <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'lancelot'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'the holy grail'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'blue'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> q<span style="color: Gray;">,</span> a <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">zip</span><span style="color: Olive;">(</span>questions<span style="color: Gray;">,</span> answers<span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">'What is your {0}?  It is {1}.'</span>.<span style="color: #05a;">format</span><span style="color: Olive;">(</span>q<span style="color: Gray;">,</span> a<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: #05a;">What</span> <span style="color: Green;font-weight:bold;">is</span> your name?  It <span style="color: Green;font-weight:bold;">is</span> lancelot.<br/>
<span style="color: #05a;">What</span> <span style="color: Green;font-weight:bold;">is</span> your quest?  It <span style="color: Green;font-weight:bold;">is</span> the holy grail.<br/>
<span style="color: #05a;">What</span> <span style="color: Green;font-weight:bold;">is</span> your favorite color?  It <span style="color: Green;font-weight:bold;">is</span> blue.<br/>
</div></div>&#13;
<p>要反向遍历一个序列，首先指定这个序列，然后调用 reversed() 函数： </p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">reversed</span><span style="color: Olive;">(</span><span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>i<span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: Maroon;">9</span><br/>
<span style="color: Maroon;">7</span><br/>
<span style="color: Maroon;">5</span><br/>
<span style="color: Maroon;">3</span><br/>
<span style="color: Maroon;">1</span><br/>
</div></div>&#13;
<p>要按顺序遍历一个序列，使用 sorted() 函数返回一个已排序的序列，并不修改原值： </p>&#13;
<div class="example"> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> basket <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">'apple'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'orange'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'apple'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'pear'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'orange'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'banana'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> f <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">sorted</span><span style="color: Olive;">(</span><span style="color: Teal;">set</span><span style="color: Olive;">(</span>basket<span style="color: Olive;">)</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>f<span style="color: Olive;">)</span><br/>
...<br/>
<span style="color: #05a;">apple</span><br/>
banana<br/>
orange<br/>
pear<br/>
</div></div>&#13;
<hr/><h2>参阅文档</h2>&#13;
<ul>&#13;
<li><a target="_blank" href="/python3/python3-list.html" rel="noopener noreferrer">Python3 列表</a></li>&#13;
<li><a target="_blank" href="/python3/python3-tuple.html" rel="noopener noreferrer">Python3 元组</a></li>&#13;
<li><a target="_blank" href="/python3/python3-dictionary.html" rel="noopener noreferrer">Python3 字典</a></li>&#13;
</ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>