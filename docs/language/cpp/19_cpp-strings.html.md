<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 字符串</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">字符串</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>C++ 提供了以下两种类型的字符串表示形式：</p>&#13;
<ul class="list">&#13;
<li>C 风格字符串</li>&#13;
<li>C++ 引入的 string 类类型</li>&#13;
</ul>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">C 风格字符串</h2>&#13;
<p>C 风格的字符串起源于 C 语言，并在 C++ 中继续得到支持。字符串实际上是使用 <b>null</b> 字符  <span class="marked">\0</span>  终止的一维字符数组。因此，一个以 null 结尾的字符串，包含了组成字符串的字符。</p>&#13;
<p>下面的声明和初始化创建了一个 <strong>RUNOOB</strong> 字符串。由于在数组的末尾存储了空字符，所以字符数组的大小比单词 <strong>RUNOOB</strong> 的字符数多一个。</p>&#13;
<pre>&#13;
char site[7] = {'R', 'U', 'N', 'O', 'O', 'B', '\0'};&#13;
</pre>&#13;
<p>依据数组初始化规则，您可以把上面的语句写成以下语句：</p>&#13;
<pre>&#13;
char site[] = "RUNOOB";&#13;
</pre>&#13;
<p>以下是 C/C++ 中定义的字符串的内存表示：</p>&#13;
<img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-strings-2020-12-21.png" alt="C/C++ 中的字符串表示"/>&#13;
<p>其实，您不需要把 <strong>null</strong> 字符放在字符串常量的末尾。C++ 编译器会在初始化数组时，自动把 <span class="marked">\0</span> 放在字符串的末尾。让我们尝试输出上面的字符串：</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">site</span><span class="hl-brackets">[</span><span class="hl-number">7</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-code">'</span><span class="hl-identifier">R</span><span class="hl-code">', '</span><span class="hl-identifier">U</span><span class="hl-code">', '</span><span class="hl-identifier">N</span><span class="hl-code">', '</span><span class="hl-identifier">O</span><span class="hl-code">', '</span><span class="hl-identifier">O</span><span class="hl-code">', '</span><span class="hl-identifier">B</span><span class="hl-code">', '\</span><span class="hl-number">0</span><span class="hl-code">'</span><span class="hl-brackets">}</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程: </span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">site</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
菜鸟教程: RUNOOB&#13;
</pre>&#13;
<p>C++ 中有大量的函数用来操作以 null 结尾的字符串:</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>函数 &amp; 目的</th></tr>&#13;
<tr><td>1</td><td><b>strcpy(s1, s2);</b><br/>复制字符串 s2 到字符串 s1。</td></tr>&#13;
<tr><td>2</td><td><b>strcat(s1, s2);</b><br/>连接字符串 s2 到字符串 s1 的末尾。连接字符串也可以用 <span class="marked">+</span> 号，例如:<br/>&#13;
<pre>string str1 = "runoob";&#13;
string str2 = "google";&#13;
string str = str1 + str2;</pre>&#13;
&#13;
</td></tr>&#13;
<tr><td>3</td><td><b>strlen(s1);</b><br/>返回字符串 s1 的长度。</td></tr>&#13;
<tr><td>4</td><td><b>strcmp(s1, s2);</b><br/>如果 s1 和 s2 是相同的，则返回 0；如果 s1&lt;s2 则返回值小于 0；如果 s1&gt;s2 则返回值大于 0。</td></tr>&#13;
<tr><td>5</td><td><b>strchr(s1, ch);</b><br/>返回一个指针，指向字符串 s1 中字符 ch 的第一次出现的位置。</td></tr>&#13;
<tr><td>6</td><td><b>strstr(s1, s2);</b><br/>返回一个指针，指向字符串 s1 中字符串 s2 的第一次出现的位置。</td></tr>&#13;
</table>&#13;
<p>下面的实例使用了上述的一些函数：</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cstring</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">str1</span><span class="hl-brackets">[</span><span class="hl-number">13</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">runoob</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">str2</span><span class="hl-brackets">[</span><span class="hl-number">13</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">google</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">str3</span><span class="hl-brackets">[</span><span class="hl-number">13</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code">  </span><span class="hl-identifier">len</span><span class="hl-code"> ;
 
   </span><span class="hl-comment">// 复制 str1 到 str3</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">str3</span><span class="hl-code">, </span><span class="hl-identifier">str1</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">strcpy( str3, str1) : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">str3</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 连接 str1 和 str2</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">strcat</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">str1</span><span class="hl-code">, </span><span class="hl-identifier">str2</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">strcat( str1, str2): </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">str1</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 连接后，str1 的总长度</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">len</span><span class="hl-code"> = </span><span class="hl-identifier">strlen</span><span class="hl-brackets">(</span><span class="hl-identifier">str1</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">strlen(str1) : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">len</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
strcpy( str3, str1) : runoob&#13;
strcat( str1, str2): runoobgoogle&#13;
strlen(str1) : 12&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">C++ 中的 String 类</h2>&#13;
<p>C++ 标准库提供了 <b>string</b> 类类型，支持上述所有的操作，另外还增加了其他更多的功能。我们将学习 C++ 标准库中的这个类，现在让我们先来看看下面这个实例：</p>&#13;
<p>现在您可能还无法透彻地理解这个实例，因为到目前为止我们还没有讨论类和对象。所以现在您可以只是粗略地看下这个实例，等理解了面向对象的概念之后再回头来理解这个实例。</p> &#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">str1</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">runoob</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">str2</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">google</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">str3</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code">  </span><span class="hl-identifier">len</span><span class="hl-code"> ;
 
   </span><span class="hl-comment">// 复制 str1 到 str3</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">str3</span><span class="hl-code"> = </span><span class="hl-identifier">str1</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">str3 : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">str3</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 连接 str1 和 str2</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">str3</span><span class="hl-code"> = </span><span class="hl-identifier">str1</span><span class="hl-code"> + </span><span class="hl-identifier">str2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">str1 + str2 : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">str3</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 连接后，str3 的总长度</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">len</span><span class="hl-code"> = </span><span class="hl-identifier">str3</span><span class="hl-code">.</span><span class="hl-identifier">size</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">str3.size() :  </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">len</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
str3 : runoob&#13;
str1 + str2 : runoobgoogle&#13;
str3.size() :  12&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>