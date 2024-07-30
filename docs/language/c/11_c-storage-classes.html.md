<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 存储类</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C <span class="color_h1">存储类</span></h1>&#13;
&#13;
<div class="tutintro">&#13;
<p>存储类定义 C 程序中变量/函数的存储位置、生命周期和作用域。</p>&#13;
<p>这些说明符放置在它们所修饰的类型之前。</p><p>下面列出 C 程序中可用的存储类：</p>&#13;
<ul class="list">&#13;
<li>auto</li>&#13;
<li>register</li>&#13;
<li>static</li>&#13;
<li>extern</li>&#13;
</ul>&#13;
</div>&#13;
&#13;
<h2 class="tutheader">auto 存储类</h2>&#13;
<p><b>auto</b> 存储类是所有局部变量默认的存储类。</p>&#13;
<p>定义在函数中的变量默认为 auto 存储类，这意味着它们在函数开始时被创建，在函数结束时被销毁。</p>&#13;
<pre>&#13;
{&#13;
   int mount;&#13;
   auto int month;&#13;
}&#13;
</pre>&#13;
 <p>上面的实例定义了两个带有相同存储类的变量，auto 只能用在函数内，即 auto 只能修饰局部变量。</p>&#13;
&#13;
<h2 class="tutheader">register 存储类</h2>&#13;
<p><b>register</b> 存储类用于定义存储在寄存器中而不是 RAM 中的局部变量。这意味着变量的最大尺寸等于寄存器的大小（通常是一个字），且不能对它应用一元的 '&amp;' 运算符（因为它没有内存位置）。</p>&#13;
<p>register 存储类定义存储在寄存器，所以变量的访问速度更快，但是它不能直接取地址，因为它不是存储在 RAM 中的。在需要频繁访问的变量上使用 register 存储类可以提高程序的运行速度。</p>&#13;
<pre>&#13;
{&#13;
   register int  miles;&#13;
}&#13;
</pre>&#13;
<p>寄存器只用于需要快速访问的变量，比如计数器。还应注意的是，定义 'register' 并不意味着变量将被存储在寄存器中，它意味着变量可能存储在寄存器中，这取决于硬件和实现的限制。</p>&#13;
&#13;
<h2 class="tutheader">static 存储类</h2>&#13;
<p><b>static</b> 存储类指示编译器在程序的生命周期内保持局部变量的存在，而不需要在每次它进入和离开作用域时进行创建和销毁。因此，使用 static 修饰局部变量可以在函数调用之间保持局部变量的值。</p>&#13;
&#13;
<p>static 修饰符也可以应用于全局变量。当 static 修饰全局变量时，会使变量的作用域限制在声明它的文件内。</p>&#13;
<p>&#13;
全局声明的一个 static 变量或方法可以被任何函数或方法调用，只要这些方法出现在跟 static 变量或方法同一个文件中。</p>&#13;
<p>静态变量在程序中只被初始化一次，即使函数被调用多次，该变量的值也不会重置。</p>&#13;
<p>以下实例演示了 static 修饰全局变量和局部变量的应用：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 函数声明 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func1</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code">=</span><span class="hl-number">10</span><span class="hl-code">;        </span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 全局变量 - static 是默认的 </span><span class="hl-mlcomment">*/</span><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">count</span><span class="hl-code">--</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">func1</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func1</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
</span><span class="hl-mlcomment">/*</span><span class="hl-mlcomment"> 'thingy' 是 'func1' 的局部变量 - 只初始化一次
 * 每次调用函数 'func1' 'thingy' 值不会被重置。
 </span><span class="hl-mlcomment">*/</span><span class="hl-code">                
  </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">thingy</span><span class="hl-code">=</span><span class="hl-number">5</span><span class="hl-code">;
  </span><span class="hl-identifier">thingy</span><span class="hl-code">++;
  </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string"> thingy 为 %d ， count 为 %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">thingy</span><span class="hl-code">, </span><span class="hl-identifier">count</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>实例中 count 作为全局变量可以在函数内使用，thingy 使用 static 修饰后，不会在每次调用时重置。</p>&#13;
<p>可能您现在还无法理解这个实例，因为我已经使用了函数和全局变量，这两个概念目前为止还没进行讲解。即使您现在不能完全理解，也没有关系，后续的章节我们会详细讲解。当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
 thingy 为 6 ， count 为 9&#13;
 thingy 为 7 ， count 为 8&#13;
 thingy 为 8 ， count 为 7&#13;
 thingy 为 9 ， count 为 6&#13;
 thingy 为 10 ， count 为 5&#13;
 thingy 为 11 ， count 为 4&#13;
 thingy 为 12 ， count 为 3&#13;
 thingy 为 13 ， count 为 2&#13;
 thingy 为 14 ， count 为 1&#13;
 thingy 为 15 ， count 为 0&#13;
</pre>&#13;
&#13;
<h2 class="tutheader">extern 存储类</h2>&#13;
<p><strong>extern</strong> 存储类用于定义在其他文件中声明的全局变量或函数。当使用 extern 关键字时，不会为变量分配任何存储空间，而只是指示编译器该变量在其他文件中定义。</p>&#13;
<p><b>extern</b> 存储类用于提供一个全局变量的引用，全局变量对所有的程序文件都是可见的。当您使用 <strong>extern</strong> 时，对于无法初始化的变量，会把变量名指向一个之前定义过的存储位置。</p>&#13;
<p>当您有多个文件且定义了一个可以在其他文件中使用的全局变量或函数时，可以在其他文件中使用 <i>extern</i> 来得到已定义的变量或函数的引用。可以这么理解，<i>extern</i> 是用来在另一个文件中声明一个全局变量或函数。</p>&#13;
<p>extern 修饰符通常用于当有两个或多个文件共享相同的全局变量或函数的时候，如下所示：</p>&#13;
<p><b>第一个文件：main.c</b></p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code"> ;
</span><span class="hl-types">extern</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">count</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
   </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><b>第二个文件：support.c</b></p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">stdio.h</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-types">extern</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">count</span><span class="hl-code">;
 
</span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">write_extern</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">count is %d</span><span class="hl-special">\</span><span class="hl-string">n</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">count</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在这里，第二个文件中的 <i>extern</i> 关键字用于声明已经在第一个文件 main.c 中定义的 <i>count</i>。现在 ，编译这两个文件，如下所示：</p>&#13;
<pre>&#13;
 $ gcc main.c support.c&#13;
</pre>&#13;
<p>这会产生 <b>a.out</b> 可执行程序，当程序被执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
count is 5&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>