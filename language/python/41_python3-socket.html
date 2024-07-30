<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 网络编程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 网络编程</h1>&#13;
<p>Python 提供了两个级别访问的网络服务。：</p>&#13;
<ul>&#13;
<li>低级别的网络服务支持基本的 Socket，它提供了标准的 BSD Sockets API，可以访问底层操作系统Socket接口的全部方法。</li>&#13;
<li>高级别的网络服务模块 SocketServer， 它提供了服务器中心类，可以简化网络服务器的开发。</li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>什么是 Socket?</h2>&#13;
<p>Socket又称"套接字"，应用程序通常通过"套接字"向网络发出请求或者应答网络请求，使主机间或者一台计算机上的进程间可以通讯。</p>&#13;
&#13;
<hr/><h2>socket()函数</h2>&#13;
<p>Python 中，我们用 socket() 函数来创建套接字，语法格式如下：</p>&#13;
<pre>&#13;
socket.socket([family[, type[, proto]]])&#13;
</pre>&#13;
<h3>参数</h3>&#13;
<ul>&#13;
<li>family: 套接字家族可以是 AF_UNIX 或者 AF_INET</li>&#13;
<li>type: 套接字类型可以根据是面向连接的还是非连接分为<code>SOCK_STREAM</code>或<code>SOCK_DGRAM</code></li>&#13;
<li>proto: 一般不填默认为0.</li>&#13;
</ul>&#13;
<h3>Socket 对象(内建)方法</h3>&#13;
<table class="reference"><thead>&#13;
<tr>&#13;
<th>函数</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
</thead><tbody>&#13;
<tr>&#13;
<td colspan="2">服务器端套接字</td>&#13;
&#13;
</tr>&#13;
<tr>&#13;
<td>s.bind()</td>&#13;
<td>绑定地址（host,port）到套接字， 在AF_INET下,以元组（host,port）的形式表示地址。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.listen()</td>&#13;
<td>开始TCP监听。backlog指定在拒绝连接之前，操作系统可以挂起的最大连接数量。该值至少为1，大部分应用程序设为5就可以了。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.accept()</td>&#13;
<td>被动接受TCP客户端连接,(阻塞式)等待连接的到来</td>&#13;
</tr>&#13;
<tr>&#13;
<td colspan="2">客户端套接字</td>&#13;
&#13;
</tr>&#13;
<tr>&#13;
<td>s.connect()</td>&#13;
<td>主动初始化TCP服务器连接，。一般address的格式为元组（hostname,port），如果连接出错，返回socket.error错误。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.connect_ex()</td>&#13;
<td>connect()函数的扩展版本,出错时返回出错码,而不是抛出异常</td>&#13;
</tr>&#13;
<tr>&#13;
<td colspan="2">公共用途的套接字函数</td>&#13;
&#13;
</tr>&#13;
<tr>&#13;
<td>s.recv()</td>&#13;
<td>接收TCP数据，数据以字符串形式返回，bufsize指定要接收的最大数据量。flag提供有关消息的其他信息，通常可以忽略。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.send()</td>&#13;
<td>发送TCP数据，将string中的数据发送到连接的套接字。返回值是要发送的字节数量，该数量可能小于string的字节大小。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.sendall()</td>&#13;
<td>完整发送TCP数据。将string中的数据发送到连接的套接字，但在返回之前会尝试发送所有数据。成功返回None，失败则抛出异常。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.recvfrom()</td>&#13;
<td>接收UDP数据，与recv()类似，但返回值是（data,address）。其中data是包含接收数据的字符串，address是发送数据的套接字地址。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.sendto()</td>&#13;
<td>发送UDP数据，将数据发送到套接字，address是形式为（ipaddr，port）的元组，指定远程地址。返回值是发送的字节数。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.close()</td>&#13;
<td>关闭套接字</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.getpeername()</td>&#13;
<td>返回连接套接字的远程地址。返回值通常是元组（ipaddr,port）。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.getsockname()</td>&#13;
<td>返回套接字自己的地址。通常是一个元组(ipaddr,port)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.setsockopt(level,optname,value)</td>&#13;
<td>设置给定套接字选项的值。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.getsockopt(level,optname[.buflen])</td>&#13;
<td>返回套接字选项的值。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.settimeout(timeout)</td>&#13;
<td>设置套接字操作的超时期，timeout是一个浮点数，单位是秒。值为None表示没有超时期。一般，超时期应该在刚创建套接字时设置，因为它们可能用于连接的操作（如connect()）</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.gettimeout()</td>&#13;
<td>返回当前超时期的值，单位是秒，如果没有设置超时期，则返回None。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.fileno()</td>&#13;
<td>返回套接字的文件描述符。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.setblocking(flag)</td>&#13;
<td>如果 flag 为 False，则将套接字设为非阻塞模式，否则将套接字设为阻塞模式（默认值）。非阻塞模式下，如果调用 recv() 没有发现任何数据，或 send() 调用无法立即发送数据，那么将引起 socket.error 异常。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>s.makefile()</td>&#13;
<td>创建一个与该套接字相关连的文件</td>&#13;
</tr>&#13;
</tbody></table>&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>简单实例</h2>&#13;
<h3>服务端</h3>&#13;
<p>我们使用 socket 模块的 <b>socket</b> 函数来创建一个 socket 对象。socket 对象可以通过调用其他函数来设置一个 socket 服务。</p>&#13;
<p>现在我们可以通过调用 <b>bind(hostname, port)</b> 函数来指定服务的 <i>port(端口)</i>。</p>&#13;
<p>接着，我们调用 socket 对象的 <i>accept</i> 方法。该方法等待客户端的连接，并返回 <i>connection</i> 对象，表示已连接到客户端。</p>&#13;
<p>完整代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<span style="color: #a50"># 文件名：server.py</span><br/>
<br/>
<span style="color: #a50"># 导入 socket、sys 模块</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">socket</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">sys</span><br/>
<br/>
<span style="color: #a50"># 创建 socket 对象</span><br/>
serversocket <span style="color: Gray;">=</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">socket</span><span style="color: Olive;">(</span><br/>
            <span style="color: #05a;">socket</span>.<span style="color: #05a;">AF_INET</span><span style="color: Gray;">,</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">SOCK_STREAM</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 获取本地主机名</span><br/>
host <span style="color: Gray;">=</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">gethostname</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
port <span style="color: Gray;">=</span> <span style="color: Maroon;">9999</span><br/>
<br/>
<span style="color: #a50"># 绑定端口号</span><br/>
serversocket.<span style="color: #05a;">bind</span><span style="color: Olive;">(</span><span style="color: Olive;">(</span>host<span style="color: Gray;">,</span> port<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 设置最大连接数，超过后排队</span><br/>
serversocket.<span style="color: #05a;">listen</span><span style="color: Olive;">(</span><span style="color: Maroon;">5</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">while</span> <span style="color: Teal;">True</span>:<br/>
    <span style="color: #a50"># 建立客户端连接</span><br/>
    clientsocket<span style="color: Gray;">,</span>addr <span style="color: Gray;">=</span> serversocket.<span style="color: #05a;">accept</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>      <br/>
<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: #a11;">"连接地址: %s"</span> % <span style="color: Teal;">str</span><span style="color: Olive;">(</span>addr<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
    <br/>
    msg<span style="color: Gray;">=</span><span style="color: #a11;">'欢迎访问菜鸟教程！'</span>+ <span style="color: #a11;">"<span style="color: #000099; font-weight: bold;">\r</span><span style="color: #000099; font-weight: bold;">\n</span>"</span><br/>
    clientsocket.<span style="color: #05a;">send</span><span style="color: Olive;">(</span>msg.<span style="color: #05a;">encode</span><span style="color: Olive;">(</span><span style="color: #a11;">'utf-8'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
    clientsocket.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<h3>客户端</h3>&#13;
<p>接下来我们写一个简单的客户端实例连接到以上创建的服务。端口号为 9999。</p>&#13;
<p><b>socket.connect(hostname, port )</b> 方法打开一个 TCP 连接到主机为 <i>hostname</i> 端口为 <i>port</i> 的服务商。连接后我们就可以从服务端获取数据，记住，操作完成后需要关闭连接。</p>&#13;
<p>完整代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<span style="color: #a50"># 文件名：client.py</span><br/>
<br/>
<span style="color: #a50"># 导入 socket、sys 模块</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">socket</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">sys</span><br/>
<br/>
<span style="color: #a50"># 创建 socket 对象</span><br/>
s <span style="color: Gray;">=</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">socket</span><span style="color: Olive;">(</span><span style="color: #05a;">socket</span>.<span style="color: #05a;">AF_INET</span><span style="color: Gray;">,</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">SOCK_STREAM</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 获取本地主机名</span><br/>
host <span style="color: Gray;">=</span> <span style="color: #05a;">socket</span>.<span style="color: #05a;">gethostname</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 设置端口号</span><br/>
port <span style="color: Gray;">=</span> <span style="color: Maroon;">9999</span><br/>
<br/>
<span style="color: #a50"># 连接服务，指定主机和端口</span><br/>
s.<span style="color: #05a;">connect</span><span style="color: Olive;">(</span><span style="color: Olive;">(</span>host<span style="color: Gray;">,</span> port<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 接收小于 1024 字节的数据</span><br/>
msg <span style="color: Gray;">=</span> s.<span style="color: #05a;">recv</span><span style="color: Olive;">(</span><span style="color: Maroon;">1024</span><span style="color: Olive;">)</span><br/>
<br/>
s.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>msg.<span style="color: #05a;">decode</span><span style="color: Olive;">(</span><span style="color: #a11;">'utf-8'</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>现在我们打开两个终端，第一个终端执行 server.py 文件：</p>&#13;
<pre>$ python3 server.py</pre>&#13;
<p>第二个终端执行 client.py 文件：</p>&#13;
<pre>&#13;
$ python3 client.py &#13;
欢迎访问菜鸟教程！&#13;
&#13;
</pre>&#13;
<p>这时我们再打开第一个终端，就会看到有以下信息输出：</p>&#13;
<pre>&#13;
连接地址： ('192.168.0.118', 33397)&#13;
</pre>&#13;
<hr/>&#13;
<h2>Python Internet 模块</h2>&#13;
<p>以下列出了 Python 网络编程的一些重要模块：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:10%">协议</th><th style="width:30%">功能用处</th><th style="width:15%">端口号</th><th>Python 模块</th>&#13;
</tr>&#13;
<tr><td>HTTP</td><td>网页访问</td><td>80</td><td>httplib, urllib, xmlrpclib</td></tr>&#13;
<tr><td>NNTP</td><td>阅读和张贴新闻文章，俗称为"帖子"</td><td>119</td><td>nntplib</td></tr>&#13;
<tr><td>FTP</td><td>文件传输</td><td>20</td><td>ftplib, urllib</td></tr>&#13;
<tr><td>SMTP</td><td>发送邮件</td><td>25</td><td>smtplib</td></tr>&#13;
<tr><td>POP3</td><td>接收邮件</td><td>110</td><td>poplib</td></tr>&#13;
<tr><td>IMAP4</td><td>获取邮件</td><td>143</td><td>imaplib</td></tr>&#13;
<tr><td>Telnet</td><td>命令行</td><td>23</td><td>telnetlib</td></tr>&#13;
<tr><td>Gopher</td><td>信息查找</td><td>70</td><td>gopherlib, urllib</td></tr>&#13;
</tbody></table>&#13;
&#13;
<p>更多内容可以参阅官网的 <a href="https://docs.python.org/3.0/library/socket.html" title="Python Socket 库" target="_blank" rel="noopener noreferrer">Python Socket Library and Modules</a>。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>