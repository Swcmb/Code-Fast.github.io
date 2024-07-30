<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 命名空间和作用域
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 命名空间和作用域&#13;
</h1>&#13;
<h2>命名空间</h2>&#13;
<p>先看看官方文档的一段话：</p>&#13;
&#13;
&#13;
<blockquote><p>A namespace is a mapping from names to objects.Most namespaces are currently implemented as Python dictionaries。</p></blockquote>&#13;
&#13;
&#13;
<p>命名空间(Namespace)是从名称到对象的映射，大部分的命名空间都是通过 Python 字典来实现的。</p>&#13;
&#13;
<p>命名空间提供了在项目中避免名字冲突的一种方法。各个命名空间是独立的，没有任何关系的，所以一个命名空间中不能有重名，但不同的命名空间是可以重名而没有任何影响。</p>&#13;
<p>&#13;
我们举一个计算机系统中的例子，一个文件夹(目录)中可以包含多个文件夹，每个文件夹中不能有相同的文件名，但不同文件夹中的文件可以重名。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2019/09/0129A8E9-30FE-431D-8C48-399EA4841E9D.jpg"/></p>&#13;
&#13;
&#13;
<p>一般有三种命名空间：</p>&#13;
<ul><li>&#13;
<strong>内置名称（built-in names</strong>）， Python 语言内置的名称，比如函数名 abs、char 和异常名称 BaseException、Exception 等等。</li><li>&#13;
<strong>全局名称（global names）</strong>，模块中定义的名称，记录了模块的变量，包括函数、类、其它导入的模块、模块级的变量和常量。</li><li>&#13;
<strong>局部名称（local names）</strong>，函数中定义的名称，记录了函数的变量，包括函数的参数和局部定义的变量。（类中定义的也是）</li></ul>&#13;
&#13;
&#13;
<p><img decoding="async" width="50%" src="https://www.runoob.com/wp-content/uploads/2014/05/types_namespace-1.png"/></p>&#13;
&#13;
<p>命名空间查找顺序: </p>&#13;
&#13;
<p>假设我们要使用变量 runoob，则 Python 的查找顺序为：<strong>局部的命名空间 -&gt; 全局命名空间 -&gt; 内置命名空间</strong>。</p>&#13;
<p>如果找不到变量 runoob，它将放弃查找并引发一个 NameError 异常:</p>&#13;
<pre>NameError: name 'runoob' is not defined。</pre>&#13;
&#13;
&#13;
<p>命名空间的生命周期：</p>&#13;
&#13;
<p>命名空间的生命周期取决于对象的作用域，如果对象执行完成，则该命名空间的生命周期就结束。</p>&#13;
<p>因此，我们无法从外部命名空间访问内部命名空间的对象。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50"># var1 是全局名称</span><br/>
var1 <span style="color: Gray;">=</span> <span style="color: Maroon;">5</span><br/>
<span style="color: Green;font-weight:bold;">def</span> some_func<span style="color: Olive;">(</span><span style="color: Olive;">)</span>: <br/>
  <br/>
    <span style="color: #a50"># var2 是局部名称</span><br/>
    var2 <span style="color: Gray;">=</span> <span style="color: Maroon;">6</span><br/>
    <span style="color: Green;font-weight:bold;">def</span> some_inner_func<span style="color: Olive;">(</span><span style="color: Olive;">)</span>: <br/>
  <br/>
        <span style="color: #a50"># var3 是内嵌的局部名称</span><br/>
        var3 <span style="color: Gray;">=</span> <span style="color: Maroon;">7</span><br/>
</div></div>&#13;
<p>如下图所示，相同的对象名称可以存在于多个命名空间中。</p>&#13;
<p><img decoding="async" width="50%" src="https://www.runoob.com/wp-content/uploads/2014/05/namespaces.png"/></p><hr/>&#13;
<h2>作用域</h2>&#13;
&#13;
&#13;
<blockquote>&#13;
<p>A scope is a textual region of a Python program where a namespace is directly accessible. "Directly accessible" here means that an unqualified reference to a name attempts to find the name in the namespace.</p></blockquote>&#13;
&#13;
&#13;
&#13;
<p>作用域就是一个 Python 程序可以直接访问命名空间的正文区域。</p>&#13;
<p>在一个 python 程序中，直接访问一个变量，会从内到外依次访问所有的作用域直到找到，否则会报未定义的错误。</p>&#13;
<p>Python 中，程序的变量并不是在哪个位置都可以访问的，访问权限决定于这个变量是在哪里赋值的。</p>&#13;
&#13;
<p>变量的作用域决定了在哪一部分程序可以访问哪个特定的变量名称。Python 的作用域一共有4种，分别是：</p>&#13;
&#13;
&#13;
<p>有四种作用域：</p>&#13;
<ul>&#13;
<li>&#13;
<strong>L（Local）</strong>：最内层，包含局部变量，比如一个函数/方法内部。</li><li>&#13;
<strong>E（Enclosing）</strong>：包含了非局部(non-local)也非全局(non-global)的变量。比如两个嵌套函数，一个函数（或类） A 里面又包含了一个函数 B ，那么对于 B 中的名称来说 A 中的作用域就为 nonlocal。</li><li>&#13;
<strong>G（Global）</strong>：当前脚本的最外层，比如当前模块的全局变量。</li><li>&#13;
<strong>B（Built-in）</strong>： 包含了内建的变量/关键字等，最后被搜索。</li></ul>&#13;
&#13;
<p>规则顺序： <strong>L –&gt; E –&gt; G –&gt; B</strong>。</p>&#13;
<p>在局部找不到，便会去局部外的局部找（例如闭包），再找不到就会去全局找，再者去内置中找。</p>&#13;
&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2014/05/1418490-20180906153626089-1835444372.png"/></p>&#13;
&#13;
<pre>&#13;
g_count = 0  # 全局作用域&#13;
def outer():&#13;
    o_count = 1  # 闭包函数外的函数中&#13;
    def inner():&#13;
        i_count = 2  # 局部作用域&#13;
</pre>&#13;
&#13;
<p>内置作用域是通过一个名为 builtin 的标准模块来实现的，但是这个变量名自身并没有放入内置作用域内，所以必须导入这个文件才能够使用它。在Python3.0中，可以使用以下的代码来查看到底预定义了哪些变量:</p>&#13;
&#13;
<pre>&gt;&gt;&gt; import builtins&#13;
&gt;&gt;&gt; dir(builtins)</pre>&#13;
&#13;
<p>Python 中只有模块（module），类（class）以及函数（def、lambda）才会引入新的作用域，其它的代码块（如 if/elif/else/、try/except、for/while等）是不会引入新的作用域的，也就是说这些语句内定义的变量，外部也可以访问，如下代码：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; if True:&#13;
...  msg = 'I am from Runoob'&#13;
... &#13;
&gt;&gt;&gt; msg&#13;
'I am from Runoob'&#13;
&gt;&gt;&gt; &#13;
</pre>&#13;
<p>实例中 msg 变量定义在 if 语句块中，但外部还是可以访问的。</p>&#13;
<p>如果将 msg 定义在函数中，则它就是局部变量，外部不能访问：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; def test():&#13;
...     msg_inner = 'I am from Runoob'&#13;
... &#13;
&gt;&gt;&gt; msg_inner&#13;
Traceback (most recent call last):&#13;
  File "&lt;stdin&gt;", line 1, in &lt;module&gt;&#13;
NameError: name 'msg_inner' is not defined&#13;
&gt;&gt;&gt; &#13;
</pre>&#13;
<p>从报错的信息上看，说明了 msg_inner 未定义，无法使用，因为它是局部变量，只有在函数内可以使用。</p>&#13;
&#13;
<h3>全局变量和局部变量</h3>&#13;
&#13;
<p>定义在函数内部的变量拥有一个局部作用域，定义在函数外的拥有全局作用域。</p>&#13;
&#13;
<p>局部变量只能在其被声明的函数内部访问，而全局变量可以在整个程序范围内访问。调用函数时，所有在函数内声明的变量名称都将被加入到作用域中。如下实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">total</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-comment"># 这是一个全局变量</span><span class="hl-code">
</span><span class="hl-comment"># 可写函数说明</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-builtin">sum</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">arg1</span><span class="hl-code">, </span><span class="hl-identifier">arg2</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-comment">#返回2个参数的和."</span><span class="hl-code">
    </span><span class="hl-identifier">total</span><span class="hl-code"> = </span><span class="hl-identifier">arg1</span><span class="hl-code"> + </span><span class="hl-identifier">arg2</span><span class="hl-code"> </span><span class="hl-comment"># total在这里是局部变量.</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">函数内是局部变量 : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">total</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">total</span><span class="hl-code">
 
</span><span class="hl-comment">#调用sum函数</span><span class="hl-code">
</span><span class="hl-builtin">sum</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-number">10</span><span class="hl-code">, </span><span class="hl-number">20</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">函数外是全局变量 : </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">total</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
函数内是局部变量 :  30&#13;
函数外是全局变量 :  0&#13;
</pre>&#13;
<h3>global 和 nonlocal关键字 </h3>&#13;
<p>当内部作用域想修改外部作用域的变量时，就要用到 global 和 nonlocal 关键字了。</p>&#13;
<p>以下实例修改全局变量 num：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-number">1</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">fun1</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-reserved">global</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">  </span><span class="hl-comment"># 需要使用 global 关键字声明</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code"> 
    </span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-number">123</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">fun1</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">num</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div><p>以上实例输出结果：</p>&#13;
<pre>&#13;
1&#13;
123&#13;
123&#13;
</pre>&#13;
<p>如果要修改嵌套作用域（enclosing 作用域，外层非全局作用域）中的变量则需要 nonlocal 关键字了，如下实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">outer</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">
    </span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">inner</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
        </span><span class="hl-identifier">nonlocal</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">   </span><span class="hl-comment"># nonlocal关键字声明</span><span class="hl-code">
        </span><span class="hl-identifier">num</span><span class="hl-code"> = </span><span class="hl-number">100</span><span class="hl-code">
        </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">inner</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">outer</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
100&#13;
100&#13;
</pre>&#13;
<p>另外有一种特殊情况，假设下面这段代码被运行：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-number">1</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>&#13;
以上程序执行，报错信息如下：</p>&#13;
<pre>&#13;
Traceback (most recent call last):&#13;
  File "test.py", line 7, in &lt;module&gt;&#13;
    test()&#13;
  File "test.py", line 5, in test&#13;
    a = a + 1&#13;
UnboundLocalError: local variable 'a' referenced before assignment&#13;
</pre>&#13;
<p>错误信息为局部作用域引用错误，因为 test 函数中的 a 使用的是局部，未定义，无法修改。</p>&#13;
<p>修改 a 为全局变量：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code"><div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-reserved">global</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">
    </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-number">1</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span></div></div>&#13;
<p>执行输出结果为：</p>&#13;
<div class="example_code">&#13;
11&#13;
</div>&#13;
</div>&#13;
<p>也可以通过函数参数传递：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例(Python 3.0+)</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">
</span><span class="hl-reserved">def</span><span class="hl-code"> </span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-brackets">)</span><span class="hl-code">:
    </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-identifier">a</span><span class="hl-code"> + </span><span class="hl-number">1</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-identifier">a</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
<p>执行输出结果为：</p>&#13;
<div class="example_code">&#13;
11&#13;
</div>&#13;
</div>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>