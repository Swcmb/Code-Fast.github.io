<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 位域</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">位域</span></h1><p>&#13;
C 语言的位域（bit-field）是一种特殊的结构体成员，允许我们按位对成员进行定义，指定其占用的位数。</p>&#13;
<p>如果程序的结构中包含多个开关的变量，即变量值为 <strong>TRUE/FALSE</strong>，如下：</p>&#13;
<pre>&#13;
struct&#13;
{&#13;
  unsigned int widthValidated;&#13;
  unsigned int heightValidated;&#13;
} status;&#13;
</pre>&#13;
<p>这种结构需要 8 字节的内存空间，但在实际上，在每个变量中，我们只存储 0 或 1，在这种情况下，C 语言提供了一种更好的利用内存空间的方式。如果您在结构内使用这样的变量，您可以定义变量的宽度来告诉编译器，您将只使用这些字节。例如，上面的结构可以重写成：</p>&#13;
<pre>&#13;
struct&#13;
{&#13;
  unsigned int widthValidated : 1;&#13;
  unsigned int heightValidated : 1;&#13;
} status;&#13;
</pre>&#13;
<p>现在，上面的结构中，status 变量将占用 4 个字节的内存空间，但是只有 2 位被用来存储值。如果您用了 32 个变量，每一个变量宽度为 1 位，那么 status 结构将使用 4 个字节，但只要您再多用一个变量，如果使用了 33 个变量，那么它将分配内存的下一段来存储第 33 个变量，这个时候就开始使用 8 个字节。让我们看看下面的实例来理解这个概念：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 定义简单的结构 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
</span><span class="hl-types">struct</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">widthValidated</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">heightValidated</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">status1</span><span class="hl-code">;
 
</span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 定义位域结构 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
</span><span class="hl-types">struct</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">widthValidated</span><span class="hl-code"> : </span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">heightValidated</span><span class="hl-code"> : </span><span class="hl-number">1</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">status2</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Memory size occupied by status1 : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-identifier">status1</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Memory size occupied by status2 : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-identifier">status2</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Memory size occupied by status1 : 8&#13;
Memory size occupied by status2 : 4&#13;
</pre>&#13;
<p>位域的特点和使用方法如下：</p>&#13;
<ul><li>定义位域时，可以指定成员的位域宽度，即成员所占用的位数。</li><li>位域的宽度不能超过其数据类型的大小，因为位域必须适应所使用的整数类型。</li><li>位域的数据类型可以是 <code>int</code>、<code>unsigned int</code>、<code>signed int</code> 等整数类型，也可以是枚举类型。</li><li>位域可以单独使用，也可以与其他成员一起组成结构体。</li><li>位域的访问是通过点运算符（<code>.</code>）来实现的，与普通的结构体成员访问方式相同。</li></ul>&#13;
<h2 class="tutheader">位域声明</h2>&#13;
<p>有些信息在存储时，并不需要占用一个完整的字节，而只需占几个或一个二进制位。例如在存放一个开关量时，只有 0 和 1 两种状态，用 1 位二进位即可。为了节省存储空间，并使处理简便，C 语言又提供了一种数据结构，称为"位域"或"位段"。</p>&#13;
<p>所谓"位域"是把一个字节中的二进位划分为几个不同的区域，并说明每个区域的位数。每个域有一个域名，允许在程序中按域名进行操作。这样就可以把几个不同的对象用一个字节的二进制位域来表示。</p>&#13;
<p>典型的实例：</p>&#13;
<ul>&#13;
<li>用 1 位二进位存放一个开关量时，只有 0 和 1 两种状态。</li>&#13;
<li>读取外部文件格式——可以读取非标准的文件格式。例如：9 位的整数。</li>&#13;
</ul>&#13;
<h3>位域的定义和位域变量的说明</h3>&#13;
<p>位域定义与结构定义相仿，其形式为：</p>&#13;
<pre>&#13;
struct 位域结构名 &#13;
{&#13;
&#13;
 位域列表&#13;
&#13;
};&#13;
</pre>&#13;
<p>其中位域列表的形式为：</p>&#13;
<pre>&#13;
type [member_name] : width ;&#13;
</pre>&#13;
&#13;
<p>下面是有关位域中变量元素的描述：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:20%">元素</th><th>描述</th></tr>&#13;
<tr><td>type</td><td>只能为 int(整型)，unsigned int(无符号整型)，signed int(有符号整型) 三种类型，决定了如何解释位域的值。</td></tr>&#13;
<tr><td>member_name</td><td>位域的名称。</td></tr>&#13;
<tr><td>width</td><td>位域中位的数量。宽度必须小于或等于指定类型的位宽度。</td></tr>&#13;
</table>&#13;
<p>带有预定义宽度的变量被称为<b>位域</b>。位域可以存储多于 1 位的数，例如，需要一个变量来存储从 0 到 7 的值，您可以定义一个宽度为 3 位的位域，如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">struct</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> : </span><span class="hl-number">3</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">Age</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上面的结构定义指示 C 编译器，age 变量将只使用 3 位来存储这个值，如果您试图使用超过 3 位，则无法完成。&#13;
</p>&#13;
&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">bs</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">:</span><span class="hl-number">8</span><span class="hl-code">;
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">:</span><span class="hl-number">2</span><span class="hl-code">;
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">:</span><span class="hl-number">6</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-identifier">data</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码定义了一个名为 <strong>struct bs</strong> 的结构体，data 为 bs 的结构体变量，共占四个字节：</p>&#13;
<p>对于位域来说，它们的宽度不能超过其数据类型的大小，在这种情况下，int 类型的大小通常是 4 个字节（32位）。</p><p>&#13;
相邻位域字段的类型相同，且其位宽之和小于类型的 sizeo f大小，则后面的字段将紧邻前一个字段存储，直到不能容纳为止。</p>&#13;
<p>让我们再来看一个实例：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">packed_struct</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">f1</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">f2</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">f3</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">f4</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">type</span><span class="hl-code">:</span><span class="hl-number">4</span><span class="hl-code">;
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">my_int</span><span class="hl-code">:</span><span class="hl-number">9</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">pack</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div><p>&#13;
以上代码定义了一个名为 packed_struct 的结构体，其中包含了六个成员变量，pack 为 packed_struct 的结构体变量。</p>&#13;
<p>在这里，packed_struct 包含了 6 个成员：四个 1 位的标识符 f1..f4、一个 4 位的 type 和一个 9 位的 my_int。</p>&#13;
&#13;
<p>让我们来看下面的实例：</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例 1</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">struct</span> packed_struct <span style="color: #000;">{</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> f1 <span style="color: #339933;">:</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span>   <span style="color: #666666; font-style: italic;">// 1位的位域</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> f2 <span style="color: #339933;">:</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span>   <span style="color: #666666; font-style: italic;">// 1位的位域</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> f3 <span style="color: #339933;">:</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span>   <span style="color: #666666; font-style: italic;">// 1位的位域</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> f4 <span style="color: #339933;">:</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span>   <span style="color: #666666; font-style: italic;">// 1位的位域</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> type <span style="color: #339933;">:</span> <span style="color: #164;">4</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 4位的位域</span><br/>
   <span style="color: #993333;">unsigned</span> <span style="color: #993333;">int</span> my_int <span style="color: #339933;">:</span> <span style="color: #164;">9</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 9位的位域</span><br/>
<span style="color: #000;">}</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
   <span style="color: #993333;">struct</span> packed_struct pack<span style="color: #339933;">;</span><br/>
<br/>
   pack.<span style="color: #202020;">f1</span> <span style="color: #339933;">=</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span><br/>
   pack.<span style="color: #202020;">f2</span> <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
   pack.<span style="color: #202020;">f3</span> <span style="color: #339933;">=</span> <span style="color: #164;">1</span><span style="color: #339933;">;</span><br/>
   pack.<span style="color: #202020;">f4</span> <span style="color: #339933;">=</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
   pack.<span style="color: #202020;">type</span> <span style="color: #339933;">=</span> <span style="color: #164;">7</span><span style="color: #339933;">;</span><br/>
   pack.<span style="color: #202020;">my_int</span> <span style="color: #339933;">=</span> <span style="color: #164;">255</span><span style="color: #339933;">;</span><br/>
<br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"f1: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">f1</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"f2: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">f2</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"f3: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">f3</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"f4: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">f4</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"type: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">type</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"my_int: %u<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> pack.<span style="color: #202020;">my_int</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
   <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>&#13;
以上实例定义了一个名为 packed_struct 的结构体，其中包含了多个位域成员。</p><p>在 main 函数中，创建了一个 packed_struct 类型的结构体变量 pack，并分别给每个位域成员赋值。</p><p>然后使用 printf 语句打印出每个位域成员的值。</p>&#13;
<p>&#13;
输出结果为：</p>&#13;
<pre>f1: 1&#13;
f2: 0&#13;
f3: 1&#13;
f4: 0&#13;
type: 7&#13;
my_int: 255</pre>&#13;
<div class="example">&#13;
<h2 class="example">实例 2</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">string.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">struct</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> : </span><span class="hl-number">3</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">Age</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> = </span><span class="hl-number">4</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Sizeof( Age ) : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-reserved">sizeof</span><span class="hl-brackets">(</span><span class="hl-identifier">Age</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Age.age : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> = </span><span class="hl-number">7</span><span class="hl-code">;
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Age.age : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> = </span><span class="hl-number">8</span><span class="hl-code">; </span><span class="hl-comment">// 二进制表示为 1000 有四位，超出</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-quotes">"</span><span class="hl-string">Age.age : %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">Age</span><span class="hl-code">.</span><span class="hl-identifier">age</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译时，它会带有警告，当上面的代码被执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Sizeof( Age ) : 4&#13;
Age.age : 4&#13;
Age.age : 7&#13;
Age.age : 0&#13;
</pre>&#13;
<p>计算字节数：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<br/>
<span style="color: #993333;">struct</span> example1 <span style="color: #000;">{</span><br/>
   <span style="color: #993333;">int</span> a <span style="color: #339933;">:</span> <span style="color: #164;">4</span><span style="color: #339933;">;</span><br/>
   <span style="color: #993333;">int</span> b <span style="color: #339933;">:</span> <span style="color: #164;">5</span><span style="color: #339933;">;</span><br/>
   <span style="color: #993333;">int</span> c <span style="color: #339933;">:</span> <span style="color: #164;">7</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
   <span style="color: #993333;">struct</span> example1 ex1<span style="color: #339933;">;</span><br/>
<br/>
   <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Size of example1: %lu bytes<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #993333;">sizeof</span><span style="color: #000;">(</span>ex1<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
   <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div><p>&#13;
以上实例中，example1 结构体包含三个位域成员 a，b 和 c，它们分别占用 4 位、5 位和 7 位。</p><p>通过 sizeof 运算符计算出 example1 结构体的字节数，并输出结果：</p>&#13;
<pre>Size of example1: 4 bytes</pre>&#13;
&#13;
<p><b>对于位域的定义尚有以下几点说明：</b></p>&#13;
<ul>&#13;
<li>&#13;
<p>一个位域存储在同一个字节中，如一个字节所剩空间不够存放另一位域时，则会从下一单元起存放该位域。也可以有意使某位域从下一单元开始。例如：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">bs</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">:</span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-types">unsigned</span><span class="hl-code">  :</span><span class="hl-number">4</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 空域 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">:</span><span class="hl-number">4</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 从下一单元开始存放 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">:</span><span class="hl-number">4</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在这个位域定义中，a 占第一字节的 4 位，后 4 位填 0 表示不使用，b 从第二字节开始，占用 4 位，c 占用 4 位。</p>&#13;
</li>&#13;
<li><p>位域的宽度不能超过它所依附的数据类型的长度，成员变量都是有类型的，这个类型限制了成员变量的最大长度，<span class="marked">:</span> 后面的数字不能超过这个长度。</p></li>&#13;
<li>&#13;
<p>位域可以是无名位域，这时它只用来作填充或调整位置。无名的位域是不能使用的。例如：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">k</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
    </span><span class="hl-types">int</span><span class="hl-code">  :</span><span class="hl-number">2</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 该 2 位不能使用 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">:</span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">:</span><span class="hl-number">2</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
</li>&#13;
</ul>&#13;
<p>从以上分析可以看出，位域在本质上就是一种结构类型，不过其成员是按二进位分配的。</p>&#13;
<h3>位域的使用</h3>&#13;
<p>位域的使用和结构成员的使用相同，其一般形式为：</p>&#13;
<pre>&#13;
位域变量名.位域名&#13;
位域变量名-&gt;位域名&#13;
</pre>&#13;
<p>位域允许用各种格式输出。</p>&#13;
<p>请看下面的实例：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">struct</span><span class="hl-code"> </span><span class="hl-identifier">bs</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">:</span><span class="hl-number">1</span><span class="hl-code">;
        </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">:</span><span class="hl-number">3</span><span class="hl-code">;
        </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">:</span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-identifier">bit</span><span class="hl-code">,*</span><span class="hl-identifier">pbit</span><span class="hl-code">;
    </span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">a</span><span class="hl-code">=</span><span class="hl-number">1</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 给位域赋值（应注意赋值不能超过该位域的允许范围） </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">b</span><span class="hl-code">=</span><span class="hl-number">7</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 给位域赋值（应注意赋值不能超过该位域的允许范围） </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">c</span><span class="hl-code">=</span><span class="hl-number">15</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 给位域赋值（应注意赋值不能超过该位域的允许范围） </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">%d,%d,%d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">a</span><span class="hl-code">,</span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">b</span><span class="hl-code">,</span><span class="hl-identifier">bit</span><span class="hl-code">.</span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 以整型量格式输出三个域的内容 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">pbit</span><span class="hl-code">=&amp;</span><span class="hl-identifier">bit</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 把位域变量 bit 的地址送给指针变量 pbit </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">a</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 用指针方式给位域 a 重新赋值，赋为 0 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">b</span><span class="hl-code">&amp;=</span><span class="hl-number">3</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 使用了复合的位运算符 "&amp;="，相当于：pbit-&gt;b=pbit-&gt;b&amp;3，位域 b 中原有值为 7，与 3 作按位与运算的结果为 3（111&amp;011=011，十进制值为 3） </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">c</span><span class="hl-code">|=</span><span class="hl-number">1</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 使用了复合位运算符"|="，相当于：pbit-&gt;c=pbit-&gt;c|1，其结果为 15 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
    </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">%d,%d,%d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">,</span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">a</span><span class="hl-code">,</span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">b</span><span class="hl-code">,</span><span class="hl-identifier">pbit</span><span class="hl-code">-&gt;</span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code">;    </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 用指针方式输出了这三个域的值 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上例程序中定义了位域结构 bs，三个位域为 a、b、c。说明了 bs 类型的变量 bit 和指向 bs 类型的指针变量 pbit。这表示位域也是可以使用指针的。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>