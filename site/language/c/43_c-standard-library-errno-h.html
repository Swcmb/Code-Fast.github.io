<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <errno.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;errno.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p>C 标准库的 <b>errno.h</b> 头文件定义了整数变量 <b>errno</b>，它是通过系统调用设置的，在错误事件中的某些库函数表明了什么发生了错误。该宏扩展为类型为 int 的可更改的左值，因此它可以被一个程序读取和修改。</p>&#13;
<p><code>&lt;errno.h&gt;</code> 是 C 标准库中的一个头文件，提供了一种在程序中报告和处理错误的机制。这个头文件定义了宏和变量，用于指示和描述运行时错误的类型。</p>&#13;
&#13;
<p><b>errno.h</b> 头文件定义了一系列表示不同错误代码的宏，这些宏应扩展为类型为 <b>int</b> 的整数常量表达式。</p>&#13;
<p><code>errno</code> 是一个全局变量，用于存储最近发生的错误代码。这个变量的类型为 <code>int</code>。当一个库函数发生错误时，它通常会设置 <code>errno</code> 以指示错误类型。</p>&#13;
<p>例如，在文件操作中，如果 <code>fopen</code> 函数因为文件不存在而失败，它会将 <code>errno</code> 设置为 <code>ENOENT</code>。</p>&#13;
<h3>常用错误码</h3>&#13;
<p>以下是一些常见的错误码，它们在 <code>&lt;errno.h&gt;</code> 中定义为宏：</p>&#13;
<ul><li><code>EPERM</code>：操作不允许</li><li><code>ENOENT</code>：没有这样的文件或目录</li><li><code>ESRCH</code>：没有这样的进程</li><li><code>EINTR</code>：中断的系统调用</li><li><code>EIO</code>：输入/输出错误</li><li><code>ENXIO</code>：没有这样的设备或地址</li><li><code>E2BIG</code>：参数列表太长</li><li><code>ENOMEM</code>：内存不足</li><li><code>EACCES</code>：权限被拒绝</li><li><code>EFAULT</code>：坏的地址</li><li><code>EBUSY</code>：资源忙</li><li><code>EEXIST</code>：文件已存在</li><li><code>EXDEV</code>：跨设备链接</li><li><code>ENODEV</code>：没有这样的设备</li><li><code>ENOTDIR</code>：不是一个目录</li><li><code>EISDIR</code>：是一个目录</li><li><code>EINVAL</code>：无效的参数</li><li><code>ENFILE</code>：系统文件表溢出</li><li><code>EMFILE</code>：打开的文件过多</li><li><code>ENOTTY</code>：不是终端设备</li><li><code>ETXTBSY</code>：文本文件忙</li><li><code>EFBIG</code>：文件过大</li><li><code>ENOSPC</code>：设备上没有空间</li><li><code>ESPIPE</code>：非法的寻址</li><li><code>EROFS</code>：只读文件系统</li><li><code>EMLINK</code>：链接过多</li><li><code>EPIPE</code>：管道破裂</li></ul>&#13;
<h3>使用示例</h3>&#13;
<p>&#13;
以下是一个使用 errno 的简单示例，演示如何处理文件打开错误：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #060;">#include &lt;errno.h&gt;</span><br/>
<span style="color: #060;">#include &lt;string.h&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">FILE</span> <span style="color: #000040;">*</span>file <span style="color: #000080;">=</span> <span style="color: #05a;">fopen</span><span style="color: #008000;">(</span><span style="color: #a11;">"nonexistent_file.txt"</span>, <span style="color: #a11;">"r"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>file <span style="color: #000080;">==</span> <span style="color: #05a;">NULL</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"Error opening file: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span>, <span style="color: #05a;">strerror</span><span style="color: #008000;">(</span><span style="color: #05a;">errno</span><span style="color: #008000;">)</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
        <span style="color: #05a;">return</span> <span style="color: #0000dd;">1</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 文件处理代码</span><br/>
    <span style="color: #05a;">fclose</span><span style="color: #008000;">(</span>file<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>在这个示例中，如果 <code>fopen</code> 函数失败，<code>errno</code> 将被设置为相应的错误码。<code>strerror</code> 函数用于将 <code>errno</code> 转换为人类可读的错误消息。</p><h3>注意事项</h3><ol><li><strong>线程安全</strong>：在多线程程序中，<code>errno</code> 通常实现为线程局部存储（Thread-Local Storage, TLS），以确保每个线程有独立的错误码。</li><li><strong>初始值</strong>：在成功调用的情况下，库函数通常不会修改 <code>errno</code> 的值。因此在检查错误之前，应确保 <code>errno</code> 被设置为 0。</li><li><strong>错误码范围</strong>：不同的操作系统和 C 标准库实现可能会定义额外的错误码。程序应避免依赖特定错误码的数值。</li></ol><h3>错误处理建议</h3><ol><li><strong>检查返回值</strong>：在调用可能失败的函数时，总是检查其返回值。</li><li><strong>设定 <code>errno</code> 为 0</strong>：在调用一个函数前，可以将 <code>errno</code> 设定为 0，以便在调用后检查 <code>errno</code> 是否被修改。</li><li><strong>使用 <code>strerror</code></strong>：通过 <code>strerror</code> 将 <code>errno</code> 转换为可读的字符串，便于调试和日志记录。</li></ol><p>总之，<code>&lt;errno.h&gt;</code> 提供了一种标准化的方式来报告和处理程序中的错误，使得错误处理代码更为一致和可维护。</p>&#13;
<h2>库宏</h2>&#13;
<p>下面列出了头文件 errno.h 中定义的宏：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-macro-errno.html">extern int errno</a><br/>这是通过系统调用设置的宏，在错误事件中的某些库函数表明了什么发生了错误。</td></tr>&#13;
<tr><td>2</td><td><a href="c-macro-edom.html">EDOM Domain Error</a><br/>这个宏表示一个域错误，它在输入参数超出数学函数定义的域时发生，errno 被设置为 EDOM。</td></tr>&#13;
<tr><td>3</td><td><a href="c-macro-erange.html">ERANGE Range Error</a><br/>这个宏表示一个范围错误，它在输入参数超出数学函数定义的范围时发生，errno 被设置为 ERANGE。</td></tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>