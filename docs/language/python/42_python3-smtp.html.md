<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 SMTP发送邮件</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 SMTP发送邮件</h1>&#13;
&#13;
<p>SMTP（Simple Mail Transfer Protocol）即简单邮件传输协议,它是一组用于由源地址到目的地址传送邮件的规则，由它来控制信件的中转方式。</p>&#13;
<p>python的smtplib提供了一种很方便的途径发送电子邮件。它对smtp协议进行了简单的封装。</p>&#13;
<p>Python创建 SMTP 对象语法如下：</p>&#13;
<pre>&#13;
import smtplib&#13;
&#13;
smtpObj = smtplib.SMTP( [host [, port [, local_hostname]]] )&#13;
</pre>&#13;
<p>参数说明：</p>&#13;
<ul>&#13;
<li>&#13;
host:  SMTP 服务器主机。 你可以指定主机的ip地址或者域名如:runoob.com，这个是可选参数。&#13;
</li><li>&#13;
port: 如果你提供了 host 参数, 你需要指定 SMTP 服务使用的端口号，一般情况下SMTP端口号为25。 &#13;
</li><li>&#13;
local_hostname: 如果SMTP在你的本机上，你只需要指定服务器地址为 localhost 即可。&#13;
</li></ul>&#13;
<p>Python SMTP对象使用sendmail方法发送邮件，语法如下：</p>&#13;
<pre>&#13;
SMTP.sendmail(from_addr, to_addrs, msg[, mail_options, rcpt_options]&#13;
</pre>&#13;
<p>参数说明：</p>&#13;
<ul>&#13;
<li>&#13;
from_addr:  邮件发送者地址。&#13;
</li><li>&#13;
to_addrs: 字符串列表，邮件发送地址。&#13;
</li><li>&#13;
msg: 发送消息&#13;
</li></ul>&#13;
<p>这里要注意一下第三个参数，msg是字符串，表示邮件。我们知道邮件一般由标题，发信人，收件人，邮件内容，附件等构成，发送邮件的时候，要注意msg的格式。这个格式就是smtp协议中定义的格式。</p>&#13;
<h3>实例</h3>&#13;
<p>以下是一个使用Python发送邮件简单的实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">header</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">Header</span><span class="hl-code">
 
</span><span class="hl-identifier">sender</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">from@runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">receivers</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">  </span><span class="hl-comment"># 接收邮件，可设置为你的QQ邮箱或者其他邮箱</span><span class="hl-code">
 
</span><span class="hl-comment"># 三个参数：第一个为文本内容，第二个 plain 设置文本格式，第三个 utf-8 设置编码</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Python 邮件发送测试...</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">plain</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">     </span><span class="hl-comment"># 发送者</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> =  </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">测试</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">          </span><span class="hl-comment"># 接收者</span><span class="hl-code">
 
</span><span class="hl-identifier">subject</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">Python SMTP 邮件测试</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
 
</span><span class="hl-reserved">try</span><span class="hl-code">:
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code"> = </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">sender</span><span class="hl-code">, </span><span class="hl-identifier">receivers</span><span class="hl-code">, </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTPException</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: 无法发送邮件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>我们使用三个引号来设置邮件信息，标准邮件需要三个头部信息： <b>From</b>, <b>To</b>, 和 <b>Subject</b> ，每个信息直接使用空行分割。</p>&#13;
<p>我们通过实例化 smtplib 模块的 SMTP 对象 <i>smtpObj</i> 来连接到 SMTP 访问，并使用 <i>sendmail</i> 方法来发送信息。</p>&#13;
<p>执行以上程序，如果你本机安装sendmail，就会输出：</p>&#13;
<pre>&#13;
$ python3 test.py &#13;
邮件发送成功&#13;
</pre>&#13;
<p>查看我们的收件箱(一般在垃圾箱)，就可以查看到邮件信息：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2016/04/smtp1.jpg"/></p>&#13;
&#13;
<p>如果我们本机没有 sendmail 访问，也可以使用其他服务商的 SMTP 访问（QQ、网易、Google等）。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">header</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">Header</span><span class="hl-code">
 
</span><span class="hl-comment"># 第三方 SMTP 服务</span><span class="hl-code">
</span><span class="hl-identifier">mail_host</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">smtp.XXX.com</span><span class="hl-quotes">"</span><span class="hl-code">  </span><span class="hl-comment">#设置服务器</span><span class="hl-code">
</span><span class="hl-identifier">mail_user</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">XXXX</span><span class="hl-quotes">"</span><span class="hl-code">    </span><span class="hl-comment">#用户名</span><span class="hl-code">
</span><span class="hl-identifier">mail_pass</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">XXXXXX</span><span class="hl-quotes">"</span><span class="hl-code">   </span><span class="hl-comment">#口令 </span><span class="hl-code">
 
 
</span><span class="hl-identifier">sender</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">from@runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">receivers</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">  </span><span class="hl-comment"># 接收邮件，可设置为你的QQ邮箱或者其他邮箱</span><span class="hl-code">
 
</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Python 邮件发送测试...</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">plain</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> =  </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">测试</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">subject</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">Python SMTP 邮件测试</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
 
</span><span class="hl-reserved">try</span><span class="hl-code">:
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code"> = </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> 
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">connect</span><span class="hl-brackets">(</span><span class="hl-identifier">mail_host</span><span class="hl-code">, </span><span class="hl-number">25</span><span class="hl-brackets">)</span><span class="hl-code">    </span><span class="hl-comment"># 25 为 SMTP 端口号</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">login</span><span class="hl-brackets">(</span><span class="hl-identifier">mail_user</span><span class="hl-code">,</span><span class="hl-identifier">mail_pass</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">sender</span><span class="hl-code">, </span><span class="hl-identifier">receivers</span><span class="hl-code">, </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTPException</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: 无法发送邮件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>使用Python发送HTML格式的邮件</h2>&#13;
<p>Python发送HTML格式的邮件与发送纯文本消息的邮件不同之处就是将MIMEText中_subtype设置为html。具体代码如下：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">header</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">Header</span><span class="hl-code">
 
</span><span class="hl-identifier">sender</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">from@runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">receivers</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">  </span><span class="hl-comment"># 接收邮件，可设置为你的QQ邮箱或者其他邮箱</span><span class="hl-code">
 
</span><span class="hl-identifier">mail_msg</span><span class="hl-code"> = </span><span class="hl-quotes">"""</span><span class="hl-string">
&lt;p&gt;Python 邮件发送测试...&lt;/p&gt;
&lt;p&gt;&lt;a href="http://www.runoob.com"&gt;这是一个链接&lt;/a&gt;&lt;/p&gt;
</span><span class="hl-quotes">"""</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-identifier">mail_msg</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">html</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> =  </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">测试</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">subject</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">Python SMTP 邮件测试</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
 
</span><span class="hl-reserved">try</span><span class="hl-code">:
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code"> = </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">sender</span><span class="hl-code">, </span><span class="hl-identifier">receivers</span><span class="hl-code">, </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTPException</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: 无法发送邮件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>执行以上程序，如果你本机安装sendmail，就会输出：</p>&#13;
<pre>&#13;
$ python3 test.py &#13;
邮件发送成功&#13;
</pre>&#13;
<p>查看我们的收件箱(一般在垃圾箱)，就可以查看到邮件信息：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2016/04/smtp2.jpg"/></p>&#13;
<hr/>&#13;
<h2>Python 发送带附件的邮件</h2>&#13;
<p>发送带附件的邮件，首先要创建MIMEMultipart()实例，然后构造附件，如果有多个附件，可依次构造，最后利用smtplib.smtp发送。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">multipart</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEMultipart</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">header</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">Header</span><span class="hl-code">
 
</span><span class="hl-identifier">sender</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">from@runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">receivers</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">  </span><span class="hl-comment"># 接收邮件，可设置为你的QQ邮箱或者其他邮箱</span><span class="hl-code">
 
</span><span class="hl-comment">#创建一个带附件的实例</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEMultipart</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> =  </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">测试</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">subject</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">Python SMTP 邮件测试</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment">#邮件正文内容</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">这是菜鸟教程Python 邮件发送测试……</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">plain</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 构造附件1，传送当前目录下的 test.txt 文件</span><span class="hl-code">
</span><span class="hl-identifier">att1</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-builtin">open</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">test.txt</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">rb</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">base64</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">att1</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">Content-Type</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">application/octet-stream</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-comment"># 这里的filename可以任意写，写什么名字，邮件中显示什么名字</span><span class="hl-code">
</span><span class="hl-identifier">att1</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">Content-Disposition</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">attachment; filename="test.txt"</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">att1</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 构造附件2，传送当前目录下的 runoob.txt 文件</span><span class="hl-code">
</span><span class="hl-identifier">att2</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-builtin">open</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">runoob.txt</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">rb</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">base64</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">att2</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">Content-Type</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">application/octet-stream</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">att2</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">Content-Disposition</span><span class="hl-quotes">"</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">attachment; filename="runoob.txt"</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">att2</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">try</span><span class="hl-code">:
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code"> = </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">sender</span><span class="hl-code">, </span><span class="hl-identifier">receivers</span><span class="hl-code">, </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTPException</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: 无法发送邮件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<pre>&#13;
$ python3 test.py &#13;
邮件发送成功&#13;
</pre>&#13;
<p>查看我们的收件箱(一般在垃圾箱)，就可以查看到邮件信息：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/11/smtp3.jpg"/></p>&#13;
&#13;
<hr/><h2>在 HTML 文本中添加图片</h2>&#13;
<p>邮件的 HTML 文本中一般邮件服务商添加外链是无效的，正确添加图片的实例如下所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">image</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEImage</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">multipart</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEMultipart</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">header</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">Header</span><span class="hl-code">
 
</span><span class="hl-identifier">sender</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">from@runoob.com</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">receivers</span><span class="hl-code"> = </span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">  </span><span class="hl-comment"># 接收邮件，可设置为你的QQ邮箱或者其他邮箱</span><span class="hl-code">
 
</span><span class="hl-identifier">msgRoot</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEMultipart</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">related</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">msgRoot</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">msgRoot</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> =  </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">测试</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">subject</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">Python SMTP 邮件测试</span><span class="hl-quotes">'</span><span class="hl-code">
</span><span class="hl-identifier">msgRoot</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">Header</span><span class="hl-brackets">(</span><span class="hl-identifier">subject</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">msgAlternative</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEMultipart</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">alternative</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">msgRoot</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">msgAlternative</span><span class="hl-brackets">)</span><span class="hl-code">
 
 
</span><span class="hl-identifier">mail_msg</span><span class="hl-code"> = </span><span class="hl-quotes">"""</span><span class="hl-string">
&lt;p&gt;Python 邮件发送测试...&lt;/p&gt;
&lt;p&gt;&lt;a href="http://www.runoob.com"&gt;菜鸟教程链接&lt;/a&gt;&lt;/p&gt;
&lt;p&gt;图片演示：&lt;/p&gt;
&lt;p&gt;&lt;img src="cid:image1"&gt;&lt;/p&gt;
</span><span class="hl-quotes">"""</span><span class="hl-code">
</span><span class="hl-identifier">msgAlternative</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-identifier">mail_msg</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">html</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 指定图片为当前目录</span><span class="hl-code">
</span><span class="hl-identifier">fp</span><span class="hl-code"> = </span><span class="hl-builtin">open</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">test.png</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">rb</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">msgImage</span><span class="hl-code"> = </span><span class="hl-identifier">MIMEImage</span><span class="hl-brackets">(</span><span class="hl-identifier">fp</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">fp</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment"># 定义图片 ID，在 HTML 文本中引用</span><span class="hl-code">
</span><span class="hl-identifier">msgImage</span><span class="hl-code">.</span><span class="hl-identifier">add_header</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">Content-ID</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">&lt;image1&gt;</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">msgRoot</span><span class="hl-code">.</span><span class="hl-identifier">attach</span><span class="hl-brackets">(</span><span class="hl-identifier">msgImage</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-reserved">try</span><span class="hl-code">:
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code"> = </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">localhost</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">smtpObj</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">sender</span><span class="hl-code">, </span><span class="hl-identifier">receivers</span><span class="hl-code">, </span><span class="hl-identifier">msgRoot</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTPException</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Error: 无法发送邮件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<pre>&#13;
$ python3 test.py &#13;
邮件发送成功&#13;
</pre>&#13;
<p>查看我们的收件箱(如果在垃圾箱可能需要移动到收件箱才可正常显示)，就可以查看到邮件信息：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2016/04/smtp4.jpg"/></p>&#13;
<hr/>&#13;
<h2>使用第三方 SMTP 服务发送</h2>&#13;
<p>这里使用了 QQ 邮箱(你也可以使用 163，Gmail等)的 SMTP 服务，需要做以下配置：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2014/01/qqmail-set2.jpg"/></p>&#13;
<p>QQ 邮箱通过生成授权码来设置密码：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2014/01/qqmail-set.jpg"/></p>&#13;
&#13;
<p>QQ 邮箱 SMTP 服务器地址：smtp.qq.com，ssl 端口：465。</p>&#13;
<p>以下实例你需要修改：发件人邮箱（你的QQ邮箱），密码，收件人邮箱（可发给自己）。</p>&#13;
<div class="example"> &#13;
<h2 class="example">QQ SMTP</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">smtplib</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">mime</span><span class="hl-code">.</span><span class="hl-identifier">text</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">MIMEText</span><span class="hl-code">
</span><span class="hl-reserved">from</span><span class="hl-code"> </span><span class="hl-identifier">email</span><span class="hl-code">.</span><span class="hl-identifier">utils</span><span class="hl-code"> </span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">formataddr</span><span class="hl-code">
 
</span><span class="hl-identifier">my_sender</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-code">    </span><span class="hl-comment"># 发件人邮箱账号</span><span class="hl-code">
</span><span class="hl-identifier">my_pass</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">xxxxxxxxxx</span><span class="hl-quotes">'</span><span class="hl-code">              </span><span class="hl-comment"># 发件人邮箱密码</span><span class="hl-code">
</span><span class="hl-identifier">my_user</span><span class="hl-code">=</span><span class="hl-quotes">'</span><span class="hl-string">429240967@qq.com</span><span class="hl-quotes">'</span><span class="hl-code">      </span><span class="hl-comment"># 收件人邮箱账号，我这边发送给自己</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">mail</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-identifier">ret</span><span class="hl-code">=</span><span class="hl-reserved">True</span><span class="hl-code">
    </span><span class="hl-reserved">try</span><span class="hl-code">:
        </span><span class="hl-identifier">msg</span><span class="hl-code">=</span><span class="hl-identifier">MIMEText</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">填写邮件内容</span><span class="hl-quotes">'</span><span class="hl-code">,</span><span class="hl-quotes">'</span><span class="hl-string">plain</span><span class="hl-quotes">'</span><span class="hl-code">,</span><span class="hl-quotes">'</span><span class="hl-string">utf-8</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">
        </span><span class="hl-identifier">msg</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">From</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-identifier">formataddr</span><span class="hl-brackets">(</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">FromRunoob</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-identifier">my_sender</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 括号里的对应发件人邮箱昵称、发件人邮箱账号</span><span class="hl-code">
        </span><span class="hl-identifier">msg</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">To</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-identifier">formataddr</span><span class="hl-brackets">(</span><span class="hl-brackets">[</span><span class="hl-quotes">"</span><span class="hl-string">FK</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-identifier">my_user</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">              </span><span class="hl-comment"># 括号里的对应收件人邮箱昵称、收件人邮箱账号</span><span class="hl-code">
        </span><span class="hl-identifier">msg</span><span class="hl-brackets">[</span><span class="hl-quotes">'</span><span class="hl-string">Subject</span><span class="hl-quotes">'</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-quotes">"</span><span class="hl-string">菜鸟教程发送邮件测试</span><span class="hl-quotes">"</span><span class="hl-code">                </span><span class="hl-comment"># 邮件的主题，也可以说是标题</span><span class="hl-code">
 
        </span><span class="hl-identifier">server</span><span class="hl-code">=</span><span class="hl-identifier">smtplib</span><span class="hl-code">.</span><span class="hl-identifier">SMTP_SSL</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">smtp.qq.com</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-number">465</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 发件人邮箱中的SMTP服务器，端口是25</span><span class="hl-code">
        </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">login</span><span class="hl-brackets">(</span><span class="hl-identifier">my_sender</span><span class="hl-code">, </span><span class="hl-identifier">my_pass</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 括号中对应的是发件人邮箱账号、邮箱密码</span><span class="hl-code">
        </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">sendmail</span><span class="hl-brackets">(</span><span class="hl-identifier">my_sender</span><span class="hl-code">,</span><span class="hl-brackets">[</span><span class="hl-identifier">my_user</span><span class="hl-code">,</span><span class="hl-brackets">]</span><span class="hl-code">,</span><span class="hl-identifier">msg</span><span class="hl-code">.</span><span class="hl-identifier">as_string</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 括号中对应的是发件人邮箱账号、收件人邮箱账号、发送邮件</span><span class="hl-code">
        </span><span class="hl-identifier">server</span><span class="hl-code">.</span><span class="hl-identifier">quit</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">  </span><span class="hl-comment"># 关闭连接</span><span class="hl-code">
    </span><span class="hl-reserved">except</span><span class="hl-code"> </span><span class="hl-reserved">Exception</span><span class="hl-code">:  </span><span class="hl-comment"># 如果 try 中的语句没有执行，则会执行下面的 ret=False</span><span class="hl-code">
        </span><span class="hl-identifier">ret</span><span class="hl-code">=</span><span class="hl-reserved">False</span><span class="hl-code">
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">ret</span><span class="hl-code">
 
</span><span class="hl-identifier">ret</span><span class="hl-code">=</span><span class="hl-identifier">mail</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">ret</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送成功</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">邮件发送失败</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<pre>&#13;
$ python test.py &#13;
邮件发送成功&#13;
</pre>&#13;
<p>发送成功后，登陆收件人邮箱即可查看：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/11/423C9FDF-EBC5-4115-8D16-0046B5E05DBC.jpg"/></p>&#13;
<p>更多内容请参阅：<a href="https://docs.python.org/3/library/email-examples.html" target="_blank">https://docs.python.org/3/library/email-examples.html</a>。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>