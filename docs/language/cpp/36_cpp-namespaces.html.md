<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 命名空间</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">命名空间</span></h1>&#13;
&#13;
<p>假设这样一种情况，当一个班上有两个名叫 Zara 的学生时，为了明确区分它们，我们在使用名字之外，不得不使用一些额外的信息，比如他们的家庭住址，或者他们父母的名字等等。</p>&#13;
<p>同样的情况也出现在 C++ 应用程序中。例如，您可能会写一个名为 xyz() 的函数，在另一个可用的库中也存在一个相同的函数 xyz()。这样，编译器就无法判断您所使用的是哪一个 xyz() 函数。</p>&#13;
<p>因此，引入了<b>命名空间</b>这个概念，专门用于解决上面的问题，它可作为附加信息来区分不同库中相同名称的函数、类、变量等。使用了命名空间即定义了上下文。本质上，命名空间就是定义了一个范围。</p>&#13;
<p>我们举一个计算机系统中的例子，一个文件夹(目录)中可以包含多个文件夹，每个文件夹中不能有相同的文件名，但不同文件夹中的文件可以重名。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2019/09/0129A8E9-30FE-431D-8C48-399EA4841E9D.jpg"/></p>&#13;
<h2>定义命名空间</h2>&#13;
<p>命名空间的定义使用关键字 <b>namespace</b>，后跟命名空间的名称，如下所示：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 代码声明</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div><p>为了调用带有命名空间的函数或变量，需要在前面加上命名空间的名称，如下所示：</p>&#13;
&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">name</span><span class="hl-code">::</span><span class="hl-identifier">code</span><span class="hl-code">;  </span><span class="hl-comment">// code 可以是变量或函数</span></div>&#13;
</div>&#13;
</div>&#13;
<p>让我们来看看命名空间如何为变量或函数等实体定义范围：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 第一个命名空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">first_space</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside first_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-comment">// 第二个命名空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">second_space</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside second_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-comment">// 调用第一个命名空间中的函数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">first_space</span><span class="hl-code">::</span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-comment">// 调用第二个命名空间中的函数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">second_space</span><span class="hl-code">::</span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">; 
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Inside first_space&#13;
Inside second_space&#13;
</pre>&#13;
&#13;
<h2>using 指令</h2>&#13;
<p>您可以使用 <b>using namespace</b> 指令，这样在使用命名空间时就可以不用在前面加上命名空间的名称。这个指令会告诉编译器，后续的代码将使用指定的命名空间中的名称。</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 第一个命名空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">first_space</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside first_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-comment">// 第二个命名空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">second_space</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside second_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">first_space</span><span class="hl-code">;
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-comment">// 调用第一个命名空间中的函数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Inside first_space&#13;
</pre>&#13;
<p>using 指令也可以用来指定命名空间中的特定项目。例如，如果您只打算使用 std 命名空间中的 cout 部分，您可以使用如下的语句：</p>&#13;
<pre>&#13;
using std::cout;&#13;
</pre>&#13;
<p>随后的代码中，在使用 cout 时就可以不用加上命名空间名称作为前缀，但是 <b>std</b> 命名空间中的其他项目仍然需要加上命名空间名称作为前缀，如下所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">cout</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">std::endl is used with std!</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">std</span><span class="hl-code">::</span><span class="hl-identifier">endl</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
std::endl is used with std!&#13;
</pre>&#13;
<p><b>using</b> 指令引入的名称遵循正常的范围规则。名称从使用 <b>using</b> 指令开始是可见的，直到该范围结束。此时，在范围以外定义的同名实体是隐藏的。</p>&#13;
&#13;
<h2>不连续的命名空间</h2>&#13;
<p>命名空间可以定义在几个不同的部分中，因此命名空间是由几个单独定义的部分组成的。一个命名空间的各个组成部分可以分散在多个文件中。</p>&#13;
<p>所以，如果命名空间中的某个组成部分需要请求定义在另一个文件中的名称，则仍然需要声明该名称。下面的命名空间定义可以是定义一个新的命名空间，也可以是为已有的命名空间增加新的元素：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 代码声明</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<h2>嵌套的命名空间</h2>&#13;
<p>命名空间可以嵌套，您可以在一个命名空间中定义另一个命名空间，如下所示：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name1</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 代码声明</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name2</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">// 代码声明</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>您可以通过使用 <span class="marked">::</span> 运算符来访问嵌套的命名空间中的成员：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">// 访问 namespace_name2 中的成员</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name1</span><span class="hl-code">::</span><span class="hl-identifier">namespace_name2</span><span class="hl-code">;
 
</span><span class="hl-comment">// 访问 namespace_name1 中的成员</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">namespace_name1</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>在上面的语句中，如果使用的是 namespace_name1，那么在该范围内 namespace_name2 中的元素也是可用的，如下所示：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 第一个命名空间</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">first_space</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside first_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-comment">// 第二个命名空间</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">second_space</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Inside second_space</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">first_space</span><span class="hl-code">::</span><span class="hl-identifier">second_space</span><span class="hl-code">;
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-comment">// 调用第二个命名空间中的函数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">func</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Inside second_space&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>