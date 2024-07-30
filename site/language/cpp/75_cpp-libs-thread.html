<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 多线程库 <thread></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 多线程库 <code>&lt;thread&gt;</code></h1>&#13;
&#13;
<p>C++11 引入了多线程支持，通过 <code>&lt;thread&gt;</code> 库，开发者可以轻松地在程序中实现并行处理。</p><p>本文将将介绍 <code>&lt;thread&gt;</code> 库的基本概念、定义、语法以及如何使用它来创建和管理线程。</p>&#13;
&#13;
<p>线程是程序执行的最小单元，是操作系统能够进行运算调度的最小单位。</p><p>在多线程程序中，多个线程可以并行执行，提高程序的执行效率。</p>&#13;
<h3>C++ <code>&lt;thread&gt;</code> 库概述</h3>&#13;
<p><code>&lt;thread&gt;</code> 库是 C++ 标准库的一部分，提供了创建和管理线程的基本功能，它包括以下几个关键组件：</p>&#13;
<ul>&#13;
<li><code>std::thread</code>：表示一个线程，可以创建、启动、等待和销毁线程。</li>&#13;
<li><code>std::this_thread</code>：提供了一些静态成员函数，用于操作当前线程。</li>&#13;
<li><code>std::thread::id</code>：线程的唯一标识符。</li>&#13;
</ul>&#13;
&#13;
<h3>创建线程</h3>&#13;
<p>要创建一个线程，你需要实例化 <code>std::thread</code> 类，并传递一个可调用对象（函数、lambda 表达式或对象的成员函数）作为参数。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_id<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"ID: "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">", Thread ID: "</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">this_thread</span><span style="color: #008080;">::</span><span style="color: #007788;">get_id</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_id, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_id, <span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>启动线程</h3>&#13;
<p>创建 <code>std::thread</code> 对象后，线程会立即开始执行，你可以调用 <code>join()</code> 方法来等待线程完成。&#13;
&#13;
</p>&#13;
<pre>t1.join();&#13;
t2.join();</pre>&#13;
<h3>等待线程完成</h3>&#13;
<p><code>join()</code> 方法会阻塞当前线程，直到被调用的线程完成执行。</p>&#13;
<h3>销毁线程</h3>&#13;
<p>当线程执行完毕后，你可以使用 <code>detach()</code> 方法来分离线程，或者让 <code>std::thread</code> 对象超出作用域自动销毁。</p>&#13;
<pre>t1.detach(); // 线程将继续运行，但无法再被 join 或 detach</pre>&#13;
<h2>实例：使用 <code>&lt;thread&gt;</code> 创建并行计算</h2>&#13;
<p>下面是一个使用 <code>&lt;thread&gt;</code> 库实现的并行计算实例，计算两个数的和。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> sum <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> add<span style="color: #008000;">(</span><span style="color: #05a;">int</span> a, <span style="color: #05a;">int</span> b<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    sum <span style="color: #000040;">+</span><span style="color: #000080;">=</span> a <span style="color: #000040;">+</span> b<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>add, a, b<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>add, a, b<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Sum: "</span> <span style="color: #000080;">&lt;&lt;</span> sum <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 输出结果：Sum: 30</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>&#13;
输出结果为：</p>&#13;
&#13;
&#13;
&#13;
<pre>Sum: 30</pre>&#13;
&#13;
<p>&#13;
以下实例我们将创建两个线程，每个线程都会执行一个简单的函数，该函数打印一个消息并休眠一段时间：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;chrono&gt;</span><br/>
<br/>
<span style="color: #666666;">// 简单的函数，在线程中执行</span><br/>
<span style="color: #05a;">void</span> print_message<span style="color: #008000;">(</span><span style="color: #05a;">const</span> std<span style="color: #008080;">::</span><span style="color: #007788;">string</span><span style="color: #000040;">&amp;</span> message, <span style="color: #05a;">int</span> delay<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">this_thread</span><span style="color: #008080;">::</span><span style="color: #007788;">sleep_for</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">chrono</span><span style="color: #008080;">::</span><span style="color: #007788;">milliseconds</span><span style="color: #008000;">(</span>delay<span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> message <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 创建两个线程，执行 print_message 函数</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_message, <span style="color: #a11;">"Hello from thread 1"</span>, <span style="color: #0000dd;">1000</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_message, <span style="color: #a11;">"Hello from thread 2"</span>, <span style="color: #0000dd;">500</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 等待线程 t1 完成</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>t1.<span style="color: #007788;">joinable</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 等待线程 t2 完成</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>t2.<span style="color: #007788;">joinable</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Main thread finished."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>&#13;
输出结果为：</p>&#13;
&#13;
<pre>Hello from thread 2&#13;
Hello from thread 1&#13;
Main thread finished.</pre>&#13;
<h3>注意事项</h3>&#13;
<ul>&#13;
<li>线程安全：在多线程环境中，共享资源需要同步访问，以避免数据竞争。</li>&#13;
<li>线程生命周期：确保在线程执行完毕后正确地处理线程对象，避免资源泄露。</li>&#13;
</ul>&#13;
<hr/><h2>&#13;
类和函数</h2>&#13;
&#13;
<p><code>&lt;thread&gt;</code> 库包含了一系列的类和函数，用于创建、管理和同步线程。</p><p>以下是对 C++ <code>&lt;thread&gt;</code> 库的详细介绍:</p>&#13;
<h3>&#13;
主要组件</h3>&#13;
<ul><li><strong>std::thread</strong></li><li><strong>std::mutex</strong></li><li><strong>std::lock_guard</strong></li><li><strong>std::unique_lock</strong></li><li><strong>std::condition_variable</strong></li><li><strong>std::future 和 std::promise</strong></li><li><strong>std::async</strong></li></ul>&#13;
&#13;
<h3>&#13;
std::thread</h3><p>&#13;
std::thread 类用于创建和管理线程。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_hello<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello from thread!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t<span style="color: #008000;">(</span>print_hello<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 等待线程 t 结束</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p><strong>重要方法</strong></p>&#13;
<ul><li><strong>join()</strong>: 等待线程结束。</li><li><strong>detach()</strong>: 将线程置于后台运行，不再等待线程结束。</li><li><strong>joinable()</strong>: 检查线程是否可被 join 或 detach。</li></ul>&#13;
<h3>std::mutex</h3><p>&#13;
std::mutex 类用于同步对共享资源的访问。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_thread_id<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">lock_guard</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lock<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Thread ID: "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::lock_guard</h3><p>&#13;
std::lock_guard 是一个 RAII 风格的锁管理器，用于自动管理锁的生命周期。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_thread_id<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">lock_guard</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lock<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Thread ID: "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::unique_lock</h3><p>&#13;
std::unique_lock 提供了比 std::lock_guard 更灵活的锁管理。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_thread_id<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">unique_lock</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lock<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Thread ID: "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    lock.<span style="color: #007788;">unlock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 可以手动解锁</span><br/>
    <span style="color: #666666;">// ... 其他操作</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_thread_id, <span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::condition_variable</h3><p>&#13;
std::condition_variable 用于线程间的等待和通知。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<span style="color: #060;">#include &lt;condition_variable&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span><br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">condition_variable</span> cv<span style="color: #008080;">;</span><br/>
<span style="color: #05a;">bool</span> ready <span style="color: #000080;">=</span> <span style="color: #05a;">false</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> print_id<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">unique_lock</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lock<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    cv.<span style="color: #007788;">wait</span><span style="color: #008000;">(</span>lock, <span style="color: #008000;">[</span><span style="color: #008000;">]</span><span style="color: #008000;">{</span> <span style="color: #05a;">return</span> ready<span style="color: #008080;">;</span> <span style="color: #008000;">}</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Thread ID: "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">void</span> set_ready<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">unique_lock</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lock<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    ready <span style="color: #000080;">=</span> <span style="color: #05a;">true</span><span style="color: #008080;">;</span><br/>
    cv.<span style="color: #007788;">notify_all</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t1<span style="color: #008000;">(</span>print_id, <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t2<span style="color: #008000;">(</span>print_id, <span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">this_thread</span><span style="color: #008080;">::</span><span style="color: #007788;">sleep_for</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">chrono</span><span style="color: #008080;">::</span><span style="color: #007788;">seconds</span><span style="color: #008000;">(</span><span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    set_ready<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <br/>
    t1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    t2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::future 和 std::promise</h3><p>&#13;
std::future 和 std::promise 用于线程间的结果传递。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<br/>
<span style="color: #05a;">void</span> calculate_square<span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">promise</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> <span style="color: #000040;">&amp;&amp;</span> p, <span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    p.<span style="color: #007788;">set_value</span><span style="color: #008000;">(</span>x <span style="color: #000040;">*</span> x<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">promise</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> p<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> f <span style="color: #000080;">=</span> p.<span style="color: #007788;">get_future</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> t<span style="color: #008000;">(</span>calculate_square, std<span style="color: #008080;">::</span><span style="color: #007788;">move</span><span style="color: #008000;">(</span>p<span style="color: #008000;">)</span>, <span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Square: "</span> <span style="color: #000080;">&lt;&lt;</span> f.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <br/>
    t.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<h3>std::async</h3><p>&#13;
std::async 用于启动异步任务，并返回一个 std::future。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;future&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> calculate_square<span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">return</span> x <span style="color: #000040;">*</span> x<span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">future</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> result <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">async</span><span style="color: #008000;">(</span>calculate_square, <span style="color: #0000dd;">5</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Square: "</span> <span style="color: #000080;">&lt;&lt;</span> result.<span style="color: #007788;">get</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p>C++ 的 <code>&lt;thread&gt;</code> 库为开发者提供了强大的多线程支持。通过本文的介绍，我们应该能够理解线程的基本概念，并学会如何使用 <code>&lt;thread&gt;</code> 库来创建和管理线程。在实际开发中，合理利用多线程可以显著提高程序的性能和响应速度。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>