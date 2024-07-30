<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ Web 编程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">Web 编程</span></h1>&#13;
&#13;
<h2>什么是 CGI？</h2>&#13;
<ul class="list">&#13;
<li>公共网关接口（CGI），是一套标准，定义了信息是如何在 Web 服务器和客户端脚本之间进行交换的。</li>&#13;
<li>CGI 规范目前是由 NCSA 维护的，NCSA 定义 CGI 如下：</li>&#13;
<li>公共网关接口（CGI），是一种用于外部网关程序与信息服务器（如 HTTP 服务器）对接的接口标准。</li>&#13;
<li>目前的版本是 CGI/1.1，CGI/1.2 版本正在推进中。</li>&#13;
</ul>&#13;
&#13;
<h2>Web 浏览</h2>&#13;
<p>为了更好地了解 CGI 的概念，让我们点击一个超链接，浏览一个特定的网页或 URL，看看会发生什么。</p>&#13;
<ul class="list">&#13;
<li>您的浏览器联系上 HTTP Web 服务器，并请求 URL，即文件名。</li>&#13;
<li>Web 服务器将解析 URL，并查找文件名。如果找到请求的文件，Web 服务器会把文件发送回浏览器，否则发送一条错误消息，表明您请求了一个错误的文件。</li>&#13;
<li>Web 浏览器从 Web 服务器获取响应，并根据接收到的响应来显示文件或错误消息。</li>&#13;
</ul>&#13;
<p>然而，以这种方式搭建起来的 HTTP 服务器，不管何时请求目录中的某个文件，HTTP 服务器发送回来的不是该文件，而是以程序形式执行，并把执行产生的输出发送回浏览器显示出来。</p>&#13;
<p>公共网关接口（CGI），是使得应用程序（称为 CGI 程序或 CGI 脚本）能够与 Web 服务器以及客户端进行交互的标准协议。这些 CGI 程序可以用 Python、PERL、Shell、C 或 C++ 等进行编写。</p>&#13;
&#13;
<h2>CGI 架构图</h2>&#13;
<p>下图演示了 CGI 的架构：</p>&#13;
<img decoding="async" src="/wp-content/uploads/2015/05/cgiarch.gif" alt="CGI 架构"/>&#13;
&#13;
<h2>Web 服务器配置</h2>&#13;
<p class="alignment">在您进行 CGI 编程之前，请确保您的 Web 服务器支持 CGI，并已配置成可以处理 CGI 程序。所有由 HTTP 服务器执行的 CGI 程序，都必须在预配置的目录中。该目录称为 CGI 目录，按照惯例命名为 /var/www/cgi-bin。虽然 CGI 文件是 C++ 可执行文件，但是按照惯例它的扩展名是 <b>.cgi</b>。</p>&#13;
<p>默认情况下，Apache Web 服务器会配置在 /var/www/cgi-bin 中运行 CGI 程序。如果您想指定其他目录来运行 CGI 脚本，您可以在 httpd.conf 文件中修改以下部分：</p>&#13;
<pre>&#13;
&lt;Directory "/var/www/cgi-bin"&gt;&#13;
   AllowOverride None&#13;
   Options ExecCGI&#13;
   Order allow,deny&#13;
   Allow from all&#13;
&lt;/Directory&gt;&#13;
 &#13;
&lt;Directory "/var/www/cgi-bin"&gt;&#13;
Options All&#13;
&lt;/Directory&gt;&#13;
</pre>&#13;
<p>在这里，我们假设已经配置好 Web 服务器并能成功运行，你可以运行任意的 CGI 程序，比如 Perl 或 Shell 等。</p>&#13;
&#13;
<h2>第一个 CGI 程序</h2>&#13;
<p>请看下面的 C++ 程序：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;Hello World - 第一个 CGI 程序&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;h2&gt;Hello World! 这是我的第一个 CGI 程序&lt;/h2&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>编译上面的代码，把可执行文件命名为 cplusplus.cgi，并把这个文件保存在 /var/www/cgi-bin 目录中。在运行 CGI 程序之前，请使用 <b>chmod 755 cplusplus.cgi</b> UNIX 命令来修改文件模式，确保文件可执行。访问可执行文件，您会看到下面的输出：</p>&#13;
<h2>Hello World! 这是我的第一个 CGI 程序</h2>&#13;
<p>上面的 C++ 程序是一个简单的程序，把它的输出写在 STDOUT 文件上，即显示在屏幕上。在这里，值得注意一点，第一行输出 <b>Content-type:text/html\r\n\r\n</b>。这一行发送回浏览器，并指定要显示在浏览器窗口上的内容类型。您必须理解 CGI 的基本概念，这样才能进一步使用 Python 编写更多复杂的 CGI 程序。C++ CGI 程序可以与任何其他外部的系统（如 RDBMS）进行交互。</p>&#13;
&#13;
<h2>HTTP 头信息</h2>&#13;
<p>行 <b>Content-type:text/html\r\n\r\n</b> 是 HTTP 头信息的组成部分，它被发送到浏览器，以便更好地理解页面内容。HTTP 头信息的形式如下：</p>&#13;
<pre>&#13;
HTTP 字段名称: 字段内容&#13;
 &#13;
例如&#13;
Content-type: text/html\r\n\r\n&#13;
</pre>&#13;
<p>还有一些其他的重要的 HTTP 头信息，这些在您的 CGI 编程中都会经常被用到。</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="30%">头信息</th>&#13;
<th>描述</th></tr>&#13;
<tr> &#13;
<td>Content-type: </td>&#13;
<td>MIME 字符串，定义返回的文件格式。例如 Content-type:text/html。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>Expires: Date </td>&#13;
<td>信息变成无效的日期。浏览器使用它来判断一个页面何时需要刷新。一个有效的日期字符串的格式应为 01 Jan 1998 12:00:00 GMT。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>Location: URL </td>&#13;
<td>这个 URL 是指应该返回的 URL，而不是请求的 URL。你可以使用它来重定向一个请求到任意的文件。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>Last-modified: Date</td>&#13;
<td>资源的最后修改日期。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>Content-length: N</td>&#13;
<td>要返回的数据的长度，以字节为单位。浏览器使用这个值来表示一个文件的预计下载时间。</td> &#13;
</tr>&#13;
<tr><td>Set-Cookie: String </td>&#13;
<td>通过 <i>string</i> 设置 cookie。</td> &#13;
</tr>&#13;
</table>&#13;
&#13;
<h2>CGI 环境变量</h2>&#13;
<p>所有的 CGI 程序都可以访问下列的环境变量。这些变量在编写 CGI 程序时扮演了非常重要的角色。</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="30%">变量名</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr> &#13;
<td>CONTENT_TYPE</td>&#13;
<td>内容的数据类型。当客户端向服务器发送附加内容时使用。例如，文件上传等功能。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>CONTENT_LENGTH</td>&#13;
<td>查询的信息长度。只对 POST 请求可用。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>HTTP_COOKIE</td>&#13;
<td>以键 &amp; 值对的形式返回设置的 cookies。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>HTTP_USER_AGENT</td>&#13;
<td>用户代理请求标头字段，递交用户发起请求的有关信息，包含了浏览器的名称、版本和其他平台性的附加信息。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>PATH_INFO</td>&#13;
<td>CGI 脚本的路径。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>QUERY_STRING</td>&#13;
<td>通过 GET 方法发送请求时的 URL 编码信息，包含 URL 中问号后面的参数。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>REMOTE_ADDR</td>&#13;
<td>发出请求的远程主机的 IP 地址。这在日志记录和认证时是非常有用的。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>REMOTE_HOST</td>&#13;
<td>发出请求的主机的完全限定名称。如果此信息不可用，则可以用 REMOTE_ADDR 来获取 IP 地址。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>REQUEST_METHOD</td>&#13;
<td>用于发出请求的方法。最常见的方法是 GET 和 POST。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>SCRIPT_FILENAME</td>&#13;
<td>CGI 脚本的完整路径。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>SCRIPT_NAME</td>&#13;
<td>CGI 脚本的名称。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>SERVER_NAME</td>&#13;
<td>服务器的主机名或 IP 地址。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>SERVER_SOFTWARE</td>&#13;
<td>服务器上运行的软件的名称和版本。</td></tr>&#13;
</table>&#13;
<p>下面的 CGI 程序列出了所有的 CGI 变量。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">const</span><span class="hl-code"> </span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">ENV</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-number">24</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-code">                 
        </span><span class="hl-quotes">"</span><span class="hl-string">COMSPEC</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">DOCUMENT_ROOT</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">GATEWAY_INTERFACE</span><span class="hl-quotes">"</span><span class="hl-code">,   
        </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_ACCEPT</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_ACCEPT_ENCODING</span><span class="hl-quotes">"</span><span class="hl-code">,             
        </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_ACCEPT_LANGUAGE</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_CONNECTION</span><span class="hl-quotes">"</span><span class="hl-code">,         
        </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_HOST</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">HTTP_USER_AGENT</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">PATH</span><span class="hl-quotes">"</span><span class="hl-code">,            
        </span><span class="hl-quotes">"</span><span class="hl-string">QUERY_STRING</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">REMOTE_ADDR</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">REMOTE_PORT</span><span class="hl-quotes">"</span><span class="hl-code">,      
        </span><span class="hl-quotes">"</span><span class="hl-string">REQUEST_METHOD</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">REQUEST_URI</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">SCRIPT_FILENAME</span><span class="hl-quotes">"</span><span class="hl-code">,
        </span><span class="hl-quotes">"</span><span class="hl-string">SCRIPT_NAME</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">SERVER_ADDR</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">SERVER_ADMIN</span><span class="hl-quotes">"</span><span class="hl-code">,      
        </span><span class="hl-quotes">"</span><span class="hl-string">SERVER_NAME</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-quotes">"</span><span class="hl-string">SERVER_PORT</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-quotes">"</span><span class="hl-string">SERVER_PROTOCOL</span><span class="hl-quotes">"</span><span class="hl-code">,     
        </span><span class="hl-quotes">"</span><span class="hl-string">SERVER_SIGNATURE</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-quotes">"</span><span class="hl-string">SERVER_SOFTWARE</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">}</span><span class="hl-code">;   
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;CGI 环境变量&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;table border = </span><span class="hl-special">\</span><span class="hl-quotes">"</span><span class="hl-number">0</span><span class="hl-code">\</span><span class="hl-quotes">"</span><span class="hl-string"> cellspacing = </span><span class="hl-special">\</span><span class="hl-quotes">"</span><span class="hl-number">2</span><span class="hl-code">\</span><span class="hl-quotes">"</span><span class="hl-string">&gt;</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">24</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;tr&gt;&lt;td&gt;</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">ENV</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/td&gt;&lt;td&gt;</span><span class="hl-quotes">"</span><span class="hl-code">;
       </span><span class="hl-comment">// 尝试检索环境变量的值</span><span class="hl-comment"/><span class="hl-code">
       </span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-identifier">value</span><span class="hl-code"> = </span><span class="hl-identifier">getenv</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">ENV</span><span class="hl-brackets">[</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> </span><span class="hl-brackets">]</span><span class="hl-code">.</span><span class="hl-identifier">c_str</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;  
       </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">value</span><span class="hl-code"> != </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">value</span><span class="hl-code">;                                 
       </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">环境变量不存在。</span><span class="hl-quotes">"</span><span class="hl-code">;
       </span><span class="hl-brackets">}</span><span class="hl-code">
       </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/td&gt;&lt;/tr&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/table&gt;&lt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>C++ CGI 库</h2>&#13;
<p>在真实的实例中，您需要通过 CGI 程序执行许多操作。这里有一个专为 C++ 程序而编写的 CGI 库，我们可以从 <a rel="nofollow noopener" href="ftp://ftp.gnu.org/gnu/cgicc/" target="_blank">ftp://ftp.gnu.org/gnu/cgicc/</a> 上下载这个 CGI 库，并按照下面的步骤安装库：</p><p>&#13;
<img decoding="async" src="/wp-content/uploads/2015/05/1662714E-4491-43C9-A38B-FD8D178F6663.jpg"/></p>&#13;
<pre>&#13;
$ tar xzf cgicc-X.X.X.tar.gz &#13;
$ cd cgicc-X.X.X/ &#13;
$ ./configure --prefix=/usr &#13;
$ make&#13;
$ make install&#13;
</pre>&#13;
&#13;
&#13;
&#13;
<blockquote><p><strong>注意：</strong>libcgicc.so 和 libcgicc.a 库会被安装到/usr/lib目录下，需执行拷贝命令：</p>&#13;
<pre>$ sudo cp /usr/lib/libcgicc.* /usr/lib64/</pre>&#13;
<p>才能使 CGI 程序自动找到 libcgicc.so 动态链接库。</p></blockquote>&#13;
&#13;
&#13;
<p>您可以点击 <a rel="nofollow noopener" href="http://www.gnu.org/software/cgicc/doc/index.html" target="_blank">C++ CGI Lib Documentation</a>，查看相关的库文档。</p>&#13;
&#13;
<h2>GET 和 POST 方法</h2>&#13;
<p>您可能有遇到过这样的情况，当您需要从浏览器传递一些信息到 Web 服务器，最后再传到 CGI 程序。通常浏览器会使用两种方法把这个信息传到 Web 服务器，分别是 GET 和 POST 方法。</p>&#13;
&#13;
<h2>使用 GET 方法传递信息</h2>&#13;
<p>GET 方法发送已编码的用户信息追加到页面请求中。页面和已编码信息通过 ? 字符分隔开，如下所示：</p>&#13;
<pre>&#13;
http://www.test.com/cgi-bin/cpp.cgi?key1=value1&amp;key2=value2&#13;
</pre>&#13;
<p>GET 方法是默认的从浏览器向 Web 服务器传信息的方法，它会在浏览器的地址栏中生成一串很长的字符串。当您向服务器传密码或其他一些敏感信息时，不要使用 GET 方法。GET 方法有大小限制，在一个请求字符串中最多可以传 1024 个字符。 </p>&#13;
<p>当使用 GET 方法时，是使用 QUERY_STRING http 头来传递信息，在 CGI 程序中可使用 QUERY_STRING 环境变量来访问。</p>&#13;
<p>您可以通过在 URL 后跟上简单连接的键值对，也可以通过使用 HTML &lt;FORM&gt; 标签的 GET 方法来传信息。</p>&#13;
&#13;
<h2>简单的 URL 实例：Get 方法</h2>&#13;
<p>下面是一个简单的 URL，使用 GET 方法传递两个值给 cpp_get.cgi 程序。</p>&#13;
<p>/cgi-bin/cpp_get.cgi?first_name=ZARA&amp;last_name=ALI</p>&#13;
<p>下面的实例生成 <b>cpp_get.cgi</b> CGI 程序，用于处理 Web 浏览器给出的输入。通过使用 C++ CGI 库，可以很容易地访问传递的信息：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">formData</span><span class="hl-code">;
   
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;使用 GET 和 POST 方法&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">form_iterator</span><span class="hl-code"> </span><span class="hl-identifier">fi</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">getElement</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">first_name</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-identifier">fi</span><span class="hl-code">-&gt;</span><span class="hl-identifier">isEmpty</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">fi</span><span class="hl-code"> != </span><span class="hl-brackets">(</span><span class="hl-code">*</span><span class="hl-identifier">formData</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">名：</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; **</span><span class="hl-identifier">fi</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">No text entered for first name</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">fi</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">getElement</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">last_name</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-identifier">fi</span><span class="hl-code">-&gt;</span><span class="hl-identifier">isEmpty</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &amp;&amp;</span><span class="hl-identifier">fi</span><span class="hl-code"> != </span><span class="hl-brackets">(</span><span class="hl-code">*</span><span class="hl-identifier">formData</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">姓：</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; **</span><span class="hl-identifier">fi</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">No text entered for last name</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>现在，编译上面的程序，如下所示：</p>&#13;
<pre>&#13;
$g++ -o cpp_get.cgi cpp_get.cpp -lcgicc&#13;
</pre>&#13;
<p>生成 cpp_get.cgi，并把它放在 CGI 目录中，并尝试使用下面的链接进行访问：</p>&#13;
<p>/cgi-bin/cpp_get.cgi?first_name=ZARA&amp;last_name=ALI</p>&#13;
<p>这会产生以下结果：</p>&#13;
<pre>&#13;
名：ZARA &#13;
姓：ALI &#13;
</pre>&#13;
&#13;
<h2>简单的表单实例：GET 方法</h2>&#13;
<p>下面是一个简单的实例，使用 HTML 表单和提交按钮传递两个值。我们将使用相同的 CGI 脚本 cpp_get.cgi 来处理输入。</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_get.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">get</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
名：</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">text</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">first_name</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">  </span><span class="hl-brackets">&lt;</span><span class="hl-reserved">br</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
 
姓：</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">text</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">last_name</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">提交</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面是上述表单的实际输出，请输入名和姓，然后点击提交按钮查看结果。</p>&#13;
&#13;
<h2>使用 POST 方法传递信息</h2>&#13;
<p>一个更可靠的向 CGI 程序传递信息的方法是 POST 方法。这种方法打包信息的方式与 GET 方法相同，不同的是，它不是把信息以文本字符串形式放在 URL 中的 ? 之后进行传递，而是把它以单独的消息形式进行传递。该消息是以标准输入的形式传给 CGI 脚本的。</p>&#13;
<p>我们同样使用 cpp_get.cgi 程序来处理 POST 方法。让我们以同样的例子，通过使用 HTML 表单和提交按钮来传递两个值，只不过这次我们使用的不是 GET 方法，而是 POST 方法，如下所示：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_get.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">post</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
名：</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">text</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">first_name</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">br</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
姓：</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">text</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">last_name</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
 
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">提交</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>向 CGI 程序传递复选框数据</h2>&#13;
<p>当需要选择多个选项时，我们使用复选框。</p>&#13;
<p>下面的 HTML 代码实例是一个带有两个复选框的表单：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_checkbox.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">POST</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">target</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">_blank</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">checkbox</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">maths</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">on</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code"> 数学
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">checkbox</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">physics</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">on</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code"> 物理
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">选择学科</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面的 C++ 程序会生成 cpp_checkbox.cgi 脚本，用于处理 Web 浏览器通过复选框给出的输入。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">formData</span><span class="hl-code">;
   </span><span class="hl-types">bool</span><span class="hl-code"> </span><span class="hl-identifier">maths_flag</span><span class="hl-code">, </span><span class="hl-identifier">physics_flag</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;向 CGI 程序传递复选框数据&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">maths_flag</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">queryCheckbox</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">maths</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">maths_flag</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Maths Flag: ON </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Maths Flag: OFF </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">physics_flag</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">queryCheckbox</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">physics</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">physics_flag</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Physics Flag: ON </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Physics Flag: OFF </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>向 CGI 程序传递单选按钮数据</h2>&#13;
<p>当只需要选择一个选项时，我们使用单选按钮。</p>&#13;
<p>下面的 HTML 代码实例是一个带有两个单选按钮的表单：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_radiobutton.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">post</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">target</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">_blank</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">radio</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">subject</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">maths</span><span class="hl-quotes">"</span><span class="hl-code"> 
                                    </span><span class="hl-var">checked</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">checked</span><span class="hl-quotes">"</span><span class="hl-brackets">/&gt;</span><span class="hl-code"> 数学 
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">radio</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">subject</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">physics</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code"> 物理
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">选择学科</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面的 C++ 程序会生成 cpp_radiobutton.cgi 脚本，用于处理 Web 浏览器通过单选按钮给出的输入。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">formData</span><span class="hl-code">;
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;向 CGI 程序传递单选按钮数据&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">form_iterator</span><span class="hl-code"> </span><span class="hl-identifier">fi</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">getElement</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">subject</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-identifier">fi</span><span class="hl-code">-&gt;</span><span class="hl-identifier">isEmpty</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">fi</span><span class="hl-code"> != </span><span class="hl-brackets">(</span><span class="hl-code">*</span><span class="hl-identifier">formData</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Radio box selected: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; **</span><span class="hl-identifier">fi</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>向 CGI 程序传递文本区域数据</h2>&#13;
<p>当需要向 CGI 程序传递多行文本时，我们使用 TEXTAREA 元素。</p>&#13;
<p>下面的 HTML 代码实例是一个带有 TEXTAREA 框的表单：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_textarea.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">post</span><span class="hl-quotes">"</span><span class="hl-code"> 
         </span><span class="hl-var">target</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">_blank</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">textarea</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">textcontent</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">cols</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">40</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">rows</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">4</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
请在这里输入文本...
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">textarea</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">提交</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面的 C++ 程序会生成 cpp_textarea.cgi 脚本，用于处理 Web 浏览器通过文本区域给出的输入。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">formData</span><span class="hl-code">;
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;向 CGI 程序传递文本区域数据&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">form_iterator</span><span class="hl-code"> </span><span class="hl-identifier">fi</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">getElement</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">textcontent</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-identifier">fi</span><span class="hl-code">-&gt;</span><span class="hl-identifier">isEmpty</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">fi</span><span class="hl-code"> != </span><span class="hl-brackets">(</span><span class="hl-code">*</span><span class="hl-identifier">formData</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Text Content: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; **</span><span class="hl-identifier">fi</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-reserved">else</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">No text entered</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
<h2>向 CGI 程序传递下拉框数据</h2>&#13;
<p>当有多个选项可用，但只能选择一个或两个选项时，我们使用下拉框。</p>&#13;
<p>下面的 HTML 代码实例是一个带有下拉框的表单：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_dropdown.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> 
                       </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">post</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">target</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">_blank</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">select</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">dropdown</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">option</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">Maths</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">selected</span><span class="hl-brackets">&gt;</span><span class="hl-code">数学</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">option</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">option</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">Physics</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">物理</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">option</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">select</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">提交</span><span class="hl-quotes">"</span><span class="hl-brackets">/&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面的 C++ 程序会生成 cpp_dropdown.cgi 脚本，用于处理 Web 浏览器通过下拉框给出的输入。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">formData</span><span class="hl-code">;
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;向 CGI 程序传递下拉框数据&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">form_iterator</span><span class="hl-code"> </span><span class="hl-identifier">fi</span><span class="hl-code"> = </span><span class="hl-identifier">formData</span><span class="hl-code">.</span><span class="hl-identifier">getElement</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">dropdown</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-identifier">fi</span><span class="hl-code">-&gt;</span><span class="hl-identifier">isEmpty</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">fi</span><span class="hl-code"> != </span><span class="hl-brackets">(</span><span class="hl-code">*</span><span class="hl-identifier">formData</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value Selected: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; **</span><span class="hl-identifier">fi</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
   </span><span class="hl-brackets">}</span><span class="hl-code">
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>在 CGI 中使用 Cookies</h2>&#13;
<p>HTTP 协议是一种无状态的协议。但对于一个商业网站，它需要在不同页面间保持会话信息。例如，一个用户在完成多个页面的步骤之后结束注册。但是，如何在所有网页中保持用户的会话信息。</p>&#13;
<p>在许多情况下，使用 cookies 是记忆和跟踪有关用户喜好、购买、佣金以及其他为追求更好的游客体验或网站统计所需信息的最有效的方法。</p>&#13;
&#13;
<h3>它是如何工作的</h3>&#13;
<p>服务器以 cookie 的形式向访客的浏览器发送一些数据。如果浏览器接受了 cookie，则 cookie 会以纯文本记录的形式存储在访客的硬盘上。现在，当访客访问网站上的另一个页面时，会检索 cookie。一旦找到 cookie，服务器就知道存储了什么。</p>&#13;
<p>cookie 是一种纯文本的数据记录，带有 5 个可变长度的字段：</p>&#13;
<ul class="list">&#13;
<li><b>Expires :</b> cookie 的过期日期。如果此字段留空，cookie 会在访客退出浏览器时过期。</li>&#13;
<li><b>Domain :</b> 网站的域名。</li>&#13;
<li><b>Path :</b> 设置 cookie 的目录或网页的路径。如果您想从任意的目录或网页检索 cookie，此字段可以留空。</li>&#13;
<li><b>Secure :</b> 如果此字段包含单词 "secure"，那么 cookie 只能通过安全服务器进行检索。如果此字段留空，则不存在该限制。</li>&#13;
<li><b>Name=Value :</b> cookie 以键值对的形式被设置和获取。</li>&#13;
</ul>&#13;
&#13;
<h3>设置 Cookies</h3>&#13;
<p>向浏览器发送 cookies 是非常简单的。这些 cookies 会在 Content-type 字段之前，与 HTTP 头一起被发送。假设您想设置 UserID 和 Password 为 cookies，设置 cookies 的步骤如下所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Set-Cookie:UserID=XYZ;</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Set-Cookie:Password=XYZ123;</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Set-Cookie:Domain=www.w3cschool.cc;</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Set-Cookie:Path=/perl;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;CGI 中的 Cookies&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">设置 cookies</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;  
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>从这个实例中，我们了解了如何设置 cookies。我们使用 <b>Set-Cookie</b> HTTP 头来设置 cookies。</p>&#13;
<p>在这里，有一些设置 cookies 的属性是可选的，比如 Expires、Domain 和 Path。值得注意的是，cookies 是在发送行 <b>"Content-type:text/html\r\n\r\n</b> 之前被设置的。</p>&#13;
<p>编译上面的程序，生成 setcookies.cgi，并尝试使用下面的链接设置 cookies。它会在您的计算机上设置四个 cookies：</p>&#13;
<p>/cgi-bin/setcookies.cgi</p>&#13;
&#13;
<h3>获取 Cookies</h3>&#13;
<p>检索所有设置的 cookies 是非常简单的。cookies 被存储在 CGI 环境变量 HTTP_COOKIE 中，且它们的形式如下：</p>&#13;
<pre>&#13;
key1=value1;key2=value2;key3=value3....&#13;
</pre>&#13;
<p>下面的实例演示了如何获取 cookies。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">cgi</span><span class="hl-code">;
   </span><span class="hl-identifier">const_cookie_iterator</span><span class="hl-code"> </span><span class="hl-identifier">cci</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;CGI 中的 Cookies&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;table border = </span><span class="hl-special">\</span><span class="hl-quotes">"</span><span class="hl-number">0</span><span class="hl-code">\</span><span class="hl-quotes">"</span><span class="hl-string"> cellspacing = </span><span class="hl-special">\</span><span class="hl-quotes">"</span><span class="hl-number">2</span><span class="hl-code">\</span><span class="hl-quotes">"</span><span class="hl-string">&gt;</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 获取环境变量</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">const</span><span class="hl-code"> </span><span class="hl-identifier">CgiEnvironment</span><span class="hl-code">&amp; </span><span class="hl-identifier">env</span><span class="hl-code"> = </span><span class="hl-identifier">cgi</span><span class="hl-code">.</span><span class="hl-identifier">getEnvironment</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">cci</span><span class="hl-code"> = </span><span class="hl-identifier">env</span><span class="hl-code">.</span><span class="hl-identifier">getCookieList</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">begin</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">cci</span><span class="hl-code"> != </span><span class="hl-identifier">env</span><span class="hl-code">.</span><span class="hl-identifier">getCookieList</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">; 
        ++</span><span class="hl-identifier">cci</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;tr&gt;&lt;td&gt;</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">cci</span><span class="hl-code">-&gt;</span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/td&gt;&lt;td&gt;</span><span class="hl-quotes">"</span><span class="hl-code">;
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">cci</span><span class="hl-code">-&gt;</span><span class="hl-identifier">getValue</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;                                 
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/td&gt;&lt;/tr&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/table&gt;&lt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
  
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;br/&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>现在，编译上面的程序，生成 getcookies.cgi，并尝试使用下面的链接获取您的计算机上所有可用的 cookies：</p>&#13;
<p>/cgi-bin/getcookies.cgi</p>&#13;
<p>这会产生一个列表，显示了上一节中设置的四个 cookies 以及您的计算机上所有其他的 cookies：</p>&#13;
<pre>&#13;
UserID XYZ &#13;
Password XYZ123 &#13;
Domain www.w3cschool.cc &#13;
Path /perl &#13;
</pre>&#13;
&#13;
<h2>文件上传实例</h2>&#13;
<p>为了上传一个文件，HTML 表单必须把 enctype 属性设置为 <b>multipart/form-data</b>。带有文件类型的 input 标签会创建一个 "Browse" 按钮。</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-brackets">&lt;</span><span class="hl-reserved">html</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">body</span><span class="hl-brackets">&gt;</span><span class="hl-code">
   </span><span class="hl-brackets">&lt;</span><span class="hl-reserved">form</span><span class="hl-code"> </span><span class="hl-var">enctype</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">multipart/form-data</span><span class="hl-quotes">"</span><span class="hl-code"> 
            </span><span class="hl-var">action</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">/cgi-bin/cpp_uploadfile.cgi</span><span class="hl-quotes">"</span><span class="hl-code"> 
            </span><span class="hl-var">method</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">post</span><span class="hl-quotes">"</span><span class="hl-brackets">&gt;</span><span class="hl-code">
   </span><span class="hl-brackets">&lt;</span><span class="hl-reserved">p</span><span class="hl-brackets">&gt;</span><span class="hl-code">文件：</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">file</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">name</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">userfile</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">p</span><span class="hl-brackets">&gt;</span><span class="hl-code">
   </span><span class="hl-brackets">&lt;</span><span class="hl-reserved">p</span><span class="hl-brackets">&gt;</span><span class="hl-brackets">&lt;</span><span class="hl-reserved">input</span><span class="hl-code"> </span><span class="hl-var">type</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">submit</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-var">value</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">上传</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">/&gt;</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">p</span><span class="hl-brackets">&gt;</span><span class="hl-code">
   </span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">form</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">body</span><span class="hl-brackets">&gt;</span><span class="hl-code">
</span><span class="hl-brackets">&lt;/</span><span class="hl-reserved">html</span><span class="hl-brackets">&gt;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>这段代码的结果是下面的表单：</p>&#13;
<form enctype="multipart/form-data" action="/cgi-bin/cpp_uploadfile.cgi" method="post">&#13;
   <p>文件：<input type="file" name="userfile"/></p>&#13;
   <p><input type="reset" value="上传"/></p>&#13;
</form>&#13;
<p><b>注意：</b>上面的实例已经故意禁用了保存上传的文件在我们的服务器上。您可以在自己的服务器上尝试上面的代码。</p>&#13;
<p>下面是用于处理文件上传的脚本 <b>cpp_uploadfile.cpp</b>：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro">  </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/CgiDefs.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/Cgicc.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTTPHTMLHeader.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"> </span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">cgicc/HTMLClasses.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">cgicc</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Cgicc</span><span class="hl-code"> </span><span class="hl-identifier">cgi</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Content-type:text/html</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-special">\</span><span class="hl-string">r</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;title&gt;CGI 中的文件上传&lt;/title&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/head&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 获取要被上传的文件列表</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">const_file_iterator</span><span class="hl-code"> </span><span class="hl-identifier">file</span><span class="hl-code"> = </span><span class="hl-identifier">cgi</span><span class="hl-code">.</span><span class="hl-identifier">getFile</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">userfile</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">file</span><span class="hl-code"> != </span><span class="hl-identifier">cgi</span><span class="hl-code">.</span><span class="hl-identifier">getFiles</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">// 在 cout 中发送数据类型</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">HTTPContentHeader</span><span class="hl-brackets">(</span><span class="hl-identifier">file</span><span class="hl-code">-&gt;</span><span class="hl-identifier">getDataType</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-comment">// 在 cout 中写入内容</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">file</span><span class="hl-code">-&gt;</span><span class="hl-identifier">writeToStream</span><span class="hl-brackets">(</span><span class="hl-identifier">cout</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;文件上传成功&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/body&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">&lt;/html&gt;</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上面的实例是在 <b>cout</b> 流中写入内容，但您可以打开文件流，并把上传的文件内容保存在目标位置的某个文件中。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>