<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 信号处理</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">信号处理</span></h1>&#13;
&#13;
<p>信号是由操作系统传给进程的中断，会提早终止一个程序。在 UNIX、LINUX、Mac OS X 或 Windows 系统上，可以通过按 Ctrl+C 产生中断。</p>&#13;
<p>有些信号不能被程序捕获，但是下表所列信号可以在程序中捕获，并可以基于信号采取适当的动作。这些信号是定义在 C++ 头文件 &lt;csignal&gt; 中。</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="20%">信号</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGABRT</td>&#13;
<td>程序的异常终止，如调用 <b>abort</b>。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGFPE</td>&#13;
<td>错误的算术运算，比如除以零或导致溢出的操作。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGILL</td>&#13;
<td>检测非法指令。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGINT</td>&#13;
<td>程序终止(interrupt)信号。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGSEGV</td>&#13;
<td>非法访问内存。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>SIGTERM</td>&#13;
<td>发送到程序的终止请求。</td>&#13;
</tr>&#13;
</table>&#13;
&#13;
<h2>signal() 函数</h2>&#13;
<p>C++ 信号处理库提供了 <b>signal</b> 函数，用来捕获突发事件。以下是 signal() 函数的语法：</p>&#13;
<pre>&#13;
void (*signal (int sig, void (*func)(int)))(int); &#13;
</pre><p>&#13;
这个看起来有点费劲，以下语法格式更容易理解：</p>&#13;
<pre>signal(registered signal, signal handler)</pre>&#13;
<p>这个函数接收两个参数：第一个参数是要设置的信号的标识符，第二个参数是指向信号处理函数的指针。函数返回值是一个指向先前信号处理函数的指针。如果先前没有设置信号处理函数，则返回值为 SIG_DFL。如果先前设置的信号处理函数为 SIG_IGN，则返回值为 SIG_IGN。</p>&#13;
<p>让我们编写一个简单的 C++ 程序，使用 signal() 函数捕获 SIGINT 信号。不管您想在程序中捕获什么信号，您都必须使用 <b>signal</b> 函数来注册信号，并将其与信号处理程序相关联。看看下面的实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">csignal</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">unistd.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">signalHandler</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">signum</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Interrupt signal (</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">signum</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">) received.</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
    </span><span class="hl-comment">// 清理并关闭</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">// 终止程序  </span><span class="hl-comment"/><span class="hl-code">
 
   </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-identifier">signum</span><span class="hl-brackets">)</span><span class="hl-code">;  
 
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-comment">// 注册信号 SIGINT 和信号处理程序</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">signal</span><span class="hl-brackets">(</span><span class="hl-identifier">SIGINT</span><span class="hl-code">, </span><span class="hl-identifier">signalHandler</span><span class="hl-brackets">)</span><span class="hl-code">;  
 
    </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Going to sleep....</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
       </span><span class="hl-identifier">sleep</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
 
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Going to sleep....&#13;
Going to sleep....&#13;
Going to sleep....&#13;
</pre>&#13;
<p>现在，按 Ctrl+C 来中断程序，您会看到程序捕获信号，程序打印如下内容并退出：</p>&#13;
<pre>&#13;
Going to sleep....&#13;
Going to sleep....&#13;
Going to sleep....&#13;
Interrupt signal (2) received.&#13;
</pre>&#13;
&#13;
<h2>raise() 函数</h2>&#13;
<p>您可以使用函数 <b>raise()</b> 生成信号，该函数带有一个整数信号编号作为参数，语法如下：</p>&#13;
<pre>&#13;
int raise (signal sig);&#13;
</pre>&#13;
<p>在这里，<b>sig</b> 是要发送的信号的编号，这些信号包括：SIGINT、SIGABRT、SIGFPE、SIGILL、SIGSEGV、SIGTERM、SIGHUP。以下是我们使用 raise() 函数内部生成信号的实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">csignal</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">unistd.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">signalHandler</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">signum</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Interrupt signal (</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">signum</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">) received.</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
    </span><span class="hl-comment">// 清理并关闭</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">// 终止程序 </span><span class="hl-comment"/><span class="hl-code">
 
   </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-identifier">signum</span><span class="hl-brackets">)</span><span class="hl-code">;  
 
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-comment">// 注册信号 SIGINT 和信号处理程序</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">signal</span><span class="hl-brackets">(</span><span class="hl-identifier">SIGINT</span><span class="hl-code">, </span><span class="hl-identifier">signalHandler</span><span class="hl-brackets">)</span><span class="hl-code">;  
 
    </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-code">++</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Going to sleep....</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
       </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> == </span><span class="hl-number">3</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">raise</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">SIGINT</span><span class="hl-brackets">)</span><span class="hl-code">;
       </span><span class="hl-brackets">}</span><span class="hl-code">
       </span><span class="hl-identifier">sleep</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
 
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果，并会自动退出：</p>&#13;
<pre>&#13;
Going to sleep....&#13;
Going to sleep....&#13;
Going to sleep....&#13;
Interrupt signal (2) received.&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>