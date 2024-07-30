<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 重载运算符和重载函数</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">重载运算符和重载函数</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>C++ 允许在同一作用域中的某个<b>函数</b>和<b>运算符</b>指定多个定义，分别称为<b>函数重载</b>和<b>运算符重载</b>。</p>&#13;
<p>重载声明是指一个与之前已经在该作用域内声明过的函数或方法具有相同名称的声明，但是它们的参数列表和定义（实现）不相同。</p>&#13;
<p>当您调用一个<b>重载函数</b>或<b>重载运算符</b>时，编译器通过把您所使用的参数类型与定义中的参数类型进行比较，决定选用最合适的定义。选择最合适的重载函数或重载运算符的过程，称为<b>重载决策</b>。</p>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">C++ 中的函数重载</h2>&#13;
<p>在同一个作用域内，可以声明几个功能类似的同名函数，但是这些同名函数的形式参数（指参数的个数、类型或者顺序）必须不同。您不能仅通过返回类型的不同来重载函数。</p>&#13;
<p>下面的实例中，同名函数 <b>print()</b> 被用于输出不同的数据类型：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">printData</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">整数为: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
 
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code">  </span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">浮点数为: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">f</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
 
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">字符串为: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">c</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printData</span><span class="hl-code"> </span><span class="hl-identifier">pd</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 输出整数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">pd</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-number">5</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-comment">// 输出浮点数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">pd</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-number">500</span><span class="hl-number">.263</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-comment">// 输出字符串</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Hello C++</span><span class="hl-quotes">"</span><span class="hl-code">;
   </span><span class="hl-identifier">pd</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
整数为: 5&#13;
浮点数为: 500.263&#13;
字符串为: Hello C++&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">C++ 中的运算符重载</h2>&#13;
<p>您可以重定义或重载大部分 C++ 内置的运算符。这样，您就能使用自定义类型的运算符。</p>&#13;
<p>重载的运算符是带有特殊名称的函数，函数名是由关键字 operator 和其后要重载的运算符符号构成的。与其他函数一样，重载运算符有一个返回类型和一个参数列表。</p>&#13;
<pre>&#13;
Box operator+(const Box&amp;);&#13;
</pre>&#13;
<p>声明加法运算符用于把两个 Box 对象相加，返回最终的 Box 对象。大多数的重载运算符可被定义为普通的非成员函数或者被定义为类成员函数。如果我们定义上面的函数为类的非成员函数，那么我们需要为每次操作传递两个参数，如下所示：</p>&#13;
<pre>&#13;
Box operator+(const Box&amp;, const Box&amp;);&#13;
</pre>&#13;
<p>下面的实例使用成员函数演示了运算符重载的概念。在这里，对象作为参数进行传递，对象的属性使用 <b>this</b> 运算符进行访问，如下所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
 
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">length</span><span class="hl-code"> * </span><span class="hl-identifier">breadth</span><span class="hl-code"> * </span><span class="hl-identifier">height</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setLength</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">len</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">length</span><span class="hl-code"> = </span><span class="hl-identifier">len</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
 
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setBreadth</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">bre</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">breadth</span><span class="hl-code"> = </span><span class="hl-identifier">bre</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
 
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">hei</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">height</span><span class="hl-code"> = </span><span class="hl-identifier">hei</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-comment">// 重载 + 运算符，用于把两个 Box 对象相加</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Box</span><span class="hl-code"> </span><span class="hl-reserved">operator</span><span class="hl-code">+</span><span class="hl-brackets">(</span><span class="hl-types">const</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-code">&amp; </span><span class="hl-identifier">b</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">Box</span><span class="hl-code"> </span><span class="hl-identifier">box</span><span class="hl-code">;
         </span><span class="hl-identifier">box</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code"> = </span><span class="hl-reserved">this</span><span class="hl-code">-&gt;</span><span class="hl-identifier">length</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">;
         </span><span class="hl-identifier">box</span><span class="hl-code">.</span><span class="hl-identifier">breadth</span><span class="hl-code"> = </span><span class="hl-reserved">this</span><span class="hl-code">-&gt;</span><span class="hl-identifier">breadth</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">.</span><span class="hl-identifier">breadth</span><span class="hl-code">;
         </span><span class="hl-identifier">box</span><span class="hl-code">.</span><span class="hl-identifier">height</span><span class="hl-code"> = </span><span class="hl-reserved">this</span><span class="hl-code">-&gt;</span><span class="hl-identifier">height</span><span class="hl-code"> + </span><span class="hl-identifier">b</span><span class="hl-code">.</span><span class="hl-identifier">height</span><span class="hl-code">;
         </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">box</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code">:
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">length</span><span class="hl-code">;      </span><span class="hl-comment">// 长度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">breadth</span><span class="hl-code">;     </span><span class="hl-comment">// 宽度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">height</span><span class="hl-code">;      </span><span class="hl-comment">// 高度</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
</span><span class="hl-comment">// 程序的主函数</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Box</span><span class="hl-code"> </span><span class="hl-identifier">Box1</span><span class="hl-code">;                </span><span class="hl-comment">// 声明 Box1，类型为 Box</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">Box</span><span class="hl-code"> </span><span class="hl-identifier">Box2</span><span class="hl-code">;                </span><span class="hl-comment">// 声明 Box2，类型为 Box</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">Box</span><span class="hl-code"> </span><span class="hl-identifier">Box3</span><span class="hl-code">;                </span><span class="hl-comment">// 声明 Box3，类型为 Box</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">volume</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-number">.0</span><span class="hl-code">;     </span><span class="hl-comment">// 把体积存储在该变量中</span><span class="hl-comment"/><span class="hl-code">
 
   </span><span class="hl-comment">// Box1 详述</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">Box1</span><span class="hl-code">.</span><span class="hl-identifier">setLength</span><span class="hl-brackets">(</span><span class="hl-number">6</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-identifier">Box1</span><span class="hl-code">.</span><span class="hl-identifier">setBreadth</span><span class="hl-brackets">(</span><span class="hl-number">7</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-identifier">Box1</span><span class="hl-code">.</span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-number">5</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-comment">// Box2 详述</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">Box2</span><span class="hl-code">.</span><span class="hl-identifier">setLength</span><span class="hl-brackets">(</span><span class="hl-number">12</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-identifier">Box2</span><span class="hl-code">.</span><span class="hl-identifier">setBreadth</span><span class="hl-brackets">(</span><span class="hl-number">13</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-identifier">Box2</span><span class="hl-code">.</span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-number">10</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-comment">// Box1 的体积</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">volume</span><span class="hl-code"> = </span><span class="hl-identifier">Box1</span><span class="hl-code">.</span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Volume of Box1 : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">volume</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// Box2 的体积</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">volume</span><span class="hl-code"> = </span><span class="hl-identifier">Box2</span><span class="hl-code">.</span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Volume of Box2 : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">volume</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 把两个对象相加，得到 Box3</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">Box3</span><span class="hl-code"> = </span><span class="hl-identifier">Box1</span><span class="hl-code"> + </span><span class="hl-identifier">Box2</span><span class="hl-code">;
 
   </span><span class="hl-comment">// Box3 的体积</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">volume</span><span class="hl-code"> = </span><span class="hl-identifier">Box3</span><span class="hl-code">.</span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Volume of Box3 : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">volume</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Volume of Box1 : 210&#13;
Volume of Box2 : 1560&#13;
Volume of Box3 : 5400&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">可重载运算符/不可重载运算符</h2>&#13;
<p>下面是可重载的运算符列表：</p>&#13;
<table class="reference">&#13;
&#13;
<tbody>&#13;
<tr>&#13;
<td>&#13;
双目算术运算符</td>&#13;
<td>&#13;
+ (加)，-(减)，*(乘)，/(除)，% (取模)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
关系运算符</td>&#13;
<td>&#13;
==(等于)，!= (不等于)，&lt; (小于)，&gt; (大于)，&lt;=(小于等于)，&gt;=(大于等于)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
逻辑运算符</td>&#13;
<td>&#13;
||(逻辑或)，&amp;&amp;(逻辑与)，!(逻辑非)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
单目运算符</td>&#13;
<td>&#13;
+ (正)，-(负)，*(指针)，&amp;(取地址)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
自增自减运算符</td>&#13;
<td>&#13;
++(自增)，--(自减)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
位运算符</td>&#13;
<td>&#13;
| (按位或)，&amp; (按位与)，~(按位取反)，^(按位异或),，&lt;&lt; (左移)，&gt;&gt;(右移)</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
赋值运算符</td>&#13;
<td>&#13;
=, +=, -=, *=, /= , % = , &amp;=, |=, ^=, &lt;&lt;=, &gt;&gt;=</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
空间申请与释放</td>&#13;
<td>&#13;
new, delete, new[ ] , delete[]</td>&#13;
</tr>&#13;
<tr>&#13;
<td>&#13;
其他运算符</td>&#13;
<td>&#13;
<span class="marked">()</span>(函数调用)，<span class="marked">-&gt;</span>(成员访问)，<span class="marked">,</span>(逗号)，<span class="marked">[]</span>(下标)</td>&#13;
</tr>&#13;
</tbody>&#13;
</table>&#13;
<p>下面是不可重载的运算符列表：</p>&#13;
<ul><li>&#13;
<span class="marked">.</span>：成员访问运算符</li><li>&#13;
<span class="marked">.*</span>, <span class="marked">-&gt;*</span>：成员指针访问运算符</li><li>&#13;
<span class="marked">::</span>：域运算符</li><li>&#13;
<span class="marked">sizeof</span>：长度运算符</li><li>&#13;
<span class="marked">?:</span>：条件运算符</li><li>&#13;
<span class="marked">#</span>： 预处理符号</li>&#13;
</ul>&#13;
&#13;
&#13;
<h2 id="examples">运算符重载实例</h2>&#13;
<p>下面提供了各种运算符重载的实例，帮助您更好地理解重载的概念。</p>&#13;
<table class="reference notranslate">&#13;
<tr><th width="5%">序号</th><th>运算符和实例</th></tr>&#13;
<tr><td>1</td><td><a href="/cplusplus/unary-operators-overloading.html">一元运算符重载</a></td></tr>&#13;
<tr><td>2</td><td><a href="/cplusplus/binary-operators-overloading.html">二元运算符重载</a></td></tr>&#13;
<tr><td>3</td><td><a href="/cplusplus/relational-operators-overloading.html">关系运算符重载</a> </td></tr>&#13;
<tr><td>4</td><td><a href="/cplusplus/input-output-operators-overloading.html">输入/输出运算符重载</a></td></tr>&#13;
<tr><td>5</td><td><a href="/cplusplus/increment-decrement-operators-overloading.html"> ++ 和 -- 运算符重载</a></td></tr>&#13;
<tr><td>6</td><td><a href="/cplusplus/assignment-operators-overloading.html">赋值运算符重载</a></td></tr>&#13;
<tr><td>7</td><td><a href="/cplusplus/function-call-operator-overloading.html">函数调用运算符 () 重载</a></td></tr>&#13;
<tr><td>8</td><td><a href="/cplusplus/subscripting-operator-overloading.html">下标运算符 [] 重载</a></td></tr>&#13;
<tr><td>9</td><td><a href="/cplusplus/class-member-access-operator-overloading.html">类成员访问运算符 -&gt; 重载</a>&#13;
</td></tr></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>