<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <atomic></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;atomic&gt;</code></h1>&#13;
&#13;
<p>在多线程编程中，数据的同步和线程安全是一个重要的问题。</p><p>C++11 标准引入了 <code>&lt;atomic&gt;</code> 库，它提供了一组原子操作，用于保证在多线程环境下对单个数据的访问是原子的，即不可分割的。这可以避免数据竞争和保证线程安全。</p>&#13;
&#13;
<p>原子操作是指在执行过程中不会被其他线程中断的操作。</p><p><code>&lt;atomic&gt;</code>库中的原子类型提供了这样的操作，它们可以保证在多线程环境中对共享数据的访问是安全的。</p>&#13;
<h2>语法</h2>&#13;
<p><code>&lt;atomic&gt;</code>库提供了多种原子类型，包括<code>atomic&lt;bool&gt;</code>, <code>atomic&lt;char&gt;</code>, <code>atomic&lt;short&gt;</code>, <code>atomic&lt;int&gt;</code>, <code>atomic&lt;long&gt;</code>, <code>atomic&lt;long long&gt;</code>, <code>atomic&lt;wchar_t&gt;</code>, <code>atomic&lt;char16_t&gt;</code>, <code>atomic&lt;char32_t&gt;</code>, <code>atomic&lt;unsigned char&gt;</code>, <code>atomic&lt;unsigned short&gt;</code>, <code>atomic&lt;unsigned&gt;</code>, <code>atomic&lt;unsigned long&gt;</code>, <code>atomic&lt;unsigned long long&gt;</code>, <code>atomic&lt;float&gt;</code>, <code>atomic&lt;double&gt;</code>, <code>atomic&lt;long double&gt;</code>等。</p>&#13;
<h3>基本操作</h3>&#13;
<ul>&#13;
<li><code>load()</code>: 安全地读取原子变量的值。</li>&#13;
<li><code>store(value)</code>: 安全地将值写入原子变量。</li>&#13;
<li><code>exchange(value)</code>: 将原子变量的值替换为<code>value</code>，并返回原子变量的旧值。</li>&#13;
<li><code>compare_exchange_weak(expected, desired)</code>: 如果原子变量的当前值等于<code>expected</code>，则将其设置为<code>desired</code>，并返回<code>true</code>。否则，将<code>expected</code>设置为原子变量的当前值，并返回<code>false</code>。</li>&#13;
<li><code>compare_exchange_strong(expected, desired)</code>: 与<code>compare_exchange_weak</code>类似，但循环直到成功。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用<code>&lt;atomic&gt;</code>库的简单示例，演示了如何在多线程环境中安全地更新一个共享计数器。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;atomic&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">atomic</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> counter<span style="color: #008000;">(</span><span style="color: #0000dd;">0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 初始化原子计数器</span><br/>
<br/>
<span style="color: #05a;">void</span> increment<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">10000</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        counter.<span style="color: #007788;">fetch_add</span><span style="color: #008000;">(</span><span style="color: #0000dd;">1</span>, std<span style="color: #008080;">::</span><span style="color: #007788;">memory_order_relaxed</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 原子增加</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>increment<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>increment<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Final counter value: "</span> <span style="color: #000080;">&lt;&lt;</span> counter <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出最终的计数器值</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>&#13;
运行上述程序，你将看到输出类似于：</p>&#13;
<pre>&#13;
Final counter value: 20000</pre>&#13;
<p>这个输出表明两个线程成功地在没有数据竞争的情况下，各自增加了10000次计数器的值。</p>&#13;
<h3>注意事项</h3>&#13;
<ul>&#13;
<li>使用<code>&lt;atomic&gt;</code>库时，需要确保所有对共享数据的访问都是通过原子操作进行的，以避免数据竞争。</li>&#13;
<li>不同的原子操作有不同的内存顺序要求，<code>std::memory_order_relaxed</code>是最低的内存顺序要求，但可能不保证操作的可见性。根据需要选择合适的内存顺序。</li>&#13;
<li>原子操作的性能开销通常比非原子操作要高，因此在单线程环境中，使用普通变量可能更高效。</li>&#13;
</ul>&#13;
<p>通过使用<code>&lt;atomic&gt;</code>库，C++程序员可以更容易地编写线程安全的代码，同时保持高性能。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>