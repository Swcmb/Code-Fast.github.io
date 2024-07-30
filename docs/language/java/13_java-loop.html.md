<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 循环结构 - for, while 及 do...while</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 循环结构 - for, while 及 do...while</h1>&#13;
<p>顺序结构的程序语句只能被执行一次。</p><p>如果您想要同样的操作执行多次，就需要使用循环结构。&#13;
</p><p>Java中有三种主要的循环结构：</p>&#13;
<ul>&#13;
	<li>&#13;
		<strong>while</strong> 循环</li>&#13;
	<li>&#13;
		<strong>do…while</strong> 循环</li>&#13;
	<li>&#13;
		<strong>for</strong> 循环</li>&#13;
</ul>&#13;
<p>在 Java5 中引入了一种主要用于数组的增强型 for 循环。</p>&#13;
<hr/>&#13;
<h2>while 循环</h2>&#13;
<p>while是最基本的循环，它的结构为：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-code"> 布尔表达式 </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">循环内容</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>只要布尔表达式为 true，循环就会一直执行下去。</p>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
      </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> &lt; </span><span class="hl-number">20</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">value of x : </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">x</span><span class="hl-code">++;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
value of x : 10&#13;
value of x : 11&#13;
value of x : 12&#13;
value of x : 13&#13;
value of x : 14&#13;
value of x : 15&#13;
value of x : 16&#13;
value of x : 17&#13;
value of x : 18&#13;
value of x : 19&#13;
</pre>&#13;
<hr/>&#13;
<h2>do…while 循环</h2>&#13;
<p>对于 while 语句而言，如果不满足条件，则不能进入循环。但有时候我们需要即使不满足条件，也至少执行一次。</p>&#13;
<p>do…while 循环和 while 循环相似，不同的是，do…while 循环至少会执行一次。</p>&#13;
<pre>&#13;
do {&#13;
       //代码语句&#13;
}while(布尔表达式);&#13;
</pre>&#13;
<p>&#13;
<strong>注意：</strong>布尔表达式在循环体的后面，所以语句块在检测布尔表达式之前已经执行了。&#13;
如果布尔表达式的值为 true，则语句块一直执行，直到布尔表达式的值为 false。&#13;
</p>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
 
      </span><span class="hl-reserved">do</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">value of x : </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">x</span><span class="hl-code">++;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> &lt; </span><span class="hl-number">20</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
value of x : 10&#13;
value of x : 11&#13;
value of x : 12&#13;
value of x : 13&#13;
value of x : 14&#13;
value of x : 15&#13;
value of x : 16&#13;
value of x : 17&#13;
value of x : 18&#13;
value of x : 19&#13;
</pre>&#13;
<hr/>&#13;
<h2>for循环</h2>&#13;
<p>虽然所有循环结构都可以用 while 或者 do...while表示，但 Java 提供了另一种语句 —— for 循环，使一些循环结构变得更加简单。&#13;
</p>&#13;
<p>for循环执行的次数是在执行前就确定的。语法格式如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code">初始化; 布尔表达式; 更新</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-comment">//</span><span class="hl-comment">代码语句</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>关于 for 循环有以下几点说明：</p>&#13;
<ul>&#13;
	<li>&#13;
		最先执行初始化步骤。可以声明一种类型，但可初始化一个或多个循环控制变量，也可以是空语句。</li>&#13;
	<li>&#13;
		然后，检测布尔表达式的值。如果为 true，循环体被执行。如果为false，循环终止，开始执行循环体后面的语句。</li>&#13;
	<li>&#13;
		执行一次循环后，更新循环控制变量。</li>&#13;
	<li>&#13;
		再次检测布尔表达式。循环执行上面的过程。</li>&#13;
</ul>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
      </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">x</span><span class="hl-code"> &lt; </span><span class="hl-number">20</span><span class="hl-code">; </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-identifier">x</span><span class="hl-code">+</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">value of x : </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
value of x : 10&#13;
value of x : 11&#13;
value of x : 12&#13;
value of x : 13&#13;
value of x : 14&#13;
value of x : 15&#13;
value of x : 16&#13;
value of x : 17&#13;
value of x : 18&#13;
value of x : 19&#13;
</pre>&#13;
<hr/>&#13;
<h2 id="java-foreach">Java 增强 for 循环</h2>&#13;
<p>Java5 引入了一种主要用于数组的增强型 for 循环。</p>&#13;
<p>Java 增强 for 循环语法格式如下:</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code">声明语句 : 表达式</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment">代码句子</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><strong>声明语句：</strong>声明新的局部变量，该变量的类型必须和数组元素的类型匹配。其作用域限定在循环语句块，其值与此时数组元素的值相等。&#13;
</p><p><strong>表达式：</strong>表达式是要访问的数组名，或者是返回值为数组的方法。</p>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">numbers</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-number">10</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-code">, </span><span class="hl-number">30</span><span class="hl-code">, </span><span class="hl-number">40</span><span class="hl-code">, </span><span class="hl-number">50</span><span class="hl-brackets">}</span><span class="hl-code">;
 
      </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> : </span><span class="hl-identifier">numbers</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">,</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">names</span><span class="hl-code"> =</span><span class="hl-brackets">{</span><span class="hl-quotes">"</span><span class="hl-string">James</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Larry</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Tom</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Lacy</span><span class="hl-quotes">"</span><span class="hl-brackets">}</span><span class="hl-code">;
      </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code"> : </span><span class="hl-identifier">names</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">,</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
10,20,30,40,50,&#13;
James,Larry,Tom,Lacy,&#13;
</pre>&#13;
<hr/>&#13;
<h2>break 关键字</h2>&#13;
<p>break 主要用在循环语句或者 switch 语句中，用来跳出整个语句块。&#13;
</p><p>break 跳出最里层的循环，并且继续执行该循环下面的语句。</p>&#13;
<h3>语法</h3>&#13;
<p>break 的用法很简单，就是循环结构中的一条语句：</p>&#13;
<pre>&#13;
break;&#13;
</pre>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">numbers</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-number">10</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-code">, </span><span class="hl-number">30</span><span class="hl-code">, </span><span class="hl-number">40</span><span class="hl-code">, </span><span class="hl-number">50</span><span class="hl-brackets">}</span><span class="hl-code">;
 
      </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> : </span><span class="hl-identifier">numbers</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-comment">//</span><span class="hl-comment"> x 等于 30 时跳出循环</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> == </span><span class="hl-number">30</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
10&#13;
20&#13;
</pre>&#13;
<hr/>&#13;
<h2>continue 关键字</h2>&#13;
<p>continue 适用于任何循环控制结构中。作用是让程序立刻跳转到下一次循环的迭代。&#13;
</p><p>在 for 循环中，continue 语句使程序立即跳转到更新语句。&#13;
</p><p>在 while 或者 do…while 循环中，程序立即跳转到布尔表达式的判断语句。&#13;
</p>&#13;
<h3>语法</h3>&#13;
<p>continue 就是循环体中一条简单的语句：</p>&#13;
<pre>&#13;
continue;&#13;
</pre>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">numbers</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-number">10</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-code">, </span><span class="hl-number">30</span><span class="hl-code">, </span><span class="hl-number">40</span><span class="hl-code">, </span><span class="hl-number">50</span><span class="hl-brackets">}</span><span class="hl-code">;
 
      </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> : </span><span class="hl-identifier">numbers</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> == </span><span class="hl-number">30</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">continue</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
10&#13;
20&#13;
40&#13;
50&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>