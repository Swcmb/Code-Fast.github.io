<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 内存管理</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">内存管理</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>本章将讲解 C 中的动态内存管理。C 语言为内存的分配和管理提供了几个函数。这些函数可以在 <b>&lt;stdlib.h&gt;</b> 头文件中找到。</p>&#13;
<p>&#13;
在 C 语言中，内存是通过指针变量来管理的。指针是一个变量，它存储了一个内存地址，这个内存地址可以指向任何数据类型的变量，包括整数、浮点数、字符和数组等。C 语言提供了一些函数和运算符，使得程序员可以对内存进行操作，包括分配、释放、移动和复制等。</p>&#13;
&#13;
&#13;
<table class="reference">&#13;
<tr><th>序号</th><th>函数和描述</th></tr>&#13;
<tr><td>1</td><td><b>void *calloc(int num, int size);</b><br/>在内存中动态地分配 num 个长度为 size 的连续空间，并将每一个字节都初始化为 0。所以它的结果是分配了 num*size 个字节长度的内存空间，并且每个字节的值都是 0。</td></tr>&#13;
<tr><td>2</td><td><b>void free(void *address); </b><br/>该函数释放 address 所指向的内存块,释放的是动态分配的内存空间。</td></tr>&#13;
<tr><td>3</td><td><b>void *malloc(int num); </b><br/>在堆区分配一块指定大小的内存空间，用来存放数据。这块内存空间在函数执行完成后不会被初始化，它们的值是未知的。</td></tr>&#13;
<tr><td>4</td><td><b>void *realloc(void *address, int newsize); </b><br/>该函数重新分配内存，把内存扩展到 <b>newsize</b>。</td></tr>&#13;
</table>&#13;
<p><strong>注意：</strong>void * 类型表示未确定类型的指针。C、C++ 规定 void * 类型可以通过类型转换强制转换为任何其它类型的指针。</p>&#13;
</div>&#13;
<br/>&#13;
<h2 class="tutheader">动态分配内存</h2>&#13;
<p>编程时，如果您预先知道数组的大小，那么定义数组时就比较容易。例如，一个存储人名的数组，它最多容纳 100 个字符，所以您可以定义数组，如下所示：</p>&#13;
<pre>&#13;
char name[100];&#13;
</pre>&#13;
<p>但是，如果您预先不知道需要存储的文本长度，例如您想存储有关一个主题的详细描述。在这里，我们需要定义一个指针，该指针指向未定义所需内存大小的字符，后续再根据需求来分配内存，如下所示：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-brackets">[</span><span class="hl-number">100</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-identifier">description</span><span class="hl-code">;
 
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-identifier">name</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Zara Ali</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 动态分配内存 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">description</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-identifier">malloc</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">200</span><span class="hl-code"> * </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code"> == </span><span class="hl-prepro">NULL</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Error - unable to allocate required memory</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Zara ali a DPS student in class 10th</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Name = %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">name</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Description: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">description</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Name = Zara Ali&#13;
Description: Zara ali a DPS student in class 10th&#13;
</pre>&#13;
<p>上面的程序也可以使用 <b>calloc()</b> 来编写，只需要把 malloc 替换为 calloc 即可，如下所示：</p>&#13;
<pre>&#13;
calloc(200, sizeof(char));&#13;
</pre>&#13;
<p>当动态分配内存时，您有完全控制权，可以传递任何大小的值。而那些预先定义了大小的数组，一旦定义则无法改变大小。</p>&#13;
&#13;
<h2 class="tutheader">重新调整内存的大小和释放内存</h2>&#13;
<p>当程序退出时，操作系统会自动释放所有分配给程序的内存，但是，建议您在不需要内存时，都应该调用函数 <b>free()</b> 来释放内存。</p>&#13;
<p>或者，您可以通过调用函数 <b>realloc()</b> 来增加或减少已分配的内存块的大小。让我们使用 realloc() 和 free() 函数，再次查看上面的实例：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdlib.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-brackets">[</span><span class="hl-number">100</span><span class="hl-brackets">]</span><span class="hl-code">;
   </span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-identifier">description</span><span class="hl-code">;
 
   </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-identifier">name</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Zara Ali</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 动态分配内存 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">description</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-identifier">malloc</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">30</span><span class="hl-code"> * </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code"> == </span><span class="hl-prepro">NULL</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Error - unable to allocate required memory</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">strcpy</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Zara ali a DPS student.</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 假设您想要存储更大的描述信息 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">description</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-code"> *</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">realloc</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code">, </span><span class="hl-number">100</span><span class="hl-code"> * </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code"> == </span><span class="hl-prepro">NULL</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">fprintf</span><span class="hl-brackets">(</span><span class="hl-identifier">stderr</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Error - unable to allocate required memory</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">strcat</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">description</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">She is in class 10th</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Name = %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">name</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Description: %s</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">description</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 使用 free() 函数释放内存 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">free</span><span class="hl-brackets">(</span><span class="hl-identifier">description</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Name = Zara Ali&#13;
Description: Zara ali a DPS student.She is in class 10th&#13;
</pre>&#13;
<p>您可以尝试一下不重新分配额外的内存，strcat() 函数会生成一个错误，因为存储 description 时可用的内存不足。</p>&#13;
&#13;
<h3> C 语言中常用的内存管理函数和运算符</h3>&#13;
<ul><li><p>malloc() 函数：用于动态分配内存。它接受一个参数，即需要分配的内存大小（以字节为单位），并返回一个指向分配内存的指针。</p></li><li><p>free() 函数：用于释放先前分配的内存。它接受一个指向要释放内存的指针作为参数，并将该内存标记为未使用状态。</p></li><li><p>calloc() 函数：用于动态分配内存，并将其初始化为零。它接受两个参数，即需要分配的内存块数和每个内存块的大小（以字节为单位），并返回一个指向分配内存的指针。</p></li><li><p>realloc() 函数：用于重新分配内存。它接受两个参数，即一个先前分配的指针和一个新的内存大小，然后尝试重新调整先前分配的内存块的大小。如果调整成功，它将返回一个指向重新分配内存的指针，否则返回一个空指针。</p></li><li><p>sizeof 运算符：用于获取数据类型或变量的大小（以字节为单位）。</p></li><li><p>指针运算符：用于获取指针所指向的内存地址或变量的值。</p></li><li><p>&amp; 运算符：用于获取变量的内存地址。</p></li><li> <p><span class="marked">*</span> 运算符：用于获取指针所指向的变量的值。</p></li>&#13;
<li><p><span class="marked">-&gt; </span>运算符：用于指针访问结构体成员，语法为 <span class="marked">pointer-&gt;member</span>，等价于 <span class="marked">(*pointer).member</span>。</p></li>&#13;
&#13;
<li><p>memcpy() 函数：用于从源内存区域复制数据到目标内存区域。它接受三个参数，即目标内存区域的指针、源内存区域的指针和要复制的数据大小（以字节为单位）。</p></li><li><p>memmove() 函数：类似于 memcpy() 函数，但它可以处理重叠的内存区域。它接受三个参数，即目标内存区域的指针、源内存区域的指针和要复制的数据大小（以字节为单位）。</p></li></ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>