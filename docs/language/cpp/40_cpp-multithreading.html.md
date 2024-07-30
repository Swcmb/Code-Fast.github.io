<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 多线程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">多线程</span></h1>&#13;
&#13;
<p>多线程是多任务处理的一种特殊形式，多任务处理允许让电脑同时运行两个或两个以上的程序。一般情况下，两种类型的多任务处理：<strong>基于进程和基于线程</strong>。</p>&#13;
<ul>&#13;
<li>基于进程的多任务处理是程序的并发执行。</li><li>基于线程的多任务处理是同一程序的片段的并发执行。</li></ul>&#13;
<p>多线程程序包含可以同时运行的两个或多个部分。这样的程序中的每个部分称为一个线程，每个线程定义了一个单独的执行路径。</p>&#13;
&#13;
<p>本教程假设您使用的是 Linux 操作系统，我们要使用 POSIX 编写多线程 C++ 程序。POSIX Threads 或 Pthreads 提供的 API 可在多种类 Unix POSIX 系统上可用，比如 FreeBSD、NetBSD、GNU/Linux、Mac OS X 和 Solaris。</p>&#13;
&#13;
<h2>创建线程</h2>&#13;
<p>下面的程序，我们可以用它来创建一个 POSIX 线程：</p>&#13;
<pre>&#13;
#include &lt;pthread.h&gt;&#13;
pthread_create (thread, attr, start_routine, arg) &#13;
</pre>&#13;
<p>在这里，<b>pthread_create</b> 创建一个新的线程，并让它可执行。下面是关于参数的说明：</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="25%">参数</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr>&#13;
<td>thread</td>&#13;
<td>指向线程标识符指针。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>attr</td>&#13;
<td>一个不透明的属性对象，可以被用来设置线程属性。您可以指定线程属性对象，也可以使用默认值 NULL。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>start_routine</td>&#13;
<td>线程运行函数起始地址，一旦线程被创建就会执行。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>arg</td>&#13;
<td>运行函数的参数。它必须通过把引用作为指针强制转换为 void 类型进行传递。如果没有传递参数，则使用 NULL。</td>&#13;
</tr>&#13;
</table>&#13;
<p>创建线程成功时，函数返回 0，若返回值不为 0 则说明创建线程失败。</p>&#13;
&#13;
<h2>终止线程</h2>&#13;
<p>使用下面的程序，我们可以用它来终止一个 POSIX 线程：</p>&#13;
<pre>&#13;
#include &lt;pthread.h&gt;&#13;
pthread_exit (status) &#13;
</pre>&#13;
<p>在这里，<b>pthread_exit</b> 用于显式地退出一个线程。通常情况下，pthread_exit() 函数是在线程完成工作后无需继续存在时被调用。</p>&#13;
<p>如果 main() 是在它所创建的线程之前结束，并通过 pthread_exit() 退出，那么其他线程将继续执行。否则，它们将在 main() 结束时自动被终止。</p>&#13;
&#13;
<h2>实例</h2>&#13;
<p>以下简单的实例代码使用 pthread_create() 函数创建了 5 个线程，每个线程输出"Hello Runoob！":</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-comment">// 必须的头文件</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">pthread.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code"> </span><span class="hl-number">5</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-comment">// 线程的运行函数</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">void</span><span class="hl-code">* </span><span class="hl-identifier">say_hello</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code">* </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Hello Runoob！</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-comment">// 定义线程的 id 变量，多个变量使用数组</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">pthread_t</span><span class="hl-code"> </span><span class="hl-identifier">tids</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">; ++</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-comment">//参数依次是：创建的线程id，线程参数，调用的函数，传入的函数参数</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">ret</span><span class="hl-code"> = </span><span class="hl-identifier">pthread_create</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">tids</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">, </span><span class="hl-prepro">NULL</span><span class="hl-code">, </span><span class="hl-identifier">say_hello</span><span class="hl-code">, </span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">ret</span><span class="hl-code"> != </span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">
        </span><span class="hl-brackets">{</span><span class="hl-code">
           </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">pthread_create error: error_code=</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">ret</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-comment">//等各个线程退出后，进程才结束，否则进程强制结束了，线程可能还没反应过来；</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>使用 -lpthread 库编译下面的程序：</p>&#13;
<pre>&#13;
$ g++ test.cpp -lpthread -o test.o&#13;
</pre>&#13;
<p>现在，执行程序，将产生下列结果：</p>&#13;
<pre>&#13;
$ ./test.o&#13;
Hello Runoob！&#13;
Hello Runoob！&#13;
Hello Runoob！&#13;
Hello Runoob！&#13;
Hello Runoob！&#13;
</pre>&#13;
<p>以下简单的实例代码使用 pthread_create() 函数创建了 5 个线程，并接收传入的参数。每个线程打印一个 "Hello Runoob!" 消息，并输出接收的参数，然后调用 pthread_exit() 终止线程。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//文件名：test.cpp</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cstdlib</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">pthread.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">     </span><span class="hl-number">5</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">PrintHello</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">threadid</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">  
   </span><span class="hl-comment">// 对传入的参数进行强制类型转换，由无类型指针变为整形数指针，然后再读取</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">tid</span><span class="hl-code"> = *</span><span class="hl-brackets">(</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code">*</span><span class="hl-brackets">)</span><span class="hl-identifier">threadid</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Hello Runoob! 线程 ID, </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">tid</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">pthread_t</span><span class="hl-code"> </span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">indexes</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;</span><span class="hl-comment">// 用数组来保存i的值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">rc</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">      
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">main() : 创建线程, </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-identifier">indexes</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code">; </span><span class="hl-comment">//先保存i的值</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-comment">// 传入的时候必须强制转换为void* 类型，即无类型指针        </span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">rc</span><span class="hl-code"> = </span><span class="hl-identifier">pthread_create</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">, </span><span class="hl-prepro">NULL</span><span class="hl-code">, 
                          </span><span class="hl-identifier">PrintHello</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-code">&amp;</span><span class="hl-brackets">(</span><span class="hl-identifier">indexes</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">rc</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Error:无法创建线程,</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">rc</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
         </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-code">-</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
<p>现在编译并执行程序，将产生下列结果：</p>&#13;
<pre>&#13;
$ g++ test.cpp -lpthread -o test.o&#13;
$ ./test.o&#13;
main() : 创建线程, 0&#13;
main() : 创建线程, 1&#13;
Hello Runoob! 线程 ID, 0&#13;
main() : 创建线程, Hello Runoob! 线程 ID, 21&#13;
&#13;
main() : 创建线程, 3&#13;
Hello Runoob! 线程 ID, 2&#13;
main() : 创建线程, 4&#13;
Hello Runoob! 线程 ID, 3&#13;
Hello Runoob! 线程 ID, 4&#13;
</pre>&#13;
&#13;
<h2>向线程传递参数</h2>&#13;
<p>这个实例演示了如何通过结构传递多个参数。您可以在线程回调中传递任意的数据类型，因为它指向 void，如下面的实例所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cstdlib</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">pthread.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">     </span><span class="hl-number">5</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">thread_data</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code">  </span><span class="hl-identifier">thread_id</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-identifier">message</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">;
 
</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">PrintHello</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">threadarg</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">thread_data</span><span class="hl-code"> *</span><span class="hl-identifier">my_data</span><span class="hl-code">;
 
   </span><span class="hl-identifier">my_data</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">thread_data</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">threadarg</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Thread ID : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">my_data</span><span class="hl-code">-&gt;</span><span class="hl-identifier">thread_id</span><span class="hl-code"> ;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string"> Message : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">my_data</span><span class="hl-code">-&gt;</span><span class="hl-identifier">message</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">pthread_t</span><span class="hl-code"> </span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">thread_data</span><span class="hl-code"> </span><span class="hl-identifier">td</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">rc</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
 
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt;</span><span class="hl-quotes">"</span><span class="hl-string">main() : creating thread, </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-identifier">td</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">.</span><span class="hl-identifier">thread_id</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code">;
      </span><span class="hl-identifier">td</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">.</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-code">*</span><span class="hl-brackets">)</span><span class="hl-quotes">"</span><span class="hl-string">This is message</span><span class="hl-quotes">"</span><span class="hl-code">;
      </span><span class="hl-identifier">rc</span><span class="hl-code"> = </span><span class="hl-identifier">pthread_create</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">, </span><span class="hl-prepro">NULL</span><span class="hl-code">,
                          </span><span class="hl-identifier">PrintHello</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-code">&amp;</span><span class="hl-identifier">td</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">rc</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Error:unable to create thread,</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">rc</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
         </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-code">-</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
$ g++ -Wno-write-strings test.cpp -lpthread -o test.o&#13;
$ ./test.o&#13;
main() : creating thread, 0&#13;
main() : creating thread, 1&#13;
Thread ID : 0 Message : This is message&#13;
main() : creating thread, Thread ID : 21&#13;
 Message : This is message&#13;
main() : creating thread, 3&#13;
Thread ID : 2 Message : This is message&#13;
main() : creating thread, 4&#13;
Thread ID : 3 Message : This is message&#13;
Thread ID : 4 Message : This is message&#13;
</pre>&#13;
&#13;
<h2>连接和分离线程</h2>&#13;
<p>我们可以使用以下两个函数来连接或分离线程：</p>&#13;
<pre>&#13;
pthread_join (threadid, status) &#13;
pthread_detach (threadid) &#13;
</pre>&#13;
<p>pthread_join() 子程序阻碍调用程序，直到指定的 threadid 线程终止为止。当创建一个线程时，它的某个属性会定义它是否是可连接的（joinable）或可分离的（detached）。只有创建时定义为可连接的线程才可以被连接。如果线程创建时被定义为可分离的，则它永远也不能被连接。</p>&#13;
<p>这个实例演示了如何使用 pthread_join() 函数来等待线程的完成。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cstdlib</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">pthread.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">unistd.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">     </span><span class="hl-number">5</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">wait</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">t</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-types">long</span><span class="hl-code"> </span><span class="hl-identifier">tid</span><span class="hl-code">;
 
   </span><span class="hl-identifier">tid</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">long</span><span class="hl-brackets">)</span><span class="hl-identifier">t</span><span class="hl-code">;
 
   </span><span class="hl-identifier">sleep</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Sleeping in thread </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Thread with id : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">tid</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">  ...exiting </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">rc</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_t</span><span class="hl-code"> </span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">NUM_THREADS</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_attr_t</span><span class="hl-code"> </span><span class="hl-identifier">attr</span><span class="hl-code">;
   </span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">status</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 初始化并设置线程为可连接的（joinable）</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">pthread_attr_init</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">attr</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_attr_setdetachstate</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">attr</span><span class="hl-code">, </span><span class="hl-identifier">PTHREAD_CREATE_JOINABLE</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">main() : creating thread, </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-identifier">rc</span><span class="hl-code"> = </span><span class="hl-identifier">pthread_create</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">, </span><span class="hl-prepro">NULL</span><span class="hl-code">, </span><span class="hl-identifier">wait</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-code">&amp;</span><span class="hl-identifier">i</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">rc</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Error:unable to create thread,</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">rc</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
         </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-code">-</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-comment">// 删除属性，并等待其他线程</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">pthread_attr_destroy</span><span class="hl-brackets">(</span><span class="hl-code">&amp;</span><span class="hl-identifier">attr</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">NUM_THREADS</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">rc</span><span class="hl-code"> = </span><span class="hl-identifier">pthread_join</span><span class="hl-brackets">(</span><span class="hl-identifier">threads</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">, &amp;</span><span class="hl-identifier">status</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">rc</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Error:unable to join,</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">rc</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
         </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-code">-</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Main: completed thread id :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> ;
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">  exiting with status :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">status</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Main: program exiting.</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">pthread_exit</span><span class="hl-brackets">(</span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
main() : creating thread, 0&#13;
main() : creating thread, 1&#13;
main() : creating thread, 2&#13;
main() : creating thread, 3&#13;
main() : creating thread, 4&#13;
Sleeping in thread &#13;
Thread with id : 4  ...exiting &#13;
Sleeping in thread &#13;
Thread with id : 3  ...exiting &#13;
Sleeping in thread &#13;
Thread with id : 2  ...exiting &#13;
Sleeping in thread &#13;
Thread with id : 1  ...exiting &#13;
Sleeping in thread &#13;
Thread with id : 0  ...exiting &#13;
Main: completed thread id :0  exiting with status :0&#13;
Main: completed thread id :1  exiting with status :0&#13;
Main: completed thread id :2  exiting with status :0&#13;
Main: completed thread id :3  exiting with status :0&#13;
Main: completed thread id :4  exiting with status :0&#13;
Main: program exiting.&#13;
</pre><hr/>&#13;
<h2>std::thread</h2>&#13;
<p>C++ 11 之后添加了新的标准线程库 <span class="marked">std::thread</span>，<span class="marked">std::thread</span> <strong>在 &lt;thread&gt;</strong> 头文件中声明，因此使用 <span class="marked">std::thread</span> 时需要包含 <strong>在 &lt;thread&gt;</strong> 头文件。</p>&#13;
&#13;
<p>之前一些编译器使用 C++ 11 的编译参数是 <strong>-std=c++11</strong>:</p>&#13;
<pre>g++ -std=c++11 test.cpp </pre>&#13;
<p><span class="marked">std::thread</span> 默认构造函数，创建一个空的<strong> std::thread</strong> 执行对象。</p>&#13;
<pre>#include&lt;thread&gt;&#13;
std::thread thread_object(callable)</pre>&#13;
<p>一个可调用对象可以是以下三个中的任何一个：</p>&#13;
<ul><li>&#13;
函数指针</li><li>&#13;
函数对象</li><li>&#13;
lambda 表达式</li></ul>&#13;
<p>定义 callable 后，将其传递给 <span class="marked">std::thread</span> 构造函数 <strong>thread_object</strong>。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #666666;">// 演示多线程的CPP程序</span><br/>
<span style="color: #666666;">// 使用三个不同的可调用对象</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;thread&gt;</span><br/>
<span style="color: #05a;">using</span> <span style="color: #05a;">namespace</span> std<span style="color: #008080;">;</span><br/>
  <br/>
<span style="color: #666666;">// 一个虚拟函数</span><br/>
<span style="color: #05a;">void</span> foo<span style="color: #008000;">(</span><span style="color: #05a;">int</span> Z<span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> Z<span style="color: #008080;">;</span> i<span style="color: #000040;">++</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"线程使用函数指针作为可调用参数<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><br/>
  <br/>
<span style="color: #666666;">// 可调用对象</span><br/>
<span style="color: #05a;">class</span> thread_obj <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">void</span> operator<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span><br/>
    <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> x<span style="color: #008080;">;</span> i<span style="color: #000040;">++</span><span style="color: #008000;">)</span><br/>
            <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"线程使用函数对象作为可调用参数<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
  <br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"线程 1 、2 、3 "</span><br/>
         <span style="color: #a11;">"独立运行"</span> <span style="color: #000080;">&lt;&lt;</span> endl<span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 函数指针</span><br/>
    thread th1<span style="color: #008000;">(</span>foo, <span style="color: #0000dd;">3</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 函数对象</span><br/>
    thread th2<span style="color: #008000;">(</span>thread_obj<span style="color: #008000;">(</span><span style="color: #008000;">)</span>, <span style="color: #0000dd;">3</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 定义 Lambda 表达式</span><br/>
    <span style="color: #05a;">auto</span> f <span style="color: #000080;">=</span> <span style="color: #008000;">[</span><span style="color: #008000;">]</span><span style="color: #008000;">(</span><span style="color: #05a;">int</span> x<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> x<span style="color: #008080;">;</span> i<span style="color: #000040;">++</span><span style="color: #008000;">)</span><br/>
            <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"线程使用 lambda 表达式作为可调用参数<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 线程通过使用 lambda 表达式作为可调用的参数</span><br/>
    thread th3<span style="color: #008000;">(</span>f, <span style="color: #0000dd;">3</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 等待线程完成</span><br/>
    <span style="color: #666666;">// 等待线程 t1 完成</span><br/>
    th1.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 等待线程 t2 完成</span><br/>
    th2.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #666666;">// 等待线程 t3 完成</span><br/>
    th3.<span style="color: #007788;">join</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
  <br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
&#13;
<p>使用 C++ 11 的编译参数 <strong>-std=c++11</strong>:</p>&#13;
<pre>g++ -std=c++11 test.cpp </pre><p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>线程 1 、2 、3 独立运行&#13;
线程使用函数指针作为可调用参数&#13;
线程使用函数指针作为可调用参数&#13;
线程使用函数指针作为可调用参数&#13;
线程使用函数对象作为可调用参数&#13;
线程使用函数对象作为可调用参数&#13;
线程使用函数对象作为可调用参数&#13;
线程使用 lambda 表达式作为可调用参数&#13;
线程使用 lambda 表达式作为可调用参数&#13;
线程使用 lambda 表达式作为可调用参数</pre>&#13;
<blockquote><p>更多实例参考：</p>&#13;
<p>&#13;
C++ 多线程: <a href="//www.runoob.com/w3cnote/cpp-multithread-demo.html" rel="noopener" target="_blank">http://www.runoob.com/w3cnote/cpp-multithread-demo.html</a></p>&#13;
<p><strong>C++ std::thread</strong>: <a href="https://www.runoob.com/w3cnote/cpp-std-thread.html" rel="noopener" target="_blank">https://www.runoob.com/w3cnote/cpp-std-thread.html</a></p></blockquote>&#13;
&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>