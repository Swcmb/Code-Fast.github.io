<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 多线程编程
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 多线程编程&#13;
</h1>&#13;
<p>&#13;
Java 给多线程编程提供了内置的支持。&#13;
一条线程指的是进程中一个单一顺序的控制流，一个进程中可以并发多个线程，每条线程并行执行不同的任务。</p><p>&#13;
多线程是多任务的一种特别的形式，但多线程使用了更小的资源开销。</p><p>&#13;
这里定义和线程相关的另一个术语 - 进程：一个进程包括由操作系统分配的内存空间，包含一个或多个线程。一个线程不能独立的存在，它必须是进程的一部分。一个进程一直运行，直到所有的非守护线程都结束运行后才能结束。</p><p>&#13;
多线程能满足程序员编写高效率的程序来达到充分利用 CPU 的目的。</p><hr/>&#13;
<h2>&#13;
一个线程的生命周期&#13;
</h2>&#13;
<p>&#13;
线程是一个动态执行的过程，它也有一个从产生到死亡的过程。</p><p>下图显示了一个线程完整的生命周期。</p>&#13;
<p>&#13;
<img decoding="async" src="//www.runoob.com/wp-content/uploads/2014/01/java-thread.jpg"/>&#13;
</p>&#13;
<ul>&#13;
<li><b>新建状态:</b><p>使用 <strong>new</strong> 关键字和 <strong>Thread</strong> 类或其子类建立一个线程对象后，该线程对象就处于新建状态。它保持这个状态直到程序 <strong>start()</strong> 这个线程。</p></li>&#13;
&#13;
<li><b>就绪状态:</b><p>当线程对象调用了start()方法之后，该线程就进入就绪状态。就绪状态的线程处于就绪队列中，要等待JVM里线程调度器的调度。</p></li>&#13;
<li><b>运行状态:</b><p>如果就绪状态的线程获取 CPU 资源，就可以执行 <strong>run()</strong>，此时线程便处于运行状态。处于运行状态的线程最为复杂，它可以变为阻塞状态、就绪状态和死亡状态。</p></li>&#13;
<li><b>阻塞状态:</b><p>如果一个线程执行了sleep（睡眠）、suspend（挂起）等方法，失去所占用资源之后，该线程就从运行状态进入阻塞状态。在睡眠时间已到或获得设备资源后可以重新进入就绪状态。可以分为三种：  </p>&#13;
&#13;
<ul><li><p>等待阻塞：运行状态中的线程执行 wait() 方法，使线程进入到等待阻塞状态。&#13;
</p></li><li><p>同步阻塞：线程在获取 synchronized 同步锁失败(因为同步锁被其他线程占用)。&#13;
</p></li><li><p>其他阻塞：通过调用线程的 sleep() 或 join() 发出了 I/O 请求时，线程就会进入到阻塞状态。当sleep() 状态超时，join() 等待线程终止或超时，或者 I/O 处理完毕，线程重新转入就绪状态。</p></li>&#13;
&#13;
</ul>&#13;
</li>&#13;
<li><b>死亡状态: </b><p>一个运行状态的线程完成任务或者其他终止条件发生时，该线程就切换到终止状态。</p></li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>&#13;
线程的优先级</h2>&#13;
<p>每一个 Java 线程都有一个优先级，这样有助于操作系统确定线程的调度顺序。</p><p>Java 线程的优先级是一个整数，其取值范围是 1 （Thread.MIN_PRIORITY ） - 10 （Thread.MAX_PRIORITY ）。</p><p>默认情况下，每一个线程都会分配一个优先级 NORM_PRIORITY（5）。&#13;
</p><p>具有较高优先级的线程对程序更重要，并且应该在低优先级的线程之前分配处理器资源。但是，线程优先级不能保证线程执行的顺序，而且非常依赖于平台。</p>&#13;
<hr/>&#13;
<h2>&#13;
创建一个线程</h2>&#13;
<p>Java 提供了三种创建线程的方法：</p>&#13;
<ul><li>&#13;
通过实现 Runnable 接口；</li><li>&#13;
通过继承  Thread 类本身；</li>&#13;
<li>通过 Callable 和 Future 创建线程。</li>&#13;
</ul>&#13;
<hr/><h2>&#13;
通过实现 Runnable 接口来创建线程</h2>&#13;
<p>&#13;
创建一个线程，最简单的方法是创建一个实现 Runnable 接口的类。</p><p>&#13;
为了实现 Runnable，一个类只需要执行一个方法调用 run()，声明如下：</p><p>&#13;
</p><div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
你可以重写该方法，重要的是理解的 run() 可以调用其他方法，使用其他类，并声明变量，就像主线程一样。</p><p>&#13;
在创建一个实现 Runnable 接口的类之后，你可以在类中实例化一个线程对象。</p><p>&#13;
Thread 定义了几个构造方法，下面的这个是我们经常使用的：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">Thread</span><span class="hl-brackets">(</span><span class="hl-identifier">Runnable</span><span class="hl-code"> </span><span class="hl-identifier">threadOb</span><span class="hl-code">,</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">threadName</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
这里，threadOb 是一个实现 Runnable 接口的类的实例，并且 threadName 指定新线程的名字。</p><p>&#13;
新线程创建之后，你调用它的 start() 方法它才会运行。</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>&#13;
下面是一个创建线程并开始让它执行的实例：&#13;
</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">RunnableDemo</span><span class="hl-code"> </span><span class="hl-reserved">implements</span><span class="hl-code"> </span><span class="hl-identifier">Runnable</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">t</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">threadName</span><span class="hl-code">;
   
   </span><span class="hl-identifier">RunnableDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">threadName</span><span class="hl-code"> = </span><span class="hl-identifier">name</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Creating </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Running </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">4</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &gt; </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">--</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">, </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-comment">//</span><span class="hl-comment"> 让线程睡眠一会</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">Thread</span><span class="hl-code">.</span><span class="hl-identifier">sleep</span><span class="hl-brackets">(</span><span class="hl-number">50</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">InterruptedException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> interrupted.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> exiting.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">start</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">t</span><span class="hl-code"> == </span><span class="hl-reserved">null</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">t</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-reserved">this</span><span class="hl-code">, </span><span class="hl-identifier">threadName</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">t</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">TestThread</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">RunnableDemo</span><span class="hl-code"> </span><span class="hl-identifier">R1</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">RunnableDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Thread-1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">R1</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      
      </span><span class="hl-identifier">RunnableDemo</span><span class="hl-code"> </span><span class="hl-identifier">R2</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">RunnableDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Thread-2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">R2</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">   
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<p>&#13;
编译以上程序运行结果如下：&#13;
 </p>&#13;
<pre>&#13;
Creating Thread-1&#13;
Starting Thread-1&#13;
Creating Thread-2&#13;
Starting Thread-2&#13;
Running Thread-1&#13;
Thread: Thread-1, 4&#13;
Running Thread-2&#13;
Thread: Thread-2, 4&#13;
Thread: Thread-1, 3&#13;
Thread: Thread-2, 3&#13;
Thread: Thread-1, 2&#13;
Thread: Thread-2, 2&#13;
Thread: Thread-1, 1&#13;
Thread: Thread-2, 1&#13;
Thread Thread-1 exiting.&#13;
Thread Thread-2 exiting.&#13;
</pre>&#13;
<hr/>&#13;
<h2>&#13;
通过继承Thread来创建线程</h2>&#13;
<p>&#13;
创建一个线程的第二种方法是创建一个新的类，该类继承 Thread 类，然后创建一个该类的实例。</p><p>&#13;
继承类必须重写 run() 方法，该方法是新线程的入口点。它也必须调用 start() 方法才能执行。</p>&#13;
<p>该方法尽管被列为一种多线程实现方式，但是本质上也是实现了 Runnable 接口的一个实例。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">ThreadDemo</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">t</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">threadName</span><span class="hl-code">;
   
   </span><span class="hl-identifier">ThreadDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">threadName</span><span class="hl-code"> = </span><span class="hl-identifier">name</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Creating </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Running </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">4</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &gt; </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">--</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">, </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-comment">//</span><span class="hl-comment"> 让线程睡眠一会</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">Thread</span><span class="hl-code">.</span><span class="hl-identifier">sleep</span><span class="hl-brackets">(</span><span class="hl-number">50</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">InterruptedException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> interrupted.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> exiting.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">start</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting </span><span class="hl-quotes">"</span><span class="hl-code"> +  </span><span class="hl-identifier">threadName</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">t</span><span class="hl-code"> == </span><span class="hl-reserved">null</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">t</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-reserved">this</span><span class="hl-code">, </span><span class="hl-identifier">threadName</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">t</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">TestThread</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">ThreadDemo</span><span class="hl-code"> </span><span class="hl-identifier">T1</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">ThreadDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Thread-1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">T1</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      
      </span><span class="hl-identifier">ThreadDemo</span><span class="hl-code"> </span><span class="hl-identifier">T2</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">ThreadDemo</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Thread-2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">T2</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">   
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<p>编译以上程序运行结果如下：&#13;
</p>&#13;
<pre>&#13;
Creating Thread-1&#13;
Starting Thread-1&#13;
Creating Thread-2&#13;
Starting Thread-2&#13;
Running Thread-1&#13;
Thread: Thread-1, 4&#13;
Running Thread-2&#13;
Thread: Thread-2, 4&#13;
Thread: Thread-1, 3&#13;
Thread: Thread-2, 3&#13;
Thread: Thread-1, 2&#13;
Thread: Thread-2, 2&#13;
Thread: Thread-1, 1&#13;
Thread: Thread-2, 1&#13;
Thread Thread-1 exiting.&#13;
Thread Thread-2 exiting.&#13;
</pre><hr/>&#13;
<h2>&#13;
Thread 方法</h2>&#13;
<p>&#13;
下表列出了Thread类的一些重要方法：&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>序号</strong></th>&#13;
			<th style="text-align: center;">&#13;
				<strong>方法描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public void start()</strong><br/>&#13;
				使该线程开始执行；<b style="color:black;background-color:#ffff66">Java</b> 虚拟机调用该线程的 run 方法。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public void run()</strong><br/>&#13;
				如果该线程是使用独立的 Runnable 运行对象构造的，则调用该 Runnable 对象的 run 方法；否则，该方法不执行任何操作并返回。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public final void setName(String name)</strong><br/>&#13;
				改变线程名称，使之与参数 name 相同。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public final void setPriority(int priority)</strong><br/>&#13;
				 更改线程的优先级。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>public final void setDaemon(boolean on)</strong><br/>&#13;
				将该线程标记为守护线程或用户线程。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				6</td>&#13;
			<td>&#13;
				<strong>public final void join(long millisec)</strong><br/>&#13;
				等待该线程终止的时间最长为 millis 毫秒。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				7</td>&#13;
			<td>&#13;
				<strong>public void interrupt()</strong><br/>&#13;
				中断线程。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				8</td>&#13;
			<td>&#13;
				<strong>public final boolean isAlive()</strong><br/>&#13;
				测试线程是否处于活动状态。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>上述方法是被 Thread 对象调用的，下面表格的方法是 Thread 类的静态方法。&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>序号</strong></th>&#13;
			<th style="text-align: center;">&#13;
				<strong>方法描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public static void yield()</strong><br/>&#13;
				暂停当前正在执行的线程对象，并执行其他线程。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public static void sleep(long millisec)</strong><br/>&#13;
				在指定的毫秒数内让当前正在执行的线程休眠（暂停执行），此操作受到系统计时器和调度程序精度和准确性的影响。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public static boolean holdsLock(Object x)</strong><br/>&#13;
				当且仅当当前线程在指定的对象上保持监视器锁时，才返回 true。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public static Thread currentThread()</strong><br/>&#13;
				返回对当前正在执行的线程对象的引用。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>public static void dumpStack()</strong><br/>&#13;
				将当前线程的堆栈跟踪打印至标准错误流。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
&#13;
<h3>实例</h3>&#13;
<p>&#13;
如下的ThreadClassDemo 程序演示了Thread类的一些方法：&#13;
</p>&#13;
<div class="example"> &#13;
<h2 class="example">DisplayMessage.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 : DisplayMessage.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">//</span><span class="hl-comment"> 通过实现 Runnable 接口创建线程</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">DisplayMessage</span><span class="hl-code"> </span><span class="hl-reserved">implements</span><span class="hl-code"> </span><span class="hl-identifier">Runnable</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-code">;
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">DisplayMessage</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-identifier">message</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-reserved">true</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<div class="example"> &#13;
<h2 class="example">GuessANumber.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 : GuessANumber.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">//</span><span class="hl-comment"> 通过继承 Thread 类创建线程</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">GuessANumber</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">GuessANumber</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">number</span><span class="hl-code"> = </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">counter</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">guess</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
      </span><span class="hl-reserved">do</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">guess</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">Math</span><span class="hl-code">.</span><span class="hl-identifier">random</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> * </span><span class="hl-number">100</span><span class="hl-code"> + </span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> guesses </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">guess</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">counter</span><span class="hl-code">++;
      </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-identifier">guess</span><span class="hl-code"> != </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">** Correct!</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">in</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">counter</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">guesses.**</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<div class="example"> &#13;
<h2 class="example">ThreadClassDemo.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 : ThreadClassDemo.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">ThreadClassDemo</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">Runnable</span><span class="hl-code"> </span><span class="hl-identifier">hello</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DisplayMessage</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">thread1</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-brackets">(</span><span class="hl-identifier">hello</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread1</span><span class="hl-code">.</span><span class="hl-identifier">setDaemon</span><span class="hl-brackets">(</span><span class="hl-reserved">true</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread1</span><span class="hl-code">.</span><span class="hl-identifier">setName</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting hello thread...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread1</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      
      </span><span class="hl-identifier">Runnable</span><span class="hl-code"> </span><span class="hl-identifier">bye</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DisplayMessage</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Goodbye</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">thread2</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-brackets">(</span><span class="hl-identifier">bye</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread2</span><span class="hl-code">.</span><span class="hl-identifier">setPriority</span><span class="hl-brackets">(</span><span class="hl-identifier">Thread</span><span class="hl-code">.</span><span class="hl-identifier">MIN_PRIORITY</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread2</span><span class="hl-code">.</span><span class="hl-identifier">setDaemon</span><span class="hl-brackets">(</span><span class="hl-reserved">true</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting goodbye thread...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread2</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting thread3...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">thread3</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">GuessANumber</span><span class="hl-brackets">(</span><span class="hl-number">27</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">thread3</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">thread3</span><span class="hl-code">.</span><span class="hl-identifier">join</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">InterruptedException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Thread interrupted.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting thread4...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">thread4</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">GuessANumber</span><span class="hl-brackets">(</span><span class="hl-number">75</span><span class="hl-brackets">)</span><span class="hl-code">;
      
      </span><span class="hl-identifier">thread4</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">main() is ending...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<p>&#13;
运行结果如下，每一次运行的结果都不一样。&#13;
 </p>&#13;
<pre>&#13;
Starting hello thread...&#13;
Starting goodbye thread...&#13;
Hello&#13;
Hello&#13;
Hello&#13;
Hello&#13;
Hello&#13;
Hello&#13;
Goodbye&#13;
Goodbye&#13;
Goodbye&#13;
Goodbye&#13;
Goodbye&#13;
.......&#13;
</pre>&#13;
&#13;
<hr/>&#13;
<h2>通过 Callable 和 Future 创建线程</h2><ul><li><p>&#13;
1. 创建 Callable 接口的实现类，并实现 call() 方法，该 call() 方法将作为线程执行体，并且有返回值。</p></li><li><p>&#13;
2. 创建 Callable 实现类的实例，使用 FutureTask 类来包装 Callable 对象，该 FutureTask 对象封装了该 Callable 对象的 call() 方法的返回值。</p></li><li><p>&#13;
3. 使用 FutureTask 对象作为 Thread 对象的 target 创建并启动新线程。</p></li><li><p>&#13;
4. 调用 FutureTask 对象的 get() 方法来获得子线程执行结束后的返回值。</p></li></ul>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">CallableThreadTest</span><span class="hl-code"> </span><span class="hl-reserved">implements</span><span class="hl-code"> </span><span class="hl-identifier">Callable</span><span class="hl-code">&lt;</span><span class="hl-identifier">Integer</span><span class="hl-code">&gt; </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">  
    </span><span class="hl-brackets">{</span><span class="hl-code">  
        </span><span class="hl-identifier">CallableThreadTest</span><span class="hl-code"> </span><span class="hl-identifier">ctt</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">CallableThreadTest</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-identifier">FutureTask</span><span class="hl-code">&lt;</span><span class="hl-identifier">Integer</span><span class="hl-code">&gt; </span><span class="hl-identifier">ft</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FutureTask</span><span class="hl-code">&lt;&gt;</span><span class="hl-brackets">(</span><span class="hl-identifier">ctt</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">100</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">  
        </span><span class="hl-brackets">{</span><span class="hl-code">  
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">Thread</span><span class="hl-code">.</span><span class="hl-identifier">currentThread</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">+</span><span class="hl-quotes">"</span><span class="hl-string"> 的循环变量i的值</span><span class="hl-quotes">"</span><span class="hl-code">+</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">;  
            </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">==</span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-code">  
            </span><span class="hl-brackets">{</span><span class="hl-code">  
                </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-brackets">(</span><span class="hl-identifier">ft</span><span class="hl-code">,</span><span class="hl-quotes">"</span><span class="hl-string">有返回值的线程</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;  
            </span><span class="hl-brackets">}</span><span class="hl-code">  
        </span><span class="hl-brackets">}</span><span class="hl-code">  
        </span><span class="hl-reserved">try</span><span class="hl-code">  
        </span><span class="hl-brackets">{</span><span class="hl-code">  
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">子线程的返回值：</span><span class="hl-quotes">"</span><span class="hl-code">+</span><span class="hl-identifier">ft</span><span class="hl-code">.</span><span class="hl-identifier">get</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">InterruptedException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">  
        </span><span class="hl-brackets">{</span><span class="hl-code">  
            </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">ExecutionException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">  
        </span><span class="hl-brackets">{</span><span class="hl-code">  
            </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-brackets">}</span><span class="hl-code">  
  
    </span><span class="hl-brackets">}</span><span class="hl-code">
    @</span><span class="hl-identifier">Override</span><span class="hl-code">  
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">Integer</span><span class="hl-code"> </span><span class="hl-identifier">call</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">Exception</span><span class="hl-code">  
    </span><span class="hl-brackets">{</span><span class="hl-code">  
        </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;  
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">100</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">  
        </span><span class="hl-brackets">{</span><span class="hl-code">  
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">Thread</span><span class="hl-code">.</span><span class="hl-identifier">currentThread</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">+</span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code">+</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">;  
        </span><span class="hl-brackets">}</span><span class="hl-code">  
        </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;  
    </span><span class="hl-brackets">}</span><span class="hl-code">  
</span><span class="hl-brackets">}</span></div>&#13;
</div><br/>&#13;
</div>&#13;
<hr/>&#13;
<h2>创建线程的三种方式的对比</h2>&#13;
<ul>&#13;
<li><p>1. 采用实现 Runnable、Callable 接口的方式创建多线程时，线程类只是实现了 Runnable 接口或 Callable 接口，还可以继承其他类。</p></li><li><p>&#13;
2. 使用继承 Thread 类的方式创建多线程时，编写简单，如果需要访问当前线程，则无需使用 Thread.currentThread() 方法，直接使用 this 即可获得当前线程。</p>&#13;
</li></ul>&#13;
<hr/>&#13;
<h2>线程的几个主要概念&#13;
</h2>&#13;
<p>&#13;
在多线程编程时，你需要了解以下几个概念：</p>&#13;
<ul>&#13;
<li>&#13;
线程同步</li><li>&#13;
线程间通信</li><li>&#13;
线程死锁</li><li>&#13;
线程控制：挂起、停止和恢复</li></ul>&#13;
<hr/><h2>多线程的使用</h2>&#13;
<p>&#13;
有效利用多线程的关键是理解程序是并发执行而不是串行执行的。例如：程序中有两个子系统需要并发执行，这时候就需要利用多线程编程。</p><p>&#13;
通过对多线程的使用，可以编写出非常高效的程序。不过请注意，如果你创建太多的线程，程序执行的效率实际上是降低了，而不是提升了。</p><p>&#13;
请记住，上下文的切换开销也很重要，如果你创建了太多的线程，CPU 花费在上下文的切换的时间将多于执行程序的时间！</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>