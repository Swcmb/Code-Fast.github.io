<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java MySQL 连接
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java MySQL 连接&#13;
</h1>&#13;
<p>本章节我们为大家介绍 Java 如何使用 使用 JDBC 连接 MySQL 数据库。</p>&#13;
<p>Java 连接 MySQL 需要驱动包，最新版下载地址为：<strong><a href="http://dev.mysql.com/downloads/connector/j/" target="_blank" rel="noopener noreferrer">http://dev.mysql.com/downloads/connector/j/</a></strong>，解压后得到 jar 库文件，然后在对应的项目中导入该库文件。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2016/08/38EF259A-CC97-4001-96AD-C6648BE2A4F4.jpg"/></p>&#13;
<p>你可以下载本站提供的 jar 包：<strong><a href="http://static.runoob.com/download/mysql-connector-java-5.1.39-bin.jar" target="_blank" rel="noopener noreferrer">mysql-connector-java-5.1.39-bin.jar</a></strong></p>&#13;
<p>本实例使用的是 Eclipse，导入 jar 包：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/12/191E2E30-DD23-41C8-A419-DFEAEAE06BF6.jpg" width="40%"/></p>&#13;
&#13;
&#13;
<blockquote><p><strong>MySQL 8.0 以上版本的数据库连接有所不同：</strong></p>&#13;
<ul><li>&#13;
<p>1、MySQL 8.0 以上版本驱动包版本 <a href="https://static.jyshare.com/download/mysql-connector-java-8.0.16.jar">mysql-connector-java-8.0.16.jar</a>。</p></li><li>&#13;
<p>2、<strong>com.mysql.jdbc.Driver</strong> 更换为 <span class="marked">com.mysql.cj.jdbc.Driver</span>。</p></li><li>&#13;
&#13;
<p>MySQL 8.0 以上版本不需要建立 SSL 连接的，需要显示关闭。</p></li><li>&#13;
<p>allowPublicKeyRetrieval=true 允许客户端从服务器获取公钥。</p></li>&#13;
<li>&#13;
<p>最后还需要设置 CST。</p>&#13;
</li></ul>&#13;
&#13;
<p>加载驱动与连接数据库方式如下：</p>&#13;
<pre>Class.forName("com.mysql.cj.jdbc.Driver");&#13;
conn = DriverManager.getConnection("jdbc:mysql://localhost:3306/test_demo?useSSL=false&amp;allowPublicKeyRetrieval=true&amp;serverTimezone=UTC","root","password");</pre></blockquote>&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>创建测试数据</h2>&#13;
<p>接下来我们在 MySQL 中创建 RUNOOB 数据库，并创建 websites 数据表，表结构如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">CREATE</span><span class="hl-code"> </span><span class="hl-reserved">TABLE</span><span class="hl-code"> </span><span class="hl-quotes">`</span><span class="hl-identifier">websites</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code">
  </span><span class="hl-quotes">`</span><span class="hl-identifier">id</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">int</span><span class="hl-brackets">(</span><span class="hl-number">11</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">NOT</span><span class="hl-code"> </span><span class="hl-reserved">NULL</span><span class="hl-code"> </span><span class="hl-identifier">AUTO_INCREMENT</span><span class="hl-code">,
  </span><span class="hl-quotes">`</span><span class="hl-identifier">name</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">char</span><span class="hl-brackets">(</span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">NOT</span><span class="hl-code"> </span><span class="hl-reserved">NULL</span><span class="hl-code"> </span><span class="hl-reserved">DEFAULT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-code"> </span><span class="hl-identifier">COMMENT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">站点名称</span><span class="hl-quotes">'</span><span class="hl-code">,
  </span><span class="hl-quotes">`</span><span class="hl-identifier">url</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">varchar</span><span class="hl-brackets">(</span><span class="hl-number">255</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">NOT</span><span class="hl-code"> </span><span class="hl-reserved">NULL</span><span class="hl-code"> </span><span class="hl-reserved">DEFAULT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-code">,
  </span><span class="hl-quotes">`</span><span class="hl-identifier">alexa</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">int</span><span class="hl-brackets">(</span><span class="hl-number">11</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">NOT</span><span class="hl-code"> </span><span class="hl-reserved">NULL</span><span class="hl-code"> </span><span class="hl-reserved">DEFAULT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">0</span><span class="hl-quotes">'</span><span class="hl-code"> </span><span class="hl-identifier">COMMENT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">Alexa 排名</span><span class="hl-quotes">'</span><span class="hl-code">,
  </span><span class="hl-quotes">`</span><span class="hl-identifier">country</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">char</span><span class="hl-brackets">(</span><span class="hl-number">10</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">NOT</span><span class="hl-code"> </span><span class="hl-reserved">NULL</span><span class="hl-code"> </span><span class="hl-reserved">DEFAULT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-code"> </span><span class="hl-identifier">COMMENT</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">国家</span><span class="hl-quotes">'</span><span class="hl-code">,
  </span><span class="hl-reserved">PRIMARY</span><span class="hl-code"> </span><span class="hl-reserved">KEY</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">`</span><span class="hl-identifier">id</span><span class="hl-quotes">`</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">ENGINE</span><span class="hl-code">=</span><span class="hl-identifier">InnoDB</span><span class="hl-code"> </span><span class="hl-identifier">AUTO_INCREMENT</span><span class="hl-code">=</span><span class="hl-number">10</span><span class="hl-code"> </span><span class="hl-reserved">DEFAULT</span><span class="hl-code"> </span><span class="hl-identifier">CHARSET</span><span class="hl-code">=</span><span class="hl-identifier">utf8</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>插入一些数据：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">INSERT</span><span class="hl-code"> </span><span class="hl-reserved">INTO</span><span class="hl-code"> </span><span class="hl-quotes">`</span><span class="hl-identifier">websites</span><span class="hl-quotes">`</span><span class="hl-code"> </span><span class="hl-reserved">VALUES</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">1</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">Google</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.google.cm/</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">1</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">USA</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">2</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">淘宝</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.taobao.com/</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">13</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">CN</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">3</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">http://www.runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">5892</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">4</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">微博</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">http://weibo.com/</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">20</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">CN</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">5</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">Facebook</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">https://www.facebook.com/</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">3</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">USA</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>数据表显示如下：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/12/mysql-data.jpg"/></p><hr/>&#13;
<h2>连接数据库</h2>&#13;
<p>以下实例使用了 JDBC 连接 MySQL 数据库，注意一些数据如用户名，密码需要根据你的开发环境来配置：</p>&#13;
<div class="example">&#13;
<h2 class="example">MySQLDemo.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">package</span><span class="hl-code"> </span><span class="hl-identifier">com</span><span class="hl-code">.</span><span class="hl-identifier">runoob</span><span class="hl-code">.</span><span class="hl-identifier">test</span><span class="hl-code">;
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">sql</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">MySQLDemo</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
    </span><span class="hl-comment">//</span><span class="hl-comment"> MySQL 8.0 以下版本 - JDBC 驱动名及数据库 URL</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">JDBC_DRIVER</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">com.mysql.jdbc.Driver</span><span class="hl-quotes">"</span><span class="hl-code">;  
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">DB_URL</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">jdbc:mysql://localhost:3306/RUNOOB</span><span class="hl-quotes">"</span><span class="hl-code">;
 
    </span><span class="hl-comment">//</span><span class="hl-comment"> MySQL 8.0 以上版本 - JDBC 驱动名及数据库 URL</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">//</span><span class="hl-comment">static final String JDBC_DRIVER = "com.mysql.cj.jdbc.Driver";  </span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">//</span><span class="hl-comment">static final String DB_URL = "jdbc:mysql://localhost:3306/RUNOOB?useSSL=false&amp;allowPublicKeyRetrieval=true&amp;serverTimezone=UTC";</span><span class="hl-comment"/><span class="hl-code">
 
 
    </span><span class="hl-comment">//</span><span class="hl-comment"> 数据库的用户名与密码，需要根据自己的设置</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">USER</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">root</span><span class="hl-quotes">"</span><span class="hl-code">;
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">PASS</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">123456</span><span class="hl-quotes">"</span><span class="hl-code">;
 
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">Connection</span><span class="hl-code"> </span><span class="hl-identifier">conn</span><span class="hl-code"> = </span><span class="hl-reserved">null</span><span class="hl-code">;
        </span><span class="hl-identifier">Statement</span><span class="hl-code"> </span><span class="hl-identifier">stmt</span><span class="hl-code"> = </span><span class="hl-reserved">null</span><span class="hl-code">;
        </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 注册 JDBC 驱动</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">Class</span><span class="hl-code">.</span><span class="hl-identifier">forName</span><span class="hl-brackets">(</span><span class="hl-identifier">JDBC_DRIVER</span><span class="hl-brackets">)</span><span class="hl-code">;
        
            </span><span class="hl-comment">//</span><span class="hl-comment"> 打开链接</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">连接数据库...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">conn</span><span class="hl-code"> = </span><span class="hl-identifier">DriverManager</span><span class="hl-code">.</span><span class="hl-identifier">getConnection</span><span class="hl-brackets">(</span><span class="hl-identifier">DB_URL</span><span class="hl-code">,</span><span class="hl-identifier">USER</span><span class="hl-code">,</span><span class="hl-identifier">PASS</span><span class="hl-brackets">)</span><span class="hl-code">;
        
            </span><span class="hl-comment">//</span><span class="hl-comment"> 执行查询</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string"> 实例化Statement对象...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">stmt</span><span class="hl-code"> = </span><span class="hl-identifier">conn</span><span class="hl-code">.</span><span class="hl-identifier">createStatement</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">sql</span><span class="hl-code">;
            </span><span class="hl-identifier">sql</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">SELECT id, name, url FROM websites</span><span class="hl-quotes">"</span><span class="hl-code">;
            </span><span class="hl-identifier">ResultSet</span><span class="hl-code"> </span><span class="hl-identifier">rs</span><span class="hl-code"> = </span><span class="hl-identifier">stmt</span><span class="hl-code">.</span><span class="hl-identifier">executeQuery</span><span class="hl-brackets">(</span><span class="hl-identifier">sql</span><span class="hl-brackets">)</span><span class="hl-code">;
        
            </span><span class="hl-comment">//</span><span class="hl-comment"> 展开结果集数据库</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-identifier">rs</span><span class="hl-code">.</span><span class="hl-identifier">next</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-comment">//</span><span class="hl-comment"> 通过字段检索</span><span class="hl-comment"/><span class="hl-code">
                </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">id</span><span class="hl-code">  = </span><span class="hl-identifier">rs</span><span class="hl-code">.</span><span class="hl-identifier">getInt</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">id</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code"> = </span><span class="hl-identifier">rs</span><span class="hl-code">.</span><span class="hl-identifier">getString</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">name</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">url</span><span class="hl-code"> = </span><span class="hl-identifier">rs</span><span class="hl-code">.</span><span class="hl-identifier">getString</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">url</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
    
                </span><span class="hl-comment">//</span><span class="hl-comment"> 输出数据</span><span class="hl-comment"/><span class="hl-code">
                </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">ID: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">id</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">, 站点名称: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">name</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">, 站点 URL: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">url</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 完成后关闭</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">rs</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">stmt</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">conn</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">SQLException</span><span class="hl-code"> </span><span class="hl-identifier">se</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 处理 JDBC 错误</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">se</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">Exception</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 处理 Class.forName 错误</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-reserved">finally</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 关闭资源</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">stmt</span><span class="hl-code">!=</span><span class="hl-reserved">null</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">stmt</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">SQLException</span><span class="hl-code"> </span><span class="hl-identifier">se2</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-brackets">}</span><span class="hl-comment">//</span><span class="hl-comment"> 什么都不做</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">conn</span><span class="hl-code">!=</span><span class="hl-reserved">null</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">conn</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">SQLException</span><span class="hl-code"> </span><span class="hl-identifier">se</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-identifier">se</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Goodbye!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例执行输出结果如下：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2016/08/result.jpg" width="70%"/></p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>