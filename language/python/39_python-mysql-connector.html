<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python MySQL - mysql-connector 驱动</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python MySQL - mysql-connector 驱动</h1>&#13;
<p>MySQL 是最流行的关系型数据库管理系统，如果你不熟悉 MySQL，可以阅读我们的 <a href="/mysql/mysql-tutorial.html" rel="noopener noreferrer" target="_blank">MySQL 教程。</a></p>&#13;
<p>本章节我们为大家介绍使用 <strong>mysql-connector</strong> 来连接使用 MySQL， <strong>mysql-connector</strong> 是 <strong>MySQL</strong> 官方提供的驱动器。</p>&#13;
<p>我们可以使用 <strong>pip</strong> 命令来安装 <strong>mysql-connector</strong>：</p>&#13;
&#13;
<pre>python -m pip install mysql-connector</pre>&#13;
&#13;
<p>使用以下代码测试 mysql-connector 是否安装成功：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span></div>&#13;
</div>&#13;
</div>&#13;
<p>执行以上代码，如果没有产生错误，表明安装成功。</p>&#13;
&#13;
&#13;
&#13;
&#13;
<blockquote><p>注<strong>意：</strong>如果你的 MySQL 是 8.0 版本，密码插件验证方式发生了变化，早期版本为 mysql_native_password，8.0 版本为 caching_sha2_password，所以需要做些改变：</p>&#13;
&#13;
<p>先修改 my.ini 配置：</p>&#13;
&#13;
<pre>[mysqld]&#13;
default_authentication_plugin=mysql_native_password</pre>&#13;
&#13;
<p>然后在 mysql 下执行以下命令来修改密码：</p>&#13;
&#13;
<pre>ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '新密码';</pre>&#13;
&#13;
<p>更多内容可以参考：<a href="https://www.runoob.com/note/45833" rel="noopener noreferrer" target="_blank">Python MySQL8.0 链接问题</a>。</p></blockquote>&#13;
&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>创建数据库连接</h2>&#13;
&#13;
<p>可以使用以下代码来连接数据库：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,       </span><span class="hl-comment"># 数据库主机地址</span><span class="hl-code">
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">yourusername</span><span class="hl-quotes">"</span><span class="hl-code">,    </span><span class="hl-comment"># 数据库用户名</span><span class="hl-code">
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">yourpassword</span><span class="hl-quotes">"</span><span class="hl-code">   </span><span class="hl-comment"># 数据库密码</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mydb</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h3>创建数据库</h3>&#13;
<p>创建数据库使用 "CREATE DATABASE" 语句，以下创建一个名为 runoob_db 的数据库：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">CREATE DATABASE runoob_db</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>创建数据库前我们也可以使用 "SHOW DATABASES" 语句来查看数据库是否存在：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<p>输出所有数据库列表：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SHOW DATABASES</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">mycursor</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>或者我们可以直接连接数据库，如果数据库不存在，会输出错误信息：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>创建数据表</h2>&#13;
<p>创建数据表使用 <strong>"CREATE TABLE"</strong> 语句，创建数据表前，需要确保数据库已存在，以下创建一个名为 <strong>sites</strong> 的数据表：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">CREATE TABLE sites (name VARCHAR(255), url VARCHAR(255))</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
执行成功后，我们可以看到数据库创建的数据表 sites，字段为  name 和 url。&#13;
&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2018/08/0F64A883-20A0-4CA3-9FE6-B6CE3F39AB56.png"/></p>&#13;
&#13;
<strong>我们也可以使用  <strong>"SHOW TABLES"</strong>  语句来查看数据表是否已存在：</strong>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SHOW TABLES</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">mycursor</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h3>主键设置</h3>&#13;
<p>创建表的时候我们一般都会设置一个主键（PRIMARY KEY），我们可以使用 <strong>"INT AUTO_INCREMENT PRIMARY KEY"</strong> 语句来创建一个主键，主键起始值为 1，逐步递增。</p>&#13;
&#13;
<p>如果我们的表已经创建，我们需要使用 <strong>ALTER TABLE</strong> 来给表添加主键：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<p>给 sites 表添加主键。</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">ALTER TABLE sites ADD COLUMN id INT AUTO_INCREMENT PRIMARY KEY</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>如果你还未创建 sites 表，可以直接使用以下代码创建。</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<p>给表创建主键。</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">CREATE TABLE sites (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(255), url VARCHAR(255))</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>插入数据</h2>&#13;
<p>插入数据使用 <strong>"INSERT INTO"</strong> 语句：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<p>向 sites 表插入一条记录。</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">INSERT INTO sites (name, url) VALUES (%s, %s)</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">RUNOOB</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">https://www.runoob.com</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">    </span><span class="hl-comment"># 数据表内容有更新，必须使用到该语句</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">记录插入成功。</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1 记录插入成功&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<h3>批量插入</h3>&#13;
<p>批量插入使用 <strong>executemany()</strong> 方法，该方法的第二个参数是一个元组列表，包含了我们要插入的数据：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
<p>向 sites 表插入多条记录。</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">INSERT INTO sites (name, url) VALUES (%s, %s)</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-code">
  </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Google</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.google.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">,
  </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Github</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.github.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">,
  </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Taobao</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.taobao.com</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">,
  </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">stackoverflow</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.stackoverflow.com/</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">]</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">executemany</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">    </span><span class="hl-comment"># 数据表内容有更新，必须使用到该语句</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">记录插入成功。</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
4 记录插入成功。&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p>执行以上代码后，我们可以看看数据表的记录：</p>&#13;
&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2018/08/E97E7F89-284A-4319-B5AB-0375D87A7D74.png"/></p>&#13;
&#13;
<p>如果我们想在数据记录插入后，获取该记录的 ID ，可以使用以下代码：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">INSERT INTO sites (name, url) VALUES (%s, %s)</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Zhihu</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">https://www.zhihu.com</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1 条记录已插入, ID:</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">lastrowid</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1 条记录已插入, ID: 6&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>查询数据</h2>&#13;
<p>查询数据使用 <strong>SELECT</strong> 语句：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">     </span><span class="hl-comment"># fetchall() 获取所有记录</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
(2, 'Google', 'https://www.google.com')&#13;
(3, 'Github', 'https://www.github.com')&#13;
(4, 'Taobao', 'https://www.taobao.com')&#13;
(5, 'stackoverflow', 'https://www.stackoverflow.com/')&#13;
(6, 'Zhihu', 'https://www.zhihu.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p>也可以读取指定的字段数据：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT name, url FROM sites</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
('RUNOOB', 'https://www.runoob.com')&#13;
('Google', 'https://www.google.com')&#13;
('Github', 'https://www.github.com')&#13;
('Taobao', 'https://www.taobao.com')&#13;
('stackoverflow', 'https://www.stackoverflow.com/')&#13;
('Zhihu', 'https://www.zhihu.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p>如果我们只想读取一条数据，可以使用 <strong>fetchone()</strong> 方法：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py:</h2> &#13;
&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchone</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">myresult</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<h3>where 条件语句</h3>&#13;
<p>如果我们要读取指定条件的数据，可以使用 <strong>where</strong> 语句：</p>&#13;
&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>读取 name 字段为 RUNOOB 的记录：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites WHERE name ='RUNOOB'</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>也可以使用通配符 <span class="marked">%</span>：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites WHERE url LIKE '%oo%'</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
(2, 'Google', 'https://www.google.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p>为了防止数据库查询发生 SQL 注入的攻击，我们可以使用 <span class="marked">%s</span> 占位符来转义查询的条件：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites WHERE name = %s</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">na</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">RUNOOB</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">na</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>排序</h3>&#13;
<p>查询结果排序可以使用 <strong>ORDER BY</strong> 语句，默认的排序方式为升序，关键字为 <strong>ASC</strong>，如果要设置降序排序，可以设置关键字 <strong>DESC</strong>。</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>按 name 字段字母的升序排序：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites ORDER BY name</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(3, 'Github', 'https://www.github.com')&#13;
(2, 'Google', 'https://www.google.com')&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
(5, 'stackoverflow', 'https://www.stackoverflow.com/')&#13;
(4, 'Taobao', 'https://www.taobao.com')&#13;
(6, 'Zhihu', 'https://www.zhihu.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p>降序排序实例：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>按 name 字段字母的降序排序：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites ORDER BY name DESC</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(6, 'Zhihu', 'https://www.zhihu.com')&#13;
(4, 'Taobao', 'https://www.taobao.com')&#13;
(5, 'stackoverflow', 'https://www.stackoverflow.com/')&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
(2, 'Google', 'https://www.google.com')&#13;
(3, 'Github', 'https://www.github.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<h3>Limit</h3>&#13;
<p>如果我们要设置查询的数据量，可以通过 <strong>"LIMIT"</strong> 语句来指定</p>&#13;
&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>读取前 3 条记录：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites LIMIT 3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(1, 'RUNOOB', 'https://www.runoob.com')&#13;
(2, 'Google', 'https://www.google.com')&#13;
(3, 'Github', 'https://www.github.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>也可以指定起始位置，使用的关键字是 <strong>OFFSET</strong>：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>从第二条开始读取前 3 条记录：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM sites LIMIT 3 OFFSET 1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 0 为 第一条，1 为第二条，以此类推</span><span class="hl-code">
 
</span><span class="hl-identifier">myresult</span><span class="hl-code"> = </span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">myresult</span><span class="hl-code">:
  </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
(2, 'Google', 'https://www.google.com')&#13;
(3, 'Github', 'https://www.github.com')&#13;
(4, 'Taobao', 'https://www.taobao.com')&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<hr/>&#13;
<h2>删除记录</h2>&#13;
&#13;
<p>删除记录使用 <strong>"DELETE FROM"</strong> 语句：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<p>删除 name 为 stackoverflow 的记录：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">DELETE FROM sites WHERE name = 'stackoverflow'</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string"> 条记录删除</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1  条记录删除&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<p><strong>注意：</strong>要慎重使用删除语句，删除语句要确保指定了 WHERE 条件语句，否则会导致整表数据被删除。</p>&#13;
<p>为了防止数据库查询发生 SQL 注入的攻击，我们可以使用 <span class="marked">%s</span> 占位符来转义删除语句的条件：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">DELETE FROM sites WHERE name = %s</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">na</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">stackoverflow</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">na</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string"> 条记录删除</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1  条记录删除&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<hr/>&#13;
<h2>更新表数据</h2>&#13;
<p>数据表更新使用 <strong>"UPDATE"</strong> 语句：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
 <p>将 name 为 Zhihu 的字段数据改为 ZH：</p>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">UPDATE sites SET name = 'ZH' WHERE name = 'Zhihu'</span><span class="hl-quotes">"</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string"> 条记录被修改</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1  条记录被修改&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
<p><strong>注意：</strong>UPDATE 语句要确保指定了 WHERE 条件语句，否则会导致整表数据被更新。</p>&#13;
<p>为了防止数据库查询发生 SQL 注入的攻击，我们可以使用 %s 占位符来转义更新语句的条件：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">UPDATE sites SET name = %s WHERE name = %s</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Zhihu</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">ZH</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-code">, </span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">rowcount</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string"> 条记录被修改</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行代码，输出结果为：</p>&#13;
<div class="example_code">&#13;
<pre>&#13;
1  条记录被修改&#13;
</pre>&#13;
</div>&#13;
</div>&#13;
&#13;
<hr/>&#13;
<h2>删除表</h2>&#13;
<p>删除表使用 <strong>"DROP TABLE"</strong> 语句， <span class="marked">IF EXISTS</span>  关键字是用于判断表是否存在，只有在存在的情况才删除：</p>&#13;
<div class="example"> &#13;
<h2 class="example">demo_mysql_test.py</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">
 
</span><span class="hl-identifier">mydb</span><span class="hl-code"> = </span><span class="hl-identifier">mysql</span><span class="hl-code">.</span><span class="hl-identifier">connector</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">passwd</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">,
  </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">runoob_db</span><span class="hl-quotes">"</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">mycursor</span><span class="hl-code"> = </span><span class="hl-identifier">mydb</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">DROP TABLE IF EXISTS sites</span><span class="hl-quotes">"</span><span class="hl-code">  </span><span class="hl-comment"># 删除数据表 sites</span><span class="hl-code">
 
</span><span class="hl-identifier">mycursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span></div>&#13;
&#13;
</div>&#13;
</div>&#13;
&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>