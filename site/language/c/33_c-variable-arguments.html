<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 可变参数</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">可变参数</span></h1>&#13;
&#13;
<p>有时，您可能会碰到这样的情况，您希望函数带有可变数量的参数，而不是预定义数量的参数。</p>&#13;
<p>C 语言为这种情况提供了一个解决方案，它允许您定义一个函数，能根据具体的需求接受可变数量的参数。</p>&#13;
<p>声明方式为：</p>&#13;
<pre>int func_name(int arg1, ...);</pre>&#13;
<p>其中，省略号 <span class="marked">...</span> 表示可变参数列表。</p>&#13;
<p>下面的实例演示了这种函数的使用：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code">, ... </span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-brackets">{</span><span class="hl-code">
   .
   .
   .
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">4</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>请注意，函数 <b>func()</b> 最后一个参数写成省略号，即三个点号（<b>...</b>），省略号之前的那个参数是 <b>int</b>，代表了要传递的可变参数的总数。为了使用这个功能，您需要使用 <b>stdarg.h</b> 头文件，该文件提供了实现可变参数功能的函数和宏。具体步骤如下：</p>&#13;
<ul class="list">&#13;
<li>定义一个函数，最后一个参数为省略号，省略号前面可以设置自定义参数。</li>&#13;
<li>在函数定义中创建一个 <b>va_list</b> 类型变量，该类型是在 stdarg.h 头文件中定义的。</li>&#13;
<li>使用 <b>int</b> 参数和 <b>va_start()</b> 宏来初始化 <b>va_list</b> 变量为一个参数列表。宏 <strong>va_start()</strong> 是在 stdarg.h 头文件中定义的。</li>&#13;
<li>使用 <b>va_arg()</b> 宏和 <b>va_list</b> 变量来访问参数列表中的每个项。</li>&#13;
<li>使用宏 <b>va_end()</b> 来清理赋予 <b>va_list</b> 变量的内存。</li>&#13;
</ul>&#13;
<p>常用的宏有：</p>&#13;
<ul>&#13;
    <li>&#13;
        <p><code><strong>va_start(ap, last_arg)</strong></code>：初始化可变参数列表。<code>ap</code> 是一个 <code>va_list</code> 类型的变量，<code>last_arg</code> 是最后一个固定参数的名称（也就是可变参数列表之前的参数）。该宏将 <code>ap</code> 指向可变参数列表中的第一个参数。</p>&#13;
    </li>&#13;
    <li>&#13;
        <p><code><strong>va_arg(ap, type)</strong></code>：获取可变参数列表中的下一个参数。<code>ap</code> 是一个 <code>va_list</code> 类型的变量，<code>type</code> 是下一个参数的类型。该宏返回类型为 <code>type</code> 的值，并将 <code>ap</code> 指向下一个参数。</p>&#13;
    </li>&#13;
    <li>&#13;
        <p><code><strong>va_end(ap)</strong></code>：结束可变参数列表的访问。<code>ap</code> 是一个 <code>va_list</code> 类型的变量。该宏将 <code>ap</code> 置为 <code>NULL</code>。</p>&#13;
    </li>&#13;
</ul>&#13;
<p>现在让我们按照上面的步骤，来编写一个带有可变数量参数的函数，并返回它们的平均值：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdarg.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">average</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">,...</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
    </span><span class="hl-identifier">va_list</span><span class="hl-code"> </span><span class="hl-identifier">valist</span><span class="hl-code">;
    </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">sum</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-number">.0</span><span class="hl-code">;
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
 
    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 为 num 个参数初始化 valist </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">va_start</span><span class="hl-brackets">(</span><span class="hl-identifier">valist</span><span class="hl-code">, </span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code">;
 
    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 访问所有赋给 valist 的参数 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">num</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">sum</span><span class="hl-code"> += </span><span class="hl-identifier">va_arg</span><span class="hl-brackets">(</span><span class="hl-identifier">valist</span><span class="hl-code">, </span><span class="hl-types">int</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 清理为 valist 保留的内存 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">va_end</span><span class="hl-brackets">(</span><span class="hl-identifier">valist</span><span class="hl-brackets">)</span><span class="hl-code">;
 
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">sum</span><span class="hl-code">/</span><span class="hl-identifier">num</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Average of 2, 3, 4, 5 = %f</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">average</span><span class="hl-brackets">(</span><span class="hl-number">4</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">,</span><span class="hl-number">3</span><span class="hl-code">,</span><span class="hl-number">4</span><span class="hl-code">,</span><span class="hl-number">5</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Average of 5, 10, 15 = %f</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">average</span><span class="hl-brackets">(</span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">5</span><span class="hl-code">,</span><span class="hl-number">10</span><span class="hl-code">,</span><span class="hl-number">15</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在上面的例子中，average() 函数接受一个整数 num 和任意数量的整数参数。函数内部使用 va_list 类型的变量 va_list 来访问可变参数列表。在循环中，每次使用 va_arg() 宏获取下一个整数参数，并输出。最后，在函数结束时使用 va_end() 宏结束可变参数列表的访问。</p>&#13;
&#13;
&#13;
&#13;
&#13;
&#13;
&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果。应该指出的是，函数 <b> average()</b> 被调用两次，每次第一个参数都是表示被传的可变参数的总数。省略号被用来传递可变数量的参数。</p>&#13;
<pre>&#13;
Average of 2, 3, 4, 5 = 3.500000&#13;
Average of 5, 10, 15 = 10.000000&#13;
</pre>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>