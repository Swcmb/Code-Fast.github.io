<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 头文件</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C <span class="color_h1">头文件</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>头文件是扩展名为 <b>.h</b> 的文件，包含了 C 函数声明和宏定义，被多个源文件中引用共享。有两种类型的头文件：程序员编写的头文件和编译器自带的头文件。</p>&#13;
<p>在程序中要使用头文件，需要使用 C 预处理指令 <b>#include</b> 来引用它。前面我们已经看过 <b>stdio.h</b> 头文件，它是编译器自带的头文件。</p>&#13;
<p>引用头文件相当于复制头文件的内容，但是我们不会直接在源文件中复制头文件的内容，因为这么做很容易出错，特别在程序是由多个源文件组成的时候。</p>&#13;
<p>A simple practice in C 或 C++ 程序中，建议把所有的常量、宏、系统全局变量和函数原型写在头文件中，在需要的时候随时引用这些头文件。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">引用头文件的语法</h2>&#13;
<p>使用预处理指令 <b>#include</b> 可以引用用户和系统头文件。它的形式有以下两种：</p>&#13;
<pre>&#13;
#include &lt;file&gt;&#13;
</pre>&#13;
<p>这种形式用于引用系统头文件。它在系统目录的标准列表中搜索名为 file 的文件。在编译源代码时，您可以通过 -I 选项把目录前置在该列表前。</p>&#13;
<pre>&#13;
#include "file"&#13;
</pre>&#13;
<p>这种形式用于引用用户头文件。它在包含当前文件的目录中搜索名为 file 的文件。在编译源代码时，您可以通过 -I 选项把目录前置在该列表前。</p>&#13;
&#13;
<h2 class="tutheader">引用头文件的操作</h2>&#13;
<p><b>#include</b> 指令会指示 C 预处理器浏览指定的文件作为输入。预处理器的输出包含了已经生成的输出，被引用文件生成的输出以及 <b>#include</b> 指令之后的文本输出。例如，如果您有一个头文件 header.h，如下：</p>&#13;
<pre>&#13;
char *test (void);&#13;
</pre>&#13;
<p>和一个使用了头文件的主程序 <i>program.c</i>，如下：</p>&#13;
<pre>&#13;
int x;&#13;
#include "header.h"&#13;
&#13;
int main (void)&#13;
{&#13;
   puts (test ());&#13;
}&#13;
</pre>&#13;
<p>编译器会看到如下的代码信息：</p>&#13;
<pre>&#13;
int x;&#13;
char *test (void);&#13;
&#13;
int main (void)&#13;
{&#13;
   puts (test ());&#13;
}&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">只引用一次头文件</h2>&#13;
<p>如果一个头文件被引用两次，编译器会处理两次头文件的内容，这将产生错误。为了防止这种情况，标准的做法是把文件的整个内容放在条件编译语句中，如下：</p>&#13;
<pre>&#13;
#ifndef HEADER_FILE&#13;
#define HEADER_FILE&#13;
&#13;
the entire header file file&#13;
&#13;
#endif&#13;
</pre>&#13;
<p>这种结构就是通常所说的包装器 <b>#ifndef</b>。当再次引用头文件时，条件为假，因为 HEADER_FILE 已定义。此时，预处理器会跳过文件的整个内容，编译器会忽略它。</p>&#13;
&#13;
<h2 class="tutheader">有条件引用</h2>&#13;
<p>有时需要从多个不同的头文件中选择一个引用到程序中。例如，需要指定在不同的操作系统上使用的配置参数。您可以通过一系列条件来实现这点，如下：</p>&#13;
<pre>&#13;
#if SYSTEM_1&#13;
   # include "system_1.h"&#13;
#elif SYSTEM_2&#13;
   # include "system_2.h"&#13;
#elif SYSTEM_3&#13;
   ...&#13;
#endif&#13;
</pre>&#13;
<p>但是如果头文件比较多的时候，这么做是很不妥当的，预处理器使用宏来定义头文件的名称。这就是所谓的<b>有条件引用</b>。它不是用头文件的名称作为 <b>#include</b> 的直接参数，您只需要使用宏名称代替即可：</p>&#13;
<pre>&#13;
 #define SYSTEM_H "system_1.h"&#13;
 ...&#13;
 #include SYSTEM_H&#13;
</pre>&#13;
<p>SYSTEM_H 会扩展，预处理器会查找 system_1.h，就像 <b>#include</b> 最初编写的那样。SYSTEM_H 可通过 -D 选项被您的 Makefile 定义。</p>&#13;
<hr/><h2>标准库头文件</h2>&#13;
<p>C 标准库头文件（Standard Library Header Files）是由 ANSI C（也称为 C89/C90）和 ISO C（C99 和 C11）标准定义的一组头文件，这些头文件提供了大量的函数、宏和类型定义，用于处理输入输出、字符串操作、数学计算、内存管理等常见的编程任务。</p>&#13;
<p>以下是一些常见的 C 标准库头文件及其功能简介：</p>&#13;
&#13;
<table class="reference">&#13;
    <thead>&#13;
        <tr>&#13;
            <th>头文件</th>&#13;
            <th>功能简介</th>&#13;
        </tr>&#13;
    </thead>&#13;
    <tbody>&#13;
        <tr>&#13;
            <td><strong>&lt;stdio.h&gt;</strong></td>&#13;
            <td>标准输入输出库，包含 <code>printf</code>、<code>scanf</code> 等函数</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;stdlib.h&gt;</strong></td>&#13;
            <td>标准库函数，包含内存分配、程序控制等函数</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;string.h&gt;</strong></td>&#13;
            <td>字符串操作函数，如 <code>strlen</code>、<code>strcpy</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;math.h&gt;</strong></td>&#13;
            <td>数学函数库，如 <code>sin</code>、<code>cos</code>、<code>sqrt</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;time.h&gt;</strong></td>&#13;
            <td>时间和日期函数，如 <code>time</code>、<code>strftime</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;ctype.h&gt;</strong></td>&#13;
            <td>字符处理函数，如 <code>isalpha</code>、<code>isdigit</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;limits.h&gt;</strong></td>&#13;
            <td>定义各种类型的限制值，如 <code>INT_MAX</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;float.h&gt;</strong></td>&#13;
            <td>定义浮点类型的限制值，如 <code>FLT_MAX</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;assert.h&gt;</strong></td>&#13;
            <td>断言宏 <code>assert</code>，用于调试检查</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;errno.h&gt;</strong></td>&#13;
            <td>定义错误码变量 <code>errno</code> 及相关宏</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;stddef.h&gt;</strong></td>&#13;
            <td>定义通用类型和宏，如 <code>size_t</code>、<code>NULL</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;signal.h&gt;</strong></td>&#13;
            <td>处理信号的函数和宏，如 <code>signal</code> 等</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;setjmp.h&gt;</strong></td>&#13;
            <td>提供非本地跳转功能的宏和函数</td>&#13;
        </tr>&#13;
        <tr>&#13;
            <td><strong>&lt;locale.h&gt;</strong></td>&#13;
            <td>地域化相关的函数和宏，如 <code>setlocale</code> 等</td>&#13;
        </tr>&#13;
    </tbody>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>