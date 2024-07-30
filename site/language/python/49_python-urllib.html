<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python urllib</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python urllib</h1>&#13;
<p>Python urllib 库用于操作网页 URL，并对网页的内容进行抓取处理。</p>&#13;
<p>本文主要介绍 Python3 的 urllib。</p>&#13;
&#13;
<p>urllib 包 包含以下几个模块：</p>&#13;
<ul><li>&#13;
<span class="marked">urllib.request</span> - 打开和读取 URL。&#13;
</li><li>&#13;
<span class="marked">urllib.error</span> - 包含 urllib.request 抛出的异常。&#13;
</li><li>&#13;
<span class="marked">urllib.parse</span> - 解析 URL。&#13;
</li><li>&#13;
<span class="marked">urllib.robotparser</span> - 解析 robots.txt 文件。</li></ul>&#13;
<p><img decoding="async" width="60%" src="https://www.runoob.com/wp-content/uploads/2021/04/ulrib-py3.svg"/></p>&#13;
<hr/>&#13;
<h2>urllib.request</h2><p>&#13;
urllib.request 定义了一些打开 URL 的函数和类，包含授权验证、重定向、浏览器 cookies等。</p>&#13;
<p>urllib.request 可以模拟浏览器的一个请求发起过程。</p>&#13;
<p>&#13;
我们可以使用 urllib.request 的 urlopen 方法来打开一个 URL，语法格式如下：&#13;
</p>&#13;
<pre>urllib.request.urlopen(url, data=None, [timeout, ]*, cafile=None, capath=None, cadefault=False, context=None)</pre>&#13;
<ul><li>&#13;
<strong>url</strong>：url 地址。</li><li>&#13;
<strong>data</strong>：发送到服务器的其他数据对象，默认为 None。</li><li>&#13;
<strong>timeout</strong>：设置访问超时时间。</li><li>&#13;
<strong>cafile 和 capath</strong>：cafile 为 CA 证书， capath 为 CA 证书的路径，使用 HTTPS 需要用到。</li><li>&#13;
<strong>cadefault</strong>：已经被弃用。</li><li>&#13;
<strong>context</strong>：ssl.SSLContext类型，用来指定 SSL 设置。</li></ul>&#13;
&#13;
<p>实例如下：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span> <span style="color: Green;font-weight:bold;">import</span> urlopen<br/>
<br/>
myURL <span style="color: Gray;">=</span> urlopen<span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>myURL.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>&#13;
以上代码使用 urlopen 打开一个 URL，然后使用 read() 函数获取网页的 HTML 实体代码。</p>&#13;
<p>&#13;
read() 是读取整个网页内容，我们可以指定读取的长度：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span> <span style="color: Green;font-weight:bold;">import</span> urlopen<br/>
<br/>
myURL <span style="color: Gray;">=</span> urlopen<span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>myURL.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Maroon;">300</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>除了 read() 函数外，还包含以下两个读取网页内容的函数：</p>&#13;
&#13;
<ul><li>&#13;
<p><strong>readline()</strong> - 读取文件的一行内容</p>&#13;
<pre>from urllib.request import urlopen&#13;
&#13;
myURL = urlopen("https://www.runoob.com/")&#13;
print(myURL.readline()) #读取一行内容</pre>&#13;
</li><li>&#13;
<p><strong>readlines()</strong> - 读取文件的全部内容，它会把读取的内容赋值给一个列表变量。</p>&#13;
&#13;
<pre>from urllib.request import urlopen&#13;
&#13;
myURL = urlopen("https://www.runoob.com/")&#13;
lines = myURL.readlines()&#13;
for line in lines:&#13;
    print(line) </pre>&#13;
</li></ul>&#13;
<p>我们在对网页进行抓取时，经常需要判断网页是否可以正常访问，这里我们就可以使用 getcode() 函数获取网页状态码，返回 200 说明网页正常，返回 404 说明网页不存在:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span><br/>
<br/>
myURL1 <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>myURL1.<span style="color: #05a;">getcode</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 200</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">try</span>:<br/>
    myURL2 <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/no.html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">except</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">error</span>.<span style="color: #05a;">HTTPError</span> <span style="color: Green;font-weight:bold;">as</span> e:<br/>
    <span style="color: Green;font-weight:bold;">if</span> e.<span style="color: #05a;">code</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">404</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Maroon;">404</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 404</span><br/>
</div></div><p>&#13;
更多网页状态码可以查阅：<a href="https://www.runoob.com/http/http-status-codes.html" rel="noopener" target="_blank">https://www.runoob.com/http/http-status-codes.html</a>。</p>&#13;
<p>如果要将抓取的网页保存到本地，可以使用 <a href="https://www.runoob.com/python3/python3-file-write.html" rel="noopener" target="_blank">Python3 File write() 方法</a> 函数：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span> <span style="color: Green;font-weight:bold;">import</span> urlopen<br/>
<br/>
myURL <span style="color: Gray;">=</span> urlopen<span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span><br/>
f <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"runoob_urllib_test.html"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"wb"</span><span style="color: Olive;">)</span><br/>
content <span style="color: Gray;">=</span> myURL.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 读取网页内容</span><br/>
f.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>content<span style="color: Olive;">)</span><br/>
f.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div><p>&#13;
执行以上代码，在本地就会生成一个 runoob_urllib_test.html 文件，里面包含了 https://www.runoob.com/ 网页的内容。</p>&#13;
<p>更多Python File 处理，可以参阅：<a href="https://www.runoob.com/python3/python3-file-methods.html" rel="noopener" target="_blank">https://www.runoob.com/python3/python3-file-methods.html</a></p>。&#13;
<p>&#13;
URL 的编码与解码可以使用 <strong>urllib.request.quote()</strong> 与 <strong>urllib.request.unquote()</strong> 方法：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span> <br/>
<br/>
encode_url <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">quote</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 编码</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>encode_url<span style="color: Olive;">)</span><br/>
<br/>
unencode_url <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">unquote</span><span style="color: Olive;">(</span>encode_url<span style="color: Olive;">)</span>    <span style="color: #a50"># 解码</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>unencode_url<span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>输出结果为：</p>&#13;
<pre>https%3A//www.runoob.com/&#13;
https://www.runoob.com/</pre>&#13;
<h3>模拟头部信息</h3><p>&#13;
我们抓取网页一般需要对 headers（网页头信息）进行模拟，这时候需要使用到 urllib.request.Request 类：</p>&#13;
<pre>class urllib.request.Request(url, data=None, headers={}, origin_req_host=None, unverifiable=False, method=None)&#13;
</pre>&#13;
<ul><li>&#13;
<strong>url</strong>：url 地址。</li><li>&#13;
<strong>data</strong>：发送到服务器的其他数据对象，默认为 None。</li><li>&#13;
<strong>headers</strong>：HTTP 请求的头部信息，字典格式。</li><li>&#13;
<strong>origin_req_host</strong>：请求的主机地址，IP 或域名。</li><li>&#13;
<strong>unverifiable</strong>：很少用这个参数，用于设置网页是否需要验证，默认是 False。</li><li>&#13;
<strong>method</strong>：请求方法， 如 GET、POST、DELETE、PUT等。</li></ul>&#13;
&#13;
<div class="example"><h2 class="example">实例 - py3_urllib_test.py 文件代码</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">parse</span><br/>
<br/>
url <span style="color: Gray;">=</span> <span style="color: #a11;">'https://www.runoob.com/?s='</span>  <span style="color: #a50"># 菜鸟教程搜索页面</span><br/>
<span style="color: #05a;">keyword</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'Python 教程'</span> <br/>
key_code <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">quote</span><span style="color: Olive;">(</span><span style="color: #05a;">keyword</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 对请求进行编码</span><br/>
url_all <span style="color: Gray;">=</span> url+key_code<br/>
header <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><br/>
    <span style="color: #a11;">'User-Agent'</span>:<span style="color: #a11;">'Mozilla/5.0 (X11; Fedora; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36'</span><br/>
<span style="color: Olive;">}</span>   <span style="color: #a50">#头部信息</span><br/>
request <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">Request</span><span style="color: Olive;">(</span>url_all<span style="color: Gray;">,</span>headers<span style="color: Gray;">=</span>header<span style="color: Olive;">)</span><br/>
reponse <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span>request<span style="color: Olive;">)</span>.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
fh <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"./urllib_test_runoob_search.html"</span><span style="color: Gray;">,</span><span style="color: #a11;">"wb"</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 将文件写入到当前目录中</span><br/>
fh.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>reponse<span style="color: Olive;">)</span><br/>
fh.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div><p>&#13;
执行以上 Python 代码，会在当前目录生成 urllib_test_runoob_search.html 文件，打开 urllib_test_runoob_search.html 文件（可以使用浏览器打开），内容如下：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2021/04/6BD0D456-E929-4C11-9118-F09C85AEA427.jpg"/></p>&#13;
<p>表单 POST 传递数据，我们先创建一个表单，代码如下，我这里使用了 PHP 代码来获取表单的数据：</p>&#13;
<div class="example"><h2 class="example">实例 - py3_urllib_test.php 文件代码：</h2> <div class="example_code">
<span style="color: #555;">&lt;!DOCTYPE html&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">meta</span> <span style="color: #00c;">charset</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"utf-8"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">title</span>&gt;</span>菜鸟教程(runoob.com) urllib POST  测试<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">title</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">head</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">form</span> <span style="color: #00c;">action</span><span style="color: #66cc66;">=</span><span style="color: #a11;">""</span> <span style="color: #00c;">method</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"post"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"myForm"</span>&gt;</span><br/>
    Name: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"name"</span>&gt;&lt;<span style="color: #170; font-weight: bold;">br</span>&gt;</span><br/>
    Tag: <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"text"</span> <span style="color: #00c;">name</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"tag"</span>&gt;&lt;<span style="color: #170; font-weight: bold;">br</span>&gt;</span><br/>
    <span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">input</span> <span style="color: #00c;">type</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"submit"</span> <span style="color: #00c;">value</span><span style="color: #66cc66;">=</span><span style="color: #a11;">"提交"</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">form</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #170; font-weight: bold;">hr</span>&gt;</span><br/>
<span style="color: #170;">&lt;?php</span><br/>
<span style="color: #170;"><span style="color: #66cc66;">//</span> 使用 PHP 来获取表单提交的数据，你可以换成其他的</span><br/>
<span style="color: #170;">if<span style="color: #66cc66;">(</span>isset<span style="color: #66cc66;">(</span>$_POST<span style="color: #66cc66;">[</span><span style="color: #a11;">'name'</span><span style="color: #66cc66;">]</span><span style="color: #66cc66;">)</span> &amp;&amp; $_POST<span style="color: #66cc66;">[</span><span style="color: #a11;">'tag'</span><span style="color: #66cc66;">]</span> <span style="color: #66cc66;">)</span> <span style="color: #66cc66;">{</span></span><br/>
<span style="color: #170;">    echo $_POST<span style="color: #66cc66;">[</span><span style="color: #a11;">"name"</span><span style="color: #66cc66;">]</span> . <span style="color: #a11;">', '</span> . $_POST<span style="color: #66cc66;">[</span><span style="color: #a11;">'tag'</span><span style="color: #66cc66;">]</span>;</span><br/>
<span style="color: #170;"><span style="color: #66cc66;">}</span></span><br/>
<span style="color: #170;">?&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">body</span>&gt;</span><br/>
<span style="color: #170;">&lt;<span style="color: #66cc66;">/</span><span style="color: #170; font-weight: bold;">html</span>&gt;</span><br/>
</div></div>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">parse</span><br/>
<br/>
url <span style="color: Gray;">=</span> <span style="color: #a11;">'https://www.runoob.com/try/py3/py3_urllib_test.php'</span>  <span style="color: #a50"># 提交到表单页面</span><br/>
data <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><span style="color: #a11;">'name'</span>:<span style="color: #a11;">'RUNOOB'</span><span style="color: Gray;">,</span> <span style="color: #a11;">'tag'</span> : <span style="color: #a11;">'菜鸟教程'</span><span style="color: Olive;">}</span>   <span style="color: #a50"># 提交数据</span><br/>
header <span style="color: Gray;">=</span> <span style="color: Olive;">{</span><br/>
    <span style="color: #a11;">'User-Agent'</span>:<span style="color: #a11;">'Mozilla/5.0 (X11; Fedora; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.36'</span><br/>
<span style="color: Olive;">}</span>   <span style="color: #a50">#头部信息</span><br/>
data <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">parse</span>.<span style="color: #05a;">urlencode</span><span style="color: Olive;">(</span>data<span style="color: Olive;">)</span>.<span style="color: #05a;">encode</span><span style="color: Olive;">(</span><span style="color: #a11;">'utf8'</span><span style="color: Olive;">)</span>  <span style="color: #a50"># 对参数进行编码，解码使用 urllib.parse.urldecode</span><br/>
request<span style="color: Gray;">=</span><span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">Request</span><span style="color: Olive;">(</span>url<span style="color: Gray;">,</span> data<span style="color: Gray;">,</span> header<span style="color: Olive;">)</span>   <span style="color: #a50"># 请求处理</span><br/>
reponse<span style="color: Gray;">=</span><span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span>request<span style="color: Olive;">)</span>.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span>      <span style="color: #a50"># 读取结果</span><br/>
<br/>
fh <span style="color: Gray;">=</span> <span style="color: Teal;">open</span><span style="color: Olive;">(</span><span style="color: #a11;">"./urllib_test_post_runoob.html"</span><span style="color: Gray;">,</span><span style="color: #a11;">"wb"</span><span style="color: Olive;">)</span>    <span style="color: #a50"># 将文件写入到当前目录中</span><br/>
fh.<span style="color: #05a;">write</span><span style="color: Olive;">(</span>reponse<span style="color: Olive;">)</span><br/>
fh.<span style="color: #05a;">close</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>执行以上代码，会提交表单数据到 py3_urllib_test.php 文件，输出结果写入到  urllib_test_post_runoob.html 文件。</p>&#13;
<p>打开 urllib_test_post_runoob.html 文件（可以使用浏览器打开），显示结果如下：</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2021/04/CFE5A0A5-6E9C-4CBF-B866-0C559F239DF8.jpg"/></p>&#13;
<hr/>&#13;
<h2>urllib.error</h2>&#13;
<p>urllib.error 模块为 urllib.request 所引发的异常定义了异常类，基础异常类是 URLError。</p>&#13;
&#13;
<p>urllib.error 包含了两个方法，URLError 和 HTTPError。</p><p>&#13;
URLError 是 OSError 的一个子类，用于处理程序在遇到问题时会引发此异常（或其派生的异常），包含的属性 reason 为引发异常的原因。</p>&#13;
<p>&#13;
HTTPError 是 URLError 的一个子类，用于处理特殊 HTTP 错误例如作为认证请求的时候，包含的属性 <span class="marked">code</span> 为 HTTP 的状态码， <span class="marked">reason</span> 为引发异常的原因，<span class="marked">headers</span> 为导致 HTTPError 的特定 HTTP 请求的 HTTP 响应头。</p>&#13;
&#13;
<p>对不存在的网页抓取并处理异常:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span><br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">error</span><br/>
<br/>
myURL1 <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>myURL1.<span style="color: #05a;">getcode</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 200</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">try</span>:<br/>
    myURL2 <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">request</span>.<span style="color: #05a;">urlopen</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/no.html"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">except</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">error</span>.<span style="color: #05a;">HTTPError</span> <span style="color: Green;font-weight:bold;">as</span> e:<br/>
    <span style="color: Green;font-weight:bold;">if</span> e.<span style="color: #05a;">code</span> <span style="color: Gray;">==</span> <span style="color: Maroon;">404</span>:<br/>
        <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span><span style="color: Maroon;">404</span><span style="color: Olive;">)</span>   <span style="color: #a50"># 404</span><br/>
</div></div><p>&#13;
</p><hr/>&#13;
<h2>urllib.parse</h2><p>&#13;
urllib.parse 用于解析 URL，格式如下：</p>&#13;
&#13;
<pre>urllib.parse.urlparse(urlstring, scheme='', allow_fragments=True)</pre>&#13;
<p>&#13;
urlstring 为 字符串的 url 地址，scheme 为协议类型，</p>&#13;
<p>allow_fragments 参数为 false，则无法识别片段标识符。相反，它们被解析为路径，参数或查询组件的一部分，并 fragment 在返回值中设置为空字符串。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">parse</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urlparse</span><br/>
<br/>
o <span style="color: Gray;">=</span> <span style="color: #05a;">urlparse</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/?s=python+%E6%95%99%E7%A8%8B"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>o<span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上实例输出结果为：</p>&#13;
<pre>ParseResult(scheme='https', netloc='www.runoob.com', path='/', params='', query='s=python+%E6%95%99%E7%A8%8B', fragment='')</pre>&#13;
<p>从结果可以看出，内容是一个元组，包含 6 个字符串：协议，位置，路径，参数，查询，判断。</p>&#13;
<p>我们可以直接读取协议内容：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">parse</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urlparse</span><br/>
<br/>
o <span style="color: Gray;">=</span> <span style="color: #05a;">urlparse</span><span style="color: Olive;">(</span><span style="color: #a11;">"https://www.runoob.com/?s=python+%E6%95%99%E7%A8%8B"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>o.<span style="color: #05a;">scheme</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上实例输出结果为：</p>&#13;
<pre>https</pre>&#13;
<p>完整内容如下：</p>&#13;
<table class="reference">&#13;
   <colgroup>&#13;
   <col style="width: 25%"/>&#13;
   <col style="width: 10%"/>&#13;
   <col style="width: 36%"/>&#13;
   <col style="width: 30%"/>&#13;
   </colgroup>&#13;
   <thead>&#13;
   <tr class="row-odd"><th class="head"><p>属性</p></th>&#13;
   <th class="head"><p>索引</p></th>&#13;
   <th class="head"><p>值</p></th>&#13;
   <th class="head"><p>值（如果不存在）</p></th>&#13;
   </tr>&#13;
   </thead>&#13;
   <tbody>&#13;
   <tr><td><p><code><span>scheme</span></code></p></td>&#13;
   <td><p>0</p></td>&#13;
   <td><p>URL协议</p></td>&#13;
   <td><p><em>scheme</em> 参数</p></td>&#13;
   </tr>&#13;
   <tr class="row-odd"><td><p><code><span>netloc</span></code></p></td>&#13;
   <td><p>1</p></td>&#13;
   <td><p>网络位置部分</p></td>&#13;
   <td><p>空字符串</p></td>&#13;
   </tr>&#13;
   <tr><td><p><code><span>path</span></code></p></td>&#13;
   <td><p>2</p></td>&#13;
   <td><p>分层路径</p></td>&#13;
   <td><p>空字符串</p></td>&#13;
   </tr>&#13;
   <tr class="row-odd"><td><p><code><span>params</span></code></p></td>&#13;
   <td><p>3</p></td>&#13;
   <td><p>最后路径元素的参数</p></td>&#13;
   <td><p>空字符串</p></td>&#13;
   </tr>&#13;
   <tr><td><p><code><span>query</span></code></p></td>&#13;
   <td><p>4</p></td>&#13;
   <td><p>查询组件</p></td>&#13;
   <td><p>空字符串</p></td>&#13;
   </tr>&#13;
   <tr class="row-odd"><td><p><code><span>fragment</span></code></p></td>&#13;
   <td><p>5</p></td>&#13;
   <td><p>片段识别</p></td>&#13;
   <td><p>空字符串</p></td>&#13;
   </tr>&#13;
   <tr><td><p><code><span>username</span></code></p></td>&#13;
   <td/>&#13;
   <td><p>用户名</p></td>&#13;
   <td><p><code><span>None</span></code></p></td>&#13;
   </tr>&#13;
   <tr class="row-odd"><td><p><code><span>password</span></code></p></td>&#13;
   <td/>&#13;
   <td><p>密码</p></td>&#13;
   <td><p><code><span>None</span></code></p></td>&#13;
   </tr>&#13;
   <tr><td><p><code><span>hostname</span></code></p></td>&#13;
   <td/>&#13;
   <td><p>主机名（小写）</p></td>&#13;
   <td><p><code><span>None</span></code></p></td>&#13;
   </tr>&#13;
   <tr class="row-odd"><td><p><code><span>port</span></code></p></td>&#13;
   <td/>&#13;
   <td><p>端口号为整数（如果存在）</p></td>&#13;
   <td><p><code><span>None</span></code></p></td>&#13;
   </tr>&#13;
   </tbody>&#13;
   </table>&#13;
<hr/><h2>urllib.robotparser</h2>&#13;
<p>urllib.robotparser 用于解析 robots.txt 文件。</p><p>&#13;
robots.txt（统一小写）是一种存放于网站根目录下的 robots 协议，它通常用于告诉搜索引擎对网站的抓取规则。</p>&#13;
<p>urllib.robotparser 提供了 RobotFileParser 类，语法如下：</p>&#13;
<pre>class urllib.robotparser.RobotFileParser(url='')</pre>&#13;
<p>这个类提供了一些可以读取、解析 robots.txt 文件的方法：</p>&#13;
<ul><li>&#13;
<p>set_url(url) - 设置 robots.txt 文件的 URL。</p>&#13;
</li><li>&#13;
<p>read() - 读取 robots.txt URL 并将其输入解析器。</p>&#13;
</li><li>&#13;
<p>parse(lines) - 解析行参数。</p>&#13;
</li><li>&#13;
<p>can_fetch(useragent, url) - 如果允许 useragent 按照被解析 robots.txt 文件中的规则来获取 url 则返回 True。</p>&#13;
</li><li>&#13;
<p>mtime() -返回最近一次获取 robots.txt 文件的时间。 这适用于需要定期检查 robots.txt 文件更新情况的长时间运行的网页爬虫。</p>&#13;
</li><li>&#13;
<p>modified() - 将最近一次获取 robots.txt 文件的时间设置为当前时间。</p>&#13;
</li><li>&#13;
<p>crawl_delay(useragent) -为指定的 useragent 从 robots.txt 返回 Crawl-delay 形参。 如果此形参不存在或不适用于指定的 useragent 或者此形参的 robots.txt 条目存在语法错误，则返回 None。</p>&#13;
</li><li>&#13;
&#13;
&#13;
<p>request_rate(useragent) -以 named tuple RequestRate(requests, seconds) 的形式从 robots.txt 返回 Request-rate 形参的内容。 如果此形参不存在或不适用于指定的 useragent 或者此形参的 robots.txt 条目存在语法错误，则返回 None。</p>&#13;
</li><li>&#13;
<p>site_maps() - 以 list() 的形式从 robots.txt 返回 Sitemap 形参的内容。 如果此形参不存在或者此形参的 robots.txt 条目存在语法错误，则返回 None。</p>&#13;
</li></ul>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Gray;">&gt;&gt;&gt;</span> <span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">robotparser</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp <span style="color: Gray;">=</span> <span style="color: #05a;">urllib</span>.<span style="color: #05a;">robotparser</span>.<span style="color: #05a;">RobotFileParser</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp.<span style="color: #05a;">set_url</span><span style="color: Olive;">(</span><span style="color: #a11;">"http://www.musi-cal.com/robots.txt"</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp.<span style="color: #05a;">read</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rrate <span style="color: Gray;">=</span> rp.<span style="color: #05a;">request_rate</span><span style="color: Olive;">(</span><span style="color: #a11;">"*"</span><span style="color: Olive;">)</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rrate.<span style="color: #05a;">requests</span><br/>
<span style="color: Maroon;">3</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rrate.<span style="color: #05a;">seconds</span><br/>
<span style="color: Maroon;">20</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp.<span style="color: #05a;">crawl_delay</span><span style="color: Olive;">(</span><span style="color: #a11;">"*"</span><span style="color: Olive;">)</span><br/>
<span style="color: Maroon;">6</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp.<span style="color: #05a;">can_fetch</span><span style="color: Olive;">(</span><span style="color: #a11;">"*"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"http://www.musi-cal.com/cgi-bin/search?city=San+Francisco"</span><span style="color: Olive;">)</span><br/>
<span style="color: Teal;">False</span><br/>
<span style="color: Gray;">&gt;&gt;&gt;</span> rp.<span style="color: #05a;">can_fetch</span><span style="color: Olive;">(</span><span style="color: #a11;">"*"</span><span style="color: Gray;">,</span> <span style="color: #a11;">"http://www.musi-cal.com/"</span><span style="color: Olive;">)</span><br/>
<span style="color: Teal;">True</span><br/>
</div></div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>