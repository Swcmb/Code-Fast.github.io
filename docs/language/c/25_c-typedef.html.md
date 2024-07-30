<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C typedef</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">typedef</span></h1>&#13;
&#13;
<p>C 语言提供了 <b>typedef</b> 关键字，您可以使用它来为类型取一个新的名字。下面的实例为单字节数字定义了一个术语 <b>BYTE</b>：</p>&#13;
<pre>&#13;
typedef unsigned char BYTE;&#13;
</pre>&#13;
<p>在这个类型定义之后，标识符 BYTE 可作为类型 <b>unsigned char</b> 的缩写，例如：&#13;
</p><pre>&#13;
BYTE  b1, b2;&#13;
</pre>&#13;
<p>按照惯例，定义时会大写字母，以便提醒用户类型名称是一个象征性的缩写，但您也可以使用小写字母，如下：</p>&#13;
<pre>&#13;
typedef unsigned char byte;&#13;
</pre>&#13;
<p>您也可以使用 <b>typedef</b> 来为用户自定义的数据类型取一个新的名字。例如，您可以对结构体使用 typedef 来定义一个新的数据类型名字，然后使用这个新的数据类型来直接定义结构变量，如下：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">typedef</span><span class="hl-code"> </span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">Books</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code">  </span><span class="hl-identifier">title</span><span class="hl-brackets">[</span><span class="hl-number">50</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code">  </span><span class="hl-identifier">author</span><span class="hl-brackets">[</span><span class="hl-number">50</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code">  </span><span class="hl-identifier">subject</span><span class="hl-brackets">[</span><span class="hl-number">100</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code">   </span><span class="hl-identifier">book_id</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">Book</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Book</span><span class="hl-code"> </span><span class="hl-identifier">book</span><span class="hl-code">;
 
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">title</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">C 教程</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">author</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Runoob</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">编程语言</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">book_id</span><span class="hl-code"> = </span><span class="hl-number">12345</span><span class="hl-code">;
 
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">书标题 : %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">title</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">书作者 : %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">author</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">书类目 : %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">subject</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">书 ID : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">book</span><span class="hl-code">.</span><span class="hl-identifier">book_id</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
书标题 : C 教程&#13;
书作者 : Runoob&#13;
书类目 : 编程语言&#13;
书 ID : 12345&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">typedef vs #define</h2>&#13;
<p><b>#define</b> 是 C 指令，用于为各种数据类型定义别名，与 <b>typedef</b> 类似，但是它们有以下几点不同：</p>&#13;
<ul class="list">&#13;
<li><b>typedef</b> 仅限于为类型定义符号名称，<b>#define</b> 不仅可以为类型定义别名，也能为数值定义别名，比如您可以定义 1 为 ONE。</li>&#13;
<li><b>typedef</b> 是由编译器执行解释的，<b>#define</b> 语句是由预编译器进行处理的。</li>&#13;
</ul>&#13;
<p>下面是 #define 的最简单的用法：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-prepro">TRUE</span><span class="hl-code">  </span><span class="hl-number">1</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#define</span><span class="hl-code"> </span><span class="hl-prepro">FALSE</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">TRUE 的值: %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">TRUE</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">FALSE 的值: %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-prepro">FALSE</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
TRUE 的值: 1&#13;
FALSE 的值: 0&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>