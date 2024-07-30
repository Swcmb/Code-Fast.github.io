<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 引用</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">引用</span></h1>&#13;
&#13;
&#13;
<p>引用变量是一个别名，也就是说，它是某个已存在变量的另一个名字。一旦把引用初始化为某个变量，就可以使用该引用名称或变量名称来指向变量。</p>&#13;
&#13;
&#13;
<h2 class="tutheader">C++ 引用 vs 指针</h2>&#13;
<p>引用很容易与指针混淆，它们之间有三个主要的不同：</p>&#13;
<ul class="list">&#13;
<li>不存在空引用。引用必须连接到一块合法的内存。</li>&#13;
<li>一旦引用被初始化为一个对象，就不能被指向到另一个对象。指针可以在任何时候指向到另一个对象。</li>&#13;
<li>引用必须在创建时被初始化。指针可以在任何时间被初始化。</li>&#13;
</ul>&#13;
&#13;
<h2 class="tutheader">C++ 中创建引用</h2>&#13;
<p>试想变量名称是变量附属在内存位置中的标签，您可以把引用当成是变量附属在内存位置中的第二个标签。因此，您可以通过原始变量名称或引用来访问变量的内容。例如：</p>&#13;
<pre>&#13;
int i = 17;&#13;
</pre>&#13;
<p>我们可以为 i 声明引用变量，如下所示：</p>&#13;
<pre>&#13;
int&amp;  r = i;&#13;
double&amp; s = d;&#13;
</pre>&#13;
<p>在这些声明中，&amp; 读作<b>引用</b>。因此，第一个声明可以读作 "r 是一个初始化为 i 的整型引用"，第二个声明可以读作 "s 是一个初始化为 d 的 double 型引用"。下面的实例使用了 int 和 double 引用：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 声明简单的变量</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code">    </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 声明引用变量</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code">&amp;    </span><span class="hl-identifier">r</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code">;
   </span><span class="hl-types">double</span><span class="hl-code">&amp; </span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-identifier">d</span><span class="hl-code">;
   
   </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value of i : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value of i reference : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">r</span><span class="hl-code">  &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">11</span><span class="hl-number">.7</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value of d : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">d</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value of d reference : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">s</span><span class="hl-code">  &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Value of i : 5&#13;
Value of i reference : 5&#13;
Value of d : 11.7&#13;
Value of d reference : 11.7&#13;
</pre>&#13;
<p>引用通常用于函数参数列表和函数返回值。下面列出了 C++ 程序员必须清楚的两个与 C++ 引用相关的重要概念：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th width="40%">概念</th><th>描述</th></tr>&#13;
<tr><td><a href="/cplusplus/passing-parameters-by-references.html" title="C++ 中通过引用传参">把引用作为参数</a></td><td>C++ 支持把引用作为参数传给函数，这比传一般的参数更安全。</td> </tr>&#13;
<tr><td><a href="/cplusplus/returning-values-by-reference.html" title="C++ 中通过引用返回值">把引用作为返回值</a></td><td>可以从 C++ 函数中返回引用，就像返回其他数据类型一样。</td> </tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>