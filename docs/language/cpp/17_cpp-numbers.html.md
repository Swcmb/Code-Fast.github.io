<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 数字</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">数字</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>通常，当我们需要用到数字时，我们会使用原始的数据类型，如 int、short、long、float 和 double 等等。这些用于数字的数据类型，其可能的值和数值范围，我们已经在 C++ 数据类型一章中讨论过。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">C++ 定义数字</h2>&#13;
<p>我们已经在之前章节的各种实例中定义过数字。下面是一个 C++ 中定义各种类型数字的综合实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 数字定义</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">short</span><span class="hl-code">  </span><span class="hl-identifier">s</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code">    </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-types">long</span><span class="hl-code">   </span><span class="hl-identifier">l</span><span class="hl-code">;
   </span><span class="hl-types">float</span><span class="hl-code">  </span><span class="hl-identifier">f</span><span class="hl-code">;
   </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 数字赋值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;      
   </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">1000</span><span class="hl-code">;    
   </span><span class="hl-identifier">l</span><span class="hl-code"> = </span><span class="hl-number">1000000</span><span class="hl-code">; 
   </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-number">230</span><span class="hl-number">.47</span><span class="hl-code">;  
   </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">30949</span><span class="hl-number">.374</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 数字输出</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">short  s :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">s</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">int    i :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">long   l :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">l</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">float  f :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">f</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">double d :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">d</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
short  s :10&#13;
int    i :1000&#13;
long   l :1000000&#13;
float  f :230.47&#13;
double d :30949.4&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">C++ 数学运算</h2>&#13;
<p>在 C++ 中，除了可以创建各种函数，还包含了各种有用的函数供您使用。这些函数写在标准 C 和 C++ 库中，叫做<b>内置</b>函数。您可以在程序中引用这些函数。</p>&#13;
<p>C++ 内置了丰富的数学函数，可对各种数字进行运算。下表列出了 C++ 中一些有用的内置的数学函数。</p>&#13;
<p>为了利用这些函数，您需要引用数学头文件 <b>&lt;cmath&gt;</b>。</p>&#13;
<table class="reference notranslate">&#13;
<tr><th width="5%">序号</th><th>函数 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>double cos(double);</b><br/>该函数返回弧度角（double 型）的余弦。</td></tr>&#13;
<tr><td>2</td><td><b>double sin(double);</b><br/>该函数返回弧度角（double 型）的正弦。</td></tr>&#13;
<tr><td>3</td><td><b>double tan(double);</b><br/>该函数返回弧度角（double 型）的正切。</td></tr>&#13;
<tr><td>4</td><td><b>double log(double);</b><br/>该函数返回参数的自然对数。</td></tr>&#13;
<tr><td>5</td><td><b>double pow(double, double);</b><br/>假设第一个参数为 x，第二个参数为 y，则该函数返回 x 的 y 次方。</td></tr>&#13;
<tr><td>6</td><td><b>double hypot(double, double);</b><br/>该函数返回两个参数的平方总和的平方根，也就是说，参数为一个直角三角形的两个直角边，函数会返回斜边的长度。</td></tr>&#13;
<tr><td>7</td><td><b>double sqrt(double);</b><br/>该函数返回参数的平方根。</td></tr>&#13;
<tr><td>8</td><td><b>int abs(int);</b><br/>该函数返回整数的绝对值。</td></tr>&#13;
<tr><td>9</td><td><b>double fabs(double);</b><br/>该函数返回任意一个浮点数的绝对值。</td></tr>&#13;
<tr><td>10</td><td><b>double floor(double);</b><br/>该函数返回一个小于或等于传入参数的最大整数。</td></tr>&#13;
</table>&#13;
<p>下面是一个关于数学运算的简单实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cmath</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 数字定义</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">short</span><span class="hl-code">  </span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code">    </span><span class="hl-identifier">i</span><span class="hl-code"> = -</span><span class="hl-number">1000</span><span class="hl-code">;
   </span><span class="hl-types">long</span><span class="hl-code">   </span><span class="hl-identifier">l</span><span class="hl-code"> = </span><span class="hl-number">100000</span><span class="hl-code">;
   </span><span class="hl-types">float</span><span class="hl-code">  </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-number">230</span><span class="hl-number">.47</span><span class="hl-code">;
   </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">200</span><span class="hl-number">.374</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 数学运算</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">sin(d) :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">sin</span><span class="hl-brackets">(</span><span class="hl-identifier">d</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">abs(i)  :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">abs</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">floor(d) :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">floor</span><span class="hl-brackets">(</span><span class="hl-identifier">d</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">sqrt(f) :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">sqrt</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">pow( d, 2) :</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">pow</span><span class="hl-brackets">(</span><span class="hl-identifier">d</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
sin(d) :-0.634939&#13;
abs(i)  :1000&#13;
floor(d) :200&#13;
sqrt(f) :15.1812&#13;
pow( d, 2 ) :40149.7&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">C++ 随机数</h2>&#13;
<p>在许多情况下，需要生成随机数。关于随机数生成器，有两个相关的函数。一个是 <b>rand()</b>，该函数只返回一个伪随机数。生成随机数之前必须先调用 <b>srand()</b> 函数。</p>&#13;
<p>下面是一个关于生成随机数的简单实例。实例中使用了 <b>time()</b> 函数来获取系统时间的秒数，通过调用 rand() 函数来生成随机数：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">ctime</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cstdlib</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">,</span><span class="hl-identifier">j</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 设置种子</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">srand</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">unsigned</span><span class="hl-brackets">)</span><span class="hl-identifier">time</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-prepro">NULL</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 生成 10 个随机数 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">// 生成实际的随机数</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">j</span><span class="hl-code">= </span><span class="hl-identifier">rand</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt;</span><span class="hl-quotes">"</span><span class="hl-string">随机数： </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">j</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
随机数： 1748144778&#13;
随机数： 630873888&#13;
随机数： 2134540646&#13;
随机数： 219404170&#13;
随机数： 902129458&#13;
随机数： 920445370&#13;
随机数： 1319072661&#13;
随机数： 257938873&#13;
随机数： 1256201101&#13;
随机数： 580322989&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>