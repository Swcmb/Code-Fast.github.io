<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 正则表达式</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 正则表达式</h1>&#13;
<p>正则表达式是一个特殊的字符序列，它能帮助你方便的检查一个字符串是否与某种模式匹配。</p><p>在 Python 中，使用 <span class="marked">re</span> 模块来处理正则表达式。</p>&#13;
&#13;
<p>&#13;
re 模块提供了一组函数，允许你在字符串中进行模式匹配、搜索和替换操作。</p>&#13;
<p><span class="marked">re</span> 模块使 Python 语言拥有完整的正则表达式功能。 </p>&#13;
&#13;
<p>本章节主要介绍 Python 中常用的正则表达式处理函数，如果你对正则表达式不了解，可以查看我们的 <a href="/regexp/regexp-tutorial.html" rel="noopener noreferrer" target="_blank">正则表达式 - 教程</a>。</p>&#13;
<hr/><h2>re.match函数</h2>&#13;
<p>re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match() 就返回 None。</p>&#13;
<p><strong>函数语法</strong>：</p>&#13;
<pre>&#13;
re.match(pattern, string, flags=0)&#13;
</pre>&#13;
<p>函数参数说明：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">参数</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>pattern</td><td>匹配的正则表达式</td></tr>&#13;
<tr><td>string</td><td>要匹配的字符串。</td></tr>&#13;
<tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="#flags">正则表达式修饰符 - 可选标志</a></td></tr>&#13;
</tbody></table>&#13;
<p>匹配成功 <span class="marked">re.match</span> 方法返回一个匹配的对象，否则返回 <strong>None</strong>。</p>&#13;
<p>我们可以使用 <span class="marked">group(num)</span> 或  <span class="marked">groups()</span> 匹配对象函数来获取匹配表达式。</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">匹配对象方法</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>group(num=0)</td><td>匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。</td></tr>&#13;
<tr><td>groups()</td><td>返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。</td></tr>&#13;
</tbody></table>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">www</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">www.runoob.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 在起始位置匹配</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">com</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">www.runoob.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">         </span><span class="hl-comment"># 不在起始位置匹配</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例运行输出结果为：</p>&#13;
<pre>&#13;
(0, 3)&#13;
None&#13;
</pre>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">line</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Cats are smarter than dogs</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-comment"># .* 表示任意匹配除换行符（\n、\r）之外的任何单个或多个字符</span><span class="hl-code">
</span><span class="hl-comment"># (.*?) 表示"非贪婪"模式，只保存第一个匹配到的子串</span><span class="hl-code">
</span><span class="hl-identifier">matchObj</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">(.*) are (.*?) .*</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">line</span><span class="hl-code">, </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">M</span><span class="hl-code">|</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">I</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">matchObj</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">matchObj.group() : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">matchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">matchObj.group(1) : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">matchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">matchObj.group(2) : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">matchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">No match!!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例执行结果如下：</p>&#13;
<pre>&#13;
matchObj.group() :  Cats are smarter than dogs&#13;
matchObj.group(1) :  Cats&#13;
matchObj.group(2) :  smarter&#13;
</pre>&#13;
<hr/><h2>re.search方法</h2>&#13;
<p>re.search 扫描整个字符串并返回第一个成功的匹配。</p>&#13;
<p>函数语法：</p>&#13;
<pre>&#13;
re.search(pattern, string, flags=0)&#13;
</pre>&#13;
<p>函数参数说明：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">参数</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>pattern</td><td>匹配的正则表达式</td></tr>&#13;
<tr><td>string</td><td>要匹配的字符串。</td></tr>&#13;
<tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="#flags">正则表达式修饰符 - 可选标志</a></td></tr>&#13;
</tbody></table>&#13;
<p>匹配成功re.search方法返回一个匹配的对象，否则返回None。</p>&#13;
<p>我们可以使用group(num) 或  groups() 匹配对象函数来获取匹配表达式。</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">匹配对象方法</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>group(num=0)</td><td>匹配的整个表达式的字符串，group() 可以一次输入多个组号，在这种情况下它将返回一个包含那些组所对应值的元组。</td></tr>&#13;
<tr><td>groups()</td><td>返回一个包含所有小组字符串的元组，从 1 到 所含的小组号。</td></tr>&#13;
</tbody></table>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">search</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">www</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">www.runoob.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 在起始位置匹配</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">search</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">com</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">www.runoob.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">         </span><span class="hl-comment"># 不在起始位置匹配</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例运行输出结果为：</p>&#13;
<pre>&#13;
(0, 3)&#13;
(11, 14)&#13;
</pre>&#13;
<div class="example">&#13;
<h2 class="example">实例 </h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">line</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Cats are smarter than dogs</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">searchObj</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">search</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">(.*) are (.*?) .*</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">line</span><span class="hl-code">, </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">M</span><span class="hl-code">|</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">I</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">searchObj</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">searchObj.group() : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">searchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">searchObj.group(1) : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">searchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">searchObj.group(2) : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">searchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Nothing found!!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
以上实例执行结果如下：&#13;
<pre>&#13;
searchObj.group() :  Cats are smarter than dogs&#13;
searchObj.group(1) :  Cats&#13;
searchObj.group(2) :  smarter&#13;
</pre>&#13;
<hr/><h2>re.match 与 re.search的区别</h2>&#13;
<p><span class="marked">re.match</span> 只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回 None，而 <span class="marked">re.search</span> 匹配整个字符串，直到找到一个匹配。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例 </h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">line</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Cats are smarter than dogs</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">matchObj</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">dogs</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">line</span><span class="hl-code">, </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">M</span><span class="hl-code">|</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">I</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">matchObj</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">match --&gt; matchObj.group() : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">matchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">No match!!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">matchObj</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">search</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">dogs</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">line</span><span class="hl-code">, </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">M</span><span class="hl-code">|</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">I</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">matchObj</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">search --&gt; matchObj.group() : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">matchObj</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">No match!!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
以上实例运行结果如下：&#13;
<pre>&#13;
No match!!&#13;
search --&gt; matchObj.group() :  dogs&#13;
</pre>&#13;
&#13;
<hr/><h2>检索和替换</h2>&#13;
<p>Python 的re模块提供了re.sub用于替换字符串中的匹配项。</p>&#13;
<p>语法：</p>&#13;
<pre>&#13;
re.sub(pattern, repl, string, count=0, flags=0)&#13;
</pre>&#13;
<p>参数：</p>&#13;
<ul>&#13;
<li>pattern : 正则中的模式字符串。</li><li>&#13;
repl : 替换的字符串，也可为一个函数。</li><li>&#13;
string : 要被查找替换的原始字符串。</li><li>&#13;
count : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。</li>&#13;
<li>flags : 编译时用的匹配模式，数字形式。</li>&#13;
</ul>&#13;
<p>前三个为必选参数，后两个为可选参数。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例 </h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">phone</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">2004-959-559 # 这是一个电话号码</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-comment"># 删除注释</span><span class="hl-code">
</span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">sub</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">#.*$</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">phone</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">电话号码 : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 移除非数字的内容</span><span class="hl-code">
</span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">sub</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-special">\D</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">phone</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">电话号码 : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">num</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例执行结果如下：</p>&#13;
<pre>&#13;
电话号码 :  2004-959-559 &#13;
电话号码 :  2004959559&#13;
</pre>&#13;
<h3>repl 参数是一个函数</h3><p>&#13;
以下实例中将字符串中的匹配的数字乘以 2：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例 </h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-comment"># 将匹配的数字乘以 2</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">double</span><span class="hl-brackets">(</span><span class="hl-identifier">matched</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-identifier">value</span><span class="hl-code"> = </span><span class="hl-builtin">int</span><span class="hl-brackets">(</span><span class="hl-identifier">matched</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">value</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-builtin">str</span><span class="hl-brackets">(</span><span class="hl-identifier">value</span><span class="hl-code"> * </span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">A23G4HFD567</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">sub</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">(?P&lt;value&gt;</span><span class="hl-special">\d</span><span class="hl-string">+)</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">double</span><span class="hl-code">, </span><span class="hl-identifier">s</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>执行输出结果为：&#13;
</p><pre>A46G8HFD1134</pre>&#13;
&#13;
&#13;
&#13;
<h3>compile 函数</h3>&#13;
&#13;
<p>compile 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 match() 和 search() 这两个函数使用。</p>&#13;
<p>语法格式为：</p>&#13;
&#13;
<pre>re.compile(pattern[, flags])</pre>&#13;
&#13;
<p>参数：</p>&#13;
<ul><li>&#13;
pattern : 一个字符串形式的正则表达式</li><li>&#13;
flags 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：</li><li><ul>&#13;
<strong>re.IGNORECASE 或 re.I</strong> - 使匹配对大小写不敏感</ul></li><li>&#13;
&#13;
re.L 表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境</li><li>&#13;
&#13;
re.MULTILINE 或 re.M -  多行模式，改变 ^ 和 $ 的行为，使它们匹配字符串的每一行的开头和结尾。</li><li>&#13;
&#13;
re.DOTALL 或 re.S - 使 <span class="marked">.</span> 匹配包括换行符在内的任意字符。</li><li>&#13;
&#13;
re.ASCII -  使 \w, \W, \b, \B, \d, \D, \s, \S 仅匹配 ASCII 字符。</li><li>&#13;
&#13;
re.VERBOSE 或 re.X -  忽略空格和注释，可以更清晰地组织复杂的正则表达式。</li></ul>&#13;
<p>这些标志可以单独使用，也可以通过按位或（|）组合使用。例如，re.IGNORECASE | re.MULTILINE 表示同时启用忽略大小写和多行模式。</p>&#13;
&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-code">&gt;&gt;&gt;</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">pattern</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-builtin">compile</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-special">\d</span><span class="hl-string">+</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">                    </span><span class="hl-comment"># 用于匹配至少一个数字</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">one12twothree34four</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">        </span><span class="hl-comment"># 查找头部，没有匹配</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">None</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">one12twothree34four</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">10</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-comment"># 从'e'的位置开始匹配，没有匹配</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">None</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">one12twothree34four</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">10</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-comment"># 从'1'的位置开始匹配，正好匹配</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">                                        </span><span class="hl-comment"># 返回一个 Match 对象</span><span class="hl-code">
&lt;</span><span class="hl-identifier">_sre</span><span class="hl-code">.</span><span class="hl-identifier">SRE_Match</span><span class="hl-code"> </span><span class="hl-identifier">object</span><span class="hl-code"> </span><span class="hl-identifier">at</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-identifier">x10a42aac0</span><span class="hl-code">&gt;
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">   </span><span class="hl-comment"># 可省略 0</span><span class="hl-code">
</span><span class="hl-quotes">'</span><span class="hl-string">12</span><span class="hl-quotes">'</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">start</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">   </span><span class="hl-comment"># 可省略 0</span><span class="hl-code">
</span><span class="hl-number">3</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">     </span><span class="hl-comment"># 可省略 0</span><span class="hl-code">
</span><span class="hl-number">5</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">    </span><span class="hl-comment"># 可省略 0</span><span class="hl-code">
</span><span class="hl-brackets">(</span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">5</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在上面，当匹配成功时返回一个 Match 对象，其中：</p>&#13;
<ul>&#13;
<li><code>group([group1, …])</code> 方法用于获得一个或多个分组匹配的字符串，当要获得整个匹配的子串时，可直接使用 <code>group()</code> 或 <code>group(0)</code>；</li>&#13;
<li><code>start([group])</code> 方法用于获取分组匹配的子串在整个字符串中的起始位置（子串第一个字符的索引），参数默认值为 0；</li>&#13;
<li><code>end([group])</code> 方法用于获取分组匹配的子串在整个字符串中的结束位置（子串最后一个字符的索引+1），参数默认值为 0；</li>&#13;
<li><code>span([group])</code> 方法返回 <code>(start(group), end(group))</code>。</li>&#13;
</ul>&#13;
&#13;
<p>再看看一个例子：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-code">&gt;&gt;&gt;</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">pattern</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-builtin">compile</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-string">([a-z]+) ([a-z]+)</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">I</span><span class="hl-brackets">)</span><span class="hl-code">   </span><span class="hl-comment"># re.I 表示忽略大小写</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">match</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Hello World Wide Web</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 匹配成功，返回一个 Match 对象</span><span class="hl-code">
&lt;</span><span class="hl-identifier">_sre</span><span class="hl-code">.</span><span class="hl-identifier">SRE_Match</span><span class="hl-code"> </span><span class="hl-identifier">object</span><span class="hl-code"> </span><span class="hl-identifier">at</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-identifier">x10bea83e8</span><span class="hl-code">&gt;
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 返回匹配成功的整个子串</span><span class="hl-code">
</span><span class="hl-quotes">'</span><span class="hl-string">Hello World</span><span class="hl-quotes">'</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">                             </span><span class="hl-comment"># 返回匹配成功的整个子串的索引</span><span class="hl-code">
</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-code">, </span><span class="hl-number">11</span><span class="hl-brackets">)</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 返回第一个分组匹配成功的子串</span><span class="hl-code">
</span><span class="hl-quotes">'</span><span class="hl-string">Hello</span><span class="hl-quotes">'</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">                             </span><span class="hl-comment"># 返回第一个分组匹配成功的子串的索引</span><span class="hl-code">
</span><span class="hl-brackets">(</span><span class="hl-number">0</span><span class="hl-code">, </span><span class="hl-number">5</span><span class="hl-brackets">)</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 返回第二个分组匹配成功的子串</span><span class="hl-code">
</span><span class="hl-quotes">'</span><span class="hl-string">World</span><span class="hl-quotes">'</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">span</span><span class="hl-brackets">(</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-code">                             </span><span class="hl-comment"># 返回第二个分组匹配成功的子串索引</span><span class="hl-code">
</span><span class="hl-brackets">(</span><span class="hl-number">6</span><span class="hl-code">, </span><span class="hl-number">11</span><span class="hl-brackets">)</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">groups</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 等价于 (m.group(1), m.group(2), ...)</span><span class="hl-code">
</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Hello</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">World</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">m</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-number">3</span><span class="hl-brackets">)</span><span class="hl-code">                            </span><span class="hl-comment"># 不存在第三个分组</span><span class="hl-code">
</span><span class="hl-identifier">Traceback</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">most</span><span class="hl-code"> </span><span class="hl-identifier">recent</span><span class="hl-code"> </span><span class="hl-identifier">call</span><span class="hl-code"> </span><span class="hl-identifier">last</span><span class="hl-brackets">)</span><span class="hl-code">:
  </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">&lt;stdin&gt;</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">line</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">, </span><span class="hl-reserved">in</span><span class="hl-code"> &lt;</span><span class="hl-identifier">module</span><span class="hl-code">&gt;
</span><span class="hl-reserved">IndexError</span><span class="hl-code">: </span><span class="hl-identifier">no</span><span class="hl-code"> </span><span class="hl-identifier">such</span><span class="hl-code"> </span><span class="hl-identifier">group</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>findall</h3>&#13;
&#13;
<p>在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表。</p>&#13;
<p><strong>注意：</strong> match 和 search  是匹配一次 findall 匹配所有。</p>&#13;
&#13;
<p>语法格式为：</p>&#13;
<pre>&#13;
re.findall(pattern, string, flags=0)&#13;
或&#13;
pattern.findall(string[, pos[, endpos]])</pre>&#13;
<p>参数：</p>&#13;
<ul>&#13;
<li><span class="marked">pattern</span> 匹配模式。&#13;
</li>&#13;
<li><span class="marked">string</span> 待匹配的字符串。&#13;
</li><li><span class="marked">pos</span> 可选参数，指定字符串的起始位置，默认为 0。&#13;
</li><li>&#13;
<span class="marked">endpos</span> 可选参数，指定字符串的结束位置，默认为字符串的长度。</li></ul>&#13;
&#13;
&#13;
<p>查找字符串中的所有数字：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">result1</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">findall</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-special">\d</span><span class="hl-string">+</span><span class="hl-quotes">'</span><span class="hl-code">,</span><span class="hl-quotes">'</span><span class="hl-string">runoob 123 google 456</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">pattern</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-builtin">compile</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">'</span><span class="hl-special">\d</span><span class="hl-string">+</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">   </span><span class="hl-comment"># 查找数字</span><span class="hl-code">
</span><span class="hl-identifier">result2</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">findall</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">runoob 123 google 456</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">result3</span><span class="hl-code"> = </span><span class="hl-identifier">pattern</span><span class="hl-code">.</span><span class="hl-identifier">findall</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">run88oob123google456</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">0</span><span class="hl-code">, </span><span class="hl-number">10</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">result1</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">result2</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">result3</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>输出结果：</p>&#13;
&#13;
<pre>&#13;
['123', '456']&#13;
['123', '456']&#13;
['88', '12']&#13;
</pre>&#13;
<p>多个匹配模式，返回元组列表：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">re</span><br/>
<br/>
result <span style="color: Gray;">=</span> <span style="color: #05a;">re</span>.<span style="color: #05a;">findall</span><span style="color: Olive;">(</span>r<span style="color: #a11;">'(<span style="color: #000099; font-weight: bold;">\w</span>+)=(<span style="color: #000099; font-weight: bold;">\d</span>+)'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'set width=20 and height=10'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>result<span style="color: Olive;">)</span><br/>
</div></div>&#13;
<pre>[('width', '20'), ('height', '10')]</pre>&#13;
<h3>re.finditer</h3>&#13;
<p>和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。</p>&#13;
&#13;
&#13;
<pre>re.finditer(pattern, string, flags=0)</pre>&#13;
 &#13;
<p>参数：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">参数</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>pattern</td><td>匹配的正则表达式</td></tr>&#13;
<tr><td>string</td><td>要匹配的字符串。</td></tr>&#13;
<tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="#flags">正则表达式修饰符 - 可选标志</a></td></tr>&#13;
</tbody></table>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
 
</span><span class="hl-identifier">it</span><span class="hl-code"> = </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">finditer</span><span class="hl-brackets">(</span><span class="hl-identifier">r</span><span class="hl-quotes">"</span><span class="hl-special">\d</span><span class="hl-string">+</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-quotes">"</span><span class="hl-string">12a32bc43jf3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code"> 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">match</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">it</span><span class="hl-code">: 
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">match</span><span class="hl-code">.</span><span class="hl-identifier">group</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>输出结果：</p><pre>&#13;
12 &#13;
32 &#13;
43 &#13;
3&#13;
</pre>&#13;
<h3>re.split</h3>&#13;
<p>split 方法按照能够匹配的子串将字符串分割后返回列表，它的使用形式如下：</p>&#13;
<pre>re.split(pattern, string[, maxsplit=0, flags=0])</pre>&#13;
<p>参数：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">参数</th><th>描述</th>&#13;
</tr>&#13;
<tr><td>pattern</td><td>匹配的正则表达式</td></tr>&#13;
<tr><td>string</td><td>要匹配的字符串。</td></tr>&#13;
<tr><td>maxsplit</td><td>分割次数，maxsplit=1 分割一次，默认为 0，不限制次数。</td></tr>&#13;
<tr><td>flags</td><td>标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。参见：<a href="#flags">正则表达式修饰符 - 可选标志</a></td></tr></tbody></table>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-code">&gt;&gt;&gt;</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">re</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">split</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-special">\W</span><span class="hl-string">+</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob, runoob, runoob.</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">split</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">(</span><span class="hl-special">\W</span><span class="hl-string">+)</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string"> runoob, runoob, runoob.</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code"> 
</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string"> </span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">, </span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">, </span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">.</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">
&gt;&gt;&gt; </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">split</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-special">\W</span><span class="hl-string">+</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string"> runoob, runoob, runoob.</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code"> 
</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">runoob, runoob, runoob.</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">
 
&gt;&gt;&gt; </span><span class="hl-identifier">re</span><span class="hl-code">.</span><span class="hl-identifier">split</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">a*</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">hello world</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">   </span><span class="hl-comment"># 对于一个找不到匹配的字符串而言，split 不会对其作出分割</span><span class="hl-code">
</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">hello world</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<hr/>&#13;
<h2>正则表达式对象</h2>&#13;
<h3>&#13;
re.RegexObject&#13;
</h3>&#13;
&#13;
<p>re.compile() 返回 RegexObject 对象。</p>&#13;
&#13;
 &#13;
<h3>&#13;
re.MatchObject&#13;
</h3>&#13;
&#13;
<p>group() 返回被 RE 匹配的字符串。</p>&#13;
<ul><li>&#13;
<span class="marked">start()</span> 返回匹配开始的位置&#13;
</li><li>&#13;
<span class="marked">end()</span> 返回匹配结束的位置&#13;
</li><li>&#13;
<span class="marked">span()</span> 返回一个元组包含匹配 (开始,结束) 的位置&#13;
</li></ul>&#13;
<hr/>&#13;
<h2 id="flags">正则表达式修饰符 - 可选标志</h2>&#13;
<p>正则表达式可以包含一些可选标志修饰符来控制匹配的模式。</p><p>&#13;
以下标志可以单独使用，也可以通过按位或（|）组合使用。例如，re.IGNORECASE | re.MULTILINE 表示同时启用忽略大小写和多行模式。</p>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:25%">修饰符</th><th>描述</th><th>实例</th></tr>&#13;
<tr><td>re.IGNORECASE 或 re.I</td><td>使匹配对大小写不敏感</td>&#13;
<td>&#13;
<pre>&#13;
import re&#13;
pattern = re.compile(r'apple', flags=re.IGNORECASE)&#13;
result = pattern.match('Apple')&#13;
print(result.group())  # 输出: 'Apple'&#13;
</pre></td>&#13;
</tr>&#13;
&#13;
<tr><td>re.MULTILINE 或 re.M</td><td>多行匹配，影响 <span class="marked">^</span> 和 <span class="marked">$</span>，使它们匹配字符串的每一行的开头和结尾。</td>&#13;
<td>&#13;
<pre>&#13;
import re&#13;
pattern = re.compile(r'^\d+', flags=re.MULTILINE)&#13;
text = '123\n456\n789'&#13;
result = pattern.findall(text)&#13;
print(result)  # 输出: ['123', '456', '789']&#13;
</pre></td>&#13;
</tr>&#13;
<tr><td>re.DOTALL 或 re.S：</td><td>使 <span class="marked">.</span> 匹配包括换行符在内的任意字符。</td>&#13;
<td>&#13;
<pre>&#13;
import re&#13;
pattern = re.compile(r'a.b', flags=re.DOTALL)&#13;
result = pattern.match('a\nb')&#13;
print(result.group())  # 输出: 'a\nb'&#13;
</pre></td>&#13;
</tr>&#13;
<tr><td>re.ASCII</td><td>使 \w, \W, \b, \B, \d, \D, \s, \S 仅匹配 ASCII 字符。</td>&#13;
<td>&#13;
<pre>&#13;
import re&#13;
pattern = re.compile(r'\w+', flags=re.ASCII)&#13;
result = pattern.match('Hello123')&#13;
print(result.group())  # 输出: 'Hello123'&#13;
</pre></td>&#13;
</tr>&#13;
<tr><td>re.VERBOSE 或 re.X</td><td>忽略空格和注释，可以更清晰地组织复杂的正则表达式。</td>&#13;
<td>&#13;
<pre>&#13;
import re&#13;
pattern = re.compile(r'''&#13;
    \d+  # 匹配数字&#13;
    [a-z]+  # 匹配小写字母&#13;
''', flags=re.VERBOSE)&#13;
result = pattern.match('123abc')&#13;
print(result.group())  # 输出: '123abc'&#13;
</pre></td>&#13;
</tr>&#13;
</tbody></table>&#13;
&#13;
<hr/>&#13;
<h2>正则表达式模式</h2>&#13;
<p>模式字符串使用特殊的语法来表示一个正则表达式。</p>&#13;
&#13;
<p>字母和数字表示他们自身。一个正则表达式模式中的字母和数字匹配同样的字符串。</p>&#13;
&#13;
<p>多数字母和数字前加一个反斜杠时会拥有不同的含义。</p>&#13;
&#13;
<p>标点符号只有被转义时才匹配自身，否则它们表示特殊的含义。</p>&#13;
&#13;
<p>反斜杠本身需要使用反斜杠转义。</p>&#13;
&#13;
<p>由于正则表达式通常都包含反斜杠，所以你最好使用原始字符串来表示它们。模式元素(如 <span class="marked">r'\t'</span>，等价于 <span class="marked">\\t</span> )匹配相应的特殊字符。</p>&#13;
<p>下表列出了正则表达式模式语法中的特殊元素。如果你使用模式的同时提供了可选的标志参数，某些模式元素的含义会改变。</p>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:25%">模式</th><th>描述</th></tr>&#13;
<tr><td>^</td><td>匹配字符串的开头</td></tr>&#13;
<tr><td>$</td><td>匹配字符串的末尾。</td></tr>&#13;
<tr><td>.</td><td>匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。</td></tr>&#13;
<tr><td>[...]</td><td>用来匹配所包含的任意一个字符，例如  [amk] 匹配 'a'，'m'或'k'</td></tr>&#13;
<tr><td>[^...]</td><td>不在[]中的字符：[^abc] 匹配除了a,b,c之外的字符。</td></tr>&#13;
<tr><td>re*</td><td>匹配0个或多个的表达式。</td></tr>&#13;
<tr><td>re+</td><td>匹配1个或多个的表达式。</td></tr>&#13;
<tr><td>re?</td><td>   匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式</td></tr>&#13;
<tr><td>re{ n}</td><td>匹配n个前面表达式。例如，"o{2}"不能匹配"Bob"中的"o"，但是能匹配"food"中的两个o。</td></tr>&#13;
<tr><td>re{ n,}</td><td>精确匹配n个前面表达式。例如，"o{2,}"不能匹配"Bob"中的"o"，但能匹配"foooood"中的所有o。"o{1,}"等价于"o+"。"o{0,}"则等价于"o*"。</td></tr>&#13;
<tr><td>re{ n, m}</td><td>匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式</td></tr>&#13;
<tr><td>a| b</td><td>匹配a或b</td></tr>&#13;
<tr><td>(re)</td><td>匹配括号内的表达式，也表示一个组</td></tr>&#13;
<tr><td>(?imx)</td><td>正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。</td></tr>&#13;
<tr><td>(?-imx)</td><td>正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。</td></tr>&#13;
<tr><td>(?: re)</td><td> 类似 (...), 但是不表示一个组</td></tr>&#13;
<tr><td>(?imx: re)</td><td>在括号中使用i, m, 或 x 可选标志</td></tr>&#13;
<tr><td>(?-imx: re)</td><td>在括号中不使用i, m, 或 x 可选标志</td></tr>&#13;
<tr><td>(?#...)</td><td>注释.</td></tr>&#13;
<tr><td>(?= re)</td><td>前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。</td></tr>&#13;
<tr><td>(?! re)</td><td>前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功。</td></tr>&#13;
<tr><td>(?&gt; re)</td><td>匹配的独立模式，省去回溯。</td></tr>&#13;
<tr><td>\w</td><td> 匹配数字字母下划线</td></tr>&#13;
<tr><td>\W</td><td>匹配非数字字母下划线</td></tr>&#13;
<tr><td>\s</td><td> 匹配任意空白字符，等价于 [\t\n\r\f]。</td></tr>&#13;
<tr><td>\S</td><td>匹配任意非空字符</td></tr>&#13;
<tr><td>\d</td><td> 匹配任意数字，等价于 [0-9]。</td></tr>&#13;
<tr><td>\D</td><td>匹配任意非数字</td></tr>&#13;
<tr><td>\A</td><td>匹配字符串开始</td></tr>&#13;
<tr><td>\Z</td><td>匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。</td></tr>&#13;
<tr><td>\z</td><td>匹配字符串结束</td></tr>&#13;
<tr><td>\G</td><td>匹配最后匹配完成的位置。</td></tr>&#13;
<tr><td>\b</td><td>匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。</td></tr>&#13;
<tr><td>\B</td><td>匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。</td></tr>&#13;
<tr><td>\n, \t, 等。</td><td>匹配一个换行符。匹配一个制表符, 等</td></tr>&#13;
<tr><td>\1...\9</td><td>匹配第n个分组的内容。</td></tr>&#13;
<tr><td>\10</td><td>匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。</td></tr>&#13;
</tbody></table>&#13;
<hr/><h2>&#13;
正则表达式实例&#13;
</h2>&#13;
<h4>字符匹配</h4>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:25%">实例</th><th>描述</th></tr>&#13;
<tr><td>python</td><td>匹配 "python". </td></tr>&#13;
</tbody></table>&#13;
<h4>字符类</h4>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:25%">实例</th><th>描述</th></tr>&#13;
<tr><td>[Pp]ython </td><td>匹配 "Python" 或 "python"</td></tr>&#13;
<tr><td>rub[ye]</td><td>匹配 "ruby" 或 "rube"</td></tr>&#13;
<tr><td>[aeiou]</td><td>匹配中括号内的任意一个字母</td></tr>&#13;
<tr><td>[0-9]</td><td>匹配任何数字。类似于 [0123456789]</td></tr>&#13;
<tr><td>[a-z]</td><td>匹配任何小写字母</td></tr>&#13;
<tr><td>[A-Z]</td><td>匹配任何大写字母</td></tr>&#13;
<tr><td>[a-zA-Z0-9]</td><td>匹配任何字母及数字</td></tr>&#13;
<tr><td>[^aeiou]</td><td>除了aeiou字母以外的所有字符 &#13;
</td></tr>&#13;
<tr><td>[^0-9]</td><td>匹配除了数字外的字符 &#13;
</td></tr>&#13;
</tbody></table>&#13;
&#13;
<h4>特殊字符类</h4>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:25%">实例</th><th>描述</th></tr>&#13;
<tr><td>.</td><td>匹配除 "\n" 之外的任何单个字符。要匹配包括 '\n' 在内的任何字符，请使用象 '[.\n]' 的模式。</td></tr>&#13;
<tr><td>\d</td><td>匹配一个数字字符。等价于 [0-9]。</td></tr>&#13;
<tr><td>\D </td><td>匹配一个非数字字符。等价于 [^0-9]。</td></tr>&#13;
<tr><td>\s</td><td>匹配任何空白字符，包括空格、制表符、换页符等等。等价于 [ \f\n\r\t\v]。</td></tr>&#13;
<tr><td>\S </td><td>匹配任何非空白字符。等价于 [^ \f\n\r\t\v]。</td></tr>&#13;
<tr><td>\w</td><td>匹配包括下划线的任何单词字符。等价于'[A-Za-z0-9_]'。</td></tr>&#13;
<tr><td>\W</td><td>匹配任何非单词字符。等价于 '[^A-Za-z0-9_]'。</td></tr>&#13;
</tbody></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>