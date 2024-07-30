<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 运算符</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">运算符</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>运算符是一种告诉编译器执行特定的数学或逻辑操作的符号。C++ 内置了丰富的运算符，并提供了以下类型的运算符：</p>&#13;
<ul class="list">&#13;
<li>算术运算符</li>&#13;
<li>关系运算符</li>&#13;
<li>逻辑运算符</li>&#13;
<li>位运算符</li>&#13;
<li>赋值运算符</li>&#13;
<li>杂项运算符</li>&#13;
</ul>&#13;
<p>本章将逐一介绍算术运算符、关系运算符、逻辑运算符、位运算符、赋值运算符和其他运算符。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">算术运算符</h2>&#13;
<p>下表显示了 C++ 支持的算术运算符。</p>&#13;
<p>假设变量 A 的值为 10，变量 B 的值为 20，则：</p>&#13;
<table class="reference notranslate">&#13;
<tbody><tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>&#13;
<tr><td>+</td><td>把两个操作数相加</td><td> A + B 将得到 30</td></tr>&#13;
<tr><td>-</td><td>从第一个操作数中减去第二个操作数</td><td> A - B 将得到 -10</td></tr>&#13;
<tr><td>*</td><td>把两个操作数相乘</td><td> A * B 将得到 200</td></tr>&#13;
<tr><td>/</td><td>分子除以分母</td><td> B / A 将得到 2</td></tr>&#13;
<tr><td>%</td><td>取模运算符，整除后的余数</td><td> B % A 将得到 0</td></tr>&#13;
<tr><td>++</td><td><a href="/cplusplus/cpp-increment-decrement-operators.html" title="C++ 中的自增运算符">自增运算符</a>，整数值增加 1</td><td> A++ 将得到 11</td></tr>&#13;
<tr><td>--</td><td><a href="/cplusplus/cpp-increment-decrement-operators.html" title="C++ 中的自减运算符">自减运算符</a>，整数值减少 1</td><td> A-- 将得到 9</td></tr>&#13;
</tbody></table>&#13;
<h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中可用的算术运算符。</p>&#13;
<p>复制并粘贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">21</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code">;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> - </span><span class="hl-identifier">b</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> * </span><span class="hl-identifier">b</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> / </span><span class="hl-identifier">b</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 4 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> % </span><span class="hl-identifier">b</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 5 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;   </span><span class="hl-comment">//  测试自增、自减</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">d</span><span class="hl-code">++;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 6 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;    </span><span class="hl-comment">// 重新赋值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">d</span><span class="hl-code">--;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 7 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
Line 1 - c 的值是 31&#13;
Line 2 - c 的值是 11&#13;
Line 3 - c 的值是 210&#13;
Line 4 - c 的值是 2&#13;
Line 5 - c 的值是 1&#13;
Line 6 - c 的值是 10&#13;
Line 7 - c 的值是 10&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">关系运算符</h2>&#13;
<p>下表显示了 C++ 支持的关系运算符。</p>&#13;
<p>假设变量 A 的值为 10，变量 B 的值为 20，则：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>&#13;
<tr><td>==</td><td>检查两个操作数的值是否相等，如果相等则条件为真。</td><td> (A == B) 不为真。</td></tr>&#13;
<tr><td>!=</td><td>检查两个操作数的值是否相等，如果不相等则条件为真。</td><td> (A != B) 为真。</td></tr>&#13;
<tr><td>&gt;</td><td>检查左操作数的值是否大于右操作数的值，如果是则条件为真。</td><td> (A &gt; B) 不为真。</td></tr>&#13;
<tr><td>&lt;</td><td>检查左操作数的值是否小于右操作数的值，如果是则条件为真。</td><td> (A &lt; B) 为真。</td></tr>&#13;
<tr><td>&gt;=</td><td>检查左操作数的值是否大于或等于右操作数的值，如果是则条件为真。</td><td> (A &gt;= B) 不为真。</td></tr>&#13;
<tr><td>&lt;=</td><td>检查左操作数的值是否小于或等于右操作数的值，如果是则条件为真。</td><td> (A &lt;= B) 为真。</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中可用的关系运算符。</p>&#13;
<p>复制并黏贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">21</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> ;
 
   </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> == </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - a 等于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - a 不等于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> &lt; </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - a 小于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - a 不小于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> &gt; </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - a 大于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - a 不大于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 改变 a 和 b 的值 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> &lt;= </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 4 - a 小于或等于 b</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> &gt;= </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 5 - b 大于或等于 a</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
Line 1 - a 不等于 b&#13;
Line 2 - a 不小于 b&#13;
Line 3 - a 大于 b&#13;
Line 4 - a 小于或等于 b&#13;
Line 5 - b 大于或等于 a&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">逻辑运算符</h2>&#13;
<p>下表显示了 C++ 支持的关系逻辑运算符。</p>&#13;
<p>假设变量 A 的值为 1，变量 B 的值为 0，则：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>&#13;
<tr><td>&amp;&amp;</td><td>称为逻辑与运算符。如果两个操作数都 true，则条件为 true。</td><td> (A &amp;&amp; B) 为 false。</td></tr>&#13;
<tr><td>||</td><td>称为逻辑或运算符。如果两个操作数中有任意一个 true，则条件为 true。</td><td> (A || B) 为 true。</td></tr>&#13;
<tr><td>!</td><td>称为逻辑非运算符。用来逆转操作数的逻辑状态，如果条件为 true 则逻辑非运算符将使其为 false。</td><td> !(A &amp;&amp; B) 为 true。</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中可用的逻辑运算符。</p>&#13;
<p>复制并黏贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> ;
 
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - 条件为真</span><span class="hl-quotes">"</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> || </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - 条件为真</span><span class="hl-quotes">"</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 改变 a 和 b 的值 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
   </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
   </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">b</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - 条件为真</span><span class="hl-quotes">"</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">else</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 4 - 条件不为真</span><span class="hl-quotes">"</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-code"> &amp;&amp; </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 5 - 条件为真</span><span class="hl-quotes">"</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
Line 1 - 条件为真&#13;
Line 2 - 条件为真&#13;
Line 4 - 条件不为真&#13;
Line 5 - 条件为真&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">位运算符</h2>&#13;
<p>位运算符作用于位，并逐位执行操作。&amp;、 | 和 ^ 的真值表如下所示：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:20%">p</th><th style="width:20%">q</th><th style="width:20%">p &amp; q</th><th style="width:20%">p | q</th><th style="width:20%">p ^ q</th></tr>&#13;
<tr><td>0</td><td>0</td><td>0</td><td>0</td><td>0</td></tr>&#13;
<tr><td>0</td><td>1</td><td>0</td><td>1</td><td>1</td></tr>&#13;
<tr><td>1</td><td>1</td><td>1</td><td>1</td><td>0</td></tr>&#13;
<tr><td>1</td><td>0</td><td>0</td><td>1</td><td>1</td></tr>&#13;
</table>&#13;
<p>假设如果 A = 60，且 B = 13，现在以二进制格式表示，它们如下所示：</p>&#13;
<p>A = 0011 1100</p>&#13;
<p>B = 0000 1101</p>&#13;
<p>-----------------</p>&#13;
<p>A&amp;B = 0000 1100</p>&#13;
<p>A|B = 0011 1101</p>&#13;
<p>A^B = 0011 0001</p>&#13;
<p>~A  = 1100 0011</p>&#13;
<p>下表显示了 C++ 支持的位运算符。假设变量 A 的值为 60，变量 B 的值为 13，则：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>&#13;
<tr><td>&amp;</td><td><p>按位与操作，按二进制位进行"与"运算。运算规则：</p>&#13;
<pre>0&amp;0=0;   &#13;
0&amp;1=0;    &#13;
1&amp;0=0;     &#13;
1&amp;1=1;</pre></td><td> (A &amp; B) 将得到 12，即为 0000 1100</td></tr>&#13;
<tr><td>|</td><td><p>按位或运算符，按二进制位进行"或"运算。运算规则：</p>&#13;
<pre>0|0=0;   &#13;
0|1=1;   &#13;
1|0=1;    &#13;
1|1=1;</pre>&#13;
</td><td> (A | B) 将得到 61，即为 0011 1101</td></tr>&#13;
<tr><td>^</td><td><p>异或运算符，按二进制位进行"异或"运算。运算规则：</p>&#13;
<pre>0^0=0;   &#13;
0^1=1;   &#13;
1^0=1;  &#13;
1^1=0;</pre>&#13;
&#13;
</td><td> (A ^ B) 将得到 49，即为 0011 0001</td></tr>&#13;
<tr><td>~</td><td><p>取反运算符，按二进制位进行"取反"运算。运算规则：</p>&#13;
<pre>~1=-2;   &#13;
~0=-1;</pre></td><td> (~A ) 将得到 -61，即为 1100 0011，一个有符号二进制数的补码形式。</td></tr>&#13;
<tr><td>&lt;&lt;</td><td>二进制左移运算符。将一个运算对象的各二进制位全部左移若干位（左边的二进制位丢弃，右边补0）。</td><td> A &lt;&lt; 2 将得到 240，即为 1111 0000</td></tr>&#13;
<tr><td>&gt;&gt;</td><td>二进制右移运算符。将一个数的各二进制位全部右移若干位，正数左补0，负数左补1，右边丢弃。</td><td> A &gt;&gt; 2 将得到 15，即为 0000 1111</td></tr>&#13;
</table><h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中可用的位运算符。</p>&#13;
<p>复制并黏贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">60</span><span class="hl-code">;      </span><span class="hl-comment">// 60 = 0011 1100  </span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">unsigned</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">13</span><span class="hl-code">;      </span><span class="hl-comment">// 13 = 0000 1101</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;           
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> &amp; </span><span class="hl-identifier">b</span><span class="hl-code">;             </span><span class="hl-comment">// 12 = 0000 1100</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> | </span><span class="hl-identifier">b</span><span class="hl-code">;             </span><span class="hl-comment">// 61 = 0011 1101</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> ^ </span><span class="hl-identifier">b</span><span class="hl-code">;             </span><span class="hl-comment">// 49 = 0011 0001</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = ~</span><span class="hl-identifier">a</span><span class="hl-code">;                </span><span class="hl-comment">// -61 = 1100 0011</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 4 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> &lt;&lt; </span><span class="hl-number">2</span><span class="hl-code">;            </span><span class="hl-comment">// 240 = 1111 0000</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 5 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> &gt;&gt; </span><span class="hl-number">2</span><span class="hl-code">;            </span><span class="hl-comment">// 15 = 0000 1111</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 6 - c 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
Line 1 - c 的值是 12&#13;
Line 2 - c 的值是 61&#13;
Line 3 - c 的值是 49&#13;
Line 4 - c 的值是 -61&#13;
Line 5 - c 的值是 240&#13;
Line 6 - c 的值是 15&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">赋值运算符</h2>&#13;
<p>下表列出了 C++ 支持的赋值运算符：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:10%">运算符</th><th style="width:55%;">描述</th><th>实例</th></tr>&#13;
<tr><td>=</td><td>简单的赋值运算符，把右边操作数的值赋给左边操作数</td><td> C = A + B 将把 A + B 的值赋给 C</td></tr>&#13;
<tr><td>+=</td><td>加且赋值运算符，把右边操作数加上左边操作数的结果赋值给左边操作数</td><td> C += A 相当于 C = C + A</td></tr>&#13;
<tr><td>-=</td><td>减且赋值运算符，把左边操作数减去右边操作数的结果赋值给左边操作数</td><td> C -= A 相当于 C = C - A</td></tr>&#13;
<tr><td>*=</td><td>乘且赋值运算符，把右边操作数乘以左边操作数的结果赋值给左边操作数</td><td> C *= A 相当于 C = C * A</td></tr>&#13;
<tr><td>/=</td><td>除且赋值运算符，把左边操作数除以右边操作数的结果赋值给左边操作数</td><td> C /= A 相当于 C = C / A</td></tr>&#13;
<tr><td>%=</td><td>求模且赋值运算符，求两个操作数的模赋值给左边操作数</td><td> C %= A 相当于 C = C % A</td></tr>&#13;
<tr><td>&lt;&lt;=</td><td>左移且赋值运算符</td><td> C &lt;&lt;= 2 等同于  C = C &lt;&lt; 2</td></tr>&#13;
<tr><td>&gt;&gt;=</td><td>右移且赋值运算符</td><td> C &gt;&gt;= 2 等同于  C = C &gt;&gt; 2</td></tr>&#13;
<tr><td>&amp;=</td><td>按位与且赋值运算符</td><td> C &amp;= 2 等同于  C = C &amp; 2</td></tr>&#13;
<tr><td>^=</td><td>按位异或且赋值运算符</td><td> C ^= 2 等同于  C = C ^ 2</td></tr>&#13;
<tr><td>|=</td><td>按位或且赋值运算符</td><td> C |= 2 等同于  C = C | 2</td></tr>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中可用的赋值运算符。</p>&#13;
<p>复制并黏贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">21</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> =  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 1 - =  运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> +=  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 2 - += 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> -=  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 3 - -= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> *=  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 4 - *= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> /=  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 5 - /= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code">  = </span><span class="hl-number">200</span><span class="hl-code">;
   </span><span class="hl-identifier">c</span><span class="hl-code"> %=  </span><span class="hl-identifier">a</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 6 - %= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt;=  </span><span class="hl-number">2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 7 - &lt;&lt;= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> &gt;&gt;=  </span><span class="hl-number">2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 8 - &gt;&gt;= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> &amp;=  </span><span class="hl-number">2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 9 - &amp;= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> ^=  </span><span class="hl-number">2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 10 - ^= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">c</span><span class="hl-code"> |=  </span><span class="hl-number">2</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Line 11 - |= 运算符实例，c 的值 = : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">c</span><span class="hl-code">&lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
Line 1 - =  运算符实例，c 的值 = 21&#13;
Line 2 - += 运算符实例，c 的值 = 42&#13;
Line 3 - -= 运算符实例，c 的值 = 21&#13;
Line 4 - *= 运算符实例，c 的值 = 441&#13;
Line 5 - /= 运算符实例，c 的值 = 21&#13;
Line 6 - %= 运算符实例，c 的值 = 11&#13;
Line 7 - &lt;&lt;= 运算符实例，c 的值 = 44&#13;
Line 8 - &gt;&gt;= 运算符实例，c 的值 = 11&#13;
Line 9 - &amp;= 运算符实例，c 的值 = 2&#13;
Line 10 - ^= 运算符实例，c 的值 = 0&#13;
Line 11 - |= 运算符实例，c 的值 = 2&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">杂项运算符</h2>&#13;
<p>下表列出了 C++ 支持的其他一些重要的运算符。</p>&#13;
<table class="reference notranslate">&#13;
<tr><th width="15%">运算符</th><th width="35%">描述</th></tr>&#13;
<tr><td>sizeof</td><td><a href="/cplusplus/cpp-sizeof-operator.html">sizeof 运算符</a>返回变量的大小。例如，sizeof(a) 将返回 4，其中 a 是整数。</td></tr>&#13;
<tr><td>Condition ? X : Y</td><td><a href="/cplusplus/cpp-conditional-operator.html">条件运算符</a>。如果 Condition 为真 ? 则值为 X : 否则值为 Y。</td></tr>&#13;
<tr><td>,</td><td><a href="/cplusplus/cpp-comma-operator.html">逗号运算符</a>会顺序执行一系列运算。整个逗号表达式的值是以逗号分隔的列表中的最后一个表达式的值。</td></tr>&#13;
<tr><td>.（点）和  -&gt;（箭头）</td><td><a href="/cplusplus/cpp-member-operators.html">成员运算符</a>用于引用类、结构和共用体的成员。</td></tr>&#13;
<tr> <td>Cast</td><td><a href="/cplusplus/cpp-casting-operators.html">强制转换运算符</a>把一种数据类型转换为另一种数据类型。例如，int(2.2000) 将返回 2。</td></tr>&#13;
<tr><td>&amp;</td><td><a href="/cplusplus/cpp-pointer-operators.html">指针运算符 &amp;</a> 返回变量的地址。例如 &amp;a; 将给出变量的实际地址。</td></tr>&#13;
<tr><td>*</td><td><a href="/cplusplus/cpp-pointer-operators.html">指针运算符 *</a> 指向一个变量。例如，*var; 将指向变量 var。</td></tr>&#13;
</table>&#13;
&#13;
<h2 class="tutheader">C++ 中的运算符优先级</h2>&#13;
<p>运算符的优先级确定表达式中项的组合。这会影响到一个表达式如何计算。某些运算符比其他运算符有更高的优先级，例如，乘除运算符具有比加减运算符更高的优先级。</p>&#13;
<p>例如 x = 7 + 3 * 2，在这里，x 被赋值为 13，而不是 20，因为运算符 * 具有比 + 更高的优先级，所以首先计算乘法 3*2，然后再加上 7。</p>&#13;
 <p>下表将按运算符优先级从高到低列出各个运算符，具有较高优先级的运算符出现在表格的上面，具有较低优先级的运算符出现在表格的下面。在表达式中，较高优先级的运算符会优先被计算。</p>&#13;
<table class="reference notranslate">&#13;
<tr> <th>类别 </th> <th>运算符 </th><th>结合性 </th> </tr> &#13;
<tr> <td>后缀 </td><td>() [] -&gt; .  ++   - -  </td> <td>从左到右 </td> </tr>&#13;
<tr> <td>一元 </td> <td>+  -   !  ~  ++  - -   (type)*  &amp;  sizeof </td> <td>从右到左 </td></tr> &#13;
<tr> <td>乘除 </td> <td>*  /  % </td><td>从左到右 </td> </tr> &#13;
<tr> <td>加减 </td><td>+  - </td> <td>从左到右 </td> </tr>&#13;
<tr> <td>移位 </td> <td>&lt;&lt; &gt;&gt; </td> <td>从左到右 </td> </tr> &#13;
<tr> <td>关系 </td><td>&lt; &lt;=  &gt; &gt;= </td> <td>从左到右 </td> </tr>&#13;
<tr> <td>相等 </td> <td>==  != </td> <td>从左到右 </td> </tr> &#13;
<tr> <td>位与 AND </td><td>&amp; </td> <td>从左到右 </td> </tr> &#13;
<tr> <td>位异或 XOR </td> <td>^ </td> <td>从左到右 </td></tr> &#13;
<tr> <td>位或 OR </td> <td>| </td> <td>从左到右 </td></tr> &#13;
<tr> <td>逻辑与 AND </td><td>&amp;&amp; </td> <td>从左到右 </td></tr>&#13;
<tr><td>逻辑或 OR </td> <td>|| </td> <td>从左到右 </td></tr> &#13;
<tr> <td>条件 </td><td>?: </td> <td>从右到左 </td> </tr>&#13;
<tr><td>赋值 </td> <td>=  +=  -=  *=  /=  %=&gt;&gt;=  &lt;&lt;=  &amp;=  ^=   |= </td><td>从右到左 </td></tr>&#13;
<tr> <td>逗号 </td> <td>, </td> <td>从左到右 </td></tr> &#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>请看下面的实例，了解 C++ 中运算符的优先级。</p>&#13;
<p>复制并黏贴下面的 C++ 程序到 test.cpp 文件中，编译并运行程序。</p>&#13;
<p>对比有括号和没有括号时的区别，这将产生不同的结果。因为 ()、 /、 * 和 + 有不同的优先级，高优先级的操作符将优先计算。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">20</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-number">15</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">d</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-code">;
 
   </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code"> * </span><span class="hl-identifier">c</span><span class="hl-code"> / </span><span class="hl-identifier">d</span><span class="hl-code">;      </span><span class="hl-comment">// ( 30 * 15 ) / 5</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">(a + b) * c / d 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">e</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code"> * </span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code"> / </span><span class="hl-identifier">d</span><span class="hl-code">;    </span><span class="hl-comment">// (30 * 15 ) / 5</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">((a + b) * c) / d 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">e</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code"> * </span><span class="hl-brackets">(</span><span class="hl-identifier">c</span><span class="hl-code"> / </span><span class="hl-identifier">d</span><span class="hl-brackets">)</span><span class="hl-code">;   </span><span class="hl-comment">// (30) * (15/5)</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">(a + b) * (c / d) 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">e</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
 
   </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-brackets">(</span><span class="hl-identifier">b</span><span class="hl-code"> * </span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code"> / </span><span class="hl-identifier">d</span><span class="hl-code">;     </span><span class="hl-comment">//  20 + (150/5)</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">a + (b * c) / d 的值是 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">e</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code"> ;
  
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生以下结果：</p>&#13;
<pre>&#13;
(a + b) * c / d 的值是 90&#13;
((a + b) * c) / d 的值是 90&#13;
(a + b) * (c / d) 的值是 90&#13;
a + (b * c) / d 的值是 50&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>