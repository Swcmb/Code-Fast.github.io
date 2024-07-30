<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 预处理器</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">预处理器</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p><b>C 预处理器</b>不是编译器的组成部分，但是它是编译过程中一个单独的步骤。简言之，C 预处理器只不过是一个文本替换工具而已，它们会指示编译器在实际编译之前完成所需的预处理。我们将把 C 预处理器（C Preprocessor）简写为 CPP。</p>&#13;
<p>所有的预处理器命令都是以井号（#）开头。它必须是第一个非空字符，为了增强可读性，预处理器指令应从第一列开始。下面列出了所有重要的预处理器指令：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:20%">指令</th><th>描述</th></tr>&#13;
<tr><td>#define</td><td>定义宏</td></tr>&#13;
<tr><td>#include</td><td>包含一个源代码文件</td></tr>&#13;
<tr><td>#undef</td><td>取消已定义的宏</td></tr>&#13;
<tr><td>#ifdef</td><td>如果宏已经定义，则返回真</td></tr>&#13;
<tr><td>#ifndef</td><td>如果宏没有定义，则返回真</td></tr>&#13;
<tr><td>#if</td><td>如果给定条件为真，则编译下面代码</td></tr>&#13;
<tr><td>#else</td><td>#if 的替代方案</td></tr>&#13;
<tr><td>#elif</td><td>如果前面的 #if 给定条件不为真，当前条件为真，则编译下面代码</td></tr>&#13;
<tr><td>#endif</td><td>结束一个 #if……#else 条件编译块</td></tr>&#13;
<tr><td>#error</td><td>当遇到标准错误时，输出错误消息</td></tr>&#13;
<tr><td>#pragma</td><td>使用标准化方法，向编译器发布特殊的命令到编译器中</td></tr>&#13;
</table>&#13;
</div>&#13;
<br/>&#13;
<h2 class="tutheader">预处理器实例</h2>&#13;
<p>分析下面的实例来理解不同的指令。</p>&#13;
<pre>&#13;
#define MAX_ARRAY_LENGTH 20&#13;
</pre>&#13;
<p>这个指令告诉 CPP 把所有的 MAX_ARRAY_LENGTH 定义为 20。使用 <i>#define</i> 定义常量来增强可读性。</p>&#13;
<pre>&#13;
#include &lt;stdio.h&gt;&#13;
#include "myheader.h"&#13;
</pre>&#13;
<p>这些指令告诉 CPP 从<b>系统库</b>中获取 stdio.h，并添加文本到当前的源文件中。下一行告诉 CPP 从本地目录中获取 <b>myheader.h</b>，并添加内容到当前的源文件中。</p>&#13;
<pre>&#13;
#undef  FILE_SIZE&#13;
#define FILE_SIZE 42&#13;
</pre>&#13;
<p>这个指令告诉 CPP 取消已定义的 FILE_SIZE，并定义它为 42。</p>&#13;
<pre>&#13;
#ifndef MESSAGE&#13;
   #define MESSAGE "You wish!"&#13;
#endif&#13;
</pre>&#13;
<p>这个指令告诉 CPP 只有当 MESSAGE 未定义时，才定义 MESSAGE。</p>&#13;
<pre>&#13;
#ifdef DEBUG&#13;
   /* Your debugging statements here */&#13;
#endif&#13;
</pre>&#13;
<p>这个指令告诉 CPP 如果定义了 DEBUG，则执行处理语句。在编译时，如果您向 gcc 编译器传递了 <i>-DDEBUG</i> 开关量，这个指令就非常有用。它定义了 DEBUG，您可以在编译期间随时开启或关闭调试。</p>&#13;
&#13;
<h2 class="tutheader">预定义宏</h2>&#13;
<p>ANSI C 定义了许多宏。在编程中您可以使用这些宏，但是不能直接修改这些预定义的宏。</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:20%">宏</th><th>描述</th></tr>&#13;
<tr><td>__DATE__</td><td>当前日期，一个以 "MMM DD YYYY" 格式表示的字符常量。</td></tr>&#13;
<tr><td>__TIME__</td><td>当前时间，一个以 "HH:MM:SS" 格式表示的字符常量。</td></tr>&#13;
<tr><td>__FILE__</td><td>这会包含当前文件名，一个字符串常量。</td></tr>&#13;
<tr><td>__LINE__</td><td>这会包含当前行号，一个十进制常量。</td></tr>&#13;
<tr><td>__STDC__</td><td>当编译器以 ANSI 标准编译时，则定义为 1。</td></tr>&#13;
</table>&#13;
<p>让我们来尝试下面的实例：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">File :%s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">__FILE__</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Date :%s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">__DATE__</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Time :%s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">__TIME__</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Line :%d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">__LINE__</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">ANSI :%d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">__STDC__</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码（在文件 <b>test.c</b> 中）被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
File :test.c&#13;
Date :Jun 2 2012&#13;
Time :03:36:24&#13;
Line :8&#13;
ANSI :1&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">预处理器运算符</h2>&#13;
<p>C 预处理器提供了下列的运算符来帮助您创建宏：</p>&#13;
<h5>宏延续运算符（\）</h5>&#13;
<p>一个宏通常写在一个单行上。但是如果宏太长，一个单行容纳不下，则使用宏延续运算符（\）。例如：</p>&#13;
<pre>&#13;
#define  message_for(a, b)  \&#13;
    printf(#a " and " #b ": We love you!\n")&#13;
&#13;
</pre>&#13;
<h5>字符串常量化运算符（#）</h5>&#13;
<p>在宏定义中，当需要把一个宏的参数转换为字符串常量时，则使用字符串常量化运算符（#）。在宏中使用的该运算符有一个特定的参数或参数列表。例如：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#define</span><span class="hl-code">  </span><span class="hl-identifier">message_for</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-code">, </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code">  \
    </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code">#</span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string"> and </span><span class="hl-quotes">"</span><span class="hl-code"> #</span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">: We love you!</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">message_for</span><span class="hl-brackets">(</span><span class="hl-identifier">Carole</span><span class="hl-code">, </span><span class="hl-identifier">Debra</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Carole and Debra: We love you!&#13;
</pre>&#13;
<h5>标记粘贴运算符（##）</h5>&#13;
<p>宏定义内的标记粘贴运算符（##）会合并两个参数。它允许在宏定义中两个独立的标记被合并为一个标记。例如：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-identifier">tokenpaster</span><span class="hl-brackets">(</span><span class="hl-identifier">n</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">printf</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">token</span><span class="hl-quotes">"</span><span class="hl-code"> #</span><span class="hl-identifier">n</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string"> = %d</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">token</span><span class="hl-code">##</span><span class="hl-identifier">n</span><span class="hl-brackets">)</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">token34</span><span class="hl-code"> = </span><span class="hl-number">40</span><span class="hl-code">;
   
   </span><span class="hl-identifier">tokenpaster</span><span class="hl-brackets">(</span><span class="hl-number">34</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
token34 = 40&#13;
</pre>&#13;
<p>这是怎么发生的，因为这个实例会从编译器产生下列的实际输出：</p>&#13;
<pre>&#13;
printf ("token34 = %d", token34);&#13;
</pre>&#13;
<p>这个实例演示了 token##n 会连接到 token34 中，在这里，我们使用了<b>字符串常量化运算符（#）</b>和<b>标记粘贴运算符（##）</b>。</p>&#13;
<h5>defined() 运算符</h5>&#13;
<p>预处理器 <b>defined</b> 运算符是用在常量表达式中的，用来确定一个标识符是否已经使用 #define 定义过。如果指定的标识符已定义，则值为真（非零）。如果指定的标识符未定义，则值为假（零）。下面的实例演示了 defined() 运算符的用法：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#if</span><span class="hl-code"> !</span><span class="hl-identifier">defined</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">MESSAGE</span><span class="hl-brackets">)</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">   #define</span><span class="hl-code"> </span><span class="hl-identifier">MESSAGE</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">You wish!</span><span class="hl-quotes">"</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#endif</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Here is the message: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">MESSAGE</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Here is the message: You wish!&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">参数化的宏</h2>&#13;
<p>CPP 一个强大的功能是可以使用参数化的宏来模拟函数。例如，下面的代码是计算一个数的平方：</p>&#13;
<pre>&#13;
int square(int x) {&#13;
   return x * x;&#13;
}&#13;
</pre>&#13;
<p>我们可以使用宏重写上面的代码，如下：</p>&#13;
<pre>&#13;
#define square(x) ((x) * (x))&#13;
</pre>&#13;
<p>在使用带有参数的宏之前，必须使用 <b>#define</b> 指令定义。参数列表是括在圆括号内，且必须紧跟在宏名称的后边。宏名称和左圆括号之间不允许有空格。例如：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-prepro">MAX</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-code">,</span><span class="hl-identifier">y</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span><span class="hl-code"> &gt; </span><span class="hl-brackets">(</span><span class="hl-identifier">y</span><span class="hl-brackets">)</span><span class="hl-code"> ? </span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span><span class="hl-code"> : </span><span class="hl-brackets">(</span><span class="hl-identifier">y</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Max between 20 and 10 is %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">MAX</span><span class="hl-brackets">(</span><span class="hl-number">10</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div></div></div>&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Max between 20 and 10 is 20&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>