<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python uWSGI  安装配置</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python uWSGI  安装配置</h1>&#13;
<p>本文主要介绍如何部署简单的 WSGI 应用和常见的 Web 框架。</p>&#13;
<p>以 Ubuntu/Debian 为例，先安装依赖包：</p>&#13;
&#13;
<pre>apt-get install build-essential python-dev</pre>&#13;
&#13;
&#13;
<h3>Python 安装 uWSGI</h3>&#13;
<p><strong>1、通过 pip 命令：</strong></p>&#13;
<pre>pip install uwsgi</pre>&#13;
&#13;
<p><strong>2、下载安装脚本：</strong></p>&#13;
<pre>curl http://uwsgi.it/install | bash -s default /tmp/uwsgi</pre>&#13;
&#13;
<p>将 uWSGI 二进制安装到 /tmp/uwsgi ，你可以修改它。</p>&#13;
&#13;
&#13;
<p><strong>3、源代码安装：</strong></p>&#13;
<pre>wget http://projects.unbit.it/downloads/uwsgi-latest.tar.gz&#13;
tar zxvf uwsgi-latest.tar.gz&#13;
cd uwsgi-latest&#13;
make</pre>&#13;
&#13;
<p>安装完成后，在当前目录下，你会获得一个 uwsgi 二进制文件。</p>&#13;
<hr/><h2>&#13;
第一个 WSGI 应用</h2>&#13;
<p>让我们从一个简单的 "Hello World" 开始，创建文件 foobar.py，代码如下：</p>&#13;
&#13;
<pre>def application(env, start_response):&#13;
    start_response('200 OK', [('Content-Type','text/html')])&#13;
    return [b"Hello World"]</pre>&#13;
&#13;
<p>uWSGI Python 加载器将会搜索的默认函数 <span class="marked">application</span> 。</p>&#13;
&#13;
<p>接下来我们启动 uWSGI 来运行一个 HTTP 服务器，将程序部署在HTTP端口 9090 上：</p>&#13;
<pre>uwsgi --http :9090 --wsgi-file foobar.py</pre>&#13;
&#13;
<h3>&#13;
添加并发和监控&#13;
</h3>&#13;
<p>默认情况下，uWSGI 启动一个单一的进程和一个单一的线程。</p>&#13;
&#13;
<p>你可以用 <span class="marked">--processes</span> 选项添加更多的进程，或者使用 <span class="marked">--threads</span> 选项添加更多的线程 ，也可以两者同时使用。</p>&#13;
&#13;
<pre>uwsgi --http :9090 --wsgi-file foobar.py --master --processes 4 --threads 2</pre>&#13;
&#13;
<p>以上命令将会生成 4 个进程, 每个进程有 2 个线程。</p>&#13;
<p>如果你要执行监控任务，可以使用 stats 子系统，监控的数据格式是 JSON：</p>&#13;
<pre>uwsgi --http :9090 --wsgi-file foobar.py --master --processes 4 --threads 2 --stats 127.0.0.1:9191</pre>&#13;
&#13;
<p>我们可以安装 uwsgitop（类似 Linux top 命令） 来查看监控数据：</p>&#13;
<pre>pip install uwsgitop</pre>&#13;
<hr/><h2>&#13;
结合 Web 服务器使用&#13;
</h2>&#13;
<p>我们可以将 uWSGI 和 Nginx Web 服务器结合使用，实现更高的并发性能。</p>&#13;
&#13;
<p>一个常用的nginx配置如下：</p>&#13;
&#13;
<pre>location / {&#13;
    include uwsgi_params;&#13;
    uwsgi_pass 127.0.0.1:3031;&#13;
}</pre>&#13;
&#13;
<p>以上代码表示使用 nginx 接收的 Web 请求传递给端口为 3031 的 uWSGI 服务来处理。</p>&#13;
&#13;
<p>现在，我们可以生成 uWSGI 来本地使用 uwsgi 协议：</p>&#13;
&#13;
<pre>uwsgi --socket 127.0.0.1:3031 --wsgi-file foobar.py --master --processes 4 --threads 2 --stats 127.0.0.1:9191</pre>&#13;
&#13;
<p>如果你的 Web 服务器使用 HTTP，那么你必须告诉 uWSGI 本地使用 http 协议 (这与会自己生成一个代理的–http不同):</p>&#13;
&#13;
<pre>uwsgi --http-socket 127.0.0.1:3031 --wsgi-file foobar.py --master --processes 4 --threads 2 --stats 127.0.0.1:9191</pre>&#13;
&#13;
<h3>&#13;
部署 Django&#13;
</h3>&#13;
<p>Django 是最常使用的 Python web 框架，假设 Django 项目位于 /home/foobar/myproject:</p>&#13;
&#13;
<pre>uwsgi --socket 127.0.0.1:3031 --chdir /home/foobar/myproject/ --wsgi-file myproject/wsgi.py --master --processes 4 --threads 2 --stats 127.0.0.1:9191</pre>&#13;
&#13;
<p><span class="marked">--chdir</span> 用于指定项目路径。</p>&#13;
&#13;
<p>我们可以把以上的命令弄成一个 yourfile.ini 配置文件:</p>&#13;
&#13;
<pre>[uwsgi]&#13;
socket = 127.0.0.1:3031&#13;
chdir = /home/foobar/myproject/&#13;
wsgi-file = myproject/wsgi.py&#13;
processes = 4&#13;
threads = 2&#13;
stats = 127.0.0.1:9191</pre>&#13;
&#13;
<p>接下来你只需要执行以下命令即可：</p>&#13;
&#13;
<pre>uwsgi yourfile.ini</pre>&#13;
&#13;
<h3>&#13;
部署 Flask&#13;
</h3>&#13;
<p>Flask 是一个流行的 Python web 框架。</p>&#13;
<p>创建文件 myflaskapp.py ，代码如下：</p>&#13;
<pre>from flask import Flask&#13;
&#13;
app = Flask(__name__)&#13;
&#13;
@app.route('/')&#13;
def index():&#13;
    return "&lt;span style='color:red'&gt;I am app 1&lt;/span&gt;"</pre>&#13;
<p>执行以下命令：</p>&#13;
&#13;
<pre>uwsgi --socket 127.0.0.1:3031 --wsgi-file myflaskapp.py --callable app --processes 4 --threads 2 --stats 127.0.0.1:9191</pre>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>