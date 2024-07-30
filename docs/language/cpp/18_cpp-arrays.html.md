<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 数组</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">数组</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>C++ 支持<b>数组</b>数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。数组是用来存储一系列数据，但它往往被认为是一系列相同类型的变量。</p>&#13;
<p>数组的声明并不是声明一个个单独的变量，比如 number0、number1、...、number99，而是声明一个数组变量，比如 numbers，然后使用 numbers[0]、numbers[1]、...、numbers[99] 来代表一个个单独的变量。数组中的特定元素可以通过索引访问。</p>&#13;
<p>所有的数组都是由连续的内存位置组成。最低的地址对应第一个元素，最高的地址对应最后一个元素。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">声明数组</h2>&#13;
<p>在 C++ 中要声明一个数组，需要指定元素的类型和元素的数量，如下所示：</p>&#13;
<pre>&#13;
type arrayName [ arraySize ];&#13;
</pre>&#13;
<p>这叫做一维数组。<b>arraySize</b> 必须是一个大于零的整数常量，<b>type</b> 可以是任意有效的 C++ 数据类型。例如，要声明一个类型为 double 的包含 10 个元素的数组 <b>balance</b>，声明语句如下：</p>&#13;
<pre>&#13;
double balance[10];&#13;
</pre>&#13;
<p>现在 <i>balance</i> 是一个可用的数组，可以容纳 10 个类型为 double 的数字。</p>&#13;
&#13;
<h2 class="tutheader">初始化数组</h2>&#13;
<p>在 C++ 中，您可以逐个初始化数组，也可以使用一个初始化语句，如下所示：</p>&#13;
<pre>&#13;
double balance[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};&#13;
</pre>&#13;
<p>大括号 { } 之间的值的数目不能大于我们在数组声明时在方括号 [ ] 中指定的元素数目。</p>&#13;
<p>如果您省略掉了数组的大小，数组的大小则为初始化时元素的个数。因此，如果：</p>&#13;
<pre>&#13;
double balance[] = {1000.0, 2.0, 3.4, 7.0, 50.0};&#13;
</pre>&#13;
<p>您将创建一个数组，它与前一个实例中所创建的数组是完全相同的。下面是一个为数组中某个元素赋值的实例：</p>&#13;
<pre>&#13;
balance[4] = 50.0;&#13;
</pre>&#13;
<p>上述的语句把数组中第五个元素的值赋为 50.0。所有的数组都是以 0 作为它们第一个元素的索引，也被称为基索引，数组的最后一个索引是数组的总大小减去 1。以下是上面所讨论的数组的的图形表示：</p>&#13;
<center>&#13;
<img decoding="async" src="/wp-content/uploads/2014/08/array_presentation.jpg" alt="数组表示"/>&#13;
</center>&#13;
&#13;
<h2 class="tutheader">访问数组元素</h2>&#13;
<p>数组元素可以通过数组名称加索引进行访问。元素的索引是放在方括号内，跟在数组名称的后边。例如：</p>&#13;
<pre>&#13;
double salary = balance[9];&#13;
</pre>&#13;
<p>上面的语句将把数组中第 10 个元素的值赋给 salary 变量。下面的实例使用了上述的三个概念，即，声明数组、数组赋值、访问数组：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iomanip</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">setw</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-number">10</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code">; </span><span class="hl-comment">// n 是一个包含 10 个整数的数组</span><span class="hl-comment"/><span class="hl-code">
 
   </span><span class="hl-comment">// 初始化数组元素          </span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code"> + </span><span class="hl-number">100</span><span class="hl-code">; </span><span class="hl-comment">// 设置元素 i 为 i + 100</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Element</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">setw</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">13</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 输出数组中每个元素的值                     </span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">j</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code"> &lt; </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">setw</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">7</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">j</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">setw</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">13</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">n</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-identifier">j</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上面的程序使用了 <b><a href="https://www.runoob.com/w3cnote/cpp-func-setw.html" rel="noopener noreferrer" target="_blank">setw() 函数</a></b> 来格式化输出。当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Element        Value&#13;
      0          100&#13;
      1          101&#13;
      2          102&#13;
      3          103&#13;
      4          104&#13;
      5          105&#13;
      6          106&#13;
      7          107&#13;
      8          108&#13;
      9          109&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">C++ 中数组详解</h2>&#13;
<p>在 C++ 中，数组是非常重要的，我们需要了解更多有关数组的细节。下面列出了 C++ 程序员必须清楚的一些与数组相关的重要概念：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:30%">概念</th><th>描述</th></tr>&#13;
<tr><td> <a href="/cplusplus/cpp-multi-dimensional-arrays.html" title="C++ 中的多维数组">多维数组</a></td><td>C++ 支持多维数组。多维数组最简单的形式是二维数组。</td> </tr>&#13;
<tr><td> <a href="/cplusplus/cpp-pointer-to-an-array.html" title="C++ 中指向数组的指针">指向数组的指针</a></td><td>您可以通过指定不带索引的数组名称来生成一个指向数组中第一个元素的指针。</td> </tr>&#13;
<tr><td> <a href="/cplusplus/cpp-passing-arrays-to-functions.html" title="C++ 中传递数组给函数作为参数">传递数组给函数</a></td><td>您可以通过指定不带索引的数组名称来给函数传递一个指向数组的指针。</td> </tr>&#13;
<tr><td> <a href="/cplusplus/cpp-return-arrays-from-function.html" title="C++ 中从函数返回数组">从函数返回数组</a></td><td>C++ 允许从函数返回数组。</td> </tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>