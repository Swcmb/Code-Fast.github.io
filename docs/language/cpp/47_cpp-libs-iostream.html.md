<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准输入输出 -- <iostream></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准输入输出 -- &lt;iostream&gt;</h1>&#13;
<p><code>&lt;iostream&gt;</code>库是 C++ 标准库中用于输入输出操作的头文件。</p><p>&lt;iostream&gt; 定义了几个常用的流类和操作符，允许程序与标准输入输出设备（如键盘和屏幕）进行交互。</p><p>以下是<code>&lt;iostream&gt;</code>库的详细使用说明，包括其主要类和常见用法示例。</p>&#13;
<h3>主要类</h3>&#13;
<ul>&#13;
    <li><code>std::istream</code>：用于输入操作的抽象基类。</li>&#13;
    <li><code>std::ostream</code>：用于输出操作的抽象基类。</li>&#13;
    <li><code>std::iostream</code>：继承自<code>std::istream</code>和<code>std::ostream</code>，用于同时进行输入和输出操作。</li>&#13;
    <li><code>std::cin</code>：标准输入流对象，通常与键盘关联。</li>&#13;
    <li><code>std::cout</code>：标准输出流对象，通常与屏幕关联。</li>&#13;
    <li><code>std::cerr</code>：标准错误输出流对象，不带缓冲，通常与屏幕关联。</li>&#13;
    <li><code>std::clog</code>：标准日志流对象，带缓冲，通常与屏幕关联。</li>&#13;
</ul>&#13;
<h3>常用操作符</h3>&#13;
<ul>&#13;
    <li><code>&gt;&gt;</code>：输入操作符，从输入流读取数据。</li>&#13;
    <li><code>&lt;&lt;</code>：输出操作符，将数据写入输出流。</li>&#13;
</ul>&#13;
<h3>基本用法</h3>&#13;
<p>标准输入和输出:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> age<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> name<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 使用 std::cout 输出到屏幕</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Enter your name: "</span><span style="color: #008080;">;</span><br/>
    <span style="color: #666666;">// 使用 std::cin 从键盘读取输入</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cin</span> <span style="color: #000080;">&gt;&gt;</span> name<span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Enter your age: "</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cin</span> <span style="color: #000080;">&gt;&gt;</span> age<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 输出读取到的数据</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello, "</span> <span style="color: #000080;">&lt;&lt;</span> name <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"! You are "</span> <span style="color: #000080;">&lt;&lt;</span> age <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">" years old."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p>标准错误输出:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cerr</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"An error occurred!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p>标准日志输出:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">clog</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"This is a log message."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p>格式化输出:</p>&#13;
<p>使用<code>&lt;iomanip&gt;</code>库可以对输出进行格式化，例如设置宽度、精度和对齐方式。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">double</span> pi <span style="color: #000080;">=</span> <span style="color:#800080;">3.14159</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 设置输出精度</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setprecision</span><span style="color: #008000;">(</span><span style="color: #0000dd;">3</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> pi <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 设置输出宽度和对齐方式</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setw</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">left</span> <span style="color: #000080;">&lt;&lt;</span> pi <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setw</span><span style="color: #008000;">(</span><span style="color: #0000dd;">10</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">right</span> <span style="color: #000080;">&lt;&lt;</span> pi <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<h3>流的状态检查:</h3>&#13;
<p>可以检查输入输出流的状态，以确定操作是否成功。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> num<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Enter a number: "</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cin</span> <span style="color: #000080;">&gt;&gt;</span> num<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 检查输入操作是否成功</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #05a;">cin</span>.<span style="color: #007788;">fail</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cerr</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Invalid input!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"You entered: "</span> <span style="color: #000080;">&lt;&lt;</span> num <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<h3>处理字符串输入</h3>&#13;
<p>使用<code>std::getline</code>函数可以读取包含空格的整行输入。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;string&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> fullName<span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Enter your full name: "</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">getline</span><span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #05a;">cin</span>, fullName<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Hello, "</span> <span style="color: #000080;">&lt;&lt;</span> fullName <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"!"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p>以上示例展示了<code>&lt;iostream&gt;</code>库的基本用法和常见操作，帮助你在C++程序中进行输入输出处理。</p>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>