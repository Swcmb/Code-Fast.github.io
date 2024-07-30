<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 接口（抽象类）</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">接口（抽象类）</span></h1>&#13;
&#13;
<p>接口描述了类的行为和功能，而不需要完成类的特定实现。</p>&#13;
<p>C++ 接口是使用<b>抽象类</b>来实现的，抽象类与数据抽象互不混淆，数据抽象是一个把实现细节与相关的数据分离开的概念。</p>&#13;
<p>如果类中至少有一个函数被声明为纯虚函数，则这个类就是抽象类。纯虚函数是通过在声明中使用 "= 0" 来指定的，如下所示：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
      </span><span class="hl-comment">// 纯虚函数</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">virtual</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code">:
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">length</span><span class="hl-code">;      </span><span class="hl-comment">// 长度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">breadth</span><span class="hl-code">;     </span><span class="hl-comment">// 宽度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">height</span><span class="hl-code">;      </span><span class="hl-comment">// 高度</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>设计<b>抽象类</b>（通常称为 ABC）的目的，是为了给其他类提供一个可以继承的适当的基类。抽象类不能被用于实例化对象，它只能作为<b>接口</b>使用。如果试图实例化一个抽象类的对象，会导致编译错误。</p>&#13;
<p>因此，如果一个 ABC 的子类需要被实例化，则必须实现每个纯虚函数，这也意味着 C++ 支持使用 ABC 声明接口。如果没有在派生类中重写纯虚函数，就尝试实例化该类的对象，会导致编译错误。</p>&#13;
<p>可用于实例化对象的类被称为<b>具体类</b>。</p>&#13;
&#13;
<h2 class="tutheader">抽象类的实例</h2>&#13;
<p>请看下面的实例，基类 Shape 提供了一个接口 <b>getArea()</b>，在两个派生类 Rectangle 和 Triangle 中分别实现了 <b>getArea()</b>：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
 
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-comment">// 基类</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Shape</span><span class="hl-code"> 
</span><span class="hl-brackets">{</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code">:
   </span><span class="hl-comment">// 提供接口框架的纯虚函数</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-types">virtual</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getArea</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setWidth</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">w</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">width</span><span class="hl-code"> = </span><span class="hl-identifier">w</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">h</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">height</span><span class="hl-code"> = </span><span class="hl-identifier">h</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">protected</span><span class="hl-code">:
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">width</span><span class="hl-code">;
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">height</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">;
 
</span><span class="hl-comment">// 派生类</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Rectangle</span><span class="hl-code">: </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">Shape</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code">:
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getArea</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code"> 
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">width</span><span class="hl-code"> * </span><span class="hl-identifier">height</span><span class="hl-brackets">)</span><span class="hl-code">; 
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Triangle</span><span class="hl-code">: </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">Shape</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code">:
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getArea</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code"> 
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">width</span><span class="hl-code"> * </span><span class="hl-identifier">height</span><span class="hl-brackets">)</span><span class="hl-code">/</span><span class="hl-number">2</span><span class="hl-code">; 
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Rectangle</span><span class="hl-code"> </span><span class="hl-identifier">Rect</span><span class="hl-code">;
   </span><span class="hl-identifier">Triangle</span><span class="hl-code">  </span><span class="hl-identifier">Tri</span><span class="hl-code">;
 
   </span><span class="hl-identifier">Rect</span><span class="hl-code">.</span><span class="hl-identifier">setWidth</span><span class="hl-brackets">(</span><span class="hl-number">5</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">Rect</span><span class="hl-code">.</span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-number">7</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-comment">// 输出对象的面积</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Total Rectangle area: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">Rect</span><span class="hl-code">.</span><span class="hl-identifier">getArea</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-identifier">Tri</span><span class="hl-code">.</span><span class="hl-identifier">setWidth</span><span class="hl-brackets">(</span><span class="hl-number">5</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">Tri</span><span class="hl-code">.</span><span class="hl-identifier">setHeight</span><span class="hl-brackets">(</span><span class="hl-number">7</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-comment">// 输出对象的面积</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Total Triangle area: </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">Tri</span><span class="hl-code">.</span><span class="hl-identifier">getArea</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">; 
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Total Rectangle area: 35&#13;
Total Triangle area: 17&#13;
</pre>&#13;
<p>从上面的实例中，我们可以看到一个抽象类是如何定义一个接口 getArea()，两个派生类是如何通过不同的计算面积的算法来实现这个相同的函数。</p>&#13;
&#13;
<h2 class="tutheader">设计策略</h2>&#13;
<p>面向对象的系统可能会使用一个抽象基类为所有的外部应用程序提供一个适当的、通用的、标准化的接口。然后，派生类通过继承抽象基类，就把所有类似的操作都继承下来。</p>&#13;
<p>外部应用程序提供的功能（即公有函数）在抽象基类中是以纯虚函数的形式存在的。这些纯虚函数在相应的派生类中被实现。</p>&#13;
<p>这个架构也使得新的应用程序可以很容易地被添加到系统中，即使是在系统被定义之后依然可以如此。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>