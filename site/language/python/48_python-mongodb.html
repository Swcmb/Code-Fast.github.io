<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python MongoDB
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python MongoDB&#13;
</h1>&#13;
<p>MongoDB 是目前最流行的 NoSQL 数据库之一，使用的数据类型 BSON（类似 JSON）。</p>&#13;
<p>MongoDB 数据库安装与介绍可以查看我们的 <a href="/mongodb/mongodb-tutorial.html" target="_blank">MongoDB 教程。</a></p>&#13;
<hr/>&#13;
<h2>PyMongo</h2>&#13;
<p>Python 要连接 MongoDB 需要 MongoDB 驱动，这里我们使用 PyMongo 驱动来连接。</p>&#13;
<h3>pip 安装</h3>&#13;
<p>pip 是一个通用的 Python 包管理工具，提供了对 Python 包的查找、下载、安装、卸载的功能。</p>&#13;
<p>安装 pymongo:</p>&#13;
&#13;
<pre>$ python3 -m pip3 install pymongo</pre>&#13;
&#13;
<p>也可以指定安装的版本:</p>&#13;
&#13;
<pre>$ python3 -m pip3 install pymongo==3.5.1</pre>&#13;
&#13;
<p>更新 pymongo 命令：</p>&#13;
&#13;
<pre>$ python3 -m pip3 install --upgrade pymongo</pre>&#13;
&#13;
<h3>easy_install 安装</h3>&#13;
<p>旧版的 Python 可以使用 easy_install 来安装，easy_install 也是 Python 包管理工具。</p>&#13;
&#13;
<pre>$ python -m easy_install pymongo</pre>&#13;
&#13;
<p>更新 pymongo 命令：</p>&#13;
<pre>$ python -m easy_install -U pymongo</pre>&#13;
&#13;
<h3>&#13;
测试 PyMongo&#13;
</h3>&#13;
<p>接下来我们可以创建一个测试文件 demo_test_mongodb.py，代码如下：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_test_mongodb.py 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymongo</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>执行以上代码文件，如果没有出现错误，表示安装成功。</p>&#13;
&#13;
<hr/>&#13;
<h2>创建数据库</h2>&#13;
<h3>创建一个数据库</h3>&#13;
<p>创建数据库需要使用 MongoClient 对象，并且指定连接的 URL 地址和要创建的数据库名。</p><p>如下实例中，我们创建的数据库 runoobdb : </p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymongo</span><span class="hl-code">
 
</span><span class="hl-identifier">myclient</span><span class="hl-code"> = </span><span class="hl-identifier">pymongo</span><span class="hl-code">.</span><span class="hl-identifier">MongoClient</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mongodb://localhost:27017/</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">myclient</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">runoobdb</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
&#13;
&#13;
<blockquote><p><strong>注意:</strong> 在 MongoDB 中，数据库只有在内容插入后才会创建! 就是说，数据库创建后要创建集合(数据表)并插入一个文档(记录)，数据库才会真正创建。</p></blockquote>&#13;
&#13;
&#13;
&#13;
&#13;
<h3>判断数据库是否已存在</h3>&#13;
<p>我们可以读取 MongoDB 中的所有数据库，并判断指定的数据库是否存在：</p>&#13;
&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymongo</span><span class="hl-code">
 
</span><span class="hl-identifier">myclient</span><span class="hl-code"> = </span><span class="hl-identifier">pymongo</span><span class="hl-code">.</span><span class="hl-identifier">MongoClient</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">mongodb://localhost:27017/</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">dblist</span><span class="hl-code"> = </span><span class="hl-identifier">myclient</span><span class="hl-code">.</span><span class="hl-identifier">list_database_names</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-comment"># dblist = myclient.database_names() </span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">runoobdb</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">dblist</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">数据库已存在！</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
&#13;
<blockquote><p><strong>注意：</strong>database_names 在最新版本的 Python 中已废弃，Python3.7+ 之后的版本改为了 list_database_names()。</p>&#13;
</blockquote>&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>创建集合</h2>&#13;
&#13;
<p>MongoDB 中的集合类似 SQL 的表。</p>&#13;
&#13;
<h3>创建一个集合</h3>&#13;
&#13;
<p>MongoDB 使用数据库对象来创建集合，实例如下：</p>&#13;
&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymongo</span><span class="hl-code">
 
</span><span class="hl-identifier">myclient</span><span class="hl-code"> = </span><span class="hl-identifier">pymongo</span><span class="hl-code">.</span><span class="hl-identifier">MongoClient</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mongodb://localhost:27017/</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">myclient</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">runoobdb</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span><span class="hl-code">
 
</span><span class="hl-identifier">mycol</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">sites</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
&#13;
&#13;
&#13;
&#13;
<blockquote><p><strong>注意:</strong> 在 MongoDB 中，集合只有在内容插入后才会创建! 就是说，创建集合(数据表)后要再插入一个文档(记录)，集合才会真正创建。</p></blockquote>&#13;
&#13;
&#13;
&#13;
&#13;
<h3>判断集合是否已存在</h3>&#13;
&#13;
&#13;
<p>我们可以读取 MongoDB 数据库中的所有集合，并判断指定的集合是否存在：</p>&#13;
&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymongo</span><span class="hl-code">
 
</span><span class="hl-identifier">myclient</span><span class="hl-code"> = </span><span class="hl-identifier">pymongo</span><span class="hl-code">.</span><span class="hl-identifier">MongoClient</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">mongodb://localhost:27017/</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">myclient</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">runoobdb</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">
 
</span><span class="hl-identifier">collist</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">. </span><span class="hl-identifier">list_collection_names</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-comment"># collist = mydb.collection_names()</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">sites</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">collist</span><span class="hl-code">:   </span><span class="hl-comment"># 判断 sites 集合是否存在</span><span class="hl-code">
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">集合已存在！</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<blockquote><p><strong>注意：</strong>collection_names 在最新版本的 Python 中已废弃，Python3.7+ 之后的版本改为了 list_collection_names()。</p></blockquote>&#13;
<hr/><h2>增、删、改、查等操作</h2>&#13;
<p>下表列出了 MongoDB 的更多操作，详情可点击具体链接：</p>&#13;
<table class="reference">&#13;
<tr>&#13;
<th>序号</th>&#13;
<th>功能</th>&#13;
</tr>&#13;
<tr>&#13;
<td>1</td>&#13;
<td><a href="/python3/python-mongodb-insert-document.html" target="_blank">添加数据</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>2</td>&#13;
<td><a href="/python3/python-mongodb-query-document.html" target="_blank">查询数据</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>3</td>&#13;
<td><a href="/python3/python-mongodb-update-document.html" target="_blank">修改数据</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>4</td>&#13;
<td><a href="/python3/python-mongodb-sort.html" target="_blank">数据排序</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>5</td>&#13;
<td><a href="/python3/python-mongodb-delete-document.html" rel="noopener" target="_blank">删除数据</a></td>&#13;
</tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>