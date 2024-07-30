<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 文件读写</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">文件读写</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>上一章我们讲解了 C 语言处理的标准输入和输出设备。本章我们将介绍 C 程序员如何创建、打开、关闭文本文件或二进制文件。</p>&#13;
<p>一个文件，无论它是文本文件还是二进制文件，都是代表了一系列的字节。C 语言不仅提供了访问顶层的函数，也提供了底层（OS）调用来处理存储设备上的文件。本章将讲解文件管理的重要调用。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">打开文件</h2>&#13;
<p>您可以使用 <b>fopen( )</b> 函数来创建一个新的文件或者打开一个已有的文件，这个调用会初始化类型 <b>FILE</b> 的一个对象，类型 <b>FILE</b> 包含了所有用来控制流的必要的信息。下面是这个函数调用的原型：</p>&#13;
<pre>&#13;
FILE *fopen( const char *filename, const char *mode );&#13;
</pre>&#13;
<p>在这里，<b>filename</b> 是字符串，用来命名文件，访问模式 <b>mode</b> 的值可以是下列值中的一个：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">模式</th><th>描述</th></tr>&#13;
<tr><td>r</td><td>打开一个已有的文本文件，允许读取文件。</td></tr>&#13;
<tr><td>w</td><td>打开一个文本文件，允许写入文件。如果文件不存在，则会创建一个新文件。在这里，您的程序会从文件的开头写入内容。如果文件存在，则该会被截断为零长度，重新写入。</td></tr>&#13;
<tr><td>a</td><td>打开一个文本文件，以追加模式写入文件。如果文件不存在，则会创建一个新文件。在这里，您的程序会在已有的文件内容中追加内容。</td></tr>&#13;
<tr><td>r+</td><td>打开一个文本文件，允许读写文件。</td></tr>&#13;
<tr><td>w+</td><td>打开一个文本文件，允许读写文件。如果文件已存在，则文件会被截断为零长度，如果文件不存在，则会创建一个新文件。</td></tr>&#13;
<tr><td>a+</td><td>打开一个文本文件，允许读写文件。如果文件不存在，则会创建一个新文件。读取会从文件的开头开始，写入则只能是追加模式。</td></tr>&#13;
</table>&#13;
<p>如果处理的是二进制文件，则需使用下面的访问模式来取代上面的访问模式：</p>&#13;
<pre>&#13;
"rb", "wb", "ab", "rb+", "r+b", "wb+", "w+b", "ab+", "a+b"&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">关闭文件</h2>&#13;
<p>为了关闭文件，请使用 fclose( ) 函数。函数的原型如下：</p>&#13;
<pre>&#13;
 int fclose( FILE *fp );&#13;
</pre>&#13;
<p>如果成功关闭文件，<b>fclose( )</b> 函数返回零，如果关闭文件时发生错误，函数返回 <b>EOF</b>。这个函数实际上，会清空缓冲区中的数据，关闭文件，并释放用于该文件的所有内存。EOF 是一个定义在头文件 <b>stdio.h</b> 中的常量。</p>&#13;
<p>C 标准库提供了各种函数来按字符或者以固定长度字符串的形式读写文件。</p>&#13;
&#13;
<h2 class="tutheader">写入文件</h2>&#13;
<p>下面是把字符写入到流中的最简单的函数：</p>&#13;
<pre>&#13;
int fputc( int c, FILE *fp );&#13;
</pre>&#13;
<p>函数 <b>fputc()</b> 把参数 c 的字符值写入到 fp 所指向的输出流中。如果写入成功，它会返回写入的字符，如果发生错误，则会返回 <b>EOF</b>。您可以使用下面的函数来把一个以 null 结尾的字符串写入到流中：</p> &#13;
<pre>&#13;
int fputs( const char *s, FILE *fp );&#13;
</pre>&#13;
<p>函数 <b>fputs()</b> 把字符串 <b>s</b> 写入到 fp 所指向的输出流中。如果写入成功，它会返回一个非负值，如果发生错误，则会返回 <b>EOF</b>。您也可以使用 <b>int fprintf(FILE *fp,const char *format, ...)</b> 函数把一个字符串写入到文件中。尝试下面的实例：</p>&#13;
&#13;
&#13;
<blockquote><p><b>注意：</b>请确保您有可用的 <b>tmp</b> 目录，如果不存在该目录，则需要在您的计算机上先创建该目录。</p>&#13;
<p><span class="marked">/tmp</span> 一般是 Linux 系统上的临时目录，如果你在 Windows 系统上运行，则需要修改为本地环境中已存在的目录，例如:<span class="marked"> C:\tmp</span>、<span class="marked">D:\tmp</span>等。</p>&#13;
</blockquote>&#13;
&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">FILE</span><span class="hl-code"> *</span><span class="hl-identifier">fp</span><span class="hl-code"> = </span><span class="hl-prepro">NULL</span><span class="hl-code">;
 
   </span><span class="hl-identifier">fp</span><span class="hl-code"> = </span><span class="hl-identifier">fopen</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">/tmp/test.txt</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">w+</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">fp</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">This is testing for fprintf...</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">fputs</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">This is testing for fputs...</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">fp</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">fclose</span><span class="hl-brackets">(</span><span class="hl-identifier">fp</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会在 /tmp 目录中创建一个新的文件 <b>test.txt</b>，并使用两个不同的函数写入两行。接下来让我们来读取这个文件。</p>&#13;
&#13;
<h2 class="tutheader">读取文件</h2>&#13;
<p>下面是从文件读取单个字符的最简单的函数：</p>&#13;
<pre>&#13;
int fgetc( FILE * fp );&#13;
</pre>&#13;
<p><b>fgetc()</b> 函数从 fp 所指向的输入文件中读取一个字符。返回值是读取的字符，如果发生错误则返回 <b>EOF</b>。下面的函数允许您从流中读取一个字符串：</p>&#13;
<pre>&#13;
char *fgets( char *buf, int n, FILE *fp );&#13;
</pre>&#13;
<p>函数 <b>fgets()</b> 从 fp 所指向的输入流中读取 n - 1 个字符。它会把读取的字符串复制到缓冲区 <b>buf</b>，并在最后追加一个 <b>null</b> 字符来终止字符串。</p>&#13;
<p>如果这个函数在读取最后一个字符之前就遇到一个换行符 '\n' 或文件的末尾 EOF，则只会返回读取到的字符，包括换行符。您也可以使用 <b>int fscanf(FILE *fp, const char *format, ...)</b> 函数来从文件中读取字符串，但是在遇到第一个空格和换行符时，它会停止读取。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">FILE</span><span class="hl-code"> *</span><span class="hl-identifier">fp</span><span class="hl-code"> = </span><span class="hl-prepro">NULL</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">buff</span><span class="hl-brackets">[</span><span class="hl-number">255</span><span class="hl-brackets">]</span><span class="hl-code">;
 
   </span><span class="hl-identifier">fp</span><span class="hl-code"> = </span><span class="hl-identifier">fopen</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">/tmp/test.txt</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">r</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">fscanf</span><span class="hl-brackets">(</span><span class="hl-identifier">fp</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">%s</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">buff</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">buff</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">fgets</span><span class="hl-brackets">(</span><span class="hl-identifier">buff</span><span class="hl-code">, </span><span class="hl-number">255</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-identifier">FILE</span><span class="hl-code">*</span><span class="hl-brackets">)</span><span class="hl-identifier">fp</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">2: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">buff</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-identifier">fgets</span><span class="hl-brackets">(</span><span class="hl-identifier">buff</span><span class="hl-code">, </span><span class="hl-number">255</span><span class="hl-code">, </span><span class="hl-brackets">(</span><span class="hl-identifier">FILE</span><span class="hl-code">*</span><span class="hl-brackets">)</span><span class="hl-identifier">fp</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">3: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">buff</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">fclose</span><span class="hl-brackets">(</span><span class="hl-identifier">fp</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会读取上一部分创建的文件，产生下列结果：</p>&#13;
<pre>&#13;
1: This&#13;
2: is testing for fprintf...&#13;
&#13;
3: This is testing for fputs...&#13;
</pre>&#13;
<p>首先，<b>fscanf()</b> 方法只读取了 <b>This</b>，因为它在后边遇到了一个空格。其次，调用 <b>fgets()</b> 读取剩余的部分，直到行尾。最后，调用 <b>fgets()</b> 完整地读取第二行。</p>&#13;
&#13;
<h2 class="tutheader">二进制 I/O 函数</h2>&#13;
<p>下面两个函数用于二进制输入和输出：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">fread</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">ptr</span><span class="hl-code">, </span><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">size_of_elements</span><span class="hl-code">, 
             </span><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">number_of_elements</span><span class="hl-code">, </span><span class="hl-identifier">FILE</span><span class="hl-code"> *</span><span class="hl-identifier">a_file</span><span class="hl-brackets">)</span><span class="hl-code">;
              
</span><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">fwrite</span><span class="hl-brackets">(</span><span class="hl-types">const</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> *</span><span class="hl-identifier">ptr</span><span class="hl-code">, </span><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">size_of_elements</span><span class="hl-code">, 
             </span><span class="hl-identifier">size_t</span><span class="hl-code"> </span><span class="hl-identifier">number_of_elements</span><span class="hl-code">, </span><span class="hl-identifier">FILE</span><span class="hl-code"> *</span><span class="hl-identifier">a_file</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>这两个函数都是用于存储块的读写 - 通常是数组或结构体。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>