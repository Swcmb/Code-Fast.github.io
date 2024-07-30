<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python CGI编程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python CGI编程</h1>&#13;
<hr/>&#13;
<h2>什么是CGI</h2>&#13;
<p>CGI 目前由NCSA维护，NCSA定义CGI如下：</p><p>&#13;
CGI(Common Gateway Interface),通用网关接口,它是一段程序,运行在服务器上如：HTTP服务器，提供同客户端HTML页面的接口。</p>&#13;
&#13;
<hr/><h2>网页浏览</h2>&#13;
<p>为了更好的了解CGI是如何工作的，我们可以从在网页上点击一个链接或URL的流程：</p>&#13;
<ul>&#13;
<li>&#13;
1、使用你的浏览器访问URL并连接到HTTP web 服务器。</li><li>&#13;
2、Web服务器接收到请求信息后会解析URL，并查找访问的文件在服务器上是否存在，如果存在返回文件的内容，否则返回错误信息。</li><li>&#13;
3、浏览器从服务器上接收信息，并显示接收的文件或者错误信息。</li></ul>&#13;
&#13;
<p>CGI程序可以是Python脚本，PERL脚本，SHELL脚本，C或者C++程序等。</p>&#13;
<hr/>&#13;
<h2>&#13;
CGI架构图&#13;
</h2>&#13;
<p><img fetchpriority="high" decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/Cgi01.png" alt="cgiarch" width="411" height="473" class="alignnone size-full wp-image-4561"/></p>&#13;
<hr/>&#13;
<h2>Web服务器支持及配置</h2>&#13;
<p>在你进行CGI编程前，确保您的Web服务器支持CGI及已经配置了CGI的处理程序。</p>&#13;
<p>Apache 支持CGI 配置：</p>&#13;
<p>设置好CGI目录：</p>&#13;
<pre>&#13;
ScriptAlias /cgi-bin/ /var/www/cgi-bin/&#13;
</pre>&#13;
&#13;
<p>&#13;
所有的HTTP服务器执行CGI程序都保存在一个预先配置的目录。这个目录被称为CGI目录，并按照惯例，它被命名为/var/www/cgi-bin目录。</p><p>&#13;
CGI文件的扩展名为.cgi，python也可以使用.py扩展名。</p><p>&#13;
默认情况下，Linux服务器配置运行的cgi-bin目录中为/var/www。</p><p>&#13;
如果你想指定其他运行CGI脚本的目录，可以修改httpd.conf配置文件，如下所示：</p>&#13;
<pre>&#13;
&lt;Directory "/var/www/cgi-bin"&gt;&#13;
   AllowOverride None&#13;
   Options +ExecCGI&#13;
   Order allow,deny&#13;
   Allow from all&#13;
&lt;/Directory&gt;&#13;
</pre>&#13;
<p>在 AddHandler 中添加 .py 后缀，这样我们就可以访问 .py 结尾的 python 脚本文件：</p>&#13;
<pre>&#13;
AddHandler cgi-script .cgi .pl .py</pre>&#13;
<hr/><h2>第一个CGI程序</h2>&#13;
<p>我们使用Python创建第一个CGI程序，文件名为hello.py，文件位于/var/www/cgi-bin目录中，内容如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span>                             <span style="color: #a50"># 空行，告诉服务器结束头部</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;html&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;head&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;meta charset="utf-8"&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;title&gt;Hello Word - 我的第一个 CGI 程序！&lt;/title&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;/head&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;body&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;h2&gt;Hello Word! 我是来自菜鸟教程的第一CGI程序&lt;/h2&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;/body&gt;'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'&lt;/html&gt;'</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>文件保存后修改 hello.py，修改文件权限为 755：</p>&#13;
<pre>chmod 755 hello.py </pre>&#13;
<p>以上程序在浏览器访问显示结果如下：</p>&#13;
<p>&#13;
<img decoding="async" width="70%" src="https://www.runoob.com/wp-content/uploads/2013/11/3E82A06B-FE1F-49B9-969C-183FABD56363.jpg"/></p>&#13;
<p>这个的hello.py脚本是一个简单的Python脚本，脚本第一行的输出内容"Content-type:text/html"发送到浏览器并告知浏览器显示的内容类型为"text/html"。</p><p>用 print 输出一个空行用于告诉服务器结束头部信息。</p>&#13;
<hr/><h2>HTTP头部</h2>&#13;
<p>hello.py文件内容中的" Content-type:text/html"即为HTTP头部的一部分，它会发送给浏览器告诉浏览器文件的内容类型。</p>&#13;
<p>HTTP头部的格式如下：</p>&#13;
<pre>&#13;
HTTP 字段名: 字段内容&#13;
</pre><p>&#13;
例如：</p><pre>&#13;
Content-type: text/html</pre>&#13;
&#13;
<p>以下表格介绍了CGI程序中HTTP头部经常使用的信息：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:30%">头</th><th>描述</th>&#13;
</tr>&#13;
<tr> <td>Content-type: </td><td>请求的与实体对应的MIME信息。例如: Content-type:text/html</td></tr>&#13;
<tr> <td>Expires: Date </td><td>响应过期的日期和时间</td> </tr>&#13;
<tr> <td>Location: URL </td><td>用来重定向接收方到非请求URL的位置来完成请求或标识新的资源</td> </tr>&#13;
<tr> <td>Last-modified: Date</td><td>请求资源的最后修改时间</td> </tr>&#13;
<tr> <td>Content-length: N</td><td>请求的内容长度</td> </tr>&#13;
<tr> <td>Set-Cookie: String </td><td>设置Http Cookie</td> </tr>&#13;
</tbody></table>&#13;
<hr/>&#13;
<h2>CGI环境变量</h2>&#13;
<p>所有的CGI程序都接收以下的环境变量，这些变量在CGI程序中发挥了重要的作用：</p>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:30%;">变量名</th><th>描述</th></tr>&#13;
<tr> <td>CONTENT_TYPE</td><td>这个环境变量的值指示所传递来的信息的MIME类型。目前，环境变量CONTENT_TYPE一般都是：application/x-www-form-urlencoded,他表示数据来自于HTML表单。</td> </tr>&#13;
<tr> <td>CONTENT_LENGTH</td><td>如果服务器与CGI程序信息的传递方式是POST，这个环境变量即使从标准输入STDIN中可以读到的有效数据的字节数。这个环境变量在读取所输入的数据时必须使用。</td> </tr>&#13;
<tr> <td>HTTP_COOKIE</td><td>客户机内的 COOKIE 内容。</td> </tr>&#13;
<tr> <td>HTTP_USER_AGENT</td><td>提供包含了版本数或其他专有数据的客户浏览器信息。</td> </tr>&#13;
<tr> <td>PATH_INFO</td><td>这个环境变量的值表示紧接在CGI程序名之后的其他路径信息。它常常作为CGI程序的参数出现。</td> </tr>&#13;
<tr> <td>QUERY_STRING</td><td>如果服务器与CGI程序信息的传递方式是GET，这个环境变量的值即使所传递的信息。这个信息经跟在CGI程序名的后面，两者中间用一个问号'?'分隔。</td> </tr>&#13;
<tr> <td>REMOTE_ADDR</td><td>这个环境变量的值是发送请求的客户机的IP地址，例如上面的192.168.1.67。这个值总是存在的。而且它是Web客户机需要提供给Web服务器的唯一标识，可以在CGI程序中用它来区分不同的Web客户机。</td> </tr>&#13;
<tr> <td>REMOTE_HOST</td><td>这个环境变量的值包含发送CGI请求的客户机的主机名。如果不支持你想查询，则无需定义此环境变量。</td> </tr>&#13;
<tr> <td>REQUEST_METHOD</td><td>提供脚本被调用的方法。对于使用 HTTP/1.0 协议的脚本，仅 GET 和 POST 有意义。</td></tr>&#13;
<tr> <td>SCRIPT_FILENAME</td><td>CGI脚本的完整路径</td></tr>&#13;
<tr> <td>SCRIPT_NAME</td><td>CGI脚本的的名称</td></tr>&#13;
<tr> <td>SERVER_NAME</td><td>这是你的 WEB 服务器的主机名、别名或IP地址。</td></tr>&#13;
<tr> <td>SERVER_SOFTWARE</td><td>这个环境变量的值包含了调用CGI程序的HTTP服务器的名称和版本号。例如，上面的值为Apache/2.2.14(Unix)</td></tr>&#13;
</tbody></table>&#13;
<p>以下是一个简单的CGI脚本输出CGI的环境变量：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">os</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type: text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;b&gt;环境变量&lt;/b&gt;&lt;br&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;ul&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">for</span> key <span style="color: Green;font-weight:bold;">in</span> <span style="color: #05a;">os</span>.<span style="color: #05a;">environ</span>.<span style="color: #05a;">keys</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;li&gt;&lt;span style='color:green'&gt;%30s &lt;/span&gt; : %s &lt;/li&gt;"</span> % <span style="color: Olive;">(</span>key<span style="color: Gray;">,</span><span style="color: #05a;">os</span>.<span style="color: #05a;">environ</span><span style="color: Olive;">[</span>key<span style="color: Olive;">]</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/ul&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>将以上点保存为 test.py ,并修改文件权限为 755，执行结果如下：</p>&#13;
<p><img decoding="async" width="70%" src="https://www.runoob.com/wp-content/uploads/2013/11/0B7EB575-8393-43A0-949A-E46DCFB840FE.jpg"/></p>&#13;
<hr/><h2>GET和POST方法</h2>&#13;
<p>浏览器客户端通过两种方法向服务器传递信息，这两种方法就是 GET 方法和 POST 方法。</p>&#13;
&#13;
<h3>使用GET方法传输数据</h3>&#13;
<p>GET方法发送编码后的用户信息到服务端，数据信息包含在请求页面的URL上，以"?"号分割, 如下所示：</p>&#13;
&#13;
<pre>&#13;
http://www.test.com/cgi-bin/hello.py?key1=value1&amp;key2=value2&#13;
</pre>&#13;
有关 GET 请求的其他一些注释：&#13;
<ul>&#13;
<li>GET 请求可被缓存</li>&#13;
<li>GET 请求保留在浏览器历史记录中</li>&#13;
<li>GET 请求可被收藏为书签</li>&#13;
<li>GET 请求不应在处理敏感数据时使用</li>&#13;
<li>GET 请求有长度限制</li>&#13;
<li>GET 请求只应当用于取回数据</li>&#13;
</ul>&#13;
<h3>简单的url实例：GET方法</h3>&#13;
<p>以下是一个简单的URL，使用GET方法向hello_get.py程序发送两个参数：</p>&#13;
<pre>&#13;
/cgi-bin/test.py?name=菜鸟教程&amp;url=http://www.runoob.com&#13;
</pre>&#13;
<p>以下为 hello_get.py 文件的代码：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># CGI处理模块</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage 的实例化</span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 获取数据</span><br/>
site_name <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'name'</span><span style="color: Olive;">)</span><br/>
site_url  <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'url'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt;%s官网：%s&lt;/h2&gt;"</span> % <span style="color: Olive;">(</span>site_name<span style="color: Gray;">,</span> site_url<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>文件保存后修改 hello_get.py，修改文件权限为 755：</p>&#13;
<pre>chmod 755 hello_get.py </pre>&#13;
<p>浏览器请求输出结果：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/4C034008-B0B0-452F-AC97-C2BE37B9C7AF.jpg"/></p>&#13;
<h3>简单的表单实例：GET方法</h3>&#13;
<p>以下是一个通过HTML的表单使用GET方法向服务器发送两个数据，提交的服务器脚本同样是hello_get.py文件，hello_get.html 代码如下：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/hello_get.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"get"</span>&gt;</span><br/>
站点名称: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"name"</span>&gt;</span>  <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">br</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<br/>
站点 URL: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"url"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
<p>默认情况下 cgi-bin 目录只能存放脚本文件，我们将 hello_get.html 存储在 test 目录下，修改文件权限为 755：</p>&#13;
<pre>&#13;
chmod 755 hello_get.html&#13;
</pre>&#13;
<p>Gif 演示如下所示：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/hello_get.gif"/></p>&#13;
<h3>使用POST方法传递数据</h3>&#13;
<p>使用POST方法向服务器传递数据是更安全可靠的，像一些敏感信息如用户密码等需要使用POST传输数据。</p>&#13;
<p>以下同样是hello_get.py ，它也可以处理浏览器提交的POST表单数据:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># CGI处理模块</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage 的实例化</span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 获取数据</span><br/>
site_name <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'name'</span><span style="color: Olive;">)</span><br/>
site_url  <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'url'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt;%s官网：%s&lt;/h2&gt;"</span> % <span style="color: Olive;">(</span>site_name<span style="color: Gray;">,</span> site_url<span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以下为表单通过POST方法（<strong>method="post"</strong>）向服务器脚本 hello_get.py 提交数据:</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/hello_get.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span>&gt;</span><br/>
站点名称: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"name"</span>&gt;</span>  <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">br</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<br/>
站点 URL: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"url"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>Gif 演示如下所示：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/hello_post.gif"/></p>&#13;
<h3>通过CGI程序传递checkbox数据</h3>&#13;
<p>checkbox用于提交一个或者多个选项数据，HTML代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/checkbox.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"POST"</span> <span style="color: #00c;">target</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"_blank"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"checkbox"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"runoob"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"on"</span> <span style="color: #66cc66;">/</span>&gt;</span> 菜鸟教程<br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"checkbox"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"google"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"on"</span> <span style="color: #66cc66;">/</span>&gt;</span> Google<br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"选择站点"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>以下为 checkbox.py 文件的代码：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 引入 CGI 处理模块 </span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage的实例 </span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 接收字段数据</span><br/>
<span style="color: Green;font-weight:bold;">if</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'google'</span><span style="color: Olive;">)</span>:<br/>
   google_flag <span style="color: Gray;">=</span> <span style="color: #a11;">"是"</span><br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   google_flag <span style="color: Gray;">=</span> <span style="color: #a11;">"否"</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">if</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'runoob'</span><span style="color: Olive;">)</span>:<br/>
   runoob_flag <span style="color: Gray;">=</span> <span style="color: #a11;">"是"</span><br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   runoob_flag <span style="color: Gray;">=</span> <span style="color: #a11;">"否"</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt; 菜鸟教程是否选择了 : %s&lt;/h2&gt;"</span> % runoob_flag<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt; Google 是否选择了 : %s&lt;/h2&gt;"</span> % google_flag<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>修改 checkbox.py 权限：</p>&#13;
<pre>&#13;
chmod 755 checkbox.py&#13;
</pre>&#13;
<p>浏览器访问 Gif 演示图：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/checkbox.gif"/></p>&#13;
<h3>通过CGI程序传递Radio数据</h3>&#13;
<p>Radio 只向服务器传递一个数据，HTML代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/radiobutton.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span> <span style="color: #00c;">target</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"_blank"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"radio"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"site"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"runoob"</span> <span style="color: #66cc66;">/</span>&gt;</span> 菜鸟教程<br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"radio"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"site"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"google"</span> <span style="color: #66cc66;">/</span>&gt;</span> Google<br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>radiobutton.py 脚本代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 引入 CGI 处理模块 </span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage的实例 </span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 接收字段数据</span><br/>
<span style="color: Green;font-weight:bold;">if</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'site'</span><span style="color: Olive;">)</span>:<br/>
   <span style="color: #05a;">site</span> <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'site'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   <span style="color: #05a;">site</span> <span style="color: Gray;">=</span> <span style="color: #a11;">"提交数据为空"</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt; 选中的网站是 %s&lt;/h2&gt;"</span> % <span style="color: #05a;">site</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>修改 radiobutton.py 权限：</p>&#13;
<pre>&#13;
chmod 755 radiobutton.py&#13;
</pre>&#13;
<p>浏览器访问 Gif 演示图：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/radiobutton.gif"/></p>&#13;
<h3>通过CGI程序传递 Textarea 数据</h3>&#13;
<p>Textarea 向服务器传递多行数据，HTML 代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/textarea.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span> <span style="color: #00c;">target</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"_blank"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">textarea</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"textcontent"</span> <span style="color: #00c;">cols</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"40"</span> <span style="color: #00c;">rows</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"4"</span>&gt;</span><br/>
在这里输入内容...<br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">textarea</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span> <span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>textarea.py 脚本代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 引入 CGI 处理模块 </span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage的实例 </span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 接收字段数据</span><br/>
<span style="color: Green;font-weight:bold;">if</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'textcontent'</span><span style="color: Olive;">)</span>:<br/>
   text_content <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'textcontent'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   text_content <span style="color: Gray;">=</span> <span style="color: #a11;">"没有内容"</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt; 输入的内容是：%s&lt;/h2&gt;"</span> % text_content<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&gt;<p>修改 textarea.py 权限：</p>&#13;
<pre>&#13;
chmod 755 textarea.py&#13;
</pre>&#13;
<p>浏览器访问 Gif 演示图：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/textarea.gif"/></p>&#13;
<h3>通过CGI程序传递下拉数据。</h3>&#13;
<p>HTML 下拉框代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/dropdown.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span> <span style="color: #00c;">target</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"_blank"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">select</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"dropdown"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">option</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"runoob"</span> selected&gt;</span>菜鸟教程<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">option</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">option</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"google"</span>&gt;</span>Google<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">option</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">select</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span><span style="color: #66cc66;">/</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>dropdown.py 脚本代码如下所示：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 引入 CGI 处理模块 </span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">cgitb</span> <br/>
<br/>
<span style="color: #a50"># 创建 FieldStorage的实例 </span><br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span> <br/>
<br/>
<span style="color: #a50"># 接收字段数据</span><br/>
<span style="color: Green;font-weight:bold;">if</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'dropdown'</span><span style="color: Olive;">)</span>:<br/>
   dropdown_value <span style="color: Gray;">=</span> form.<span style="color: #05a;">getvalue</span><span style="color: Olive;">(</span><span style="color: #a11;">'dropdown'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   dropdown_value <span style="color: Gray;">=</span> <span style="color: #a11;">"没有内容"</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type:text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;html&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;meta charset=<span style="color: #000099; font-weight: bold;">\"</span>utf-8<span style="color: #000099; font-weight: bold;">\"</span>&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;title&gt;菜鸟教程 CGI 测试实例&lt;/title&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/head&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;h2&gt; 选中的选项是：%s&lt;/h2&gt;"</span> % dropdown_value<span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/body&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"&lt;/html&gt;"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>修改 dropdown.py 权限：</p>&#13;
<pre>&#13;
chmod 755 dropdown.py&#13;
</pre>&#13;
<p>浏览器访问 Gif 演示图：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/dropdown.gif"/></p>&#13;
<hr/>&#13;
<h2>CGI中使用Cookie</h2>&#13;
<p>在 http 协议一个很大的缺点就是不对用户身份的进行判断，这样给编程人员带来很大的不便，&#13;
而 cookie 功能的出现弥补了这个不足。</p><p> &#13;
cookie 就是在客户访问脚本的同时，通过客户的浏览器，在客户硬盘上写入纪录数据 &#13;
，当下次客户访问脚本时取回数据信息，从而达到身份判别的功能，cookie 常用在身份校验中。</p>&#13;
　 &#13;
<h3>cookie的语法</h3> &#13;
<p>http cookie的发送是通过http头部来实现的，他早于文件的传递，头部set-cookie的语法如下：</p>&#13;
<pre>&#13;
Set-cookie:name=name;expires=date;path=path;domain=domain;secure &#13;
</pre>&#13;
<ul>&#13;
<li> &#13;
&#13;
<strong>name=name:</strong> 需要设置cookie的值(name不能使用"<strong>;</strong>"和"<strong>,</strong>"号),有多个name值时用 "<strong>;</strong>" 分隔，例如：<strong>name1=name1;name2=name2;name3=name3</strong>。 </li> <li>&#13;
<strong>expires=date:</strong> cookie的有效期限,格式： expires="Wdy,DD-Mon-YYYY HH:MM:SS"</li> <li>&#13;
</li> <li><strong>path=path: </strong>设置cookie支持的路径,如果path是一个路径，则cookie对这个目录下的所有文件及子目录生效，例如： path="/cgi-bin/"，如果path是一个文件，则cookie指对这个文件生效，例如：path="/cgi-bin/cookie.cgi"。&#13;
</li> <li><strong>domain=domain:</strong> 对cookie生效的域名，例如：domain="www.runoob.com"&#13;
</li> <li><strong>secure:</strong> 如果给出此标志，表示cookie只能通过SSL协议的https服务器来传递。 &#13;
</li> <li>cookie的接收是通过设置环境变量HTTP_COOKIE来实现的，CGI程序可以通过检索该变量获取cookie信息。</li></ul>&#13;
<hr/><h2>Cookie设置 </h2>&#13;
<p>Cookie的 设置非常简单，cookie 会在 http 头部单独发送。以下实例在 cookie 中设置了 name 和 expires：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'Set-Cookie: name="菜鸟教程";expires=Wed, 28 Aug 2016 18:30:00 GMT'</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">'Content-Type: text/html'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"""<br/>
&lt;html&gt;<br/>
  &lt;head&gt;<br/>
    &lt;meta charset="utf-8"&gt;<br/>
    &lt;title&gt;菜鸟教程(runoob.com)&lt;/title&gt;<br/>
  &lt;/head&gt;<br/>
    &lt;body&gt;<br/>
        &lt;h1&gt;Cookie set OK!&lt;/h1&gt;<br/>
    &lt;/body&gt;<br/>
&lt;/html&gt;<br/>
"""</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>将以上代码保存到 cookie_set.py，并修改 cookie_set.py 权限：</p>&#13;
<pre>&#13;
chmod 755 cookie_set.py&#13;
</pre>&#13;
<p>以上实例使用了 Set-Cookie 头信息来设置 Cookie 信息，可选项中设置了 Cookie 的其他属性，如过期时间 Expires，域名 Domain，路径 Path。这些信息设置在 <strong>"Content-type:text/html"</strong> 之前。&#13;
</p>&#13;
<hr/>&#13;
<h2>&#13;
检索Cookie信息</h2><p>&#13;
Cookie信息检索页非常简单，Cookie信息存储在CGI的环境变量HTTP_COOKIE中，存储格式如下：</p>&#13;
&#13;
<pre>&#13;
key1=value1;key2=value2;key3=value3....&#13;
</pre>&#13;
<p>以下是一个简单的CGI检索cookie信息的程序：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># 导入模块</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">os</span><br/>
<span style="color: Green;font-weight:bold;">import</span> http.<span style="color: #05a;">cookies</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-type: text/html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"""<br/>
&lt;html&gt;<br/>
&lt;head&gt;<br/>
&lt;meta charset="utf-8"&gt;<br/>
&lt;title&gt;菜鸟教程(runoob.com)&lt;/title&gt;<br/>
&lt;/head&gt;<br/>
&lt;body&gt;<br/>
&lt;h1&gt;读取cookie信息&lt;/h1&gt;<br/>
"""</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">if</span> <span style="color: #a11;">'HTTP_COOKIE'</span> <span style="color: Green;font-weight:bold;">in</span> <span style="color: #05a;">os</span>.<span style="color: #05a;">environ</span>:<br/>
    cookie_string<span style="color: Gray;">=</span><span style="color: #05a;">os</span>.<span style="color: #05a;">environ</span>.<span style="color: #05a;">get</span><span style="color: Olive;">(</span><span style="color: #a11;">'HTTP_COOKIE'</span><span style="color: Olive;">)</span><br/>
    c<span style="color: Gray;">=</span> http.<span style="color: #05a;">cookies</span>.<span style="color: #05a;">SimpleCookie</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
   <span style="color: #a50"># c=Cookie.SimpleCookie()</span><br/>
    c.<span style="color: #05a;">load</span><span style="color: Olive;">(</span>cookie_string<span style="color: Olive;">)</span><br/>
<br/>
    <span style="color: Green;font-weight:bold;">try</span>:<br/>
        data<span style="color: Gray;">=</span>c<span style="color: Olive;">[</span><span style="color: #a11;">'name'</span><span style="color: Olive;">]</span>.<span style="color: #05a;">value</span><br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"cookie data: "</span>+data+<span style="color: #a11;">"&lt;br&gt;"</span><span style="color: Olive;">)</span><br/>
    <span style="color: Green;font-weight:bold;">except</span> <span style="color: Teal;">KeyError</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"cookie 没有设置或者已过去&lt;br&gt;"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"""<br/>
&lt;/body&gt;<br/>
&lt;/html&gt;<br/>
"""</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>将以上代码保存到 cookie_get.py，并修改 cookie_get.py 权限：</p>&#13;
<pre>&#13;
chmod 755 cookie_get.py&#13;
</pre>&#13;
<p>以上 cookie 设置演示 Gif 如下所示：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/cookie.gif"/></p>&#13;
<h3>文件上传实例</h3>&#13;
<p>HTML设置上传文件的表单需要设置 <strong>enctype</strong> 属性为 <strong>multipart/form-data</strong>，代码如下所示：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com)<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
 <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">enctype</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"multipart/form-data"</span> </span><br/>
<span style="color: #170;">                     <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"/cgi-bin/save_file.py"</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span>&gt;</span><br/>
   <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">p</span>&gt;</span>选中文件: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"file"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"filename"</span> <span style="color: #66cc66;">/</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">p</span>&gt;</span><br/>
   <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">p</span>&gt;&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"上传"</span> <span style="color: #66cc66;">/</span>&gt;&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">p</span>&gt;</span><br/>
   <span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<p>save_file.py 脚本文件代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgi</span><span style="color: Gray;">,</span> <span style="color: #05a;">os</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">cgitb</span><span style="color: Gray;">;</span> <span style="color: #05a;">cgitb</span>.<span style="color: #05a;">enable</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
form <span style="color: Gray;">=</span> <span style="color: #05a;">cgi</span>.<span style="color: #05a;">FieldStorage</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 获取文件名</span><br/>
fileitem <span style="color: Gray;">=</span> form<span style="color: Olive;">[</span><span style="color: #a11;">'filename'</span><span style="color: Olive;">]</span><br/>
<br/>
<span style="color: #a50"># 检测文件是否上传</span><br/>
<span style="color: Green;font-weight:bold;">if</span> fileitem.<span style="color: #05a;">filename</span>:<br/>
   <span style="color: #a50"># 设置文件路径 </span><br/>
   fn <span style="color: Gray;">=</span> <span style="color: #05a;">os</span>.<span style="color: #05a;">path</span>.<span style="color: #05a;">basename</span><span style="color: Olive;">(</span>fileitem.<span style="color: #05a;">filename</span><span style="color: Olive;">)</span><br/>
   <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">'/tmp/'</span> + fn<span style="color: Gray;">,</span> <span style="color: #a11;">'wb'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>fileitem.<span style="color: Teal;">file</span>.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
   message <span style="color: Gray;">=</span> <span style="color: #a11;">'文件 "'</span> + fn + <span style="color: #a11;">'" 上传成功'</span><br/>
   <br/>
<span style="color: Green;font-weight:bold;">else</span>:<br/>
   message <span style="color: Gray;">=</span> <span style="color: #a11;">'文件没有上传'</span><br/>
   <br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"""<span style="color: #000099; font-weight: bold;">\</span><br/>
Content-Type: text/html<span style="color: #000099; font-weight: bold;">\n</span><br/>
&lt;html&gt;<br/>
&lt;head&gt;<br/>
&lt;meta charset="utf-8"&gt;<br/>
&lt;title&gt;菜鸟教程(runoob.com)&lt;/title&gt;<br/>
&lt;/head&gt;<br/>
&lt;body&gt;<br/>
   &lt;p&gt;%s&lt;/p&gt;<br/>
&lt;/body&gt;<br/>
&lt;/html&gt;<br/>
"""</span> % <span style="color: Olive;">(</span>message<span style="color: Gray;">,</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>将以上代码保存到 save_file.py，并修改 save_file.py 权限：</p>&#13;
<pre>&#13;
chmod 755 save_file.py&#13;
</pre>&#13;
<p>以上 cookie 设置演示 Gif 如下所示：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/savefile.gif"/></p>&#13;
<p>如果你使用的系统是Unix/Linux，你必须替换文件分隔符，在window下只需要使用open()语句即可：</p>&#13;
<pre>&#13;
fn = os.path.basename(fileitem.filename.replace("\\", "/" ))&#13;
</pre>&#13;
<hr/><h2>文件下载对话框</h2>&#13;
<p>我们先在当前目录下创建 foo.txt 文件，用于程序的下载。</p>&#13;
<p>文件下载通过设置HTTP头信息来实现，功能代码如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: #a50"># HTTP 头部</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Content-Disposition: attachment; filename=<span style="color: #000099; font-weight: bold;">\"</span>foo.txt<span style="color: #000099; font-weight: bold;">\"</span>"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: #a50"># 打开文件</span><br/>
fo <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"foo.txt"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"rb"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: Teal;">str</span> <span style="color: Gray;">=</span> fo.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Gray;">;</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: Teal;">str</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 关闭文件</span><br/>
fo.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>