<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 错误处理</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">错误处理</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>C 语言不提供对错误处理的直接支持，但是作为一种系统编程语言，它以返回值的形式允许您访问底层数据。在发生错误时，大多数的 C 或 UNIX 函数调用返回 1 或 NULL，同时会设置一个错误代码 <b>errno</b>，该错误代码是全局变量，表示在函数调用期间发生了错误。您可以在 errno.h 头文件中找到各种各样的错误代码。</p>&#13;
<p>所以，C 程序员可以通过检查返回值，然后根据返回值决定采取哪种适当的动作。开发人员应该在程序初始化时，把 errno 设置为 0，这是一种良好的编程习惯。0 值表示程序中没有错误。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">errno、perror() 和 strerror()</h2>&#13;
<p>C 语言提供了 <b>perror()</b> 和 <b>strerror()</b> 函数来显示与 <b>errno</b> 相关的文本消息。</p>&#13;
<ul class="list">&#13;
<li><b>perror()</b> 函数显示您传给它的字符串，后跟一个冒号、一个空格和当前 errno 值的文本表示形式。</li>&#13;
<li><b>strerror()</b> 函数，返回一个指针，指针指向当前 errno 值的文本表示形式。</li>&#13;
</ul>&#13;
<p>让我们来模拟一种错误情况，尝试打开一个不存在的文件。您可以使用多种方式来输出错误消息，在这里我们使用函数来演示用法。另外有一点需要注意，您应该使用 <b>stderr</b> 文件流来输出所有的错误。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">errno.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">extern</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">errno</span><span class="hl-code"> ;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">FILE</span><span class="hl-code"> * </span><span class="hl-identifier">pf</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">errnum</span><span class="hl-code">;
   </span><span class="hl-identifier">pf</span><span class="hl-code"> = </span><span class="hl-identifier">fopen</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">unexist.txt</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">rb</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">pf</span><span class="hl-code"> == </span><span class="hl-prepro">NULL</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">errnum</span><span class="hl-code"> = </span><span class="hl-identifier">errno</span><span class="hl-code">;
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">错误号: %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">errno</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">perror</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">通过 perror 输出错误</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">打开文件错误: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">strerror</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">errnum</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fclose</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">pf</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
错误号: 2&#13;
通过 perror 输出错误: No such file or directory&#13;
打开文件错误: No such file or directory&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">被零除的错误</h2>&#13;
<p>在进行除法运算时，如果不检查除数是否为零，则会导致一个运行时错误。</p>&#13;
<p>为了避免这种情况发生，下面的代码在进行除法运算前会先检查除数是否为零：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">dividend</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">divisor</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">quotient</span><span class="hl-code">;
 
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">divisor</span><span class="hl-code"> == </span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">除数为 0 退出运行...</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-code">-</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">quotient</span><span class="hl-code"> = </span><span class="hl-identifier">dividend</span><span class="hl-code"> / </span><span class="hl-identifier">divisor</span><span class="hl-code">;
   </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">quotient 变量的值为 : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">quotient</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
除数为 0 退出运行...&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">程序退出状态</h2>&#13;
<p>通常情况下，程序成功执行完一个操作正常退出的时候会带有值 EXIT_SUCCESS。在这里，EXIT_SUCCESS 是宏，它被定义为 0。</p>&#13;
<p>如果程序中存在一种错误情况，当您退出程序时，会带有状态值 EXIT_FAILURE，被定义为 -1。所以，上面的程序可以写成：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">dividend</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">divisor</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">quotient</span><span class="hl-code">;
 
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">divisor</span><span class="hl-code"> == </span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">除数为 0 退出运行...</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-identifier">EXIT_FAILURE</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">quotient</span><span class="hl-code"> = </span><span class="hl-identifier">dividend</span><span class="hl-code"> / </span><span class="hl-identifier">divisor</span><span class="hl-code">;
   </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">quotient 变量的值为: %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">quotient</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-identifier">EXIT_SUCCESS</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
quotient 变量的值为 : 4&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>