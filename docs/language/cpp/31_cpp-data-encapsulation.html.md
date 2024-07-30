<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 数据封装</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">数据封装</span></h1>&#13;
<p>数据封装（Data Encapsulation）是面向对象编程（OOP）的一个基本概念，它通过将数据和操作数据的函数封装在一个类中来实现。这种封装确保了数据的私有性和完整性，防止了外部代码对其直接访问和修改。</p>&#13;
<p>所有的 C++ 程序都有以下两个基本要素： </p>&#13;
<ul class="list">&#13;
<li><b>程序语句（代码）：</b>这是程序中执行动作的部分，它们被称为函数。</li>&#13;
<li><b>程序数据：</b>数据是程序的信息，会受到程序函数的影响。</li>&#13;
</ul>&#13;
<p>封装是面向对象编程中的把数据和操作数据的函数绑定在一起的一个概念，这样能避免受到外界的干扰和误用，从而确保了安全。数据封装引申出了另一个重要的 OOP 概念，即<b>数据隐藏</b>。</p>&#13;
<p><b>数据封装</b>是一种把数据和操作数据的函数捆绑在一起的机制，<b>数据抽象</b>是一种仅向用户暴露接口而把具体的实现细节隐藏起来的机制。</p>&#13;
<p>C++ 通过创建<b>类</b>来支持封装和数据隐藏（public、protected、private）。我们已经知道，类包含私有成员（private）、保护成员（protected）和公有成员（public）成员。默认情况下，在类中定义的所有项目都是私有的。例如：</p>&#13;
<div class="example"> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Box</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getVolume</span><span class="hl-brackets">(</span><span class="hl-types">void</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">length</span><span class="hl-code"> * </span><span class="hl-identifier">breadth</span><span class="hl-code"> * </span><span class="hl-identifier">height</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code">:
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">length</span><span class="hl-code">;      </span><span class="hl-comment">// 长度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">breadth</span><span class="hl-code">;     </span><span class="hl-comment">// 宽度</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">height</span><span class="hl-code">;      </span><span class="hl-comment">// 高度</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>变量 length、breadth 和 height 都是私有的（private）。这意味着它们只能被 Box 类中的其他成员访问，而不能被程序中其他部分访问。这是实现封装的一种方式。</p>&#13;
<p>为了使类中的成员变成公有的（即，程序中的其他部分也能访问），必须在这些成员前使用 <b>public</b> 关键字进行声明。所有定义在 public 标识符后边的变量或函数可以被程序中所有其他的函数访问。</p>&#13;
<p>把一个类定义为另一个类的友元类，会暴露实现细节，从而降低了封装性。理想的做法是尽可能地对外隐藏每个类的实现细节。</p><p><strong>访问修饰符：</strong></p>&#13;
<ul><li><strong>private</strong>: 私有成员只能在类的内部访问，不能被类的外部代码直接访问。</li><li><strong>public</strong>: 公有成员可以被类的外部代码直接访问。</li><li><strong>protected</strong>: 受保护成员可以被类和其派生类访问。</li></ul>&#13;
<h2 class="tutheader">数据封装的实例</h2>&#13;
<p>C++ 程序中，任何带有公有和私有成员的类都可以作为数据封装和数据抽象的实例。请看下面的实例：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">class</span><span class="hl-code"> </span><span class="hl-identifier">Adder</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code">:
      </span><span class="hl-comment">// 构造函数</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-identifier">Adder</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">total</span><span class="hl-code"> = </span><span class="hl-identifier">i</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-comment">// 对外的接口</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">addNum</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">total</span><span class="hl-code"> += </span><span class="hl-identifier">number</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-comment">// 对外的接口</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getTotal</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">total</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code">:
      </span><span class="hl-comment">// 对外隐藏的数据</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">total</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">;
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-identifier">Adder</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code">;
   
   </span><span class="hl-identifier">a</span><span class="hl-code">.</span><span class="hl-identifier">addNum</span><span class="hl-brackets">(</span><span class="hl-number">10</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">a</span><span class="hl-code">.</span><span class="hl-identifier">addNum</span><span class="hl-brackets">(</span><span class="hl-number">20</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-identifier">a</span><span class="hl-code">.</span><span class="hl-identifier">addNum</span><span class="hl-brackets">(</span><span class="hl-number">30</span><span class="hl-brackets">)</span><span class="hl-code">;
 
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">Total </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">a</span><span class="hl-code">.</span><span class="hl-identifier">getTotal</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt;</span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
Total 60&#13;
</pre>&#13;
<p>上面的类把数字相加，并返回总和。公有成员 <b>addNum</b> 和 <b>getTotal</b> 是对外的接口，用户需要知道它们以便使用类。私有成员 <b>total</b> 是对外隐藏的，用户不需要了解它，但它又是类能正常工作所必需的。</p>&#13;
<p>数据封装通过类和访问修饰符（public, private, protected）来实现，以下是一个简单的例子：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #05a;">using</span> <span style="color: #05a;">namespace</span> std<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">class</span> Student <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">private</span><span style="color: #008080;">:</span><br/>
    string name<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int</span> age<span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #666666;">// 构造函数</span><br/>
    Student<span style="color: #008000;">(</span>string studentName, <span style="color: #05a;">int</span> studentAge<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        name <span style="color: #000080;">=</span> studentName<span style="color: #008080;">;</span><br/>
        age <span style="color: #000080;">=</span> studentAge<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 访问器函数（getter）</span><br/>
    string getName<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">return</span> name<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">int</span> getAge<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">return</span> age<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 修改器函数（setter）</span><br/>
    <span style="color: #05a;">void</span> setName<span style="color: #008000;">(</span>string studentName<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        name <span style="color: #000080;">=</span> studentName<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">void</span> setAge<span style="color: #008000;">(</span><span style="color: #05a;">int</span> studentAge<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>studentAge <span style="color: #000080;">&gt;</span> <span style="color: #0000dd;">0</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
            age <span style="color: #000080;">=</span> studentAge<span style="color: #008080;">;</span><br/>
        <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
            <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Invalid age!"</span> <span style="color: #000080;">&lt;&lt;</span> endl<span style="color: #008080;">;</span><br/>
        <span style="color: #008000;">}</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #666666;">// 打印学生信息</span><br/>
    <span style="color: #05a;">void</span> printInfo<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        <span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Name: "</span> <span style="color: #000080;">&lt;&lt;</span> name <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">", Age: "</span> <span style="color: #000080;">&lt;&lt;</span> age <span style="color: #000080;">&lt;&lt;</span> endl<span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 创建一个 Student 对象</span><br/>
    Student student1<span style="color: #008000;">(</span><span style="color: #a11;">"Alice"</span>, <span style="color: #0000dd;">20</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 访问和修改数据</span><br/>
    student1.<span style="color: #007788;">printInfo</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    student1.<span style="color: #007788;">setName</span><span style="color: #008000;">(</span><span style="color: #a11;">"Bob"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    student1.<span style="color: #007788;">setAge</span><span style="color: #008000;">(</span><span style="color: #0000dd;">22</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    student1.<span style="color: #007788;">printInfo</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
&#13;
<h2 class="tutheader">设计策略</h2>&#13;
<p>通常情况下，我们都会设置类成员状态为私有（private），除非我们真的需要将其暴露，这样才能保证良好的<b>封装性</b>。</p>&#13;
<p>这通常应用于数据成员，但它同样适用于所有成员，包括虚函数。</p>&#13;
<h2 class="tutheader">数据封装的优点</h2>&#13;
<ul><li><strong>数据隐藏</strong>: 通过将数据成员声明为私有，防止外部代码直接访问这些数据。</li><li><strong>提高代码可维护性</strong>: 提供公共方法来访问和修改数据，这使得可以在不影响外部代码的情况下修改类的内部实现。</li><li><strong>增强安全性</strong>: 防止不合法的数据输入和不当的修改操作。</li><li><strong>实现抽象</strong>: 提供了一种机制，使得用户不需要了解类的内部实现细节，只需要了解如何使用类的公共接口即可。</li></ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>