<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 流(Stream)、文件(File)和IO</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 流(Stream)、文件(File)和IO</h1>&#13;
<p>Java.io 包几乎包含了所有操作输入、输出需要的类。所有这些流类代表了输入源和输出目标。&#13;
</p><p>Java.io 包中的流支持很多种格式，比如：基本类型、对象、本地化字符集等等。&#13;
</p><p>一个流可以理解为一个数据的序列。输入流表示从一个源读取数据，输出流表示向一个目标写数据。&#13;
</p><p>Java 为 I/O 提供了强大的而灵活的支持，使其更广泛地应用到文件传输和网络编程中。&#13;
</p><p>但本节讲述最基本的和流与 I/O 相关的功能。我们将通过一个个例子来学习这些功能。&#13;
</p><hr/><h2>读取控制台输入</h2>&#13;
&#13;
<p>&#13;
Java 的控制台输入由 System.in 完成。&#13;
</p><p>为了获得一个绑定到控制台的字符流，你可以把 System.in 包装在一个 BufferedReader 对象中来创建一个字符流。&#13;
</p><p>下面是创建 BufferedReader 的基本语法：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">BufferedReader</span><span class="hl-code"> </span><span class="hl-identifier">br</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">BufferedReader</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> 
                      </span><span class="hl-identifier">InputStreamReader</span><span class="hl-brackets">(</span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">in</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>BufferedReader 对象创建后，我们便可以使用 read() 方法从控制台读取一个字符，或者用 readLine() 方法读取一个字符串。&#13;
</p><hr/><h2>从控制台读取多字符输入</h2>&#13;
<p>&#13;
从 BufferedReader 对象读取一个字符要使用 read() 方法，它的语法如下：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span></div>&#13;
</div>&#13;
</div>&#13;
<p>每次调用 read() 方法，它从输入流读取一个字符并把该字符作为整数值返回。 当流结束的时候返回 -1。该方法抛出 IOException。&#13;
</p><p>下面的程序示范了用 read() 方法从控制台不断读取字符直到用户输入 <span class="marked">q</span>。</p>&#13;
<div class="example">&#13;
<h2 class="example">BRRead.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment">使用 BufferedReader 在控制台读取字符</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">BRRead</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 使用 System.in 创建 BufferedReader</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-identifier">BufferedReader</span><span class="hl-code"> </span><span class="hl-identifier">br</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">BufferedReader</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InputStreamReader</span><span class="hl-brackets">(</span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">in</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">输入字符, 按下 'q' 键退出。</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 读取字符</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-reserved">do</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">br</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">c</span><span class="hl-code"> != </span><span class="hl-quotes">'</span><span class="hl-string">q</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下:</p>&#13;
<pre>&#13;
输入字符, 按下 'q' 键退出。&#13;
runoob&#13;
r&#13;
u&#13;
n&#13;
o&#13;
o&#13;
b&#13;
&#13;
&#13;
q&#13;
q&#13;
</pre>&#13;
<hr/><h2>从控制台读取字符串</h2>&#13;
<p>&#13;
从标准输入读取一个字符串需要使用 BufferedReader 的 readLine() 方法。&#13;
</p><p>它的一般格式是：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">readLine</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
下面的程序读取和显示字符行直到你输入了单词"end"。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">BRReadLines.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment">使用 BufferedReader 在控制台读取字符</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">BRReadLines</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-comment">//</span><span class="hl-comment"> 使用 System.in 创建 BufferedReader</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-identifier">BufferedReader</span><span class="hl-code"> </span><span class="hl-identifier">br</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">BufferedReader</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InputStreamReader</span><span class="hl-brackets">(</span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">in</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">str</span><span class="hl-code">;
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Enter lines of text.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Enter 'end' to quit.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-reserved">do</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">str</span><span class="hl-code"> = </span><span class="hl-identifier">br</span><span class="hl-code">.</span><span class="hl-identifier">readLine</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">str</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code">!</span><span class="hl-identifier">str</span><span class="hl-code">.</span><span class="hl-identifier">equals</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">end</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下:</p>&#13;
<pre>&#13;
Enter lines of text.&#13;
Enter 'end' to quit.&#13;
This is line one&#13;
This is line one&#13;
This is line two&#13;
This is line two&#13;
end&#13;
end&#13;
</pre>&#13;
<blockquote>&#13;
<p>JDK 5 后的版本我们也可以使用 <a href="//www.runoob.com/java/java-scanner-class.html" target="_blank" rel="noopener">Java Scanner</a> 类来获取控制台的输入。</p></blockquote>&#13;
&#13;
&#13;
<h2>控制台输出</h2>&#13;
<p>&#13;
在此前已经介绍过，控制台的输出由 print( ) 和 println() 完成。这些方法都由类 PrintStream 定义，System.out 是该类对象的一个引用。&#13;
</p><p>PrintStream 继承了 OutputStream类，并且实现了方法 write()。这样，write() 也可以用来往控制台写操作。&#13;
</p><p>PrintStream 定义 write() 的最简单格式如下所示：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">write</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">byteval</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>该方法将 byteval 的低八位字节写到流中。&#13;
</p>&#13;
<h3>实例</h3>&#13;
<p>&#13;
下面的例子用 write() 把字符 "A" 和紧跟着的换行符输出到屏幕：&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">WriteDemo.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-comment">//</span><span class="hl-comment">演示 System.out.write().</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">WriteDemo</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">;
        </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">A</span><span class="hl-quotes">'</span><span class="hl-code">;
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">write</span><span class="hl-brackets">(</span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">write</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-special">\n</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>运行以上实例在输出窗口输出 "A" 字符</p>&#13;
<pre>&#13;
A&#13;
</pre>&#13;
<p><strong>注意：</strong>write() 方法不经常使用，因为 print() 和 println() 方法用起来更为方便。&#13;
</p>&#13;
<hr/><h2>读写文件</h2>&#13;
<p>&#13;
如前所述，一个流被定义为一个数据序列。输入流用于从源读取数据，输出流用于向目标写数据。&#13;
</p><p>下图是一个描述输入流和输出流的类层次图。</p>&#13;
<p>&#13;
<a href="https://www.runoob.com/wp-content/uploads/2013/12/iostream2xx.png" target="_blank" rel="noopener"><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/12/iostream2xx.png"/></a></p>&#13;
<p>下面将要讨论的两个重要的流是 <strong>FileInputStream</strong> 和 <strong>FileOutputStream</strong>。&#13;
</p><hr/>&#13;
<h2>FileInputStream</h2>&#13;
<p>该流用于从文件读取数据，它的对象可以用关键字 new 来创建。&#13;
</p><p>有多种构造方法可用来创建对象。&#13;
</p><p>可以使用字符串类型的文件名来创建一个输入流对象来读取文件：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">InputStream</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">C:/java/hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>也可以使用一个文件对象来创建一个输入流对象来读取文件。我们首先得使用 File() 方法来创建一个文件对象：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">C:/java/hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">InputStream</span><span class="hl-code"> </span><span class="hl-identifier">in</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>创建了InputStream对象，就可以使用下面的方法来读取流或者进行其他的流操作。</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th style="width:44px;">&#13;
				<strong>序号</strong></th>&#13;
			<th style="width:533px;">&#13;
				<strong>方法及描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:44px;">&#13;
				1</td>&#13;
			<td style="width:533px;">&#13;
				<strong>public void close() throws IOException{}</strong><br/>&#13;
				关闭此文件输入流并释放与此流有关的所有系统资源。抛出IOException异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:44px;">&#13;
				2</td>&#13;
			<td style="width:533px;">&#13;
				<strong>protected void finalize()throws IOException {}</strong><br/>&#13;
				这个方法清除与该文件的连接。确保在不再引用文件输入流时调用其 close 方法。抛出IOException异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:44px;">&#13;
				3</td>&#13;
			<td style="width:533px;">&#13;
				<strong>public int read(int r)throws IOException{}</strong><br/>&#13;
				这个方法从 InputStream 对象读取指定字节的数据。返回为整数值。返回下一字节数据，如果已经到结尾则返回-1。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:44px;">&#13;
				4</td>&#13;
			<td style="width:533px;">&#13;
				<strong>public int read(byte[] r) throws IOException{}</strong><br/>&#13;
				这个方法从输入流读取r.length长度的字节。返回读取的字节数。如果是文件结尾则返回-1。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:44px;">&#13;
				5</td>&#13;
			<td style="width:533px;">&#13;
				<strong>public int available() throws IOException{}</strong><br/>&#13;
				返回下一次对此输入流调用的方法可以不受阻塞地从此输入流读取的字节数。返回一个整数值。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>除了 InputStream 外，还有一些其他的输入流，更多的细节参考下面链接：</p>&#13;
<ul>&#13;
<li>&#13;
<a href="/java/java-bytearrayinputstream.html" target="_blank" rel="noopener">ByteArrayInputStream</a></li><li>&#13;
<a href="/java/java-datainputstream.html" target="_blank" rel="noopener">DataInputStream</a></li>&#13;
</ul>&#13;
<hr/><h2>&#13;
FileOutputStream</h2><p>&#13;
该类用来创建一个文件并向文件中写数据。</p><p>&#13;
如果该流在打开文件进行输出前，目标文件不存在，那么该流会创建该文件。</p><p>&#13;
有两个构造方法可以用来创建 FileOutputStream 对象。</p><p>&#13;
使用字符串类型的文件名来创建一个输出流对象：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">OutputStream</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileOutputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">C:/java/hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>也可以使用一个文件对象来创建一个输出流来写文件。我们首先得使用File()方法来创建一个文件对象：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">C:/java/hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">OutputStream</span><span class="hl-code"> </span><span class="hl-identifier">fOut</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileOutputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
创建OutputStream 对象完成后，就可以使用下面的方法来写入流或者进行其他的流操作。&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th style="width:47px;">&#13;
				<strong>序号</strong></th>&#13;
			<th style="width:529px;">&#13;
				<strong>方法及描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:47px;">&#13;
				1</td>&#13;
			<td style="width:529px;">&#13;
				<strong>public void close() throws IOException{}</strong><br/>&#13;
				关闭此文件输入流并释放与此流有关的所有系统资源。抛出IOException异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:47px;">&#13;
				2</td>&#13;
			<td style="width:529px;">&#13;
				<strong>protected void finalize()throws IOException {}</strong><br/>&#13;
				这个方法清除与该文件的连接。确保在不再引用文件输入流时调用其 close 方法。抛出IOException异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:47px;">&#13;
				3</td>&#13;
			<td style="width:529px;">&#13;
				<strong>public void write(int w)throws IOException{}</strong><br/>&#13;
				这个方法把指定的字节写到输出流中。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:47px;">&#13;
				4</td>&#13;
			<td style="width:529px;">&#13;
				<strong>public void write(byte[] w)</strong><br/>&#13;
				把指定数组中w.length长度的字节写到OutputStream中。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>除了OutputStream外，还有一些其他的输出流，更多的细节参考下面链接：</p>&#13;
<ul>&#13;
<li>&#13;
<a href="/java/java-bytearrayoutputstream.html" target="_blank" rel="noopener">ByteArrayOutputStream</a></li><li>&#13;
<a href="/java/java-dataoutputstream.html" target="_blank" rel="noopener">DataOutputStream</a></li></ul>&#13;
<h3>实例</h3>&#13;
<p>&#13;
下面是一个演示 InputStream 和 OutputStream 用法的例子：&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">fileStreamTest.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">fileStreamTest</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">try</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-types">byte</span><span class="hl-code"> </span><span class="hl-identifier">bWrite</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-code"> </span><span class="hl-number">11</span><span class="hl-code">, </span><span class="hl-number">21</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">40</span><span class="hl-code">, </span><span class="hl-number">5</span><span class="hl-code"> </span><span class="hl-brackets">}</span><span class="hl-code">;
            </span><span class="hl-identifier">OutputStream</span><span class="hl-code"> </span><span class="hl-identifier">os</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileOutputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">test.txt</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">x</span><span class="hl-code"> &lt; </span><span class="hl-identifier">bWrite</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">x</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-identifier">os</span><span class="hl-code">.</span><span class="hl-identifier">write</span><span class="hl-brackets">(</span><span class="hl-identifier">bWrite</span><span class="hl-brackets">[</span><span class="hl-identifier">x</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment"> writes the bytes</span><span class="hl-comment"/><span class="hl-code">
            </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-identifier">os</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
            </span><span class="hl-identifier">InputStream</span><span class="hl-code"> </span><span class="hl-identifier">is</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">test.txt</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">size</span><span class="hl-code"> = </span><span class="hl-identifier">is</span><span class="hl-code">.</span><span class="hl-identifier">available</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
            </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">size</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">is</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">  </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-identifier">is</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">catch</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Exception</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上面的程序首先创建文件test.txt，并把给定的数字以二进制形式写进该文件，同时输出到控制台上。&#13;
</p>&#13;
<p>以上代码由于是二进制写入，可能存在乱码，你可以使用以下代码实例来解决乱码问题：</p>&#13;
<div class="example">&#13;
<h2 class="example">fileStreamTest2.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment">文件名 :fileStreamTest2.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">fileStreamTest2</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
        </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">a.txt</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">FileOutputStream</span><span class="hl-code"> </span><span class="hl-identifier">fop</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileOutputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 构建FileOutputStream对象,文件不存在会自动新建</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">OutputStreamWriter</span><span class="hl-code"> </span><span class="hl-identifier">writer</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">OutputStreamWriter</span><span class="hl-brackets">(</span><span class="hl-identifier">fop</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">UTF-8</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 构建OutputStreamWriter对象,参数可以指定编码,默认为操作系统默认编码,windows上是gbk</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">writer</span><span class="hl-code">.</span><span class="hl-identifier">append</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">中文输入</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 写入到缓冲区</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">writer</span><span class="hl-code">.</span><span class="hl-identifier">append</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\r</span><span class="hl-special">\n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 换行</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">writer</span><span class="hl-code">.</span><span class="hl-identifier">append</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">English</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 刷新缓存冲,写入到文件,如果下面已经没有写入的内容了,直接close也会写入</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">writer</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 关闭写入流,同时会把缓冲区内容写入文件,所以上面的注释掉</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">fop</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 关闭输出流,释放系统资源</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">FileInputStream</span><span class="hl-code"> </span><span class="hl-identifier">fip</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 构建FileInputStream对象</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">InputStreamReader</span><span class="hl-code"> </span><span class="hl-identifier">reader</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InputStreamReader</span><span class="hl-brackets">(</span><span class="hl-identifier">fip</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">UTF-8</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 构建InputStreamReader对象,编码与写入相同</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">StringBuffer</span><span class="hl-code"> </span><span class="hl-identifier">sb</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">StringBuffer</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">reader</span><span class="hl-code">.</span><span class="hl-identifier">ready</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">sb</span><span class="hl-code">.</span><span class="hl-identifier">append</span><span class="hl-brackets">(</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">reader</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-comment">//</span><span class="hl-comment"> 转成char加到StringBuffer对象中</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">sb</span><span class="hl-code">.</span><span class="hl-identifier">toString</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">reader</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 关闭读取流</span><span class="hl-comment"/><span class="hl-code">
 
        </span><span class="hl-identifier">fip</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 关闭输入流,释放系统资源</span><span class="hl-comment"/><span class="hl-code">
 
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>文件和I/O</h2><p>&#13;
还有一些关于文件和I/O的类，我们也需要知道：</p>&#13;
<ul>&#13;
<li>&#13;
<a href="/java/java-file.html" target="_blank" rel="noopener">File Class(类)</a></li><li>&#13;
<a href="/java/java-filereader.html" target="_blank" rel="noopener">FileReader Class(类)</a></li><li>&#13;
<a href="/java/java-filewriter.html" target="_blank" rel="noopener">FileWriter Class(类)</a></li></ul>&#13;
<hr/>&#13;
<h2>Java中的目录</h2>&#13;
&#13;
<h3>创建目录：</h3><p>&#13;
File类中有两个方法可以用来创建文件夹：</p>&#13;
<ul>&#13;
<li>&#13;
		<strong>mkdir( )</strong>方法创建一个文件夹，成功则返回true，失败则返回false。失败表明File对象指定的路径已经存在，或者由于整个路径还不存在，该文件夹不能被创建。</li>&#13;
	<li>&#13;
		<strong>mkdirs()</strong>方法创建一个文件夹和它的所有父文件夹。</li>&#13;
</ul>&#13;
<p>&#13;
下面的例子创建 "/tmp/user/java/bin"文件夹：</p>&#13;
<div class="example">&#13;
<h2 class="example">CreateDir.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.</span><span class="hl-identifier">File</span><span class="hl-code">;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">CreateDir</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">dirname</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">/tmp/user/java/bin</span><span class="hl-quotes">"</span><span class="hl-code">;
        </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-identifier">dirname</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-comment">//</span><span class="hl-comment"> 现在创建目录</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-identifier">d</span><span class="hl-code">.</span><span class="hl-identifier">mkdirs</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>编译并执行上面代码来创建目录 "/tmp/user/java/bin"。&#13;
</p><p><strong>注意：</strong> Java 在 UNIX 和 Windows 自动按约定分辨文件路径分隔符。如果你在 Windows 版本的 Java 中使用分隔符 (/) ，路径依然能够被正确解析。&#13;
</p><hr/>&#13;
<h2>读取目录</h2>&#13;
<p>&#13;
一个目录其实就是一个 File 对象，它包含其他文件和文件夹。&#13;
</p><p>如果创建一个 File 对象并且它是一个目录，那么调用 isDirectory() 方法会返回 true。&#13;
</p><p>可以通过调用该对象上的 list() 方法，来提取它包含的文件和文件夹的列表。&#13;
</p><p>下面展示的例子说明如何使用 list() 方法来检查一个文件夹中包含的内容：</p>&#13;
<div class="example">&#13;
<h2 class="example">DirList.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.</span><span class="hl-identifier">File</span><span class="hl-code">;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">DirList</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">dirname</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">/tmp</span><span class="hl-quotes">"</span><span class="hl-code">;
        </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f1</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-identifier">dirname</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">f1</span><span class="hl-code">.</span><span class="hl-identifier">isDirectory</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">目录 </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">dirname</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">f1</span><span class="hl-code">.</span><span class="hl-identifier">list</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">s</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-identifier">dirname</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string">/</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-code">.</span><span class="hl-identifier">isDirectory</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                    </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> 是一个目录</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">else</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                    </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> 是一个文件</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">else</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">dirname</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> 不是一个目录</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
目录 /tmp&#13;
bin 是一个目录&#13;
lib 是一个目录&#13;
demo 是一个目录&#13;
test.txt 是一个文件&#13;
README 是一个文件&#13;
index.html 是一个文件&#13;
include 是一个目录&#13;
</pre>&#13;
<hr/>&#13;
<h2>删除目录或文件</h2>&#13;
<p>删除文件可以使用  <strong>java.io.File.delete()</strong> 方法。</p>&#13;
<p>以下代码会删除目录 <strong>/tmp/java/</strong>，需要注意的是当删除某一目录时，必须保证该目录下没有其他文件才能正确删除，否则将删除失败。</p>&#13;
<p>测试目录结构：</p>&#13;
<pre>&#13;
/tmp/java/&#13;
|-- 1.log&#13;
|-- test&#13;
</pre>&#13;
<div class="example">&#13;
<h2 class="example">DeleteFileDemo.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.</span><span class="hl-identifier">File</span><span class="hl-code">;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">DeleteFileDemo</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-comment">//</span><span class="hl-comment"> 这里修改为自己的测试目录</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">folder</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">File</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">/tmp/java/</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">deleteFolder</span><span class="hl-brackets">(</span><span class="hl-identifier">folder</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
 
    </span><span class="hl-comment">//</span><span class="hl-comment"> 删除文件及目录</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">deleteFolder</span><span class="hl-brackets">(</span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">folder</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">File</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">files</span><span class="hl-code"> = </span><span class="hl-identifier">folder</span><span class="hl-code">.</span><span class="hl-identifier">listFiles</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">files</span><span class="hl-code"> != </span><span class="hl-reserved">null</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">File</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code"> : </span><span class="hl-identifier">files</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-code">.</span><span class="hl-identifier">isDirectory</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                    </span><span class="hl-identifier">deleteFolder</span><span class="hl-brackets">(</span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">else</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
                    </span><span class="hl-identifier">f</span><span class="hl-code">.</span><span class="hl-identifier">delete</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
                </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-identifier">folder</span><span class="hl-code">.</span><span class="hl-identifier">delete</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>