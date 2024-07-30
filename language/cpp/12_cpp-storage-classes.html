<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 存储类</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">存储类</span></h1>&#13;
&#13;
<p>存储类定义 C++ 程序中变量/函数的范围（可见性）和生命周期。这些说明符放置在它们所修饰的类型之前。下面列出 C++ 程序中可用的存储类：</p>&#13;
<ul class="list">&#13;
<li><p><strong>auto</strong>：这是默认的存储类说明符，通常可以省略不写。auto 指定的变量具有自动存储期，即它们的生命周期仅限于定义它们的块（block）。auto 变量通常在栈上分配。</p></li>&#13;
<li><p><strong>register</strong>：用于建议编译器将变量存储在CPU寄存器中以提高访问速度。在 C++11 及以后的版本中，register 已经是一个废弃的特性，不再具有实际作用。</p></li>&#13;
<li><p><strong>static</strong>：用于定义具有静态存储期的变量或函数，它们的生命周期贯穿整个程序的运行期。在函数内部，static变量的值在函数调用之间保持不变。在文件内部或全局作用域，static变量具有内部链接，只能在定义它们的文件中访问。</p></li>&#13;
<li><p><strong>extern</strong>：用于声明具有外部链接的变量或函数，它们可以在多个文件之间共享。默认情况下，全局变量和函数具有 extern 存储类。在一个文件中使用extern声明另一个文件中定义的全局变量或函数，可以实现跨文件共享。</p></li>&#13;
<li><p><strong>mutable (C++11)</strong>：用于修饰类中的成员变量，允许在const成员函数中修改这些变量的值。通常用于缓存或计数器等需要在const上下文中修改的数据。</p></li>&#13;
<li><p><strong>thread_local (C++11)</strong>：用于定义具有线程局部存储期的变量，每个线程都有自己的独立副本。线程局部变量的生命周期与线程的生命周期相同。&#13;
</p></li>&#13;
</ul>&#13;
<p>从 C++ 17 开始，auto 关键字不再是 C++ 存储类说明符，且 register 关键字被弃用。</p>&#13;
&#13;
<p>中的存储类说明符为程序员提供了控制变量和函数生命周期及可见性的手段。</p><p>合理使用存储类说明符可以提高程序的可维护性和性能。</p><p>&#13;
从 C++11 开始，register 已经失去了原有的作用，而 mutable 和 thread_local 则是新引入的特性，用于解决特定的编程问题。</p>&#13;
<p>下面是一个展示不同存储类说明符的实例：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #666666;">// 全局变量，具有外部链接，默认存储类为extern</span><br/>
<span style="color: #05a;">int</span> globalVar<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">void</span> function<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 局部变量，具有自动存储期，默认存储类为auto</span><br/>
    <span style="color: #05a;">auto</span> <span style="color: #05a;">int</span> localVar <span style="color: #000080;">=</span> <span style="color: #0000dd;">10</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 静态变量，具有静态存储期，生命周期贯穿整个程序</span><br/>
    <span style="color: #05a;">static</span> <span style="color: #05a;">int</span> staticVar <span style="color: #000080;">=</span> <span style="color: #0000dd;">20</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">const</span> <span style="color: #05a;">int</span> constVar <span style="color: #000080;">=</span> <span style="color: #0000dd;">30</span><span style="color: #008080;">;</span> <span style="color: #666666;">// const变量默认具有static存储期</span><br/>
<br/>
    <span style="color: #666666;">// 尝试修改const变量，编译错误</span><br/>
    <span style="color: #666666;">// constVar = 40;</span><br/>
<br/>
    <span style="color: #666666;">// mutable成员变量，可以在const成员函数中修改</span><br/>
    <span style="color: #05a;">class</span> MyClass <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
        mutable <span style="color: #05a;">int</span> mutableVar<span style="color: #008080;">;</span><br/>
<br/>
        <span style="color: #05a;">void</span> constMemberFunc<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #05a;">const</span> <span style="color: #008000;">{</span><br/>
            mutableVar <span style="color: #000080;">=</span> <span style="color: #0000dd;">50</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 允许修改mutable成员变量</span><br/>
        <span style="color: #008000;">}</span><br/>
    <span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 线程局部变量，每个线程有自己的独立副本</span><br/>
    thread_local <span style="color: #05a;">int</span> threadVar <span style="color: #000080;">=</span> <span style="color: #0000dd;">60</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">extern</span> <span style="color: #05a;">int</span> externalVar<span style="color: #008080;">;</span> <span style="color: #666666;">// 声明具有外部链接的变量</span><br/>
<br/>
    function<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<h2 class="tutheader">auto 存储类</h2>&#13;
<p>自 C++ 11 以来，<strong>auto</strong> 关键字用于两种情况：声明变量时根据初始化表达式自动推断该变量的类型、声明函数时函数返回值的占位符。&#13;
</p><p>C++98 标准中 auto 关键字用于自动变量的声明，但由于使用极少且多余，在 C++17 中已删除这一用法。</p>&#13;
<p>根据初始化表达式自动推断被声明的变量的类型，如：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">auto</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-code">=</span><span class="hl-number">3</span><span class="hl-number">.14</span><span class="hl-code">;      </span><span class="hl-comment">//double</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">auto</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">hello</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;  </span><span class="hl-comment">//const char*</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">auto</span><span class="hl-code"> </span><span class="hl-identifier">z</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">auto</span><span class="hl-brackets">(</span><span class="hl-number">9</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-comment">// int*</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">auto</span><span class="hl-code"> </span><span class="hl-identifier">x1</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">, </span><span class="hl-identifier">x2</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-number">.0</span><span class="hl-code">, </span><span class="hl-identifier">x3</span><span class="hl-code">='</span><span class="hl-identifier">r</span><span class="hl-code">';</span><span class="hl-comment">//错误，必须是初始化为同一类型</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
&#13;
<h2 class="tutheader">register 存储类</h2><p>&#13;
register 是一种存储类（storage class），用于声明变量，并提示编译器将这些变量存储在寄存器中，以便快速访问。</p>&#13;
<p>使用 register 关键字可以提高程序的执行速度，因为它减少了对内存的访问次数。</p><p>&#13;
然而，需要注意的是，register 存储类只是一种提示，编译器可以忽略它，因为现代的编译器通常会自动优化代码，选择合适的存储位置。</p>&#13;
<p><strong>语法格式：</strong></p><pre>register data_type variable_name;</pre>&#13;
<ul><li><code>register</code> 是存储类的关键字，用于提示编译器将变量存储在寄存器中。</li><li><code>data_type</code> 是变量的数据类型，可以是任何合法的 C++ 数据类型。</li><li><code>variable_name</code> 是变量的名称。</li></ul>&#13;
&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">loop</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">register</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
    </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">1000</span><span class="hl-code">; ++</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-comment">// 循环体</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div><p>&#13;
register 存储类用于提示编译器将变量存储在寄存器中，以便提高访问速度。然而，由于现代编译器的自动优化能力，使用 register 关键字并不是必需的，而且在实践中很少使用。</p>&#13;
<p>&#13;
在 C++11 标准中，register 关键字不再是一个存储类说明符，而是一个废弃的特性。这意味着在 C++11 及以后的版本中，使用 register 关键字将不会对程序产生任何影响。</p>&#13;
<p>在 C++ 中，可以使用引用或指针来提高访问速度，尤其是在处理大型数据结构时。</p>&#13;
&#13;
<h2 class="tutheader">static 存储类</h2>&#13;
<p><b>static</b> 存储类指示编译器在程序的生命周期内保持局部变量的存在，而不需要在每次它进入和离开作用域时进行创建和销毁。因此，使用 static 修饰局部变量可以在函数调用之间保持局部变量的值。</p>&#13;
<p>static 修饰符也可以应用于全局变量。当 static 修饰全局变量时，会使变量的作用域限制在声明它的文件内。</p>&#13;
<p>在 C++ 中，当 static 用在类数据成员上时，会导致仅有一个该成员的副本被类的所有对象共享。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-comment">// 函数声明 </span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">; </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 全局变量 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-identifier">count</span><span class="hl-code">--</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-comment">// 函数定义</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">; </span><span class="hl-comment">// 局部静态变量</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">i</span><span class="hl-code">++;
    </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">变量 i 为 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> ;
    </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string"> , 变量 count 为 </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">count</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">endl</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
变量 i 为 6 , 变量 count 为 9&#13;
变量 i 为 7 , 变量 count 为 8&#13;
变量 i 为 8 , 变量 count 为 7&#13;
变量 i 为 9 , 变量 count 为 6&#13;
变量 i 为 10 , 变量 count 为 5&#13;
变量 i 为 11 , 变量 count 为 4&#13;
变量 i 为 12 , 变量 count 为 3&#13;
变量 i 为 13 , 变量 count 为 2&#13;
变量 i 为 14 , 变量 count 为 1&#13;
变量 i 为 15 , 变量 count 为 0&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">extern 存储类</h2>&#13;
<p><b>extern</b> 存储类用于提供一个全局变量的引用，全局变量对所有的程序文件都是可见的。当您使用 'extern' 时，对于无法初始化的变量，会把变量名指向一个之前定义过的存储位置。</p>&#13;
<p>当您有多个文件且定义了一个可以在其他文件中使用的全局变量或函数时，可以在其他文件中使用 <i>extern</i> 来得到已定义的变量或函数的引用。可以这么理解，<i>extern</i> 是用来在另一个文件中声明一个全局变量或函数。</p>&#13;
<p>extern 修饰符通常用于当有两个或多个文件共享相同的全局变量或函数的时候，如下所示：</p>&#13;
<p>第一个文件：main.cpp</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code"> ;
</span><span class="hl-types">extern</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">count</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>第二个文件：support.cpp</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">extern</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code">;
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Count is </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">count</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">endl</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在这里，第二个文件中的 <i>extern</i> 关键字用于声明已经在第一个文件 main.cpp 中定义的 count。现在 ，编译这两个文件，如下所示：</p>&#13;
<pre>&#13;
$ g++ main.cpp support.cpp -o write&#13;
</pre>&#13;
<p>这会产生 <b>write</b> 可执行程序，尝试执行 <b>write</b>，它会产生下列结果：</p>&#13;
<pre>&#13;
$ ./write&#13;
Count is 5&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">mutable 存储类</h2>&#13;
<p><b>mutable</b> 说明符仅适用于类的对象，这将在本教程的最后进行讲解。它允许对象的成员替代常量。也就是说，mutable 成员可以通过 const 成员函数修改。</p>&#13;
&#13;
<h2 class="tutheader">thread_local 存储类</h2>&#13;
<p>使用 thread_local 说明符声明的变量仅可在它在其上创建的线程上访问。 变量在创建线程时创建，并在销毁线程时销毁。 每个线程都有其自己的变量副本。</p>&#13;
<p>thread_local 说明符可以与 static 或 extern 合并。</p><p>&#13;
可以将 thread_local 仅应用于数据声明和定义，thread_local 不能用于函数声明或定义。</p>&#13;
<p>以下演示了可以被声明为 thread_local 的变量：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">thread_local</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code">;  </span><span class="hl-comment">// 命名空间下的全局变量</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">X</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-identifier">thread_local</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-code">; </span><span class="hl-comment">// 类的static成员变量</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
</span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-identifier">thread_local</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">string</span><span class="hl-code"> </span><span class="hl-identifier">X</span><span class="hl-code">::</span><span class="hl-identifier">s</span><span class="hl-code">;  </span><span class="hl-comment">// X::s 是需要定义的</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">foo</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">thread_local</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">vector</span><span class="hl-code">&lt;</span><span class="hl-types">int</span><span class="hl-code">&gt; </span><span class="hl-identifier">v</span><span class="hl-code">;  </span><span class="hl-comment">// 本地变量</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>