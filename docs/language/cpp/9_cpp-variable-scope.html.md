<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 变量作用域</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">变量作用域</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>一般来说有三个地方可以定义变量：</p>&#13;
<ul class="list">&#13;
<li><p>在函数或一个代码块内部声明的变量，称为<strong>局部变量</strong>。</p></li>&#13;
<li><p>在函数参数的定义中声明的变量，称为<strong>形式参数</strong>。</p></li>&#13;
<li><p>在所有函数外部声明的变量，称为<strong>全局变量</strong>。</p></li>&#13;
&#13;
</ul><p>&#13;
作用域是程序的一个区域，变量的作用域可以分为以下几种：</p>&#13;
&#13;
<ul><li><p><strong>局部作用域</strong>：在函数内部声明的变量具有局部作用域，它们只能在函数内部访问。局部变量在函数每次被调用时被创建，在函数执行完后被销毁。</p></li>&#13;
<li><p><strong>全局作用域</strong>：在所有函数和代码块之外声明的变量具有全局作用域，它们可以被程序中的任何函数访问。全局变量在程序开始时被创建，在程序结束时被销毁。</p></li>&#13;
<li><p><strong>块作用域</strong>：在代码块内部声明的变量具有块作用域，它们只能在代码块内部访问。块作用域变量在代码块每次被执行时被创建，在代码块执行完后被销毁。</p></li><li><p><strong>类作用域</strong>：在类内部声明的变量具有类作用域，它们可以被类的所有成员函数访问。类作用域变量的生命周期与类的生命周期相同。</p></li></ul>&#13;
</div>&#13;
<p><strong>注意：</strong>如果在内部作用域中声明的变量与外部作用域中的变量同名，则内部作用域中的变量将覆盖外部作用域中的变量。</p>&#13;
<h2 class="tutheader">局部变量</h2>&#13;
<p>在函数或一个代码块内部声明的变量，称为局部变量。它们只能被函数内部或者代码块内部的语句使用。下面的实例使用了局部变量：</p>&#13;
&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">// 局部变量声明</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">, </span><span class="hl-identifier">b</span><span class="hl-code">;
  </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">;
 
  </span><span class="hl-comment">// 实际初始化</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
  </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
  </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">;
 
  </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code">;
 
  </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">全局变量</h2>&#13;
<p>在所有函数外部定义的变量（通常是在程序的头部），称为全局变量。全局变量的值在程序的整个生命周期内都是有效的。</p>&#13;
<p>全局变量可以被任何函数访问。也就是说，全局变量一旦声明，在整个程序中都是可用的。下面的实例使用了全局变量和局部变量：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 全局变量声明</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">g</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">// 局部变量声明</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">, </span><span class="hl-identifier">b</span><span class="hl-code">;
 
  </span><span class="hl-comment">// 实际初始化</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
  </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
  </span><span class="hl-identifier">g</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">;
 
  </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">g</span><span class="hl-code">;
 
  </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在程序中，局部变量和全局变量的名称可以相同，但是在函数内，局部变量的值会覆盖全局变量的值。下面是一个实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 全局变量声明</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">g</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">// 局部变量声明</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">g</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
 
  </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">g</span><span class="hl-code">;
 
  </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
10&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">初始化局部变量和全局变量</h2>&#13;
<p>当局部变量被定义时，系统不会对其初始化，您必须自行对其初始化。定义全局变量时，系统会自动初始化为下列值：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th width="30%">数据类型</th><th>初始化默认值</th></tr>&#13;
<tr><td>   int     </td><td>  0    </td> </tr>&#13;
<tr><td>   char    </td><td>  '\0' </td> </tr>&#13;
<tr><td>   float   </td><td>  0    </td> </tr>&#13;
<tr><td>   double   </td><td>  0    </td> </tr>&#13;
<tr><td>   pointer </td><td>  NULL </td> </tr>&#13;
</table>&#13;
<p>正确地初始化变量是一个良好的编程习惯，否则有时候程序可能会产生意想不到的结果。</p>&#13;
<hr/>&#13;
<h2/><p>&#13;
块作用域指的是在代码块内部声明的变量：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">int</span> a <span style="color: #000080;">=</span> <span style="color: #0000dd;">20</span><span style="color: #008080;">;</span>  <span style="color: #666666;">// 块作用域变量</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"块变量: "</span> <span style="color: #000080;">&lt;&lt;</span> a <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"外部变量: "</span> <span style="color: #000080;">&lt;&lt;</span> a <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>以上实例中，内部的代码块中声明了一个名为 a 的变量，它与外部作用域中的变量 a 同名。内部作用域中的变量 a 将覆盖外部作用域中的变量 a，在内部作用域中访问 a 时输出的是20，而在外部作用域中访问 a 时输出的是 10。</p>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
块变量: 20&#13;
外部变量: 10&#13;
</pre>&#13;
<h2>类作用域</h2><p>&#13;
类作用域指的是在类内部声明的变量：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> MyClass <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">static</span> <span style="color: #05a;">int</span> class_var<span style="color: #008080;">;</span>  <span style="color: #666666;">// 类作用域变量</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> MyClass<span style="color: #008080;">::</span><span style="color: #007788;">class_var</span> <span style="color: #000080;">=</span> <span style="color: #0000dd;">30</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"类变量: "</span> <span style="color: #000080;">&lt;&lt;</span> MyClass<span style="color: #008080;">::</span><span style="color: #007788;">class_var</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>以上实例中，MyClass 类中声明了一个名为 class_var 的类作用域变量。可以使用类名和作用域解析运算符 <span class="marked">::</span> 来访问这个变量。在 main() 函数中访问 class_var 时输出的是 30。</p>&#13;
<pre>&#13;
类变量: 30&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>