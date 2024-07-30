<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 MySQL 数据库连接 - PyMySQL 驱动</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 MySQL 数据库连接 - PyMySQL 驱动</h1>&#13;
<p>本文我们为大家介绍 Python3 使用 <a href="https://github.com/PyMySQL/PyMySQL" target="_blank" rel="noopener">PyMySQL</a> 连接数据库，并实现简单的增删改查。</p>&#13;
<h3>什么是 PyMySQL？</h3>&#13;
<p>PyMySQL 是在 Python3.x 版本中用于连接 MySQL 服务器的一个库，Python2 中则使用 mysqldb。</p>&#13;
<p>PyMySQL 遵循 Python 数据库 API v2.0 规范，并包含了 pure-Python MySQL 客户端库。</p>&#13;
<hr/>&#13;
<h2>PyMySQL 安装</h2>&#13;
<p>在使用 PyMySQL 之前，我们需要确保 PyMySQL 已安装。</p>&#13;
<p>PyMySQL 下载地址：<a href="https://github.com/PyMySQL/PyMySQL" rel="noopener" target="_blank">https://github.com/PyMySQL/PyMySQL</a>。</p>&#13;
<p>如果还未安装，我们可以使用以下命令安装最新版的 PyMySQL：</p>&#13;
<pre>&#13;
$ pip3 install PyMySQL&#13;
</pre>&#13;
<p>如果你的系统不支持 pip 命令，可以使用以下方式安装：</p>&#13;
&#13;
<p>1、使用 git 命令下载安装包安装(你也可以手动下载)：</p>&#13;
<pre>&#13;
$ git clone https://github.com/PyMySQL/PyMySQL&#13;
$ cd PyMySQL/&#13;
$ python3 setup.py install&#13;
</pre>&#13;
<p>2、如果需要制定版本号，可以使用 curl 命令来安装：</p>&#13;
<pre>&#13;
$ # X.X 为 PyMySQL 的版本号&#13;
$ curl -L https://github.com/PyMySQL/PyMySQL/tarball/pymysql-X.X | tar xz&#13;
$ cd PyMySQL*&#13;
$ python3 setup.py install&#13;
$ # 现在你可以删除 PyMySQL* 目录&#13;
</pre>&#13;
<p><strong>注意：</strong>请确保您有root权限来安装上述模块。</p>&#13;
<blockquote><p>安装的过程中可能会出现"ImportError: No module named setuptools"的错误提示，意思是你没有安装setuptools，你可以访问<a href="https://pypi.python.org/pypi/setuptools" target="_blank" rel="noopener">https://pypi.python.org/pypi/setuptools</a> 找到各个系统的安装方法。&#13;
</p>&#13;
<p>Linux 系统安装实例：</p>&#13;
<pre>&#13;
$ wget https://bootstrap.pypa.io/ez_setup.py&#13;
$ python3 ez_setup.py&#13;
</pre>&#13;
</blockquote>&#13;
<hr/>&#13;
<h2>数据库连接</h2>&#13;
<p>连接数据库前，请先确认以下事项：</p>&#13;
<ul>&#13;
<li>您已经创建了数据库 TESTDB.</li>&#13;
<li>在 TESTDB 数据库中您已经创建了表 EMPLOYEE</li>&#13;
<li>EMPLOYEE 表字段为 FIRST_NAME, LAST_NAME, AGE, SEX 和 INCOME。</li>&#13;
<li>连接数据库 TESTDB 使用的用户名为 "testuser"，密码为 "test123"，你可以可以自己设定或者直接使用 root 用户名及其密码，MySQL 数据库用户授权请使用 Grant 命令。</li>&#13;
<li>在你的机子上已经安装了 Python  <strong>pymysql</strong> 模块。</li>&#13;
<li>如果您对 sql 语句不熟悉，可以访问我们的 <a href="/sql/sql-tutorial.html">SQL基础教程</a>&#13;
</li>&#13;
</ul>&#13;
<h3>实例：</h3>&#13;
<p>以下实例链接 Mysql 的 TESTDB 数据库：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用 cursor() 方法创建一个游标对象 cursor</span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用 execute()  方法执行 SQL 查询 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SELECT VERSION()</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用 fetchone() 方法获取单条数据.</span><span class="hl-code">
</span><span class="hl-identifier">data</span><span class="hl-code"> = </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchone</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Database version : %s </span><span class="hl-quotes">"</span><span class="hl-code"> % </span><span class="hl-identifier">data</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>执行以上脚本输出结果如下：</p>&#13;
<pre>&#13;
Database version : 5.5.20-log&#13;
</pre>&#13;
<hr/>&#13;
<h2>&#13;
创建数据库表</h2><p>&#13;
如果数据库连接存在我们可以使用execute()方法来为数据库创建表，如下所示创建表EMPLOYEE：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用 cursor() 方法创建一个游标对象 cursor</span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用 execute() 方法执行 SQL，如果表存在则删除</span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">DROP TABLE IF EXISTS EMPLOYEE</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用预处理语句创建表</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"""</span><span class="hl-string">CREATE TABLE EMPLOYEE (
         FIRST_NAME  CHAR(20) NOT NULL,
         LAST_NAME  CHAR(20),
         AGE INT,  
         SEX CHAR(1),
         INCOME FLOAT )</span><span class="hl-quotes">"""</span><span class="hl-code">
 
</span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>数据库插入操作</h2><p>&#13;
以下实例使用执行 SQL INSERT 语句向表 EMPLOYEE 插入记录：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用cursor()方法获取操作游标 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># SQL 插入语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"""</span><span class="hl-string">INSERT INTO EMPLOYEE(FIRST_NAME,
         LAST_NAME, AGE, SEX, INCOME)
         VALUES ('Mac', 'Mohan', 20, 'M', 2000)</span><span class="hl-quotes">"""</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行sql语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 提交到数据库执行</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-comment"># 如果发生错误则回滚</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">rollback</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上例子也可以写成如下形式：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用cursor()方法获取操作游标 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># SQL 插入语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">INSERT INTO EMPLOYEE(FIRST_NAME, \
       LAST_NAME, AGE, SEX, INCOME) \
       VALUES ('%s', '%s',  %s,  '%s',  %s)</span><span class="hl-quotes">"</span><span class="hl-code"> % \
       </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Mac</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">Mohan</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">M</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-number">2000</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行sql语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 执行sql语句</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-comment"># 发生错误时回滚</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">rollback</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以下代码使用变量向SQL语句中传递参数:</p>&#13;
<pre>&#13;
..................................&#13;
user_id = "test123"&#13;
password = "password"&#13;
&#13;
con.execute('insert into Login values( %s,  %s)' % \&#13;
             (user_id, password))&#13;
..................................&#13;
</pre>&#13;
<hr/>&#13;
<h2>数据库查询操作</h2>&#13;
<p>Python查询Mysql使用 fetchone() 方法获取单条数据, 使用fetchall() 方法获取多条数据。</p>&#13;
<ul> <li><b>fetchone():</b> 该方法获取下一个查询结果集。结果集是一个对象</li> <li><b>fetchall(): </b>接收全部的返回结果行.</li> <li><b>rowcount:</b> 这是一个只读属性，并返回执行execute()方法后影响的行数。</li> </ul>&#13;
<h3>实例：</h3>&#13;
<p>查询EMPLOYEE表中salary（工资）字段大于1000的所有数据：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用cursor()方法获取操作游标 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># SQL 查询语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT * FROM EMPLOYEE \
       WHERE INCOME &gt; %s</span><span class="hl-quotes">"</span><span class="hl-code"> % </span><span class="hl-brackets">(</span><span class="hl-number">1000</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行SQL语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 获取所有记录列表</span><span class="hl-code">
   </span><span class="hl-identifier">results</span><span class="hl-code"> = </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">fetchall</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-identifier">row</span><span class="hl-code"> </span><span class="hl-reserved">in</span><span class="hl-code"> </span><span class="hl-identifier">results</span><span class="hl-code">:
      </span><span class="hl-identifier">fname</span><span class="hl-code"> = </span><span class="hl-identifier">row</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code">
      </span><span class="hl-identifier">lname</span><span class="hl-code"> = </span><span class="hl-identifier">row</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-code">
      </span><span class="hl-identifier">age</span><span class="hl-code"> = </span><span class="hl-identifier">row</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code">
      </span><span class="hl-identifier">sex</span><span class="hl-code"> = </span><span class="hl-identifier">row</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-code">
      </span><span class="hl-identifier">income</span><span class="hl-code"> = </span><span class="hl-identifier">row</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code">
       </span><span class="hl-comment"># 打印结果</span><span class="hl-code">
      </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">fname=%s,lname=%s,age=%s,sex=%s,income=%s</span><span class="hl-quotes">"</span><span class="hl-code"> % \
             </span><span class="hl-brackets">(</span><span class="hl-identifier">fname</span><span class="hl-code">, </span><span class="hl-identifier">lname</span><span class="hl-code">, </span><span class="hl-identifier">age</span><span class="hl-code">, </span><span class="hl-identifier">sex</span><span class="hl-code">, </span><span class="hl-identifier">income</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: unable to fetch data</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上脚本执行结果如下：</p>&#13;
<pre>&#13;
fname=Mac, lname=Mohan, age=20, sex=M, income=2000&#13;
</pre><hr/>&#13;
<h2>数据库更新操作</h2>&#13;
<p>更新操作用于更新数据表的数据，以下实例将 TESTDB 表中 SEX 为 'M' 的 AGE 字段递增 1：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用cursor()方法获取操作游标 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># SQL 更新语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">UPDATE EMPLOYEE SET AGE = AGE + 1 WHERE SEX = '%c'</span><span class="hl-quotes">"</span><span class="hl-code"> % </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">M</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行SQL语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 提交到数据库执行</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-comment"># 发生错误时回滚</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">rollback</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>删除操作</h2>&#13;
<p>删除操作用于删除数据表中的数据，以下实例演示了删除数据表 EMPLOYEE 中 AGE 大于 20 的所有数据：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">pymysql</span><span class="hl-code">
 
</span><span class="hl-comment"># 打开数据库连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code"> = </span><span class="hl-identifier">pymysql</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">host</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">testuser</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">password</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">test123</span><span class="hl-quotes">'</span><span class="hl-code">,
                     </span><span class="hl-identifier">database</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">TESTDB</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 使用cursor()方法获取操作游标 </span><span class="hl-code">
</span><span class="hl-identifier">cursor</span><span class="hl-code"> = </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">cursor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># SQL 删除语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">DELETE FROM EMPLOYEE WHERE AGE &gt; %s</span><span class="hl-quotes">"</span><span class="hl-code"> % </span><span class="hl-brackets">(</span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行SQL语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 提交修改</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-comment"># 发生错误时回滚</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">rollback</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 关闭连接</span><span class="hl-code">
</span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>执行事务</h2>&#13;
<p>事务机制可以确保数据一致性。</p>&#13;
<p>事务应该具有4个属性：原子性、一致性、隔离性、持久性。这四个属性通常称为ACID特性。</p>&#13;
<ul> <li>原子性（atomicity）。一个事务是一个不可分割的工作单位，事务中包括的诸操作要么都做，要么都不做。</li><li> 一致性（consistency）。事务必须是使数据库从一个一致性状态变到另一个一致性状态。一致性与原子性是密切相关的。</li><li> 隔离性（isolation）。一个事务的执行不能被其他事务干扰。即一个事务内部的操作及使用的数据对并发的其他事务是隔离的，并发执行的各个事务之间不能互相干扰。</li><li> 持久性（durability）。持续性也称永久性（permanence），指一个事务一旦提交，它对数据库中数据的改变就应该是永久性的。接下来的其他操作或故障不应该对其有任何影响。 </li></ul>&#13;
<p>Python DB API 2.0 的事务提供了两个方法 commit 或 rollback。</p>&#13;
<h3>实例</h3>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment"># SQL删除记录语句</span><span class="hl-code">
</span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">DELETE FROM EMPLOYEE WHERE AGE &gt; %s</span><span class="hl-quotes">"</span><span class="hl-code"> % </span><span class="hl-brackets">(</span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">try</span><span class="hl-code">:
   </span><span class="hl-comment"># 执行SQL语句</span><span class="hl-code">
   </span><span class="hl-identifier">cursor</span><span class="hl-code">.</span><span class="hl-identifier">execute</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-comment"># 向数据库提交</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">commit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code">:
   </span><span class="hl-comment"># 发生错误时回滚</span><span class="hl-code">
   </span><span class="hl-identifier">db</span><span class="hl-code">.</span><span class="hl-identifier">rollback</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>对于支持事务的数据库， 在Python数据库编程中，当游标建立之时，就自动开始了一个隐形的数据库事务。 </p>&#13;
<p>commit()方法游标的所有更新操作，rollback（）方法回滚当前游标的所有操作。每一个方法都开始了一个新的事务。</p>&#13;
<hr/>&#13;
<h2>错误处理</h2>&#13;
<p>DB API中定义了一些数据库操作的错误及异常，下表列出了这些错误和异常:</p>&#13;
<table class="reference"> <tbody><tr> <th style="width:15%">异常</th><th>描述</th> </tr> <tr><td>Warning</td><td>当有严重警告时触发，例如插入数据是被截断等等。必须是 StandardError 的子类。</td></tr> <tr><td>Error</td><td>警告以外所有其他错误类。必须是 StandardError 的子类。</td></tr> <tr><td>InterfaceError</td><td>当有数据库接口模块本身的错误（而不是数据库的错误）发生时触发。 必须是Error的子类。</td></tr> <tr><td>DatabaseError</td><td>和数据库有关的错误发生时触发。 必须是Error的子类。</td></tr> <tr><td>DataError</td><td>当有数据处理时的错误发生时触发，例如：除零错误，数据超范围等等。 必须是DatabaseError的子类。</td></tr> <tr><td>OperationalError</td><td>指非用户控制的，而是操作数据库时发生的错误。例如：连接意外断开、 数据库名未找到、事务处理失败、内存分配错误等等操作数据库是发生的错误。 必须是DatabaseError的子类。</td></tr> <tr><td>IntegrityError</td><td>完整性相关的错误，例如外键检查失败等。必须是DatabaseError子类。</td></tr> <tr><td>InternalError</td><td> 数据库的内部错误，例如游标（cursor）失效了、事务同步失败等等。 必须是DatabaseError子类。</td></tr> <tr><td>ProgrammingError</td><td>程序错误，例如数据表（table）没找到或已存在、SQL语句语法错误、 参数数量错误等等。必须是DatabaseError的子类。</td></tr> <tr><td>NotSupportedError</td><td>不支持错误，指使用了数据库不支持的函数或API等。例如在连接对象上 使用.rollback()函数，然而数据库并不支持事务或者事务已关闭。 必须是DatabaseError的子类。</td></tr> </tbody></table>&#13;
<p>&#13;
以下为异常的继承结构：</p>&#13;
<pre>Exception&#13;
|__Warning&#13;
|__Error&#13;
   |__InterfaceError&#13;
   |__DatabaseError&#13;
      |__DataError&#13;
      |__OperationalError&#13;
      |__IntegrityError&#13;
      |__InternalError&#13;
      |__ProgrammingError&#13;
      |__NotSupportedError</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>