<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 语言教程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">语言教程</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/09/c-mini-logo.png"/>&#13;
<p>C 语言是一种通用的、面向过程式的计算机程序设计语言。1972 年，为了移植与开发 UNIX 操作系统，丹尼斯·里奇在贝尔电话实验室设计开发了 C 语言。</p>&#13;
<p>C 语言是一种广泛使用的计算机语言，它与 Java 编程语言一样普及，二者在现代软件程序员之间都得到广泛使用。</p>&#13;
<p>当前最新的 C 语言标准为 C18 ，在它之前的 C 语言标准有 C17、C11...C99 等。</p>&#13;
<p><b><a href="/cprogramming/c-intro.html">现在开始学习 C 编程！</a></b></p>&#13;
<p><a href="/try/showc.php?filename=helloworld&amp;language=c" target="_blank" rel="noopener noreferrer">C 在线工具</a></p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">谁适合阅读本教程？</h2>&#13;
<p>本教程是专门为需要从零开始了解 C 语言的软件程序员打造的。本教程将让您对 C 语言有足够的认识，从而提升您自己的专业知识水平。</p>&#13;
&#13;
<h2 class="tutheader">阅读本教程前，您需要了解的知识：</h2>&#13;
<p>在开始学习本教程之前，您需要对计算机编程术语有基本的了解。对任何一种编程语言有基本的了解将有助于您理解 C 语言编程概念，并有助于加快您的学习进度。</p>&#13;
&#13;
<h2 class="tutheader">编译/执行 C 程序</h2>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 我的第一个 C 程序 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Hello, World! </span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
<br/><a target="_blank" href="/try/runcode.php?filename=helloworld&amp;type=c" class="showbtn" rel="noopener noreferrer">运行实例 »</a>&#13;
</div>&#13;
&#13;
&#13;
<p><b>实例解析：</b></p>&#13;
&#13;
<ul>&#13;
	<li>所有的 C 语言程序都需要包含 <b>main()</b> 函数。 代码从 <b>main()</b> 函数开始执行。</li>&#13;
<li><strong>/* ... */</strong> 用于注释说明。</li>&#13;
	<li><b>printf()</b> 用于格式化输出到屏幕。<b>printf()</b> 函数在 <b>"stdio.h"</b> 头文件中声明。</li>&#13;
	<li><b>stdio.h</b> 是一个头文件 (标准输入输出头文件) , <b>#include</b> 是一个预处理命令，用来引入头文件。&#13;
	 当编译器遇到 <b>printf()</b> 函数时，如果没有找到 <b>stdio.h</b> 头文件，会发生编译错误。</li>&#13;
	<li><b>return 0;</b> 语句用于表示退出程序。</li>&#13;
</ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>