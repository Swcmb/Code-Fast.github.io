<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 文件和流</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">文件和流</span></h1>&#13;
&#13;
<p>到目前为止，我们已经使用了 <b>iostream</b> 标准库，它提供了 <b>cin</b> 和 <b>cout</b> 方法分别用于从标准输入读取流和向标准输出写入流。</p>&#13;
<p>本教程介绍如何从文件读取流和向文件写入流。这就需要用到 C++ 中另一个标准库 <b>fstream</b>，它定义了三个新的数据类型：</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="30%">数据类型</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr> &#13;
<td>ofstream</td>&#13;
<td>该数据类型表示输出文件流，用于创建文件并向文件写入信息。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>ifstream</td>&#13;
<td>该数据类型表示输入文件流，用于从文件读取信息。</td> &#13;
</tr>&#13;
<tr> &#13;
<td>fstream</td>&#13;
<td>该数据类型通常表示文件流，且同时具有 ofstream 和 ifstream 两种功能，这意味着它可以创建文件，向文件写入信息，从文件读取信息。</td> &#13;
</tr>&#13;
</table>&#13;
<p>要在 C++ 中进行文件处理，必须在 C++ 源代码文件中包含头文件 &lt;iostream&gt; 和 &lt;fstream&gt;。</p>&#13;
&#13;
<h2>打开文件</h2>&#13;
<p>在从文件读取信息或者向文件写入信息之前，必须先打开文件。<b>ofstream</b> 和 <b>fstream</b> 对象都可以用来打开文件进行写操作，如果只需要打开文件进行读操作，则使用 <b>ifstream</b> 对象。</p>&#13;
<p>下面是 open() 函数的标准语法，open() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。</p>&#13;
<pre>&#13;
void open(const char *filename, ios::openmode mode);&#13;
</pre>&#13;
<p>在这里，<b>open()</b> 成员函数的第一参数指定要打开的文件的名称和位置，第二个参数定义文件被打开的模式。</p>&#13;
<table class="reference notranslate">&#13;
<tr>&#13;
<th width="30%">模式标志</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr> &#13;
<td>ios::app</td>&#13;
<td>追加模式。所有写入都追加到文件末尾。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>ios::ate</td>&#13;
<td>文件打开后定位到文件末尾。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>ios::in</td>&#13;
<td>打开文件用于读取。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>ios::out</td>&#13;
<td>打开文件用于写入。</td>&#13;
</tr>&#13;
<tr> &#13;
<td>ios::trunc</td>&#13;
<td>如果该文件已经存在，其内容将在打开文件之前被截断，即把文件长度设为 0。</td>&#13;
</tr>&#13;
</table>&#13;
<p>您可以把以上两种或两种以上的模式结合使用。例如，如果您想要以写入模式打开文件，并希望截断文件，以防文件已存在，那么您可以使用下面的语法：</p>&#13;
<pre>&#13;
ofstream outfile;&#13;
outfile.open("file.dat", ios::out | ios::trunc );&#13;
</pre>&#13;
<p>类似地，您如果想要打开一个文件用于读写，可以使用下面的语法：</p>&#13;
<pre>&#13;
ifstream  afile;&#13;
afile.open("file.dat", ios::out | ios::in );&#13;
</pre>&#13;
&#13;
<h2>关闭文件</h2>&#13;
<p>当 C++ 程序终止时，它会自动关闭刷新所有流，释放所有分配的内存，并关闭所有打开的文件。但程序员应该养成一个好习惯，在程序终止前关闭所有打开的文件。</p>&#13;
<p>下面是 close() 函数的标准语法，close() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。</p>&#13;
<pre>&#13;
void close();&#13;
</pre>&#13;
&#13;
<h2>写入文件</h2>&#13;
<p>在 C++ 编程中，我们使用流插入运算符（ &lt;&lt; ）向文件写入信息，就像使用该运算符输出信息到屏幕上一样。唯一不同的是，在这里您使用的是 <b>ofstream</b> 或 <b>fstream</b> 对象，而不是 <b>cout</b> 对象。</p>&#13;
&#13;
<h2>读取文件</h2>&#13;
<p>在 C++ 编程中，我们使用流提取运算符（ &gt;&gt; ）从文件读取信息，就像使用该运算符从键盘输入信息一样。唯一不同的是，在这里您使用的是 <b>ifstream</b> 或 <b>fstream</b> 对象，而不是 <b>cin</b> 对象。</p>&#13;
&#13;
<h2>读取 &amp; 写入实例</h2>&#13;
<p>下面的 C++ 程序以读写模式打开一个文件。在向文件 afile.dat 写入用户输入的信息之后，程序从文件读取信息，并将其输出到屏幕上：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">fstream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">data</span><span class="hl-brackets">[</span><span class="hl-number">100</span><span class="hl-brackets">]</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 以写模式打开文件</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">ofstream</span><span class="hl-code"> </span><span class="hl-identifier">outfile</span><span class="hl-code">;
   </span><span class="hl-identifier">outfile</span><span class="hl-code">.</span><span class="hl-identifier">open</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">afile.dat</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Writing to the file</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Enter your name: </span><span class="hl-quotes">"</span><span class="hl-code">; 
   </span><span class="hl-identifier">cin</span><span class="hl-code">.</span><span class="hl-identifier">getline</span><span class="hl-brackets">(</span><span class="hl-identifier">data</span><span class="hl-code">, </span><span class="hl-number">100</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 向文件写入用户输入的数据</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">outfile</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">data</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Enter your age: </span><span class="hl-quotes">"</span><span class="hl-code">; 
   </span><span class="hl-identifier">cin</span><span class="hl-code"> &gt;&gt; </span><span class="hl-identifier">data</span><span class="hl-code">;
   </span><span class="hl-identifier">cin</span><span class="hl-code">.</span><span class="hl-identifier">ignore</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 再次向文件写入用户输入的数据</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">outfile</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">data</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 关闭打开的文件</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">outfile</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 以读模式打开文件</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">ifstream</span><span class="hl-code"> </span><span class="hl-identifier">infile</span><span class="hl-code">; 
   </span><span class="hl-identifier">infile</span><span class="hl-code">.</span><span class="hl-identifier">open</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">afile.dat</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">; 
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Reading from the file</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">; 
   </span><span class="hl-identifier">infile</span><span class="hl-code"> &gt;&gt; </span><span class="hl-identifier">data</span><span class="hl-code">; 
 
   </span><span class="hl-comment">// 在屏幕上写入数据</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">data</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 再次从文件读取数据，并显示它</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">infile</span><span class="hl-code"> &gt;&gt; </span><span class="hl-identifier">data</span><span class="hl-code">; 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">data</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">; 
 
   </span><span class="hl-comment">// 关闭打开的文件</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">infile</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列输入和输出：</p>&#13;
<pre>&#13;
$./a.out&#13;
Writing to the file&#13;
Enter your name: Zara&#13;
Enter your age: 9&#13;
Reading from the file&#13;
Zara&#13;
9&#13;
</pre>&#13;
<p>上面的实例中使用了 cin 对象的附加函数，比如 getline()函数从外部读取一行，ignore() 函数会忽略掉之前读语句留下的多余字符。</p>&#13;
&#13;
<h2>文件位置指针</h2>&#13;
<p><b>istream</b> 和 <b>ostream</b> 都提供了用于重新定位文件位置指针的成员函数。这些成员函数包括关于 istream 的 <b>seekg</b>（"seek get"）和关于 ostream 的 <b>seekp</b>（"seek put"）。</p>&#13;
<p>seekg 和 seekp 的参数通常是一个长整型。第二个参数可以用于指定查找方向。查找方向可以是 <b>ios::beg</b>（默认的，从流的开头开始定位），也可以是 <b>ios::cur</b>（从流的当前位置开始定位），也可以是 <b>ios::end</b>（从流的末尾开始定位）。</p>&#13;
<p>文件位置指针是一个整数值，指定了从文件的起始位置到指针所在位置的字节数。下面是关于定位 "get" 文件位置指针的实例：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">// 定位到 fileObject 的第 n 个字节（假设是 ios::beg）</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">fileObject</span><span class="hl-code">.</span><span class="hl-identifier">seekg</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">n</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-comment">// 把文件的读指针从 fileObject 当前位置向后移 n 个字节</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">fileObject</span><span class="hl-code">.</span><span class="hl-identifier">seekg</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">n</span><span class="hl-code">, </span><span class="hl-identifier">ios</span><span class="hl-code">::</span><span class="hl-identifier">cur</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-comment">// 把文件的读指针从 fileObject 末尾往回移 n 个字节</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">fileObject</span><span class="hl-code">.</span><span class="hl-identifier">seekg</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">n</span><span class="hl-code">, </span><span class="hl-identifier">ios</span><span class="hl-code">::</span><span class="hl-identifier">end</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-comment">// 定位到 fileObject 的末尾</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">fileObject</span><span class="hl-code">.</span><span class="hl-identifier">seekg</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">, </span><span class="hl-identifier">ios</span><span class="hl-code">::</span><span class="hl-identifier">end</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>