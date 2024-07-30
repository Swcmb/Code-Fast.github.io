<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <stdio.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;stdio.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p><b>stdio .h</b> 头文件定义了三个变量类型、一些宏和各种函数来执行输入和输出。</p>&#13;
<p><code>&lt;stdio.h&gt;</code> 是 C 标准库中的一个头文件，定义了处理文件和标准输入/输出流的各种函数和类型。</p>&#13;
<h2>库变量</h2>&#13;
<p>下面是头文件 stdio.h 中定义的变量类型：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>变量 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>size_t </b><br/>这是无符号整数类型，它是 <b>sizeof</b> 关键字的结果，表示对象大小。</td></tr>&#13;
<tr><td>2</td><td><b>FILE </b><br/>文件流类型，适合存储文件流信息的对象类型。</td></tr>&#13;
<tr><td>3</td><td><b>fpos_t </b><br/>文件位置类型，适合存储文件中任何位置的对象类型。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库宏</h2>&#13;
<p>下面是头文件 stdio.h 中定义的宏：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:5%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><b>NULL</b><br/>这个宏是一个空指针常量的值。</td></tr>&#13;
<tr><td>2</td><td><b>_IOFBF、_IOLBF</b> 和 <b> _IONBF </b><br/>这些宏扩展了带有特定值的整型常量表达式，并适用于 <b>setvbuf</b> 函数的第三个参数。</td></tr>&#13;
<tr><td>3</td><td><b>BUFSIZ</b><br/>这个宏是一个整数，该整数代表了 <b>setbuf</b> 函数使用的缓冲区大小。</td></tr>&#13;
<tr><td>4</td><td><b>EOF</b> <br/>这个宏是一个表示已经到达文件结束的负整数。</td></tr>&#13;
<tr><td>5</td><td><b>FOPEN_MAX</b> <br/>这个宏是一个整数，该整数代表了系统可以同时打开的文件数量。</td></tr>&#13;
<tr><td>6</td><td><b>FILENAME_MAX</b> <br/>这个宏是一个整数，该整数代表了字符数组可以存储的文件名的最大长度。如果实现没有任何限制，则该值应为推荐的最大值。</td></tr>&#13;
<tr><td>7</td><td><b>L_tmpnam</b> <br/>这个宏是一个整数，该整数代表了字符数组可以存储的由 tmpnam 函数创建的临时文件名的最大长度。</td></tr>&#13;
<tr><td>8</td><td><b>SEEK_CUR、SEEK_END</b> 和 <b>SEEK_SET</b> <br/>这些宏是在 <b>fseek</b> 函数中使用，用于在一个文件中定位不同的位置。</td></tr>&#13;
<tr><td>9</td><td><b>TMP_MAX </b> <br/>这个宏是 tmpnam 函数可生成的独特文件名的最大数量。</td></tr>&#13;
<tr><td>10</td><td><b>stderr、stdin</b> 和 <b>stdout </b> <br/>这些宏是指向 FILE 类型的指针，分别对应于标准错误、标准输入和标准输出流。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库函数</h2>&#13;
<p>下面是头文件 stdio.h 中定义的函数：</p>&#13;
<blockquote>为了更好地理解函数，请按照下面的序列学习这些函数，因为第一个函数中创建的文件会在后续的函数中使用到。</blockquote>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">序号</th><th>函数 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-function-fclose.html">int fclose(FILE *stream)</a><br/>关闭流 stream。刷新所有的缓冲区。</td></tr>&#13;
<tr><td>2</td><td><a href="c-function-clearerr.html">void clearerr(FILE *stream)</a><br/>清除给定流 stream 的文件结束和错误标识符。</td></tr>&#13;
<tr><td>3</td><td><a href="c-function-feof.html">int feof(FILE *stream)</a><br/>测试给定流 stream 的文件结束标识符。</td></tr>&#13;
<tr><td>4</td><td><a href="c-function-ferror.html">int ferror(FILE *stream)</a><br/>测试给定流 stream 的错误标识符。</td></tr>&#13;
<tr><td>5</td><td><a href="c-function-fflush.html">int fflush(FILE *stream)</a><br/>刷新流 stream 的输出缓冲区。</td></tr>&#13;
<tr><td>6</td><td><a href="c-function-fgetpos.html">int fgetpos(FILE *stream, fpos_t *pos)</a><br/>获取流 stream 的当前文件位置，并把它写入到 pos。</td></tr>&#13;
<tr><td>7</td><td><a href="c-function-fopen.html">FILE *fopen(const char *filename, const char *mode)</a><br/>使用给定的模式 mode 打开 filename 所指向的文件。</td></tr>&#13;
<tr><td>8</td><td><a href="c-function-fread.html">size_t fread(void *ptr, size_t size, size_t nmemb, FILE *stream)</a><br/>从给定流 stream 读取数据到 ptr 所指向的数组中。</td></tr>&#13;
<tr><td>9</td><td><a href="c-function-freopen.html">FILE *freopen(const char *filename, const char *mode, FILE *stream)</a><br/>把一个新的文件名 filename 与给定的打开的流 stream 关联，同时关闭流中的旧文件。</td></tr>&#13;
<tr><td>10</td><td><a href="c-function-fseek.html">int fseek(FILE *stream, long int offset, int whence)</a><br/>设置流 stream 的文件位置为给定的偏移 offset，参数 <i>offset</i> 意味着从给定的 <i>whence</i> 位置查找的字节数。</td></tr>&#13;
<tr><td>11</td><td><a href="c-function-fsetpos.html">int fsetpos(FILE *stream, const fpos_t *pos)</a><br/>设置给定流 stream 的文件位置为给定的位置。参数 <i>pos</i> 是由函数 fgetpos 给定的位置。</td></tr>&#13;
<tr><td>12</td><td><a href="c-function-ftell.html">long int ftell(FILE *stream)</a><br/>返回给定流 stream 的当前文件位置。</td></tr>&#13;
<tr><td>13</td><td><a href="c-function-fwrite.html">size_t fwrite(const void *ptr, size_t size, size_t nmemb, FILE *stream)</a><br/>把 ptr 所指向的数组中的数据写入到给定流 stream 中。</td></tr>&#13;
<tr><td>14</td><td><a href="c-function-remove.html">int remove(const char *filename)</a><br/>删除给定的文件名 filename，以便它不再被访问。</td></tr>&#13;
<tr><td>15</td><td><a href="c-function-rename.html">int rename(const char *old_filename, const char *new_filename)</a><br/>把 old_filename 所指向的文件名改为 new_filename。</td></tr>&#13;
<tr><td>16</td><td><a href="c-function-rewind.html">void rewind(FILE *stream)</a><br/>设置文件位置为给定流 stream 的文件的开头。</td></tr>&#13;
<tr><td>17</td><td><a href="c-function-setbuf.html">void setbuf(FILE *stream, char *buffer)</a><br/>定义流 stream 应如何缓冲。</td></tr>&#13;
<tr><td>18</td><td><a href="c-function-setvbuf.html">int setvbuf(FILE *stream, char *buffer, int mode, size_t size)</a><br/>另一个定义流 stream 应如何缓冲的函数。</td></tr>&#13;
<tr><td>19</td><td><a href="c-function-tmpfile.html">FILE *tmpfile(void)</a><br/>以二进制更新模式(wb+)创建临时文件。</td></tr>&#13;
<tr><td>20</td><td><a href="c-function-tmpnam.html">char *tmpnam(char *str)</a><br/>生成并返回一个有效的临时文件名，该文件名之前是不存在的。</td></tr>&#13;
<tr><td>21</td><td><a href="c-function-fprintf.html">int fprintf(FILE *stream, const char *format, ...)</a><br/>发送格式化输出到流 stream 中。</td></tr>&#13;
<tr><td>22</td><td><a href="c-function-printf.html">int printf(const char *format, ...)</a><br/>发送格式化输出到标准输出 stdout。</td></tr>&#13;
<tr><td>23</td><td><a href="c-function-sprintf.html">int sprintf(char *str, const char *format, ...)</a><br/>发送格式化输出到字符串。</td></tr>&#13;
<tr><td>24</td><td><a href="c-function-vfprintf.html">int vfprintf(FILE *stream, const char *format, va_list arg)</a><br/>使用参数列表发送格式化输出到流 stream 中。</td></tr>&#13;
<tr><td>25</td><td><a href="c-function-vprintf.html">int vprintf(const char *format, va_list arg)</a><br/>使用参数列表发送格式化输出到标准输出 stdout。</td></tr>&#13;
<tr><td>26</td><td><a href="c-function-vsprintf.html">int vsprintf(char *str, const char *format, va_list arg)</a><br/>使用参数列表发送格式化输出到字符串。</td></tr>&#13;
<tr><td>27</td><td><a href="c-function-fscanf.html">int fscanf(FILE *stream, const char *format, ...)</a><br/>从流 stream 读取格式化输入。</td></tr>&#13;
<tr><td>28</td><td><a href="c-function-scanf.html">int scanf(const char *format, ...)</a><br/>从标准输入 stdin 读取格式化输入。</td></tr>&#13;
<tr><td>29</td><td><a href="c-function-sscanf.html">int sscanf(const char *str, const char *format, ...)</a><br/>从字符串读取格式化输入。</td></tr>&#13;
<tr><td>30</td><td><a href="c-function-fgetc.html">int fgetc(FILE *stream)</a><br/>从指定的流 stream 获取下一个字符（一个无符号字符），并把位置标识符往前移动。</td></tr>&#13;
<tr><td>31</td><td><a href="c-function-fgets.html">char *fgets(char *str, int n, FILE *stream)</a><br/>从指定的流 stream 读取一行，并把它存储在 str 所指向的字符串内。当读取 <b>(n-1)</b> 个字符时，或者读取到换行符时，或者到达文件末尾时，它会停止，具体视情况而定。</td></tr>&#13;
<tr><td>32</td><td><a href="c-function-fputc.html">int fputc(int char, FILE *stream)</a><br/>把参数 char 指定的字符（一个无符号字符）写入到指定的流 stream 中，并把位置标识符往前移动。</td></tr>&#13;
<tr><td>33</td><td><a href="c-function-fputs.html">int fputs(const char *str, FILE *stream)</a><br/>把字符串写入到指定的流 stream 中，但不包括空字符。</td></tr>&#13;
<tr><td>34</td><td><a href="c-function-getc.html">int getc(FILE *stream)</a><br/>从指定的流 stream 获取下一个字符（一个无符号字符），并把位置标识符往前移动。</td></tr>&#13;
<tr><td>35</td><td><a href="c-function-getchar.html">int getchar(void)</a><br/>从标准输入 stdin 获取一个字符（一个无符号字符）。</td></tr>&#13;
<tr><td>36</td><td><a href="c-function-gets.html">char *gets(char *str)</a><br/>从标准输入 stdin 读取一行，并把它存储在 str 所指向的字符串中。当读取到换行符时，或者到达文件末尾时，它会停止，具体视情况而定。</td></tr>&#13;
<tr><td>37</td><td><a href="c-function-putc.html">int putc(int char, FILE *stream)</a><br/>把参数 char 指定的字符（一个无符号字符）写入到指定的流 stream 中，并把位置标识符往前移动。</td></tr>&#13;
<tr><td>38</td><td><a href="c-function-putchar.html">int putchar(int char)</a><br/>把参数 char 指定的字符（一个无符号字符）写入到标准输出 stdout 中。</td></tr>&#13;
<tr><td>39</td><td><a href="c-function-puts.html">int puts(const char *str)</a><br/>把一个字符串写入到标准输出 stdout，直到空字符，但不包括空字符。换行符会被追加到输出中。</td></tr>&#13;
<tr><td>40</td><td><a href="c-function-ungetc.html">int ungetc(int char, FILE *stream)</a><br/>把字符 char（一个无符号字符）推入到指定的流 stream 中，以便它是下一个被读取到的字符。</td></tr>&#13;
<tr><td>41</td><td><a href="c-function-perror.html">void perror(const char *str)</a><br/>把一个描述性错误消息输出到标准错误 stderr。首先输出字符串 str，后跟一个冒号，然后是一个空格。</td></tr>&#13;
<tr><td>42</td><td><a href="c-function-snprintf.html">int snprintf(char *str, size_t size, const char *format, ...)</a><br/>格式字符串到 str 中。</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>&#13;
以下是一些使用 <code>&lt;stdio.h&gt;</code> 中函数的示例：</p>&#13;
<p>&#13;
打开和关闭文件:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    FILE <span style="color: #339933;">*</span>file <span style="color: #339933;">=</span> <span style="color: #000066;">fopen</span><span style="color: #000;">(</span><span style="color: #a11;">"example.txt"</span><span style="color: #339933;">,</span> <span style="color: #a11;">"r"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">if</span> <span style="color: #000;">(</span>file <span style="color: #339933;">==</span> NULL<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">perror</span><span style="color: #000;">(</span><span style="color: #a11;">"Error opening file"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #708;">return</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
    <span style="color: #666666; font-style: italic;">// 进行文件操作</span><br/>
    <span style="color: #000066;">fclose</span><span style="color: #000;">(</span>file<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
<p>读取文件内容:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    FILE <span style="color: #339933;">*</span>file <span style="color: #339933;">=</span> <span style="color: #000066;">fopen</span><span style="color: #000;">(</span><span style="color: #a11;">"example.txt"</span><span style="color: #339933;">,</span> <span style="color: #a11;">"r"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">if</span> <span style="color: #000;">(</span>file <span style="color: #339933;">==</span> NULL<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">perror</span><span style="color: #000;">(</span><span style="color: #a11;">"Error opening file"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #708;">return</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
<br/>
    <span style="color: #993333;">char</span> buffer<span style="color: #000;">[</span><span style="color: #164;">256</span><span style="color: #000;">]</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">while</span> <span style="color: #000;">(</span><span style="color: #000066;">fgets</span><span style="color: #000;">(</span>buffer<span style="color: #339933;">,</span> <span style="color: #993333;">sizeof</span><span style="color: #000;">(</span>buffer<span style="color: #000;">)</span><span style="color: #339933;">,</span> file<span style="color: #000;">)</span> <span style="color: #339933;">!=</span> NULL<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"%s"</span><span style="color: #339933;">,</span> buffer<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
<br/>
    <span style="color: #000066;">fclose</span><span style="color: #000;">(</span>file<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
写入文件内容:&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    FILE <span style="color: #339933;">*</span>file <span style="color: #339933;">=</span> <span style="color: #000066;">fopen</span><span style="color: #000;">(</span><span style="color: #a11;">"example.txt"</span><span style="color: #339933;">,</span> <span style="color: #a11;">"w"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">if</span> <span style="color: #000;">(</span>file <span style="color: #339933;">==</span> NULL<span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
        <span style="color: #000066;">perror</span><span style="color: #000;">(</span><span style="color: #a11;">"Error opening file"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #708;">return</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000;">}</span><br/>
<br/>
    <span style="color: #000066;">fprintf</span><span style="color: #000;">(</span>file<span style="color: #339933;">,</span> <span style="color: #a11;">"Hello, World!<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #000066;">fclose</span><span style="color: #000;">(</span>file<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><h3>注意事项</h3><ul><li>使用 <code>fopen</code> 打开文件后，务必使用 <code>fclose</code> 关闭文件，以避免文件资源泄漏。</li><li>使用 <code>fgets</code> 读取字符串时，务必注意缓冲区的大小，以避免缓冲区溢出。</li><li>使用 <code>printf</code>、<code>scanf</code> 等函数时，务必注意格式化字符串的正确性，以避免未定义行为。</li></ul><p>通过理解和使用 <code>&lt;stdio.h&gt;</code> 提供的函数，可以方便地进行文件和标准输入/输出操作，编写更为健壮和灵活的 C 程序。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>