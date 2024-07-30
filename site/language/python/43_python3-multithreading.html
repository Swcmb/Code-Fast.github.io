<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 多线程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 多线程</h1>&#13;
<p>多线程类似于同时执行多个不同程序，多线程运行有如下优点：</p>&#13;
<ul>&#13;
<li>使用线程可以把占据长时间的程序中的任务放到后台去处理。</li>&#13;
<li>用户界面可以更加吸引人，比如用户点击了一个按钮去触发某些事件的处理，可以弹出一个进度条来显示处理的进度。</li>&#13;
<li>程序的运行速度可能加快。</li>&#13;
<li>在一些等待的任务实现上如用户输入、文件读写和网络收发数据等，线程就比较有用了。在这种情况下我们可以释放一些珍贵的资源如内存占用等等。</li>&#13;
</ul>&#13;
<p>每个独立的线程有一个程序运行的入口、顺序执行序列和程序的出口。但是线程不能够独立执行，必须依存在应用程序中，由应用程序提供多个线程执行控制。&#13;
</p>&#13;
<p>每个线程都有他自己的一组CPU寄存器，称为线程的上下文，该上下文反映了线程上次运行该线程的CPU寄存器的状态。&#13;
</p><p>指令指针和堆栈指针寄存器是线程上下文中两个最重要的寄存器，线程总是在进程得到上下文中运行的，这些地址都用于标志拥有线程的进程地址空间中的内存。&#13;
</p>&#13;
<ul>&#13;
&#13;
<li>线程可以被抢占（中断）。</li>&#13;
<li>在其他线程正在运行时，线程可以暂时搁置（也称为睡眠） -- 这就是线程的退让。&#13;
</li>&#13;
</ul>&#13;
<p>线程可以分为:</p>&#13;
&#13;
<ul>&#13;
<li><strong>内核线程：</strong>由操作系统内核创建和撤销。</li>&#13;
<li><strong>用户线程：</strong>不需要内核支持而在用户程序中实现的线程。</li>&#13;
</ul>&#13;
&#13;
<p>Python3 线程中常用的两个模块为：</p>&#13;
<ul>&#13;
<li><b>_thread</b></li>&#13;
<li><b>threading(推荐使用)</b></li>&#13;
</ul>&#13;
<p> thread 模块已被废弃。用户可以使用 threading 模块代替。所以，在 Python3 中不能再使用"thread" 模块。为了兼容性，Python3 将 thread 重命名为 "_thread"。 </p>&#13;
<br/>&#13;
<h2>开始学习Python线程</h2>&#13;
<p>Python中使用线程有两种方式：函数或者用类来包装线程对象。</p>&#13;
<p>函数式：调用 _thread 模块中的start_new_thread()函数来产生新线程。语法如下:</p>&#13;
<pre>&#13;
_thread.start_new_thread ( function, args[, kwargs] )&#13;
</pre>&#13;
<p>参数说明:</p>&#13;
<ul>&#13;
<li>function - 线程函数。</li>&#13;
<li>args - 传递给线程函数的参数,他必须是个tuple类型。</li>&#13;
<li>kwargs - 可选参数。</li>&#13;
</ul>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> _thread<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
<span style="color: #a50"># 为线程定义一个函数</span><br/>
<span style="color: Green;font-weight:bold;">def</span> print_time<span style="color: Olive;">(</span> threadName<span style="color: Gray;">,</span> delay<span style="color: Olive;">)</span>:<br/>
   count <span style="color: Gray;">=</span> <span style="color: Maroon;">0</span><br/>
   <span style="color: Green;font-weight:bold;">while</span> count <span style="color: Gray;">&lt;</span> <span style="color: Maroon;">5</span>:<br/>
      <span style="color: #05a;">time</span>.<span style="color: #05a;">sleep</span><span style="color: Olive;">(</span>delay<span style="color: Olive;">)</span><br/>
      count +<span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
      <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"%s: %s"</span> % <span style="color: Olive;">(</span> threadName<span style="color: Gray;">,</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">ctime</span><span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">time</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span> <span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 创建两个线程</span><br/>
<span style="color: Green;font-weight:bold;">try</span>:<br/>
   _thread.<span style="color: #05a;">start_new_thread</span><span style="color: Olive;">(</span> print_time<span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Thread-1"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: Olive;">)</span> <span style="color: Olive;">)</span><br/>
   _thread.<span style="color: #05a;">start_new_thread</span><span style="color: Olive;">(</span> print_time<span style="color: Gray;">,</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Thread-2"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Olive;">)</span> <span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">except</span>:<br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Error: 无法启动线程"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">while</span> <span style="color: Maroon;">1</span>:<br/>
   <span style="color: Green;font-weight:bold;">pass</span><br/>
</div></div>&#13;
&#13;
<p>执行以上程序输出结果如下：</p>&#13;
<pre>&#13;
Thread-1: Wed Jan  5 17:38:08 2022&#13;
Thread-2: Wed Jan  5 17:38:10 2022&#13;
Thread-1: Wed Jan  5 17:38:10 2022&#13;
Thread-1: Wed Jan  5 17:38:12 2022&#13;
Thread-2: Wed Jan  5 17:38:14 2022&#13;
Thread-1: Wed Jan  5 17:38:14 2022&#13;
Thread-1: Wed Jan  5 17:38:16 2022&#13;
Thread-2: Wed Jan  5 17:38:18 2022&#13;
Thread-2: Wed Jan  5 17:38:22 2022&#13;
Thread-2: Wed Jan  5 17:38:26 2022&#13;
</pre>&#13;
<p>执行以上程后可以按下 ctrl-c 退出。</p>&#13;
&#13;
&#13;
<p>&#13;
</p><hr/>&#13;
<h2>线程模块</h2>&#13;
<p>Python3 通过两个标准库 _thread 和 threading 提供对线程的支持。</p><p>&#13;
_thread 提供了低级别的、原始的线程以及一个简单的锁，它相比于 threading 模块的功能还是比较有限的。</p>&#13;
<p>threading 模块除了包含 _thread 模块中的所有方法外，还提供的其他方法： </p>&#13;
<ul>&#13;
<li><strong>threading.current_thread()</strong>: 返回当前的线程变量。 </li>&#13;
<li><strong>threading.enumerate()</strong>: 返回一个包含正在运行的线程的列表。正在运行指线程启动后、结束前，不包括启动前和终止后的线程。 </li>&#13;
<li><strong>threading.active_count()</strong>: 返回正在运行的线程数量，与 len(threading.enumerate()) 有相同的结果。</li>&#13;
<li><strong>threading.Thread(target, args=(), kwargs={}, daemon=None)</strong>：<br/><ul><li>创建<code>Thread</code>类的实例。</li><li><code>target</code>：线程将要执行的目标函数。</li><li><code>args</code>：目标函数的参数，以元组形式传递。</li><li><code>kwargs</code>：目标函数的关键字参数，以字典形式传递。</li><li><code>daemon</code>：指定线程是否为守护线程。</li></ul></li>&#13;
</ul>&#13;
<p>threading.Thread 类提供了以下方法与属性:</p>&#13;
<ol><li><p><strong><code>__init__(self, group=None, target=None, name=None, args=(), kwargs={}, *, daemon=None)</code>：</strong></p><ul><li>初始化<code>Thread</code>对象。</li><li><code>group</code>：线程组，暂时未使用，保留为将来的扩展。</li><li><code>target</code>：线程将要执行的目标函数。</li><li><code>name</code>：线程的名称。</li><li><code>args</code>：目标函数的参数，以元组形式传递。</li><li><code>kwargs</code>：目标函数的关键字参数，以字典形式传递。</li><li><code>daemon</code>：指定线程是否为守护线程。</li></ul></li><li><p><strong><code>start(self)</code>：</strong></p><ul><li>启动线程。将调用线程的<code>run()</code>方法。</li></ul></li><li><p><strong><code>run(self)</code>：</strong></p><ul><li>线程在此方法中定义要执行的代码。</li></ul></li><li><p><strong><code>join(self, timeout=None)</code>：</strong></p><ul><li>等待线程终止。默认情况下，<code>join()</code>会一直阻塞，直到被调用线程终止。如果指定了<code>timeout</code>参数，则最多等待<code>timeout</code>秒。</li></ul></li><li><p><strong><code>is_alive(self)</code>：</strong></p><ul><li>返回线程是否在运行。如果线程已经启动且尚未终止，则返回<code>True</code>，否则返回<code>False</code>。</li></ul></li><li><p><strong><code>getName(self)</code>：</strong></p><ul><li>返回线程的名称。</li></ul></li><li><p><strong><code>setName(self, name)</code>：</strong></p><ul><li>设置线程的名称。</li></ul></li><li><p><strong><code>ident</code>属性：</strong></p><ul><li>线程的唯一标识符。</li></ul></li><li><p><strong><code>daemon</code>属性：</strong></p><ul><li>线程的守护标志，用于指示是否是守护线程。</li></ul></li><li><p><strong><code>isDaemon()</code>方法：</strong></p></li></ol>&#13;
<p>一个简单的线程实例：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">threading</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">def</span> print_numbers<span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">for</span> i <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: #05a;">time</span>.<span style="color: #05a;">sleep</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>i<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 创建线程</span><br/>
<span style="color: #05a;">thread</span> <span style="color: Gray;">=</span> <span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span><span style="color: Olive;">(</span>target<span style="color: Gray;">=</span>print_numbers<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 启动线程</span><br/>
<span style="color: #05a;">thread</span>.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 等待线程结束</span><br/>
<span style="color: #05a;">thread</span>.<span style="color: #05a;">join</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>输出结果为：</p>&#13;
<pre>0&#13;
1&#13;
2&#13;
3&#13;
4</pre>&#13;
<hr/>&#13;
<h2>使用 threading 模块创建线程</h2>&#13;
<p>我们可以通过直接从 threading.Thread 继承创建一个新的子类，并实例化后调用 start() 方法启动新线程，即它调用了线程的 run()  方法：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">threading</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
exitFlag <span style="color: Gray;">=</span> <span style="color: Maroon;">0</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">class</span> myThread <span style="color: Olive;">(</span><span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> threadID<span style="color: Gray;">,</span> name<span style="color: Gray;">,</span> delay<span style="color: Olive;">)</span>:<br/>
        <span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span>.<span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span><br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">threadID</span> <span style="color: Gray;">=</span> threadID<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span> <span style="color: Gray;">=</span> name<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">delay</span> <span style="color: Gray;">=</span> delay<br/>
    <span style="color: Green;font-weight:bold;">def</span> run<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"开始线程："</span> + <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Olive;">)</span><br/>
        print_time<span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">delay</span><span style="color: Gray;">,</span> <span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"退出线程："</span> + <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">def</span> print_time<span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> delay<span style="color: Gray;">,</span> counter<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">while</span> counter:<br/>
        <span style="color: Green;font-weight:bold;">if</span> exitFlag:<br/>
            threadName.<span style="color: #05a;">exit</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <span style="color: #05a;">time</span>.<span style="color: #05a;">sleep</span><span style="color: Olive;">(</span>delay<span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"%s: %s"</span> % <span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">ctime</span><span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">time</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
        counter -<span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
<br/>
<span style="color: #a50"># 创建新线程</span><br/>
thread1 <span style="color: Gray;">=</span> myThread<span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-1"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
thread2 <span style="color: Gray;">=</span> myThread<span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-2"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 开启新线程</span><br/>
thread1.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
thread2.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
thread1.<span style="color: #05a;">join</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
thread2.<span style="color: #05a;">join</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"退出主线程"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上程序执行结果如下；</p>&#13;
<pre>&#13;
开始线程：Thread-1&#13;
开始线程：Thread-2&#13;
Thread-1: Wed Jan  5 17:34:54 2022&#13;
Thread-2: Wed Jan  5 17:34:55 2022&#13;
Thread-1: Wed Jan  5 17:34:55 2022&#13;
Thread-1: Wed Jan  5 17:34:56 2022&#13;
Thread-2: Wed Jan  5 17:34:57 2022&#13;
Thread-1: Wed Jan  5 17:34:57 2022&#13;
Thread-1: Wed Jan  5 17:34:58 2022&#13;
退出线程：Thread-1&#13;
Thread-2: Wed Jan  5 17:34:59 2022&#13;
Thread-2: Wed Jan  5 17:35:01 2022&#13;
Thread-2: Wed Jan  5 17:35:03 2022&#13;
退出线程：Thread-2&#13;
退出主线程&#13;
</pre>&#13;
<hr/>&#13;
<h2>线程同步</h2>&#13;
<p>如果多个线程共同对某个数据修改，则可能出现不可预料的结果，为了保证数据的正确性，需要对多个线程进行同步。&#13;
</p>&#13;
<p>&#13;
使用 Thread 对象的 Lock 和 Rlock 可以实现简单的线程同步，这两个对象都有 acquire 方法和 release 方法，对于那些需要每次只允许一个线程操作的数据，可以将其操作放到 acquire 和 release 方法之间。如下：&#13;
</p>&#13;
<p>多线程的优势在于可以同时运行多个任务（至少感觉起来是这样）。但是当线程需要共享数据时，可能存在数据不同步的问题。</p>&#13;
<p>&#13;
考虑这样一种情况：一个列表里所有元素都是 0，线程 "set" 从后向前把所有元素改成 1，而线程 "print" 负责从前往后读取列表并打印。</p>&#13;
<p>&#13;
那么，可能线程"set"开始改的时候，线程"print"便来打印列表了，输出就成了一半0一半1，这就是数据的不同步。为了避免这种情况，引入了锁的概念。&#13;
</p>&#13;
<p>&#13;
锁有两种状态——锁定和未锁定。每当一个线程比如"set"要访问共享数据时，必须先获得锁定；如果已经有别的线程比如"print"获得锁定了，那么就让线程"set"暂停，也就是同步阻塞；等到线程"print"访问完毕，释放锁以后，再让线程"set"继续。&#13;
</p>&#13;
<p>&#13;
经过这样的处理，打印列表时要么全部输出0，要么全部输出1，不会再出现一半0一半1的尴尬场面。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">threading</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">class</span> myThread <span style="color: Olive;">(</span><span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> threadID<span style="color: Gray;">,</span> name<span style="color: Gray;">,</span> delay<span style="color: Olive;">)</span>:<br/>
        <span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span>.<span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span><br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">threadID</span> <span style="color: Gray;">=</span> threadID<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span> <span style="color: Gray;">=</span> name<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">delay</span> <span style="color: Gray;">=</span> delay<br/>
    <span style="color: Green;font-weight:bold;">def</span> run<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"开启线程： "</span> + <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Olive;">)</span><br/>
        <span style="color: #a50"># 获取锁，用于线程同步</span><br/>
        threadLock.<span style="color: #05a;">acquire</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        print_time<span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">delay</span><span style="color: Gray;">,</span> <span style="color: Maroon;">3</span><span style="color: Olive;">)</span><br/>
        <span style="color: #a50"># 释放锁，开启下一个线程</span><br/>
        threadLock.<span style="color: #05a;">release</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">def</span> print_time<span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> delay<span style="color: Gray;">,</span> counter<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">while</span> counter:<br/>
        <span style="color: #05a;">time</span>.<span style="color: #05a;">sleep</span><span style="color: Olive;">(</span>delay<span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"%s: %s"</span> % <span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">ctime</span><span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">time</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
        counter -<span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
<br/>
threadLock <span style="color: Gray;">=</span> <span style="color: #05a;">threading</span>.<span style="color: #05a;">Lock</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
threads <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
<br/>
<span style="color: #a50"># 创建新线程</span><br/>
thread1 <span style="color: Gray;">=</span> myThread<span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-1"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
thread2 <span style="color: Gray;">=</span> myThread<span style="color: Olive;">(</span><span style="color: Maroon;">2</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-2"</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 开启新线程</span><br/>
thread1.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
thread2.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 添加线程到线程列表</span><br/>
threads.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>thread1<span style="color: Olive;">)</span><br/>
threads.<span style="color: #05a;">append</span><span style="color: Olive;">(</span>thread2<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 等待所有线程完成</span><br/>
<span style="color: Green;font-weight:bold;">for</span> t <span style="color: Green;font-weight:bold;">in</span> threads:<br/>
    t.<span style="color: #05a;">join</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"退出主线程"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>执行以上程序，输出结果为：</p>&#13;
<pre>&#13;
开启线程： Thread-1&#13;
开启线程： Thread-2&#13;
Thread-1: Wed Jan  5 17:36:50 2022&#13;
Thread-1: Wed Jan  5 17:36:51 2022&#13;
Thread-1: Wed Jan  5 17:36:52 2022&#13;
Thread-2: Wed Jan  5 17:36:54 2022&#13;
Thread-2: Wed Jan  5 17:36:56 2022&#13;
Thread-2: Wed Jan  5 17:36:58 2022&#13;
退出主线程&#13;
</pre>&#13;
<hr/>&#13;
<h2>线程优先级队列（ Queue）&#13;
</h2>&#13;
<p>Python 的 Queue 模块中提供了同步的、线程安全的队列类，包括FIFO（先入先出)队列Queue，LIFO（后入先出）队列LifoQueue，和优先级队列 PriorityQueue。&#13;
</p><p>这些队列都实现了锁原语，能够在多线程中直接使用，可以使用队列来实现线程间的同步。</p>&#13;
&#13;
<p>Queue 模块中的常用方法:</p><p>&#13;
</p><ul>&#13;
<li>Queue.qsize() 返回队列的大小 </li>&#13;
<li>Queue.empty() 如果队列为空，返回True,反之False </li>&#13;
<li>Queue.full() 如果队列满了，返回True,反之False</li>&#13;
<li>Queue.full 与 maxsize 大小对应 </li>&#13;
<li>Queue.get([block[, timeout]])获取队列，timeout等待时间 </li>&#13;
<li>Queue.get_nowait() 相当Queue.get(False)</li>&#13;
<li>Queue.put(item) 写入队列，timeout等待时间 </li>&#13;
<li>Queue.put_nowait(item) 相当Queue.put(item, False)</li>&#13;
<li>Queue.task_done() 在完成一项工作之后，Queue.task_done()函数向任务已经完成的队列发送一个信号</li>&#13;
<li>Queue.join() 实际上意味着等到队列为空，再执行别的操作</li>&#13;
</ul>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> queue<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">threading</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
exitFlag <span style="color: Gray;">=</span> <span style="color: Maroon;">0</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">class</span> myThread <span style="color: Olive;">(</span><span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> threadID<span style="color: Gray;">,</span> name<span style="color: Gray;">,</span> q<span style="color: Olive;">)</span>:<br/>
        <span style="color: #05a;">threading</span>.<span style="color: #05a;">Thread</span>.<span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span><br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">threadID</span> <span style="color: Gray;">=</span> threadID<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span> <span style="color: Gray;">=</span> name<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">q</span> <span style="color: Gray;">=</span> q<br/>
    <span style="color: Green;font-weight:bold;">def</span> run<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"开启线程："</span> + <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Olive;">)</span><br/>
        process_data<span style="color: Olive;">(</span><span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">q</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"退出线程："</span> + <span style="color: Teal;">self</span>.<span style="color: #05a;">name</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">def</span> process_data<span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> q<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">while</span> <span style="color: Green;font-weight:bold;">not</span> exitFlag:<br/>
        queueLock.<span style="color: #05a;">acquire</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">if</span> <span style="color: Green;font-weight:bold;">not</span> workQueue.<span style="color: #05a;">empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
            data <span style="color: Gray;">=</span> q.<span style="color: #05a;">get</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
            queueLock.<span style="color: #05a;">release</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
            <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"%s processing %s"</span> % <span style="color: Olive;">(</span>threadName<span style="color: Gray;">,</span> data<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
        <span style="color: Green;font-weight:bold;">else</span>:<br/>
            queueLock.<span style="color: #05a;">release</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <span style="color: #05a;">time</span>.<span style="color: #05a;">sleep</span><span style="color: Olive;">(</span><span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
<br/>
threadList <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">"Thread-1"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-2"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Thread-3"</span><span style="color: Olive;">]</span><br/>
nameList <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: #a11;">"One"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Two"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Three"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Four"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"Five"</span><span style="color: Olive;">]</span><br/>
queueLock <span style="color: Gray;">=</span> <span style="color: #05a;">threading</span>.<span style="color: #05a;">Lock</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
workQueue <span style="color: Gray;">=</span> queue.<span style="color: #05a;">Queue</span><span style="color: Olive;">(</span><span style="color: Maroon;">10</span><span style="color: Olive;">)</span><br/>
threads <span style="color: Gray;">=</span> <span style="color: Olive;">[</span><span style="color: Olive;">]</span><br/>
threadID <span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
<br/>
<span style="color: #a50"># 创建新线程</span><br/>
<span style="color: Green;font-weight:bold;">for</span> tName <span style="color: Green;font-weight:bold;">in</span> threadList:<br/>
    <span style="color: #05a;">thread</span> <span style="color: Gray;">=</span> myThread<span style="color: Olive;">(</span>threadID<span style="color: Gray;">,</span> tName<span style="color: Gray;">,</span> workQueue<span style="color: Olive;">)</span><br/>
    <span style="color: #05a;">thread</span>.<span style="color: #05a;">start</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
    threads.<span style="color: #05a;">append</span><span style="color: Olive;">(</span><span style="color: #05a;">thread</span><span style="color: Olive;">)</span><br/>
    threadID +<span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
<br/>
<span style="color: #a50"># 填充队列</span><br/>
queueLock.<span style="color: #05a;">acquire</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">for</span> word <span style="color: Green;font-weight:bold;">in</span> nameList:<br/>
    workQueue.<span style="color: #05a;">put</span><span style="color: Olive;">(</span>word<span style="color: Olive;">)</span><br/>
queueLock.<span style="color: #05a;">release</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 等待队列清空</span><br/>
<span style="color: Green;font-weight:bold;">while</span> <span style="color: Green;font-weight:bold;">not</span> workQueue.<span style="color: #05a;">empty</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">pass</span><br/>
<br/>
<span style="color: #a50"># 通知线程是时候退出</span><br/>
exitFlag <span style="color: Gray;">=</span> <span style="color: Maroon;">1</span><br/>
<br/>
<span style="color: #a50"># 等待所有线程完成</span><br/>
<span style="color: Green;font-weight:bold;">for</span> t <span style="color: Green;font-weight:bold;">in</span> threads:<br/>
    t.<span style="color: #05a;">join</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"退出主线程"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以上程序执行结果：</p>&#13;
&#13;
<pre>&#13;
开启线程：Thread-1&#13;
开启线程：Thread-2&#13;
开启线程：Thread-3&#13;
Thread-3 processing One&#13;
Thread-1 processing Two&#13;
Thread-2 processing Three&#13;
Thread-3 processing Four&#13;
Thread-1 processing Five&#13;
退出线程：Thread-3&#13;
退出线程：Thread-2&#13;
退出线程：Thread-1&#13;
退出主线程&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>