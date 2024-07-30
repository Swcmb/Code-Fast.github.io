<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <mutex>：初学者指南</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;mutex&gt;</code>：初学者指南</h1>&#13;
&#13;
<p>在多线程编程中，确保数据的一致性和线程安全是至关重要的。</p><p>C++ 标准库提供了一套丰富的同步原语，用于控制对共享资源的访问。<code>&lt;mutex&gt;</code> 头文件是 C++11 引入的，它包含了用于互斥锁（mutex）的类和函数。互斥锁是一种同步机制，用于防止多个线程同时访问共享资源。</p>&#13;
&#13;
<p>互斥锁（Mutex）是一个用于控制对共享资源访问的同步原语。当一个线程需要访问共享资源时，它会尝试锁定互斥锁。如果互斥锁已经被其他线程锁定，请求线程将被阻塞，直到互斥锁被释放。</p>&#13;
<h2>基本语法</h2>&#13;
<p>在 C++ 中，<code>&lt;mutex&gt;</code> 头文件提供了以下主要类：</p>&#13;
<ul>&#13;
<li><code>std::mutex</code>：基本的互斥锁。</li>&#13;
<li><code>std::recursive_mutex</code>：递归互斥锁，允许同一个线程多次锁定。</li>&#13;
<li><code>std::timed_mutex</code>：具有超时功能的互斥锁。</li>&#13;
<li><code>std::recursive_timed_mutex</code>：具有超时功能的递归互斥锁。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>1. 使用 <code>std::mutex</code></h3>&#13;
<p>下面是一个简单的示例，展示了如何在 C++ 中使用 <code>std::mutex</code> 来同步对共享资源的访问。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span> <span style="color: #666666;">// 全局互斥锁</span><br/>
<span style="color: #05a;">int</span> shared_resource <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> increment<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">10000</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        mtx.<span style="color: #007788;">lock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 锁定互斥锁</span><br/>
        <span style="color: #000040;">++</span>shared_resource<span style="color: #008080;">;</span><br/>
        mtx.<span style="color: #007788;">unlock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 解锁互斥锁</span><br/>
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
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Final value of shared_resource: "</span> <span style="color: #000080;">&lt;&lt;</span> shared_resource <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Final value of shared_resource: 20000</pre>&#13;
<h3>2. 使用 <code>std::recursive_mutex</code></h3>&#13;
<p>递归互斥锁允许同一个线程多次锁定同一个互斥锁。下面是一个使用 <code>std::recursive_mutex</code> 的示例。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">recursive_mutex</span> mtx<span style="color: #008080;">;</span> <span style="color: #666666;">// 递归互斥锁</span><br/>
<span style="color: #05a;">int</span> shared_resource <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> recursive_increment<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">10000</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        mtx.<span style="color: #007788;">lock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 锁定互斥锁</span><br/>
        <span style="color: #000040;">++</span>shared_resource<span style="color: #008080;">;</span><br/>
        mtx.<span style="color: #007788;">unlock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 解锁互斥锁</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>recursive_increment<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>recursive_increment<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Final value of shared_resource: "</span> <span style="color: #000080;">&lt;&lt;</span> shared_resource <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div><p>&#13;
输出结果：</p>&#13;
&#13;
<pre>Final value of shared_resource: 20000</pre>&#13;
<h2>注意事项</h2>&#13;
<ul>&#13;
<li>确保在每次锁定互斥锁后，都进行解锁操作，以避免死锁。</li>&#13;
<li>使用 <code>std::lock_guard</code> 或 <code>std::unique_lock</code> 可以自动管理互斥锁的锁定和解锁，减少出错的可能性。</li>&#13;
<li>避免在持有互斥锁的情况下调用可能抛出异常的函数，因为这可能导致死锁。</li>&#13;
</ul>&#13;
&#13;
<p><code>&lt;mutex&gt;</code> 是 C++ 标准库中一个非常重要的头文件，它为多线程编程提供了基本的同步机制。通过使用互斥锁，我们可以确保对共享资源的访问是安全的，从而避免数据竞争和不一致的问题。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>