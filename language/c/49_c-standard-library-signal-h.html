<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <signal.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;signal.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p><code>&lt;signal.h&gt;</code> 是 C 标准库中的一个头文件，用于处理信号。</p><p>&#13;
</p><p><b>signal.h</b> 头文件定义了一个变量类型 <b>sig_atomic_t</b>、两个函数调用和一些宏来处理程序执行期间报告的不同信号。</p>&#13;
<p>信号是一种异步通知机制，允许进程在特定事件发生时执行预定义的处理函数。</p>&#13;
<p>&#13;
下面是一个简单的示例程序，演示如何使用 signal 函数来捕捉 SIGINT 信号（通常由 Ctrl+C 产生）。&#13;
</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;signal.h&gt;</span><br/>
<span style="color: #085;">#include &lt;unistd.h&gt;</span><br/>
<br/>
<span style="color: #666666; font-style: italic;">// 全局变量，指示程序是否应退出</span><br/>
<span style="color: #993333;">volatile</span> sig_atomic_t stop <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #993333;">void</span> handle_sigint<span style="color: #000;">(</span><span style="color: #993333;">int</span> sig<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Caught signal %d<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> sig<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    stop <span style="color: #339933;">=</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 设置退出标志</span><br/>
<span style="color: #000;">}</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #666666; font-style: italic;">// 将 SIGINT 信号的处理程序设置为 handle_sigint 函数</span><br/>
    signal<span style="color: #000;">(</span>SIGINT<span style="color: #339933;">,</span> handle_sigint<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #708;">while</span> <span style="color: #000;">(</span><span style="color: #339933;">!</span>stop<span style="color: #000;">)</span> <span style="color: #000;">{</span> <span style="color: #666666; font-style: italic;">// 检查是否应退出</span><br/>
        <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Running...<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
        sleep<span style="color: #000;">(</span><span style="color: #164;">1</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
<br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Exiting...<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>&#13;
以上代码中，当程序运行时，如果用户按下 <span class="marked">Ctrl+C</span>，会捕捉到 SIGINT 信号并调用 handle_sigint 函数，打印出信号编号。</p>&#13;
<p>编译执行以上代码，输出结果如下：</p>&#13;
<pre>Running...&#13;
Running...&#13;
Running...&#13;
^CCaught signal 2&#13;
Exiting...</pre><p>&#13;
代码解析：</p>&#13;
<ul><li><code>volatile sig_atomic_t stop = 0;</code>：定义一个全局变量 <code>stop</code>，用于指示程序是否应退出。使用 <code>volatile</code> 关键字确保编译器不会优化掉对该变量的访问，因为它可能在信号处理程序中被修改。<code>sig_atomic_t</code> 类型保证了对该变量的访问是原子的。</li><li>在 <code>handle_sigint</code> 信号处理函数中，将 <code>stop</code> 设置为 1，指示程序应退出。</li><li>在主循环中，检查 <code>stop</code> 变量的值，如果它被设置为 1，则跳出循环，结束程序。</li></ul>&#13;
<h2>库变量</h2>&#13;
<p>下面是头文件 signal.h 中定义的变量类型：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>变量 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>sig_atomic_t </b><br/>这是 <b>int</b> 类型，在信号处理程序中作为变量使用。它是一个对象的整数类型，该对象可以作为一个原子实体访问，即使存在异步信号时，该对象可以作为一个原子实体访问。</td></tr>&#13;
&#13;
<tr><td>2</td><td><b>sigset_t </b><br/>一种数据类型，用于表示信号集。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库宏</h2>&#13;
&lt;<p>在 C 标准库中，<code>SIG_</code> 前缀的宏与 <code>signal</code> 函数一起使用，用于定义和处理信号的行为。下面是常见的 <code>SIG_</code> 宏及其用途：</p>&#13;
<table class="reference notranslate">&#13;
<tbody><tr><th style="width:5%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1 </td><td><b>SIG_DFL</b><br/>表示信号的默认处理程序。使用此宏将信号恢复到其默认行为。</td></tr>&#13;
<tr><td>2 </td><td><b>SIG_ERR</b><br/>表示信号处理函数设置出错的返回值。</td></tr>&#13;
<tr><td>3 </td><td><b>SIG_IGN</b><br/>忽略信号。</td></tr>&#13;
</tbody></table>&#13;
<p>信号类型：</p>&#13;
<table class="reference">&#13;
<thead><tr><th>常量</th><th>描述</th></tr></thead><tbody><tr><td><code>SIGABRT</code></td><td>由 <code>abort</code> 函数产生的信号，表示异常终止</td></tr><tr><td><code>SIGALRM</code></td><td>由 <code>alarm</code> 函数设定的定时器到期信号</td></tr><tr><td><code>SIGBUS</code></td><td>非法内存访问（例如，访问未对齐的内存地址）</td></tr><tr><td><code>SIGCHLD</code></td><td>子进程状态改变（退出或停止）</td></tr><tr><td><code>SIGCONT</code></td><td>继续执行被暂停的进程</td></tr><tr><td><code>SIGFPE</code></td><td>算术错误（例如，除零错误、浮点异常）</td></tr><tr><td><code>SIGHUP</code></td><td>挂起信号（通常用于检测终端断开）</td></tr><tr><td><code>SIGILL</code></td><td>非法指令</td></tr><tr><td><code>SIGINT</code></td><td>中断信号（通常由 Ctrl+C 产生）</td></tr><tr><td><code>SIGKILL</code></td><td>立即终止信号（不能被捕捉或忽略）</td></tr><tr><td><code>SIGPIPE</code></td><td>向无读进程的管道写数据</td></tr><tr><td><code>SIGQUIT</code></td><td>终端退出信号（通常由 Ctrl+\ 产生），生成核心转储</td></tr><tr><td><code>SIGSEGV</code></td><td>段错误（非法内存访问）</td></tr><tr><td><code>SIGSTOP</code></td><td>停止进程的执行（不能被捕捉或忽略）</td></tr><tr><td><code>SIGTERM</code></td><td>终止信号</td></tr><tr><td><code>SIGTSTP</code></td><td>暂停进程（通常由 Ctrl+Z 产生）</td></tr><tr><td><code>SIGTTIN</code></td><td>后台进程从终端读数据时产生的信号</td></tr><tr><td><code>SIGTTOU</code></td><td>后台进程向终端写数据时产生的信号</td></tr><tr><td><code>SIGUSR1</code></td><td>用户自定义信号 1</td></tr><tr><td><code>SIGUSR2</code></td><td>用户自定义信号 2</td></tr><tr><td><code>SIGPOLL</code></td><td>I/O 事件（取代 SIGIO）</td></tr><tr><td><code>SIGPROF</code></td><td>定时器到期信号（由 <code>setitimer</code> 设置的 profiling timer）</td></tr><tr><td><code>SIGSYS</code></td><td>非法系统调用</td></tr><tr><td><code>SIGTRAP</code></td><td>断点或陷阱指令</td></tr><tr><td><code>SIGURG</code></td><td>套接字紧急条件信号</td></tr><tr><td><code>SIGVTALRM</code></td><td>虚拟时钟定时器到期信号</td></tr><tr><td><code>SIGXCPU</code></td><td>超过 CPU 时间限制</td></tr><tr><td><code>SIGXFSZ</code></td><td>超过文件大小限制</td></tr></tbody></table>&#13;
<h2>库函数</h2>&#13;
<p>下面是头文件 signal.h 中定义的函数：</p>&#13;
&#13;
<table class="reference">&#13;
    <thead>&#13;
        <tr>&#13;
            <th>函数</th>&#13;
            <th>描述</th>&#13;
        </tr>&#13;
    </thead>&#13;
    <tbody>&#13;
        <tr>&#13;
            <td><code><a href="c-function-signal.html">void (*signal(int sig, void (*func)(int)))(int);</a></code></td>&#13;
            <td>设置信号处理程序。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-raise.html">int raise(int sig);</a></code></td>&#13;
            <td>向当前进程发送信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-kill.html">int kill(pid_t pid, int sig);</a></code></td>&#13;
            <td>向指定进程发送信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigprocmask.html">int sigprocmask(int how, const sigset_t *set, sigset_t *oldset);</a></code></td>&#13;
            <td>检查或更改阻塞信号集。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigaction.html">int sigaction(int sig, const struct sigaction *act, struct sigaction *oldact);</a></code></td>&#13;
            <td>检查或更改信号处理程序。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigsuspend.html">int sigsuspend(const sigset_t *mask);</a></code></td>&#13;
            <td>暂时替换当前信号屏蔽字并挂起进程直到捕捉到信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigpending.html">int sigpending(sigset_t *set);</a></code></td>&#13;
            <td>检查未决信号集。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigemptyset.html">int sigemptyset(sigset_t *set);</a></code></td>&#13;
            <td>初始化信号集为空集。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigfillset.html">int sigfillset(sigset_t *set);</a></code></td>&#13;
            <td>初始化信号集为全信号集。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigaddset.html">int sigaddset(sigset_t *set, int signum);</a></code></td>&#13;
            <td>向信号集中添加指定信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigdelset.html">int sigdelset(sigset_t *set, int signum);</a></code></td>&#13;
            <td>从信号集中删除指定信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigismember.html">int sigismember(const sigset_t *set, int signum);</a></code></td>&#13;
            <td>检查指定信号是否在信号集中。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-abort.html">void abort(void);</a></code></td>&#13;
            <td>产生 <code>SIGABRT</code> 信号，导致进程异常终止。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-alarm.html">unsigned int alarm(unsigned int seconds);</a></code></td>&#13;
            <td>在指定秒数后发送 <code>SIGALRM</code> 信号给调用进程。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-pause.html">int pause(void);</a></code></td>&#13;
            <td>挂起进程直到捕捉到信号。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-psignal.html">void psignal(int sig, const char *s);</a></code></td>&#13;
            <td>打印信号描述信息。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-strsignal.html">char *strsignal(int sig);</a></code></td>&#13;
            <td>返回信号描述字符串。</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><code><a href="c-function-sigwait.html">int sigwait(const sigset_t *set, int *sig);</a></code></td>&#13;
            <td>阻塞等待信号并处理。</td>&#13;
        </tr>&#13;
    </tbody>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>