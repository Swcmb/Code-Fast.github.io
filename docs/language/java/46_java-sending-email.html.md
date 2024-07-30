<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 发送邮件
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 发送邮件&#13;
</h1>&#13;
<p>&#13;
使用Java应用程序发送 E-mail 十分简单，但是首先你应该在你的机器上安装 JavaMail API 和Java Activation Framework (JAF) 。</p><ul>&#13;
<li>您可以从 Java 网站下载最新版本的 <a href="http://www.oracle.com/technetwork/java/javamail/index.html" target="_blank">JavaMail</a>，打开网页右侧有个 <strong>Downloads</strong> 链接，点击它下载。</li>&#13;
<li>您可以从 Java 网站下载最新版本的 <a href="http://www.oracle.com/technetwork/articles/java/index-135046.html" target="_blank">JAF（版本 1.1.1）</a>。</li>&#13;
</ul>&#13;
<p>你也可以使用本站提供的下载链接：</p>&#13;
<ul>&#13;
<li>&#13;
<a href="http://static.runoob.com/download/mail.jar" target="_blank" download="">JavaMail mail.jar 1.4.5</a>&#13;
</li><li>&#13;
</li><li>&#13;
<a href="http://static.runoob.com/download/activation.jar" target="_blank" download=""> JAF（版本 1.1.1） activation.jar</a>&#13;
</li><li>&#13;
</li></ul>&#13;
<p>下载并解压缩这些文件，在新创建的顶层目录中，您会发现这两个应用程序的一些 jar 文件。您需要把 <b>mail.jar</b> 和 <b>activation.jar</b> 文件添加到您的 CLASSPATH 中。</p>&#13;
&#13;
<p>如果你使用第三方邮件服务器如QQ的SMTP服务器，可查看文章底部用户认证完整的实例。</p>&#13;
<hr/>&#13;
<h2>&#13;
发送一封简单的 E-mail</h2>&#13;
<p>&#13;
下面是一个发送简单E-mail的例子。假设你的本地主机已经连接到网络。</p>&#13;
<div class="example">&#13;
<h2 class="example">SendEmail.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 SendEmail.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">util</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">internet</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">activation</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SendEmail</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">   
      </span><span class="hl-comment">//</span><span class="hl-comment"> 收件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">to</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">abcd@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 发件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">from</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">web@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 指定发送邮件的主机为 localhost</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">host</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取系统属性</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Properties</span><span class="hl-code"> </span><span class="hl-identifier">properties</span><span class="hl-code"> = </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">getProperties</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 设置邮件服务器</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">properties</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.host</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">host</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取默认session对象</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Session</span><span class="hl-code"> </span><span class="hl-identifier">session</span><span class="hl-code"> = </span><span class="hl-identifier">Session</span><span class="hl-code">.</span><span class="hl-identifier">getDefaultInstance</span><span class="hl-brackets">(</span><span class="hl-identifier">properties</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建默认的 MimeMessage 对象</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">MimeMessage</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeMessage</span><span class="hl-brackets">(</span><span class="hl-identifier">session</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set From: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setFrom</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">from</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set To: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">addRecipient</span><span class="hl-brackets">(</span><span class="hl-identifier">Message</span><span class="hl-code">.</span><span class="hl-identifier">RecipientType</span><span class="hl-code">.</span><span class="hl-identifier">TO</span><span class="hl-code">,
                                  </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">to</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set Subject: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setSubject</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is the Subject Line!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 设置消息体</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setText</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is actual message</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 发送消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">Transport</span><span class="hl-code">.</span><span class="hl-identifier">send</span><span class="hl-brackets">(</span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Sent message successfully....</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">MessagingException</span><span class="hl-code"> </span><span class="hl-identifier">mex</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">mex</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
编译并运行这个程序来发送一封简单的E-mail：&#13;
</p>&#13;
<pre>&#13;
$ java SendEmail&#13;
Sent message successfully....&#13;
</pre>&#13;
<p>&#13;
如果你想发送一封e-mail给多个收件人，那么使用下面的方法来指定多个收件人ID：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">addRecipients</span><span class="hl-brackets">(</span><span class="hl-identifier">Message</span><span class="hl-code">.</span><span class="hl-identifier">RecipientType</span><span class="hl-code"> </span><span class="hl-identifier">type</span><span class="hl-code">,
                   </span><span class="hl-identifier">Address</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">addresses</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">MessagingException</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
下面是对于参数的描述：&#13;
</p>&#13;
<ul>&#13;
<li><p><b>type:</b>要被设置为 TO, CC 或者 BCC，这里 CC 代表抄送、BCC 代表秘密抄送。举例：<b>Message.RecipientType.TO</b></p></li>&#13;
<li><p><b>addresses:</b> 这是 email ID 的数组。在指定电子邮件 ID 时，你将需要使用 InternetAddress() 方法。</p></li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>&#13;
发送一封 HTML E-mail</h2>&#13;
<p>&#13;
下面是一个发送 HTML E-mail 的例子。假设你的本地主机已经连接到网络。</p><p>&#13;
和上一个例子很相似，除了我们要使用 setContent() 方法来通过第二个参数为 "text/html"，来设置内容来指定要发送HTML 内容。</p>&#13;
<div class="example">&#13;
<h2 class="example">SendHTMLEmail.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 SendHTMLEmail.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">util</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">internet</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">activation</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SendHTMLEmail</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
     
      </span><span class="hl-comment">//</span><span class="hl-comment"> 收件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">to</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">abcd@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 发件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">from</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">web@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 指定发送邮件的主机为 localhost</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">host</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取系统属性</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Properties</span><span class="hl-code"> </span><span class="hl-identifier">properties</span><span class="hl-code"> = </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">getProperties</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 设置邮件服务器</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">properties</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.host</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">host</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取默认的 Session 对象。</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Session</span><span class="hl-code"> </span><span class="hl-identifier">session</span><span class="hl-code"> = </span><span class="hl-identifier">Session</span><span class="hl-code">.</span><span class="hl-identifier">getDefaultInstance</span><span class="hl-brackets">(</span><span class="hl-identifier">properties</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建默认的 MimeMessage 对象。</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">MimeMessage</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeMessage</span><span class="hl-brackets">(</span><span class="hl-identifier">session</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set From: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setFrom</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">from</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set To: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">addRecipient</span><span class="hl-brackets">(</span><span class="hl-identifier">Message</span><span class="hl-code">.</span><span class="hl-identifier">RecipientType</span><span class="hl-code">.</span><span class="hl-identifier">TO</span><span class="hl-code">,
                                  </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">to</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set Subject: 头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setSubject</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is the Subject Line!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 发送 HTML 消息, 可以插入html标签</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setContent</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">&lt;h1&gt;This is actual message&lt;/h1&gt;</span><span class="hl-quotes">"</span><span class="hl-code">,
                            </span><span class="hl-quotes">"</span><span class="hl-string">text/html</span><span class="hl-quotes">"</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 发送消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">Transport</span><span class="hl-code">.</span><span class="hl-identifier">send</span><span class="hl-brackets">(</span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Sent message successfully....</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">MessagingException</span><span class="hl-code"> </span><span class="hl-identifier">mex</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">mex</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
编译并运行此程序来发送HTML e-mail：</p>&#13;
<pre>&#13;
$ java SendHTMLEmail&#13;
Sent message successfully....&#13;
</pre><hr/>&#13;
<h2>发送带有附件的 E-mail&#13;
</h2>&#13;
<p>&#13;
下面是一个发送带有附件的 E-mail的例子。假设你的本地主机已经连接到网络。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">SendFileEmail.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 SendFileEmail.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">util</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">internet</span><span class="hl-code">.*;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">activation</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SendFileEmail</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
     
      </span><span class="hl-comment">//</span><span class="hl-comment"> 收件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">to</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">abcd@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 发件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">from</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">web@gmail.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 指定发送邮件的主机为 localhost</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">host</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">localhost</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取系统属性</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Properties</span><span class="hl-code"> </span><span class="hl-identifier">properties</span><span class="hl-code"> = </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">getProperties</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 设置邮件服务器</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">properties</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.host</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">host</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取默认的 Session 对象。</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Session</span><span class="hl-code"> </span><span class="hl-identifier">session</span><span class="hl-code"> = </span><span class="hl-identifier">Session</span><span class="hl-code">.</span><span class="hl-identifier">getDefaultInstance</span><span class="hl-brackets">(</span><span class="hl-identifier">properties</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建默认的 MimeMessage 对象。</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">MimeMessage</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeMessage</span><span class="hl-brackets">(</span><span class="hl-identifier">session</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set From: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setFrom</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">from</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set To: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">addRecipient</span><span class="hl-brackets">(</span><span class="hl-identifier">Message</span><span class="hl-code">.</span><span class="hl-identifier">RecipientType</span><span class="hl-code">.</span><span class="hl-identifier">TO</span><span class="hl-code">,
                                  </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">to</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set Subject: 头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setSubject</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is the Subject Line!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建消息部分</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">BodyPart</span><span class="hl-code"> </span><span class="hl-identifier">messageBodyPart</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeBodyPart</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">messageBodyPart</span><span class="hl-code">.</span><span class="hl-identifier">setText</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is message body</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建多重消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">Multipart</span><span class="hl-code"> </span><span class="hl-identifier">multipart</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeMultipart</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 设置文本消息部分</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">multipart</span><span class="hl-code">.</span><span class="hl-identifier">addBodyPart</span><span class="hl-brackets">(</span><span class="hl-identifier">messageBodyPart</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 附件部分</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">messageBodyPart</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeBodyPart</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">filename</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">file.txt</span><span class="hl-quotes">"</span><span class="hl-code">;
         </span><span class="hl-identifier">DataSource</span><span class="hl-code"> </span><span class="hl-identifier">source</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileDataSource</span><span class="hl-brackets">(</span><span class="hl-identifier">filename</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">messageBodyPart</span><span class="hl-code">.</span><span class="hl-identifier">setDataHandler</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">DataHandler</span><span class="hl-brackets">(</span><span class="hl-identifier">source</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">messageBodyPart</span><span class="hl-code">.</span><span class="hl-identifier">setFileName</span><span class="hl-brackets">(</span><span class="hl-identifier">filename</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">multipart</span><span class="hl-code">.</span><span class="hl-identifier">addBodyPart</span><span class="hl-brackets">(</span><span class="hl-identifier">messageBodyPart</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 发送完整消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setContent</span><span class="hl-brackets">(</span><span class="hl-identifier">multipart</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment">   发送消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">Transport</span><span class="hl-code">.</span><span class="hl-identifier">send</span><span class="hl-brackets">(</span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Sent message successfully....</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">MessagingException</span><span class="hl-code"> </span><span class="hl-identifier">mex</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">mex</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
编译并运行你的程序来发送一封带有附件的邮件。&#13;
</p>&#13;
<pre>&#13;
$ java SendFileEmail&#13;
Sent message successfully....&#13;
</pre>&#13;
<hr/><h2>&#13;
用户认证部分</h2>&#13;
<p>&#13;
&#13;
如果需要提供用户名和密码给e-mail服务器来达到用户认证的目的，你可以通过如下设置来完成：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">props</span><span class="hl-code">.</span><span class="hl-identifier">put</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.auth</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">true</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">props</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.user</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">myuser</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">props</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.password</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">mypwd</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
 <p>&#13;
e-mail其他的发送机制和上述保持一致。</p>&#13;
<h3>需要用户名密码验证邮件发送实例:</h3>&#13;
<p>本实例以 QQ 邮件服务器为例，你需要在登录QQ邮箱后台在"设置"=》账号中开启POP3/SMTP服务 ，如下图所示：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2014/01/qqmail-set2.jpg"/></p>&#13;
<p>QQ 邮箱通过生成授权码来设置密码：</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2014/01/qqmail-set.jpg"/></p>&#13;
<p>Java 代码如下：</p>&#13;
<div class="example">&#13;
<h2 class="example">SendEmail2.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 需要用户名密码邮件发送实例</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">//</span><span class="hl-comment">文件名 SendEmail2.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">//</span><span class="hl-comment">本实例以QQ邮箱为例，你需要在qq后台设置</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">util</span><span class="hl-code">.</span><span class="hl-identifier">Properties</span><span class="hl-code">;
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">Authenticator</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">Message</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">MessagingException</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">PasswordAuthentication</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">Session</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">Transport</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">internet</span><span class="hl-code">.</span><span class="hl-identifier">InternetAddress</span><span class="hl-code">;
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">javax</span><span class="hl-code">.</span><span class="hl-identifier">mail</span><span class="hl-code">.</span><span class="hl-identifier">internet</span><span class="hl-code">.</span><span class="hl-identifier">MimeMessage</span><span class="hl-code">;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SendEmail2</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment"> 收件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">to</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">xxx@qq.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 发件人电子邮箱</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">from</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">xxx@qq.com</span><span class="hl-quotes">"</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 指定发送邮件的主机为 smtp.qq.com</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">host</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">smtp.qq.com</span><span class="hl-quotes">"</span><span class="hl-code">;  </span><span class="hl-comment">//</span><span class="hl-comment">QQ 邮件服务器</span><span class="hl-comment"/><span class="hl-code">
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取系统属性</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Properties</span><span class="hl-code"> </span><span class="hl-identifier">properties</span><span class="hl-code"> = </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">getProperties</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 设置邮件服务器</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">properties</span><span class="hl-code">.</span><span class="hl-identifier">setProperty</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.host</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">host</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-identifier">properties</span><span class="hl-code">.</span><span class="hl-identifier">put</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">mail.smtp.auth</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">true</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-comment">//</span><span class="hl-comment"> 获取默认session对象</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Session</span><span class="hl-code"> </span><span class="hl-identifier">session</span><span class="hl-code"> = </span><span class="hl-identifier">Session</span><span class="hl-code">.</span><span class="hl-identifier">getDefaultInstance</span><span class="hl-brackets">(</span><span class="hl-identifier">properties</span><span class="hl-code">,</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Authenticator</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">PasswordAuthentication</span><span class="hl-code"> </span><span class="hl-identifier">getPasswordAuthentication</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
        </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">PasswordAuthentication</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">xxx@qq.com</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">qq邮箱授权码</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">发件人邮件用户名、授权码</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code">
       </span><span class="hl-brackets">}</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-comment">//</span><span class="hl-comment"> 创建默认的 MimeMessage 对象</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">MimeMessage</span><span class="hl-code"> </span><span class="hl-identifier">message</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MimeMessage</span><span class="hl-brackets">(</span><span class="hl-identifier">session</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set From: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setFrom</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">from</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set To: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">addRecipient</span><span class="hl-brackets">(</span><span class="hl-identifier">Message</span><span class="hl-code">.</span><span class="hl-identifier">RecipientType</span><span class="hl-code">.</span><span class="hl-identifier">TO</span><span class="hl-code">,
                                  </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InternetAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">to</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> Set Subject: 头部头字段</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setSubject</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is the Subject Line!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 设置消息体</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">message</span><span class="hl-code">.</span><span class="hl-identifier">setText</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is actual message</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
         </span><span class="hl-comment">//</span><span class="hl-comment"> 发送消息</span><span class="hl-comment"/><span class="hl-code">
         </span><span class="hl-identifier">Transport</span><span class="hl-code">.</span><span class="hl-identifier">send</span><span class="hl-brackets">(</span><span class="hl-identifier">message</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Sent message successfully....from runoob.com</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">MessagingException</span><span class="hl-code"> </span><span class="hl-identifier">mex</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">mex</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>