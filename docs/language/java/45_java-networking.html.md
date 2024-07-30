<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 网络编程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 网络编程</h1>&#13;
<p>&#13;
网络编程是指编写运行在多个设备（计算机）的程序，这些设备都通过网络连接起来。</p><p>&#13;
java.net 包中 J2SE 的 API 包含有类和接口，它们提供低层次的通信细节。你可以直接使用这些类和接口，来专注于解决问题，而不用关注通信细节。</p><p>&#13;
java.net 包中提供了两种常见的网络协议的支持：</p>&#13;
<ul>&#13;
	<li><p><strong>TCP</strong>：TCP（英语：Transmission Control Protocol，传输控制协议） 是一种面向连接的、可靠的、基于字节流的传输层通信协议，TCP 层是位于 IP 层之上，应用层之下的中间层。TCP 保障了两个应用程序之间的可靠通信。通常用于互联网协议，被称 TCP / IP。</p></li>&#13;
	<li><p><strong>UDP</strong>：UDP （英语：User Datagram Protocol，用户数据报协议），位于 OSI 模型的传输层。一个无连接的协议。提供了应用程序之间要发送数据的数据报。由于UDP缺乏可靠性且属于无连接协议，所以应用程序通常必须容许一些丢失、错误或重复的数据包。</p></li>&#13;
</ul>&#13;
<p>本教程主要讲解以下两个主题。</p>&#13;
<ul>&#13;
	<li><p><strong>Socket 编程</strong>：这是使用最广泛的网络概念，它已被解释地非常详细。</p></li>&#13;
	<li><p><strong>URL 处理</strong>：这部分会在另外的篇幅里讲，点击这里更详细地了解在 <a href="/java/java-url-processing.html" title="java url处理" target="_blank" rel="noopener">Java 语言中的 URL 处理</a>。</p></li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>&#13;
Socket 编程&#13;
</h2>&#13;
<p>&#13;
套接字使用TCP提供了两台计算机之间的通信机制。 客户端程序创建一个套接字，并尝试连接服务器的套接字。</p><p>&#13;
当连接建立时，服务器会创建一个 Socket 对象。客户端和服务器现在可以通过对 Socket 对象的写入和读取来进行通信。</p><p>&#13;
java.net.Socket 类代表一个套接字，并且 java.net.ServerSocket 类为服务器程序提供了一种来监听客户端，并与他们建立连接的机制。</p><p>&#13;
以下步骤在两台计算机之间使用套接字建立TCP连接时会出现：</p>&#13;
<ul>&#13;
	<li><p>服务器实例化一个 ServerSocket 对象，表示通过服务器上的端口通信。</p></li>&#13;
	<li><p>服务器调用 ServerSocket 类的 accept() 方法，该方法将一直等待，直到客户端连接到服务器上给定的端口。</p></li>&#13;
	<li><p>服务器正在等待时，一个客户端实例化一个 Socket 对象，指定服务器名称和端口号来请求连接。</p></li>&#13;
	<li><p>Socket 类的构造函数试图将客户端连接到指定的服务器和端口号。如果通信被建立，则在客户端创建一个 Socket 对象能够与服务器进行通信。</p></li>&#13;
	<li><p>在服务器端，accept() 方法返回服务器上一个新的 socket 引用，该 socket 连接到客户端的 socket。</p></li>&#13;
</ul><p>&#13;
连接建立后，通过使用 I/O 流在进行通信，每一个socket都有一个输出流和一个输入流，客户端的输出流连接到服务器端的输入流，而客户端的输入流连接到服务器端的输出流。&#13;
</p><p>TCP 是一个双向的通信协议，因此数据可以通过两个数据流在同一时间发送。以下是一些类提供的一套完整的有用的方法来实现 socket。&#13;
</p>&#13;
<hr/>&#13;
<h2>&#13;
ServerSocket 类的方法</h2>&#13;
<p>&#13;
&#13;
服务器应用程序通过使用 java.net.ServerSocket 类以获取一个端口,并且侦听客户端请求。</p><p>&#13;
ServerSocket 类有四个构造方法：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<td>&#13;
				<strong>序号</strong></td>&#13;
			<td style="text-align: center;">&#13;
				<strong>方法描述</strong></td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public ServerSocket(int port) throws IOException</strong><br/>&#13;
				创建绑定到特定端口的服务器套接字。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public ServerSocket(int port, int backlog) throws IOException</strong><br/>&#13;
				利用指定的 backlog 创建服务器套接字并将其绑定到指定的本地端口号。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public ServerSocket(int port, int backlog, InetAddress address) throws IOException</strong><br/>&#13;
				使用指定的端口、侦听 backlog 和要绑定到的本地 IP 地址创建服务器。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public ServerSocket() throws IOException</strong><br/>&#13;
				创建非绑定服务器套接字。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>&#13;
创建非绑定服务器套接字。 如果 ServerSocket 构造方法没有抛出异常，就意味着你的应用程序已经成功绑定到指定的端口，并且侦听客户端请求。&#13;
</p><p>这里有一些 ServerSocket 类的常用方法：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<td>&#13;
				<strong>序号</strong></td>&#13;
			<td style="text-align: center;">&#13;
				<strong>方法描述</strong></td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public int getLocalPort()</strong><br/>&#13;
				  返回此套接字在其上侦听的端口。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public Socket accept() throws IOException</strong><br/>&#13;
				侦听并接受到此套接字的连接。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public void setSoTimeout(int timeout)</strong><br/>&#13;
				 通过指定超时值启用/禁用 SO_TIMEOUT，以毫秒为单位。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public void bind(SocketAddress host, int backlog)</strong><br/>&#13;
				将 ServerSocket 绑定到特定地址（IP 地址和端口号）。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/><h2>&#13;
Socket 类的方法</h2>&#13;
<p>java.net.Socket 类代表客户端和服务器都用来互相沟通的套接字。客户端要获取一个 Socket 对象通过实例化 ，而 服务器获得一个 Socket 对象则通过 accept() 方法的返回值。&#13;
</p><p>Socket 类有五个构造方法.</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<td>&#13;
				<strong>序号</strong></td>&#13;
			<td style="text-align: center;">&#13;
				<strong>方法描述</strong></td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public Socket(String host, int port) throws UnknownHostException, IOException.</strong><br/>&#13;
				创建一个流套接字并将其连接到指定主机上的指定端口号。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public Socket(InetAddress host, int port) throws IOException</strong><br/>&#13;
				创建一个流套接字并将其连接到指定 IP 地址的指定端口号。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public Socket(String host, int port, InetAddress localAddress, int localPort) throws IOException.</strong><br/>&#13;
				创建一个套接字并将其连接到指定远程主机上的指定远程端口。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public Socket(InetAddress host, int port, InetAddress localAddress, int localPort) throws IOException.</strong><br/>&#13;
				创建一个套接字并将其连接到指定远程地址上的指定远程端口。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>public Socket()</strong><br/>&#13;
				通过系统默认类型的 SocketImpl 创建未连接套接字</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>当 Socket 构造方法返回，并没有简单的实例化了一个 Socket 对象，它实际上会尝试连接到指定的服务器和端口。</p>&#13;
<p>&#13;
下面列出了一些感兴趣的方法，注意客户端和服务器端都有一个 Socket 对象，所以无论客户端还是服务端都能够调用这些方法。&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<td>&#13;
				<strong>序号</strong></td>&#13;
			<td style="text-align: center;">&#13;
				<strong>方法描述</strong></td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public void connect(SocketAddress host, int timeout) throws IOException</strong><br/>&#13;
				将此套接字连接到服务器，并指定一个超时值。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public InetAddress getInetAddress()</strong><br/>&#13;
				 返回套接字连接的地址。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public int getPort()</strong><br/>&#13;
				返回此套接字连接到的远程端口。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public int getLocalPort()</strong><br/>&#13;
				返回此套接字绑定到的本地端口。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>public SocketAddress getRemoteSocketAddress()</strong><br/>&#13;
				返回此套接字连接的端点的地址，如果未连接则返回 null。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				6</td>&#13;
			<td>&#13;
				<strong>public InputStream getInputStream() throws IOException</strong><br/>&#13;
				返回此套接字的输入流。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				7</td>&#13;
			<td>&#13;
				<strong>public OutputStream getOutputStream() throws IOException</strong><br/>&#13;
				返回此套接字的输出流。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				8</td>&#13;
			<td>&#13;
				<strong>public void close() throws IOException</strong><br/>&#13;
				关闭此套接字。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/>&#13;
<h2>&#13;
InetAddress 类的方法&#13;
</h2>&#13;
<p>这个类表示互联网协议(IP)地址。下面列出了 Socket 编程时比较有用的方法：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<td>&#13;
				<strong>序号</strong></td>&#13;
			<td style="text-align: center;">&#13;
				<strong>方法描述</strong></td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>static InetAddress getByAddress(byte[] addr)</strong><br/>&#13;
				在给定原始 IP 地址的情况下，返回 InetAddress 对象。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>static InetAddress getByAddress(String host, byte[] addr)</strong><br/>&#13;
				根据提供的主机名和 IP 地址创建 InetAddress。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>static InetAddress getByName(String host)</strong><br/>&#13;
				在给定主机名的情况下确定主机的 IP 地址。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>String getHostAddress() </strong><br/>&#13;
				返回 IP 地址字符串（以文本表现形式）。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>String getHostName() </strong><br/>&#13;
				 获取此 IP 地址的主机名。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				6</td>&#13;
			<td>&#13;
				<strong>static InetAddress getLocalHost()</strong><br/>&#13;
				返回本地主机。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				7</td>&#13;
			<td>&#13;
				<strong>String toString()</strong><br/>&#13;
				将此 IP 地址转换为 String。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/>&#13;
<h2>&#13;
Socket 客户端实例</h2>&#13;
<p>如下的 GreetingClient 是一个客户端程序，该程序通过 socket 连接到服务器并发送一个请求，然后等待一个响应。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">GreetingClient.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 GreetingClient.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">net</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">GreetingClient</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">serverName</span><span class="hl-code"> = </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">port</span><span class="hl-code"> = </span><span class="hl-identifier">Integer</span><span class="hl-code">.</span><span class="hl-identifier">parseInt</span><span class="hl-brackets">(</span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">连接到主机：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">serverName</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> ，端口号：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">port</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">Socket</span><span class="hl-code"> </span><span class="hl-identifier">client</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Socket</span><span class="hl-brackets">(</span><span class="hl-identifier">serverName</span><span class="hl-code">, </span><span class="hl-identifier">port</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">远程主机地址：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">client</span><span class="hl-code">.</span><span class="hl-identifier">getRemoteSocketAddress</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">OutputStream</span><span class="hl-code"> </span><span class="hl-identifier">outToServer</span><span class="hl-code"> = </span><span class="hl-identifier">client</span><span class="hl-code">.</span><span class="hl-identifier">getOutputStream</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">DataOutputStream</span><span class="hl-code"> </span><span class="hl-identifier">out</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DataOutputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">outToServer</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">writeUTF</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Hello from </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">client</span><span class="hl-code">.</span><span class="hl-identifier">getLocalSocketAddress</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">InputStream</span><span class="hl-code"> </span><span class="hl-identifier">inFromServer</span><span class="hl-code"> = </span><span class="hl-identifier">client</span><span class="hl-code">.</span><span class="hl-identifier">getInputStream</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">DataInputStream</span><span class="hl-code"> </span><span class="hl-identifier">in</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DataInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">inFromServer</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">服务器响应： </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">in</span><span class="hl-code">.</span><span class="hl-identifier">readUTF</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">client</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/><h2>&#13;
Socket 服务端实例&#13;
</h2>&#13;
<p>&#13;
如下的GreetingServer 程序是一个服务器端应用程序，使用 Socket 来监听一个指定的端口。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">GreetingServer.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 GreetingServer.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">net</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">GreetingServer</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Thread</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">ServerSocket</span><span class="hl-code"> </span><span class="hl-identifier">serverSocket</span><span class="hl-code">;
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">GreetingServer</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">port</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">serverSocket</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">ServerSocket</span><span class="hl-brackets">(</span><span class="hl-identifier">port</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">serverSocket</span><span class="hl-code">.</span><span class="hl-identifier">setSoTimeout</span><span class="hl-brackets">(</span><span class="hl-number">10000</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-reserved">true</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">try</span><span class="hl-code">
         </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">等待远程连接，端口号为：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">serverSocket</span><span class="hl-code">.</span><span class="hl-identifier">getLocalPort</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">Socket</span><span class="hl-code"> </span><span class="hl-identifier">server</span><span class="hl-code"> = </span><span class="hl-identifier">serverSocket</span><span class="hl-code">.</span><span class="hl-identifier">accept</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">远程主机地址：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">getRemoteSocketAddress</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">DataInputStream</span><span class="hl-code"> </span><span class="hl-identifier">in</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DataInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">getInputStream</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">in</span><span class="hl-code">.</span><span class="hl-identifier">readUTF</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">DataOutputStream</span><span class="hl-code"> </span><span class="hl-identifier">out</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DataOutputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">getOutputStream</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">writeUTF</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">谢谢连接我：</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">getLocalSocketAddress</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-string">Goodbye!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">SocketTimeoutException</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-brackets">)</span><span class="hl-code">
         </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Socket timed out!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">
         </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">port</span><span class="hl-code"> = </span><span class="hl-identifier">Integer</span><span class="hl-code">.</span><span class="hl-identifier">parseInt</span><span class="hl-brackets">(</span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">Thread</span><span class="hl-code"> </span><span class="hl-identifier">t</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">GreetingServer</span><span class="hl-brackets">(</span><span class="hl-identifier">port</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">t</span><span class="hl-code">.</span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>编译以上两个 java 文件代码，并执行以下命令来启动服务，使用端口号为 6066：</p>&#13;
<pre>&#13;
$ javac GreetingServer.java &#13;
$ java GreetingServer 6066&#13;
等待远程连接，端口号为：6066...&#13;
</pre><p>&#13;
新开一个命令窗口，执行以上命令来开启客户端：</p>&#13;
<pre>&#13;
$ javac GreetingClient.java &#13;
$ java GreetingClient localhost 6066&#13;
连接到主机：localhost ，端口号：6066&#13;
远程主机地址：localhost/127.0.0.1:6066&#13;
服务器响应： 谢谢连接我：/127.0.0.1:6066&#13;
Goodbye!&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>