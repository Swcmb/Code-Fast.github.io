<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 命令行参数</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C <span class="color_h1">命令行参数</span></h1>&#13;
&#13;
<p>执行程序时，可以从命令行传值给 C 程序。这些值被称为<b>命令行参数</b>，它们对程序很重要，特别是当您想从外部控制程序，而不是在代码内对这些值进行硬编码时，就显得尤为重要了。</p>&#13;
<p>&#13;
在 C 语言中，命令行参数是一种从命令行获取输入的方法，可以用于运行程序时传递信息给程序。命令行参数通过 main 函数的参数传递给程序。main 函数的原型可以是如下两种形式之一：</p>&#13;
<pre>int main(int argc, char *argv[]);</pre>&#13;
<p>&#13;
或者:</p>&#13;
&#13;
<pre>int main(int argc, char **argv);</pre>&#13;
&#13;
<ul><li><p><strong><code>argc</code> (argument count)</strong>: 表示命令行参数的数量，包括程序名本身。因此，<code>argc</code> 至少为 1。</p></li><li><p><strong><code>argv</code> (argument vector)</strong>: 是一个指向字符串数组的指针，其中每个字符串是一个命令行参数。数组的第一个元素（即 <code>argv[0]</code>）通常是程序的名称。接下来的元素是传递给程序的命令行参数。</p></li></ul>&#13;
<p>下面是一个简单的实例，检查命令行是否有提供参数，并根据参数执行相应的动作：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span> <span style="color: #993333;">int</span> argc<span style="color: #339933;">,</span> <span style="color: #993333;">char</span> <span style="color: #339933;">*</span>argv<span style="color: #000;">[</span><span style="color: #000;">]</span> <span style="color: #000;">)</span>  <br/>
<span style="color: #000;">{</span><br/>
   <span style="color: #708;">if</span><span style="color: #000;">(</span> argc <span style="color: #339933;">==</span> <span style="color: #164;">2</span> <span style="color: #000;">)</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"The argument supplied is %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> argv<span style="color: #000;">[</span><span style="color: #164;">1</span><span style="color: #000;">]</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
   <span style="color: #708;">else</span> <span style="color: #708;">if</span><span style="color: #000;">(</span> argc <span style="color: #339933;">&gt;</span> <span style="color: #164;">2</span> <span style="color: #000;">)</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Too many arguments supplied.<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
   <span style="color: #708;">else</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"One argument expected.<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
&#13;
<p>使用一个参数，编译并执行上面的代码，它会产生下列结果：</p>&#13;
<pre>&#13;
$./a.out testing&#13;
The argument supplied is testing&#13;
</pre>&#13;
<p>使用两个参数，编译并执行上面的代码，它会产生下列结果：</p>&#13;
<pre>&#13;
$./a.out testing1 testing2&#13;
Too many arguments supplied.&#13;
</pre>&#13;
<p>不传任何参数，编译并执行上面的代码，它会产生下列结果：</p>&#13;
<pre>&#13;
$./a.out&#13;
One argument expected&#13;
</pre>&#13;
<p>应当指出的是，<b>argv[0]</b> 存储程序的名称，<b>argv[1]</b> 是一个指向第一个命令行参数的指针，*argv[n] 是最后一个参数。如果没有提供任何参数，argc 将为 1，否则，如果传递了一个参数，<b>argc</b> 将被设置为 2。</p>&#13;
<p>多个命令行参数之间用空格分隔，但是如果参数本身带有空格，那么传递参数的时候应把参数放置在双引号 "" 或单引号 '' 内部。让我们重新编写上面的实例，有一个空格，那么你可以通过这样的观点，把它们放在双引号或单引号""""。让我们重新编写上面的实例，向程序传递一个放置在双引号内部的命令行参数：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span> <span style="color: #993333;">int</span> argc<span style="color: #339933;">,</span> <span style="color: #993333;">char</span> <span style="color: #339933;">*</span>argv<span style="color: #000;">[</span><span style="color: #000;">]</span> <span style="color: #000;">)</span>  <br/>
<span style="color: #000;">{</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Program name %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> argv<span style="color: #000;">[</span><span style="color: #164;">0</span><span style="color: #000;">]</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
 <br/>
   <span style="color: #708;">if</span><span style="color: #000;">(</span> argc <span style="color: #339933;">==</span> <span style="color: #164;">2</span> <span style="color: #000;">)</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"The argument supplied is %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> argv<span style="color: #000;">[</span><span style="color: #164;">1</span><span style="color: #000;">]</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
   <span style="color: #708;">else</span> <span style="color: #708;">if</span><span style="color: #000;">(</span> argc <span style="color: #339933;">&gt;</span> <span style="color: #164;">2</span> <span style="color: #000;">)</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Too many arguments supplied.<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
   <span style="color: #708;">else</span><br/>
   <span style="color: #000;">{</span><br/>
      <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"One argument expected.<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000;">}</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
&#13;
<p>使用一个用空格分隔的简单参数，参数括在双引号中，编译并执行上面的代码，它会产生下列结果：</p>&#13;
<pre>&#13;
$./a.out "testing1 testing2"&#13;
&#13;
Progranm name ./a.out&#13;
The argument supplied is testing1 testing2&#13;
</pre>&#13;
<h3>&#13;
使用场景</h3>&#13;
<p>&#13;
命令行参数在许多情况下都很有用，例如：</p><ul><li>配置文件路径</li><li>模式选择（例如调试模式）</li><li>输入文件和输出文件名</li><li>运行时选项和标志（如 <code>-v</code> 表示详细模式）</li></ul><h3>注意事项</h3><ul><li>命令行参数通常是字符串，如果需要将其转换为数值类型，可以使用标准库函数如 <code>atoi</code> 或 <code>strtol</code>。</li><li>应该始终验证和处理命令行参数，以防止输入错误或恶意输入。</li></ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>