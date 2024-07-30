<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 动态内存</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">动态内存</span></h1>&#13;
&#13;
<p>了解动态内存在 C++ 中是如何工作的是成为一名合格的 C++ 程序员必不可少的。C++ 程序中的内存分为两个部分：</p>&#13;
<ul class="list">&#13;
<li><b>栈：</b>在函数内部声明的所有变量都将占用栈内存。</li>&#13;
<li><b>堆：</b>这是程序中未使用的内存，在程序运行时可用于动态分配内存。</li>&#13;
</ul>&#13;
<p>很多时候，您无法提前预知需要多少内存来存储某个定义变量中的特定信息，所需内存的大小需要在运行时才能确定。</p>&#13;
<p>在 C++ 中，您可以使用特殊的运算符为给定类型的变量在运行时分配堆内的内存，这会返回所分配的空间地址。这种运算符即 <b>new</b> 运算符。</p>&#13;
<p>如果您不再需要动态分配的内存空间，可以使用 <b>delete</b> 运算符，删除之前由 new 运算符分配的内存。</p>&#13;
&#13;
<h2>new 和 delete 运算符</h2>&#13;
<p>下面是使用 new 运算符来为任意的数据类型动态分配内存的通用语法：</p>&#13;
<pre>&#13;
new data-type;&#13;
</pre>&#13;
<p>在这里，<b>data-type</b> 可以是包括数组在内的任意内置的数据类型，也可以是包括类或结构在内的用户自定义的任何数据类型。让我们先来看下内置的数据类型。例如，我们可以定义一个指向 double 类型的指针，然后请求内存，该内存在执行时被分配。我们可以按照下面的语句使用 <b>new</b> 运算符来完成这点：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">double</span><span class="hl-code">* </span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-prepro">NULL</span><span class="hl-code">; </span><span class="hl-comment">// 初始化为 null 的指针</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code">;   </span><span class="hl-comment">// 为变量请求内存</span></div>&#13;
</div>&#13;
</div>&#13;
<p>如果自由存储区已被用完，可能无法成功分配内存。所以建议检查 new 运算符是否返回 NULL 指针，并采取以下适当的操作：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">double</span><span class="hl-code">* </span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-prepro">NULL</span><span class="hl-code">;
</span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-code"> !</span><span class="hl-brackets">(</span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Error: out of memory.</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-identifier">exit</span><span class="hl-brackets">(</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><b>malloc()</b> 函数在 C 语言中就出现了，在 C++ 中仍然存在，但建议尽量不要使用 malloc() 函数。new 与 malloc() 函数相比，其主要的优点是，new 不只是分配了内存，它还创建了对象。</p>&#13;
<p>在任何时候，当您觉得某个已经动态分配内存的变量不再需要使用时，您可以使用 delete 操作符释放它所占用的内存，如下所示：</p>&#13;
<pre>&#13;
delete pvalue;        // 释放 pvalue 所指向的内存&#13;
</pre>&#13;
<p>下面的实例中使用了上面的概念，演示了如何使用 new 和 delete 运算符：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">double</span><span class="hl-code">* </span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-prepro">NULL</span><span class="hl-code">; </span><span class="hl-comment">// 初始化为 null 的指针</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">pvalue</span><span class="hl-code">  = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code">;   </span><span class="hl-comment">// 为变量请求内存</span><span class="hl-comment"/><span class="hl-code">
 
   *</span><span class="hl-identifier">pvalue</span><span class="hl-code"> = </span><span class="hl-number">29494</span><span class="hl-number">.99</span><span class="hl-code">;     </span><span class="hl-comment">// 在分配的地址存储值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Value of pvalue : </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; *</span><span class="hl-identifier">pvalue</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-identifier">pvalue</span><span class="hl-code">;         </span><span class="hl-comment">// 释放内存</span><span class="hl-comment"/><span class="hl-code">
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Value of pvalue : 29495&#13;
</pre>&#13;
&#13;
<h2>数组的动态内存分配</h2>&#13;
<p>假设我们要为一个字符数组（一个有 20 个字符的字符串）分配内存，我们可以使用上面实例中的语法来为数组动态地分配内存，如下所示：</p>&#13;
<pre>&#13;
char* pvalue  = NULL;   // 初始化为 null 的指针&#13;
pvalue  = new char[20]; // 为变量请求内存&#13;
</pre>&#13;
<p>要删除我们刚才创建的数组，语句如下：</p>&#13;
<pre>&#13;
delete [] pvalue;        // 删除 pvalue 所指向的数组&#13;
</pre>&#13;
<p>下面是 new 操作符的通用语法，可以为多维数组分配内存，如下所示：</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">一维数组</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">// 动态分配,数组长度为 m</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">int</span><span class="hl-code"> *</span><span class="hl-identifier">array</span><span class="hl-code">=</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-identifier">m</span><span class="hl-brackets">]</span><span class="hl-code">;
 
</span><span class="hl-comment">//释放内存</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
&#13;
<div class="example">&#13;
<h2 class="example">二维数组</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">int</span><span class="hl-code"> **</span><span class="hl-identifier">array</span><span class="hl-code">;
</span><span class="hl-comment">// 假定数组第一维长度为 m， 第二维长度为 n</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">// 动态分配空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">array</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> *</span><span class="hl-brackets">[</span><span class="hl-identifier">m</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-identifier">m</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-identifier">n</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-comment">//释放</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-identifier">m</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>二维数组实例测试：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> **</span><span class="hl-identifier">p</span><span class="hl-code">;   
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">,</span><span class="hl-identifier">j</span><span class="hl-code">;   </span><span class="hl-comment">//p[4][8] </span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">//开始分配4行8列的二维数据   </span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">p</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> *</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">4</span><span class="hl-code">;</span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-number">8</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
 
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">4</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-number">8</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">j</span><span class="hl-code">*</span><span class="hl-identifier">i</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">   
    </span><span class="hl-comment">//打印数据   </span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">4</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-number">8</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">     
        </span><span class="hl-brackets">{</span><span class="hl-code">   
            </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">==</span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">cout</span><span class="hl-code">&lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;   
            </span><span class="hl-identifier">cout</span><span class="hl-code">&lt;&lt;</span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code">&lt;&lt;</span><span class="hl-quotes">"</span><span class="hl-special">\</span><span class="hl-string">t</span><span class="hl-quotes">"</span><span class="hl-code">;   
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">   
    </span><span class="hl-comment">//开始释放申请的堆   </span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">4</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;   
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">p</span><span class="hl-code">;   
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
<div class="example">&#13;
<h2 class="example">三维数组</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">int</span><span class="hl-code"> ***</span><span class="hl-identifier">array</span><span class="hl-code">;
</span><span class="hl-comment">// 假定数组第一维为 m， 第二维为 n， 第三维为h</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">// 动态分配空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">array</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> **</span><span class="hl-brackets">[</span><span class="hl-identifier">m</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-identifier">m</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> *</span><span class="hl-brackets">[</span><span class="hl-identifier">n</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-identifier">n</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-identifier">h</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-comment">//释放</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-identifier">m</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-identifier">n</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++ </span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">delete</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-reserved">delete</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">delete</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>三维数组测试实例：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">   
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">,</span><span class="hl-identifier">j</span><span class="hl-code">,</span><span class="hl-identifier">k</span><span class="hl-code">;   </span><span class="hl-comment">// p[2][3][4]</span><span class="hl-comment"/><span class="hl-code">
    
    </span><span class="hl-types">int</span><span class="hl-code"> ***</span><span class="hl-identifier">p</span><span class="hl-code">;
    </span><span class="hl-identifier">p</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> **</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code">; 
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">2</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> 
    </span><span class="hl-brackets">{</span><span class="hl-code"> 
        </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> *</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-code">; 
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-number">3</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> 
            </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code">; 
    </span><span class="hl-brackets">}</span><span class="hl-code">
    
    </span><span class="hl-comment">//输出 p[i][j][k] 三维数据</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">2</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">   
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-number">3</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">   
        </span><span class="hl-brackets">{</span><span class="hl-code"> 
            </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">k</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">;</span><span class="hl-identifier">k</span><span class="hl-code">&lt;</span><span class="hl-number">4</span><span class="hl-code">;</span><span class="hl-identifier">k</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">
            </span><span class="hl-brackets">{</span><span class="hl-code"> 
                </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">k</span><span class="hl-brackets">]</span><span class="hl-code">=</span><span class="hl-identifier">i</span><span class="hl-code">+</span><span class="hl-identifier">j</span><span class="hl-code">+</span><span class="hl-identifier">k</span><span class="hl-code">;
                </span><span class="hl-identifier">cout</span><span class="hl-code">&lt;&lt;</span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">k</span><span class="hl-brackets">]</span><span class="hl-code">&lt;&lt;</span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code">;
            </span><span class="hl-brackets">}</span><span class="hl-code">
            </span><span class="hl-identifier">cout</span><span class="hl-code">&lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
        </span><span class="hl-brackets">}</span><span class="hl-code">
        </span><span class="hl-identifier">cout</span><span class="hl-code">&lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    
    </span><span class="hl-comment">// 释放内存</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">2</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> 
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">j</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">&lt;</span><span class="hl-number">3</span><span class="hl-code">; </span><span class="hl-identifier">j</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> 
        </span><span class="hl-brackets">{</span><span class="hl-code">   
            </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code">;   
        </span><span class="hl-brackets">}</span><span class="hl-code">   
    </span><span class="hl-brackets">}</span><span class="hl-code">       
    </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code">=</span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">&lt;</span><span class="hl-number">2</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code">   
    </span><span class="hl-brackets">{</span><span class="hl-code">       
        </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">p</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;   
    </span><span class="hl-brackets">}</span><span class="hl-code">   
    </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">p</span><span class="hl-code">;  
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>对象的动态内存分配</h2>&#13;
<p>对象与简单的数据类型没有什么不同。例如，请看下面的代码，我们将使用一个对象数组来理清这一概念：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
      </span><span class="hl-identifier">Box</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code"> 
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">调用构造函数！</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">; 
      </span><span class="hl-brackets">}</span><span class="hl-code">
      ~</span><span class="hl-identifier">Box</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code"> 
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">调用析构函数！</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">; 
      </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Box</span><span class="hl-code">* </span><span class="hl-identifier">myBoxArray</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code">;
 
   </span><span class="hl-reserved">delete</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">myBoxArray</span><span class="hl-code">; </span><span class="hl-comment">// 删除数组</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>如果要为一个包含四个 Box 对象的数组分配内存，构造函数将被调用 4 次，同样地，当删除这些对象时，析构函数也将被调用相同的次数（4次）。</p>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
调用构造函数！&#13;
调用构造函数！&#13;
调用构造函数！&#13;
调用构造函数！&#13;
调用析构函数！&#13;
调用析构函数！&#13;
调用析构函数！&#13;
调用析构函数！&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>