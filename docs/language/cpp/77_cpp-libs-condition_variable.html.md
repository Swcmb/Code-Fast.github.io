<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <condition_variable></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;condition_variable&gt;</code></h1>&#13;
&#13;
<p>在多线程编程中，线程间的同步是一个非常重要的问题。</p><p>C++11 标准引入了 <code>&lt;condition_variable&gt;</code> 头文件，它提供了一种机制，允许线程在某些条件不满足时挂起，直到其他线程通知它们条件已经满足。</p><p><code>condition_variable</code>是用于线程间同步的一种高级工具，它比使用低级同步原语（如互斥锁和条件变量）更加安全和方便。</p>&#13;
<p><code>condition_variable</code>是一个类模板，用于在多线程环境中实现线程间的同步。它允许一个或多个线程等待某个条件变为真，而其他线程可以唤醒这些等待的线程。</p>&#13;
<h2>语法</h2>&#13;
<p>以下是<code>condition_variable</code>的基本语法：</p>&#13;
<pre>#include &lt;condition_variable&gt;&#13;
&#13;
void notify_one() {&#13;
    // 唤醒一个等待的线程&#13;
}&#13;
&#13;
void notify_all() {&#13;
    // 唤醒所有等待的线程&#13;
}&#13;
&#13;
template &lt;class Mutex&gt;&#13;
class condition_variable {&#13;
public:&#13;
    condition_variable();&#13;
    ~condition_variable();&#13;
&#13;
    void wait(unique_lock&lt;mutex&gt;&amp; lock);&#13;
    void wait_for(unique_lock&lt;mutex&gt;&amp; lock, chrono::duration&lt;Rep, Period&gt; const&amp; rel_time);&#13;
    void wait_until(unique_lock&lt;mutex&gt;&amp; lock, chrono::time_point&lt;Clock, Duration&gt; const&amp; abs_time);&#13;
&#13;
    void notify_one() noexcept;&#13;
    void notify_all() noexcept;&#13;
};</pre>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用<code>condition_variable</code>的简单示例，展示了生产者-消费者问题的基本实现。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;condition_variable&gt;</span><br/>
<span style="color: #060;">#include &lt;mutex&gt;</span><br/>
<span style="color: #060;">#include &lt;queue&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span> mtx<span style="color: #008080;">;</span><br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">condition_variable</span> cv<span style="color: #008080;">;</span><br/>
std<span style="color: #008080;">::</span><span style="color: #007788;">queue</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> product<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> producer<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #007788;">unique_lock</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lck<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        product.<span style="color: #007788;">push</span><span style="color: #008000;">(</span>id <span style="color: #000040;">*</span> <span style="color: #0000dd;">100</span> <span style="color: #000040;">+</span> i<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Producer "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" produced "</span> <span style="color: #000080;">&lt;&lt;</span> product.<span style="color: #007788;">back</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
        cv.<span style="color: #007788;">notify_one</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        lck.<span style="color: #007788;">unlock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #007788;">this_thread</span><span style="color: #008080;">::</span><span style="color: #007788;">sleep_for</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">chrono</span><span style="color: #008080;">::</span><span style="color: #007788;">milliseconds</span><span style="color: #008000;">(</span><span style="color: #0000dd;">100</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">void</span> consumer<span style="color: #008000;">(</span><span style="color: #05a;">int</span> id<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">while</span> <span style="color: #008000;">(</span><span style="color: #05a;">true</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #007788;">unique_lock</span><span style="color: #000080;">&lt;</span>std<span style="color: #008080;">::</span><span style="color: #007788;">mutex</span><span style="color: #000080;">&gt;</span> lck<span style="color: #008000;">(</span>mtx<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        cv.<span style="color: #007788;">wait</span><span style="color: #008000;">(</span>lck, <span style="color: #008000;">[</span><span style="color: #008000;">]</span><span style="color: #008000;">{</span> <span style="color: #05a;">return</span> <span style="color: #000040;">!</span>product.<span style="color: #007788;">empty</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span> <span style="color: #008000;">}</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        <span style="color: #05a;">if</span> <span style="color: #008000;">(</span><span style="color: #000040;">!</span>product.<span style="color: #007788;">empty</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
            <span style="color: #05a;">int</span> prod <span style="color: #000080;">=</span> product.<span style="color: #007788;">front</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
            product.<span style="color: #007788;">pop</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
            std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Consumer "</span> <span style="color: #000080;">&lt;&lt;</span> id <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" consumed "</span> <span style="color: #000080;">&lt;&lt;</span> prod <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
        <span style="color: #008000;">}</span><br/>
        lck.<span style="color: #007788;">unlock</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> producers<span style="color: #008000;">[</span><span style="color: #0000dd;">2</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span> consumers<span style="color: #008000;">[</span><span style="color: #0000dd;">2</span><span style="color: #008000;">]</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">2</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        producers<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span><span style="color: #008000;">(</span>producer, i <span style="color: #000040;">+</span> <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">2</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        consumers<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span> <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">thread</span><span style="color: #008000;">(</span>consumer, i <span style="color: #000040;">+</span> <span style="color: #0000dd;">1</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">2</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        producers<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span>.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        consumers<span style="color: #008000;">[</span>i<span style="color: #008000;">]</span>.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>这个程序的输出可能会有所不同，因为它依赖于线程调度。但是，你会看到生产者生产产品，然后消费者消费这些产品。输出将类似于：</p>&#13;
&#13;
<pre>Producer 1 produced 100&#13;
Producer 2 produced 200&#13;
Consumer 1 consumed 100&#13;
Producer 1 produced 101&#13;
Consumer 2 consumed 200&#13;
Producer 2 produced 201&#13;
Consumer 1 consumed 101&#13;
...</pre>&#13;
<h2>注意事项</h2>&#13;
<ul>&#13;
<li>使用<code>condition_variable</code>时，必须确保在等待之前获取互斥锁，并且在唤醒后释放互斥锁。</li>&#13;
<li><code>wait</code>、<code>wait_for</code>和<code>wait_until</code>函数都会释放互斥锁，然后在等待期间重新获取它。</li>&#13;
<li><code>notify_one</code>唤醒一个等待的线程，而<code>notify_all</code>唤醒所有等待的线程。</li>&#13;
</ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>