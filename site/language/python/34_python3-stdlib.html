<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 标准库概览</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 标准库概览</h1>&#13;
<p>Python 标准库非常庞大，所提供的组件涉及范围十分广泛，使用标准库我们可以让您轻松地完成各种任务。</p>&#13;
<p>以下是一些 Python3 标准库中的模块：</p>&#13;
<ul><li><p>os 模块：os 模块提供了许多与操作系统交互的函数，例如创建、移动和删除文件和目录，以及访问环境变量等。</p></li><li><p>sys 模块：sys 模块提供了与 Python 解释器和系统相关的功能，例如解释器的版本和路径，以及与 stdin、stdout 和 stderr 相关的信息。</p></li><li><p>time 模块：time 模块提供了处理时间的函数，例如获取当前时间、格式化日期和时间、计时等。</p></li><li><p>datetime 模块：datetime 模块提供了更高级的日期和时间处理函数，例如处理时区、计算时间差、计算日期差等。</p></li><li><p>random 模块：random 模块提供了生成随机数的函数，例如生成随机整数、浮点数、序列等。</p></li><li><p>math 模块：math 模块提供了数学函数，例如三角函数、对数函数、指数函数、常数等。</p></li><li><p>re 模块：re 模块提供了正则表达式处理函数，可以用于文本搜索、替换、分割等。</p></li><li><p>json 模块：json 模块提供了 JSON 编码和解码函数，可以将 Python 对象转换为 JSON 格式，并从 JSON 格式中解析出 Python 对象。</p></li><li><p>urllib 模块：urllib 模块提供了访问网页和处理 URL 的功能，包括下载文件、发送 POST 请求、处理 cookies 等。</p></li></ul>&#13;
&#13;
<h2>操作系统接口</h2>&#13;
<p>os 模块提供了不少与操作系统相关联的函数，例如文件和目录的操作。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">os</span><br/>
<br/>
<span style="color: #a50"># 获取当前工作目录</span><br/>
current_dir <span style="color: Gray;">=</span> <span style="color: #05a;">os</span>.<span style="color: #05a;">getcwd</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"当前工作目录:"</span><span style="color: Gray;">,</span> current_dir<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 列出目录下的文件</span><br/>
files <span style="color: Gray;">=</span> <span style="color: #05a;">os</span>.<span style="color: #05a;">listdir</span><span style="color: Olive;">(</span>current_dir<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"目录下的文件:"</span><span style="color: Gray;">,</span> files<span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>建议使用 <span class="marked">import os</span> 风格而非 <span class="marked">from os import *</span>，这样可以保证随操作系统不同而有所变化的 <strong>os.open()</strong> 不会覆盖内置函数 open()。&#13;
</p>&#13;
<p>在使用 os 这样的大型模块时内置的 dir() 和 help() 函数非常有用:</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import os&#13;
&gt;&gt;&gt; dir(os)&#13;
&lt;returns a list of all module functions&gt;&#13;
&gt;&gt;&gt; help(os)&#13;
&lt;returns an extensive manual page created from the module's docstrings&gt;&#13;
</pre>&#13;
<p>针对日常的文件和目录管理任务，:mod:shutil 模块提供了一个易于使用的高级接口:</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import shutil&#13;
&gt;&gt;&gt; shutil.copyfile('data.db', 'archive.db')&#13;
&gt;&gt;&gt; shutil.move('/build/executables', 'installdir')&#13;
</pre>&#13;
<hr/>&#13;
<h2>文件通配符</h2>&#13;
<p>glob 模块提供了一个函数用于从目录通配符搜索中生成文件列表:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">glob</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">glob</span>.<span style="color: #05a;">glob</span><span style="color: Olive;">(</span><span style="color: #a11;">'*.py'</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'primes.py'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'random.py'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'quote.py'</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<hr/>&#13;
<h2>命令行参数</h2>&#13;
<p>通用工具脚本经常调用命令行参数。这些命令行参数以链表形式存储于 sys 模块的 argv 变量。例如在命令行中执行 "python demo.py one two three" 后可以得到以下输出结果:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">sys</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #05a;">sys</span>.<span style="color: #05a;">argv</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'demo.py'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'one'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'two'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'three'</span><span style="color: Olive;">]</span><br/>
</div></div>&#13;
&#13;
<hr/>&#13;
<h2>错误输出重定向和程序终止</h2>&#13;
<p>sys 还有 stdin，stdout 和 stderr 属性，即使在 stdout 被重定向时，后者也可以用于显示警告和错误信息。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">sys</span>.<span style="color: #05a;">stderr</span>.<span style="color: #05a;">write</span><span style="color: Olive;">(</span><span style="color: #a11;">'Warning, log file not found starting a new one<span style="color: #000099; font-weight: bold;">\n</span>'</span><span style="color: Olive;">)</span><br/>
<span style="color: Teal;">Warning</span><span style="color: Gray;">,</span> log <span style="color: Teal;">file</span> <span style="color: Green;font-weight:bold;">not</span> found starting a <span style="color: #05a;">new</span> one<br/>
</div></div>&#13;
&#13;
<p>大多脚本的定向终止都使用 <span class="marked">sys.exit()</span>。</p>&#13;
<hr/>&#13;
<h2>字符串正则匹配</h2>&#13;
<p><strong>re</strong> 模块为高级字符串处理提供了正则表达式工具。对于复杂的匹配和处理，正则表达式提供了简洁、优化的解决方案:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">re</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">re</span>.<span style="color: #05a;">findall</span><span style="color: Olive;">(</span>r<span style="color: #a11;">'<span style="color: #000099; font-weight: bold;">\b</span>f[a-z]*'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'which foot or hand fell fastest'</span><span style="color: Olive;">)</span><br/>
<span style="color: Olive;">[</span><span style="color: #a11;">'foot'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'fell'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'fastest'</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">re</span>.<span style="color: #05a;">sub</span><span style="color: Olive;">(</span>r<span style="color: #a11;">'(<span style="color: #000099; font-weight: bold;">\b</span>[a-z]+) <span style="color: #000099; font-weight: bold;">\1</span>'</span><span style="color: Gray;">,</span> r<span style="color: #a11;">'<span style="color: #000099; font-weight: bold;">\1</span>'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'cat in the the hat'</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'cat in the hat'</span><br/>
</div></div>&#13;
&#13;
<p>如果只需要简单的功能，应该首先考虑字符串方法，因为它们非常简单，易于阅读和调试:&#13;
</p>&#13;
<pre>&#13;
&gt;&gt;&gt; 'tea for too'.replace('too', 'two')&#13;
'tea for two'&#13;
</pre>&#13;
<hr/>&#13;
<h2>数学 </h2>&#13;
<p><strong>math</strong> 模块为浮点运算提供了对底层 C 函数库的访问:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">math</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">math</span>.<span style="color: #05a;">cos</span><span style="color: Olive;">(</span><span style="color: #05a;">math</span>.<span style="color: #05a;">pi</span> / <span style="color: Maroon;">4</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">0.70710678118654757</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">math</span>.<span style="color: #05a;">log</span><span style="color: Olive;">(</span><span style="color: Maroon;">1024</span><span style="color: Gray;">,</span> <span style="color: Maroon;">2</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">10.0</span><br/>
</div></div>&#13;
&#13;
<p><strong>random</strong> 提供了生成随机数的工具。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">random</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">random</span>.<span style="color: #05a;">choice</span><span style="color: Olive;">(</span><span style="color: Olive;">[</span><span style="color: #a11;">'apple'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'pear'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'banana'</span><span style="color: Olive;">]</span><span style="color: Olive;">)</span><br/>
<span style="color: #a11;">'apple'</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">random</span>.<span style="color: #05a;">sample</span><span style="color: Olive;">(</span><span style="color: Teal;">range</span><span style="color: Olive;">(</span><span style="color: Maroon;">100</span><span style="color: Olive;">)</span><span style="color: Gray;">,</span> <span style="color: Maroon;">10</span><span style="color: Olive;">)</span>   <span style="color: #a50"># sampling without replacement</span><br/>
<span style="color: Olive;">[</span><span style="color: Maroon;">30</span><span style="color: Gray;">,</span> <span style="color: Maroon;">83</span><span style="color: Gray;">,</span> <span style="color: Maroon;">16</span><span style="color: Gray;">,</span> <span style="color: Maroon;">4</span><span style="color: Gray;">,</span> <span style="color: Maroon;">8</span><span style="color: Gray;">,</span> <span style="color: Maroon;">81</span><span style="color: Gray;">,</span> <span style="color: Maroon;">41</span><span style="color: Gray;">,</span> <span style="color: Maroon;">50</span><span style="color: Gray;">,</span> <span style="color: Maroon;">18</span><span style="color: Gray;">,</span> <span style="color: Maroon;">33</span><span style="color: Olive;">]</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">random</span>.<span style="color: #05a;">random</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>    <span style="color: #a50"># random float</span><br/>
<span style="color: Maroon;">0.17970987693706186</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: #05a;">random</span>.<span style="color: #05a;">randrange</span><span style="color: Olive;">(</span><span style="color: Maroon;">6</span><span style="color: Olive;">)</span>    <span style="color: #a50"># random integer chosen from range(6)</span><br/>
<span style="color: Maroon;">4</span><br/>
</div></div>&#13;
&#13;
<hr/>&#13;
<h2>访问&#13;
互联网</h2>&#13;
<p>有几个模块用于访问互联网以及处理网络通信协议。其中最简单的两个是用于处理从 urls 接收的数据的 urllib.request 以及用于发送电子邮件的 smtplib:&#13;
</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span> <span style="color: Green;font-weight:bold;">import</span> urlopen<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">for</span> line <span style="color: Green;font-weight:bold;">in</span> urlopen<span style="color: Olive;">(</span><span style="color: #a11;">'http://tycho.usno.navy.mil/cgi-bin/timer.pl'</span><span style="color: Olive;">)</span>:<br/>
...     <span style="color: #05a;">line</span> <span style="color: Gray;">=</span> line.<span style="color: #05a;">decode</span><span style="color: Olive;">(</span><span style="color: #a11;">'utf-8'</span><span style="color: Olive;">)</span>  <span style="color: #a50"># Decoding the binary data to text.</span><br/>
...     <span style="color: Green;font-weight:bold;">if</span> <span style="color: #a11;">'EST'</span> <span style="color: Green;font-weight:bold;">in</span> line <span style="color: Green;font-weight:bold;">or</span> <span style="color: #a11;">'EDT'</span> <span style="color: Green;font-weight:bold;">in</span> line:  <span style="color: #a50"># look for Eastern Time</span><br/>
...         <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>line<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Gray;">&lt;</span>BR<span style="color: Gray;">&gt;</span>Nov. <span style="color: Maroon;">25</span><span style="color: Gray;">,</span> <span style="color: Maroon;">09</span>:<span style="color: Maroon;">43</span>:<span style="color: Maroon;">32</span> PM EST<br/>
<br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">smtplib</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> server <span style="color: Gray;">=</span> <span style="color: #05a;">smtplib</span>.<span style="color: #05a;">SMTP</span><span style="color: Olive;">(</span><span style="color: #a11;">'localhost'</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> server.<span style="color: #05a;">sendmail</span><span style="color: Olive;">(</span><span style="color: #a11;">'soothsayer@example.org'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'jcaesar@example.org'</span><span style="color: Gray;">,</span><br/>
... <span style="color: #a11;">"""To: jcaesar@example.org<br/>
... From: soothsayer@example.org<br/>
...<br/>
... Beware the Ides of March.<br/>
... """</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> server.<span style="color: #05a;">quit</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>注意第二个例子需要本地有一个在运行的邮件服务器。</p>&#13;
<hr/>&#13;
<h2>日期和时间</h2>&#13;
<p><strong>datetime</strong> 模块为日期和时间处理同时提供了简单和复杂的方法。</p>&#13;
<p>支持日期和时间算法的同时，实现的重点放在更有效的处理和格式化输出。&#13;
</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">datetime</span><br/>
<br/>
<span style="color: #a50">#获取当前日期和时间</span><br/>
current_datetime <span style="color: Gray;">=</span> <span style="color: #05a;">datetime</span>.<span style="color: #05a;">datetime</span>.<span style="color: #05a;">now</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>current_datetime<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 获取当前日期</span><br/>
current_date <span style="color: Gray;">=</span> <span style="color: #05a;">datetime</span>.<span style="color: #05a;">date</span>.<span style="color: #05a;">today</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>current_date<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 格式化日期</span><br/>
formatted_datetime <span style="color: Gray;">=</span> current_datetime.<span style="color: #05a;">strftime</span><span style="color: Olive;">(</span><span style="color: #a11;">"%Y-%m-%d %H:%M:%S"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>formatted_datetime<span style="color: Olive;">)</span>  <span style="color: #a50"># 输出：2023-07-17 15:30:45</span><br/>
</div></div>&#13;
<p>输出结果为：</p>&#13;
&#13;
<pre>2023-07-17 18:37:56.036914&#13;
2023-07-17&#13;
2023-07-17 18:37:56</pre>&#13;
<p>该模块还支持时区处理:&#13;
</p>&#13;
<pre>&#13;
&gt;&gt;&gt; # 导入了 datetime 模块中的 date 类&#13;
&gt;&gt;&gt; from datetime import date&#13;
&gt;&gt;&gt; now = date.today()    # 当前日期&#13;
&gt;&gt;&gt; now&#13;
datetime.date(2023, 7, 17)&#13;
&gt;&gt;&gt; now.strftime("%m-%d-%y. %d %b %Y is a %A on the %d day of %B.")&#13;
'07-17-23. 17 Jul 2023 is a Monday on the 17 day of July.'&#13;
&#13;
&gt;&gt;&gt; # 创建了一个表示生日的日期对象&#13;
&gt;&gt;&gt; birthday = date(1964, 7, 31)&#13;
&gt;&gt;&gt; age = now - birthday   # 计算两个日期之间的时间差&#13;
&gt;&gt;&gt; age.days             # 变量age的days属性，表示时间差的天数&#13;
21535&#13;
</pre>&#13;
<hr/>&#13;
<h2>数据压缩</h2>&#13;
<p>以下模块直接支持通用的数据打包和压缩格式：zlib，gzip，bz2，zipfile，以及 tarfile。</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import zlib&#13;
&gt;&gt;&gt; s = b'witch which has which witches wrist watch'&#13;
&gt;&gt;&gt; len(s)&#13;
41&#13;
&gt;&gt;&gt; t = zlib.compress(s)&#13;
&gt;&gt;&gt; len(t)&#13;
37&#13;
&gt;&gt;&gt; zlib.decompress(t)&#13;
b'witch which has which witches wrist watch'&#13;
&gt;&gt;&gt; zlib.crc32(s)&#13;
226805979&#13;
</pre>&#13;
<hr/>&#13;
<h2>性能度量</h2>&#13;
<p>有些用户对了解解决同一问题的不同方法之间的性能差异很感兴趣。Python 提供了一个度量工具，为这些问题提供了直接答案。</p>&#13;
<p>例如，使用元组封装和拆封来交换元素看起来要比使用传统的方法要诱人的多,timeit 证明了现代的方法更快一些。</p>&#13;
<pre>&#13;
&gt;&gt;&gt; from timeit import Timer&#13;
&gt;&gt;&gt; Timer('t=a; a=b; b=t', 'a=1; b=2').timeit()&#13;
0.57535828626024577&#13;
&gt;&gt;&gt; Timer('a,b = b,a', 'a=1; b=2').timeit()&#13;
0.54962537085770791&#13;
</pre>&#13;
<p>相对于 timeit 的细粒度，:mod:profile 和 pstats 模块提供了针对更大代码块的时间度量工具。</p>&#13;
<hr/>&#13;
<h2>测试模块</h2>&#13;
<p>开发高质量软件的方法之一是为每一个函数开发测试代码，并且在开发过程中经常进行测试&#13;
</p>&#13;
<p>doctest模块提供了一个工具，扫描模块并根据程序中内嵌的文档字符串执行测试。&#13;
</p><p>测试构造如同简单的将它的输出结果剪切并粘贴到文档字符串中。&#13;
</p><p>通过用户提供的例子，它强化了文档，允许 doctest 模块确认代码的结果是否与文档一致:&#13;
</p>&#13;
<pre>&#13;
def average(values):&#13;
    """Computes the arithmetic mean of a list of numbers.&#13;
&#13;
    &gt;&gt;&gt; print(average([20, 30, 70]))&#13;
    40.0&#13;
    """&#13;
    return sum(values) / len(values)&#13;
&#13;
import doctest&#13;
doctest.testmod()   # 自动验证嵌入测试&#13;
</pre>&#13;
<p>unittest模块不像 doctest模块那么容易使用，不过它可以在一个独立的文件里提供一个更全面的测试集:&#13;
</p>&#13;
<pre>&#13;
import unittest&#13;
&#13;
class TestStatisticalFunctions(unittest.TestCase):&#13;
&#13;
    def test_average(self):&#13;
        self.assertEqual(average([20, 30, 70]), 40.0)&#13;
        self.assertEqual(round(average([1, 5, 7]), 1), 4.3)&#13;
        self.assertRaises(ZeroDivisionError, average, [])&#13;
        self.assertRaises(TypeError, average, 20, 30, 70)&#13;
&#13;
unittest.main() # Calling from the command line invokes all tests&#13;
</pre>&#13;
&#13;
<p>以上我们看到的只是 Python3 标准库中的一部分模块，还有很多其他模块可以在官方文档中查看完整的标准库文档：<a href="https://docs.python.org/zh-cn/3/library/index.html" rel="noopener" target="_blank">https://docs.python.org/zh-cn/3/library/index.html</a></p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>