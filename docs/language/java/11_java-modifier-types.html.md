<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 修饰符</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 修饰符</h1>&#13;
<p>Java语言提供了很多修饰符，主要分为以下两类：</p>&#13;
<ul>&#13;
<li>访问修饰符</li>&#13;
<li>非访问修饰符</li>&#13;
</ul>&#13;
<p>&#13;
修饰符用来定义类、方法或者变量，通常放在语句的最前端。我们通过下面的例子来说明：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">ClassName</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment"> ...</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">boolean</span><span class="hl-code"> </span><span class="hl-identifier">myFlag</span><span class="hl-code">;
</span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">weeks</span><span class="hl-code"> = </span><span class="hl-number">9</span><span class="hl-number">.5</span><span class="hl-code">;
</span><span class="hl-reserved">protected</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">BOXWIDTH</span><span class="hl-code"> = </span><span class="hl-number">42</span><span class="hl-code">;
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">arguments</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment"> 方法体</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>&#13;
访问控制修饰符&#13;
</h2>&#13;
<p>Java中，可以使用访问控制符来保护对类、变量、方法和构造方法的访问。Java 支持 4 种不同的访问权限。</p>&#13;
<ul><li>&#13;
<p><strong>default</strong> (即默认，什么也不写）: 在同一包内可见，不使用任何修饰符。使用对象：类、接口、变量、方法。</p></li><li>&#13;
<p><strong>private</strong> : 在同一类内可见。使用对象：变量、方法。 <strong>注意：不能修饰类（外部类）</strong></p></li><li>&#13;
<p><strong>public</strong> : 对所有类可见。使用对象：类、接口、变量、方法</p></li><li>&#13;
<p><strong>protected</strong> : 对同一包内的类和所有子类可见。使用对象：变量、方法。 <strong>注意：不能修饰类（外部类）</strong>。</p></li></ul>&#13;
<p>我们可以通过以下表来说明访问权限：</p>&#13;
<table class="reference">&#13;
<caption style="font-weight: bold;font-size:16px;font-weight: bold;" id="accesscontrol-levels">访问控制</caption>&#13;
<tbody><tr>&#13;
<th>修饰符</th>&#13;
<th>当前类</th>&#13;
<th>同一包内</th>&#13;
<th>子孙类(同一包)</th>&#13;
<th>子孙类(不同包)</th>&#13;
<th>其他包</th>&#13;
</tr>&#13;
<tr>&#13;
<td headers="h1"><code>public</code></td>&#13;
<td headers="h2">Y</td>&#13;
<td headers="h3">Y</td>&#13;
<td headers="h4">Y</td>&#13;
<td headers="h5">Y</td>&#13;
<td headers="h6">Y</td>&#13;
</tr>&#13;
<tr>&#13;
<td headers="h1"><code>protected</code></td>&#13;
<td headers="h2">Y</td>&#13;
<td headers="h3">Y</td>&#13;
<td headers="h4">Y</td>&#13;
&#13;
<td headers="h5">Y/N（<a href="#protected-desc">说明</a>）</td>&#13;
<td headers="h6">N</td>&#13;
</tr>&#13;
<tr>&#13;
<td headers="h1"><code>default</code></td>&#13;
<td headers="h2">Y</td>&#13;
<td headers="h3">Y</td>&#13;
<td headers="h4">Y</td>&#13;
<td headers="h5">N</td>&#13;
<td headers="h6">N</td>&#13;
</tr>&#13;
<tr>&#13;
<td headers="h1"><code>private</code></td>&#13;
<td headers="h2">Y</td>&#13;
<td headers="h3">N</td>&#13;
<td headers="h4">N</td>&#13;
<td headers="h5">N</td>&#13;
<td headers="h6">N</td>&#13;
</tr>&#13;
</tbody></table>&#13;
<h3>默认访问修饰符-不使用任何关键字</h3>&#13;
<p>&#13;
如果在类、变量、方法或构造函数的定义中没有指定任何访问修饰符，那么它们就默认具有默认访问修饰符。</p>&#13;
<p>默认访问修饰符的访问级别是包级别（package-level），即只能被同一包中的其他类访问。</p>&#13;
&#13;
<p>&#13;
如下例所示，变量和方法的声明可以不使用任何修饰符。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> MyClass.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">MyClass</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  </span><span class="hl-comment">//</span><span class="hl-comment"> 默认访问修饰符</span><span class="hl-comment"/><span class="hl-code">
 
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;  </span><span class="hl-comment">//</span><span class="hl-comment"> 默认访问修饰符</span><span class="hl-comment"/><span class="hl-code">
 
    </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">display</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">  </span><span class="hl-comment">//</span><span class="hl-comment"> 默认访问修饰符</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Value of x is: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">x</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-comment">//</span><span class="hl-comment"> MyOtherClass.java</span><span class="hl-comment"/><span class="hl-code">
 
</span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">MyOtherClass</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">MyClass</span><span class="hl-code"> </span><span class="hl-identifier">obj</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">MyClass</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
        </span><span class="hl-identifier">obj</span><span class="hl-code">.</span><span class="hl-identifier">display</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;  </span><span class="hl-comment">//</span><span class="hl-comment"> 访问 MyClass 中的默认访问修饰符变量和方法</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div><p>&#13;
以上实例中，MyClass 类和它的成员变量 x 和方法 display() 都使用默认访问修饰符进行了定义。MyOtherClass 类在同一包中，因此可以访问 MyClass 类和它的成员变量和方法。</p>&#13;
<h3>私有访问修饰符-private</h3>&#13;
&#13;
<p>私有访问修饰符是最严格的访问级别，所以被声明为 <strong>private</strong> 的方法、变量和构造方法只能被所属类访问，并且类和接口不能声明为 <strong>private</strong>。</p>&#13;
<p>声明为私有访问类型的变量只能通过类中公共的 getter 方法被外部类访问。</p>&#13;
<p>Private 访问修饰符的使用主要用来隐藏类的实现细节和保护类的数据。</p>&#13;
<p>下面的类使用了私有访问修饰符：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Logger</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">format</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">getFormat</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">format</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setFormat</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">format</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">format</span><span class="hl-code"> = </span><span class="hl-identifier">format</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
实例中，Logger 类中的 format 变量为私有变量，所以其他类不能直接得到和设置该变量的值。为了使其他类能够操作该变量，定义了两个 public 方法：getFormat() （返回 format的值）和 setFormat(String)（设置 format 的值）&#13;
</p>&#13;
<h3>公有访问修饰符-public</h3>&#13;
&#13;
<p>被声明为 public 的类、方法、构造方法和接口能够被任何其他类访问。&#13;
</p><p>如果几个相互访问的 public 类分布在不同的包中，则需要导入相应 public 类所在的包。由于类的继承性，类所有的公有方法和变量都能被其子类继承。&#13;
</p><p>&#13;
以下函数使用了公有访问控制：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">arguments</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment"> ...</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>Java 程序的 main() 方法必须设置成公有的，否则，Java 解释器将不能运行该类。</p>&#13;
&#13;
<h3 id="protected-desc">受保护的访问修饰符-protected</h3>&#13;
<p>protected 需要从以下两个点来分析说明：</p>&#13;
<ul>&#13;
<li><p><strong>子类与基类在同一包中</strong>：被声明为 protected 的变量、方法和构造器能被同一个包中的任何其他类访问；</p></li>&#13;
<li><p><strong>子类与基类不在同一包中</strong>：那么在子类中，子类实例可以访问其从基类继承而来的 protected 方法，而不能访问基类实例的protected方法。</p></li>&#13;
</ul>&#13;
<p>protected 可以修饰数据成员，构造方法，方法成员，<strong>不能修饰类（内部类除外）</strong>。</p>&#13;
<p>接口及接口的成员变量和成员方法不能声明为 protected。 可以看看下图演示：&#13;
</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/12/java-protected.gif"/></p>&#13;
&#13;
<p>子类能访问 protected 修饰符声明的方法和变量，这样就能保护不相关的类使用这些方法和变量。&#13;
</p><p>&#13;
下面的父类使用了 protected 访问修饰符，子类重写了父类的 openSpeaker() 方法。</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">AudioPlayer</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">protected</span><span class="hl-code"> </span><span class="hl-types">boolean</span><span class="hl-code"> </span><span class="hl-identifier">openSpeaker</span><span class="hl-brackets">(</span><span class="hl-identifier">Speaker</span><span class="hl-code"> </span><span class="hl-identifier">sp</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment"> 实现细节</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">StreamingAudioPlayer</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">AudioPlayer</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">protected</span><span class="hl-code"> </span><span class="hl-types">boolean</span><span class="hl-code"> </span><span class="hl-identifier">openSpeaker</span><span class="hl-brackets">(</span><span class="hl-identifier">Speaker</span><span class="hl-code"> </span><span class="hl-identifier">sp</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment"> 实现细节</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>如果把 openSpeaker() 方法声明为 private，那么除了 AudioPlayer 外，其他类将不能访问该方法。</p><p>&#13;
如果把 openSpeaker() 声明为 public，那么所有的类都能够访问该方法。</p><p>&#13;
如果我们只想让该方法对其所在类的子类可见，则将该方法声明为 protected。</p>&#13;
&#13;
&#13;
&#13;
&#13;
<blockquote><p>protected 是最难理解的一种 Java 类成员访问权限修饰词，更多详细内容请查看 <a href="//www.runoob.com/w3cnote/java-protected-keyword-detailed-explanation.html" rel="noopener noreferrer" target="_blank">Java protected 关键字详解</a>。</p></blockquote>&#13;
&#13;
&#13;
<h3>访问控制和继承</h3>&#13;
<p>&#13;
&#13;
请注意以下方法继承的规则：&#13;
</p>&#13;
<ul>&#13;
	<li><p>父类中声明为 public 的方法在子类中也必须为 public。</p>&#13;
	</li>&#13;
	<li><p>父类中声明为 protected 的方法在子类中要么声明为 protected，要么声明为 public，不能声明为 private。</p>&#13;
	</li>&#13;
	&#13;
	<li>&#13;
		<p>&#13;
			父类中声明为 private 的方法，不能够被子类继承。</p>&#13;
	</li>&#13;
</ul>&#13;
&#13;
&#13;
&#13;
&#13;
<hr/>&#13;
<h2>&#13;
非访问修饰符</h2>&#13;
<p>为了实现一些其他的功能，Java 也提供了许多非访问修饰符。</p>&#13;
<p>static 修饰符，用来修饰类方法和类变量。</p>&#13;
<p>final 修饰符，用来修饰类、方法和变量，final 修饰的类不能够被继承，修饰的方法不能被继承类重新定义，修饰的变量为常量，是不可修改的。</p>&#13;
<p>abstract 修饰符，用来创建抽象类和抽象方法。</p>&#13;
<p>synchronized 和 volatile 修饰符，主要用于线程的编程。</p>&#13;
<h3>static 修饰符</h3>&#13;
<ul>&#13;
<li>&#13;
<p><strong>静态变量：</strong></p><p>&#13;
static 关键字用来声明独立于对象的静态变量，无论一个类实例化多少对象，它的静态变量只有一份拷贝。&#13;
静态变量也被称为类变量。局部变量不能被声明为 static 变量。&#13;
</p></li><li>&#13;
<p><strong>静态方法：</strong></p><p>&#13;
static 关键字用来声明独立于对象的静态方法。静态方法不能使用类的非静态变量。静态方法从参数列表得到数据，然后计算这些数据。&#13;
</p></li></ul>&#13;
<p>&#13;
对类变量和方法的访问可以直接使用 <strong>classname.variablename</strong> 和 <strong>classname.methodname</strong> 的方式访问。&#13;
</p>&#13;
<p>&#13;
如下例所示，static 修饰符用来创建类方法和类变量。</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">InstanceCounter</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">numInstances</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
   </span><span class="hl-reserved">protected</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getCount</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">numInstances</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">addInstance</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">numInstances</span><span class="hl-code">++;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-identifier">InstanceCounter</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">InstanceCounter</span><span class="hl-code">.</span><span class="hl-identifier">addInstance</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">arguments</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Starting with </span><span class="hl-quotes">"</span><span class="hl-code"> +
      </span><span class="hl-identifier">InstanceCounter</span><span class="hl-code">.</span><span class="hl-identifier">getCount</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> instances</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">500</span><span class="hl-code">; ++</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InstanceCounter</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
          </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Created </span><span class="hl-quotes">"</span><span class="hl-code"> +
      </span><span class="hl-identifier">InstanceCounter</span><span class="hl-code">.</span><span class="hl-identifier">getCount</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> instances</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例运行编辑结果如下:</p>&#13;
<pre>&#13;
Starting with 0 instances&#13;
Created 500 instances&#13;
</pre>&#13;
<h3>final 修饰符</h3>&#13;
<p><strong>final 变量：</strong></p>&#13;
&#13;
<p>final 表示"最后的、最终的"含义，变量一旦赋值后，不能被重新赋值。被 final 修饰的实例变量必须显式指定初始值。</p>&#13;
<p>final 修饰符通常和 static 修饰符一起使用来创建类常量。</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">value</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
  </span><span class="hl-comment">//</span><span class="hl-comment"> 下面是声明常量的实例</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">BOXWIDTH</span><span class="hl-code"> = </span><span class="hl-number">6</span><span class="hl-code">;
  </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">TITLE</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Manager</span><span class="hl-quotes">"</span><span class="hl-code">;
 
  </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">changeValue</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
     </span><span class="hl-identifier">value</span><span class="hl-code"> = </span><span class="hl-number">12</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">将输出一个错误</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><strong>final 方法</strong></p>&#13;
<p>父类中的 final 方法可以被子类继承，但是不能被子类重写。</p>&#13;
<p>声明 final 方法的主要目的是防止该方法的内容被修改。</p>&#13;
<p>如下所示，使用 final 修饰符声明方法。</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">changeName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-comment">//</span><span class="hl-comment"> 方法体</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><strong>final 类</strong></p>&#13;
<p>final 类不能被继承，没有类能够继承 final 类的任何特性。</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment"> 类体</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>abstract 修饰符</h3>&#13;
<p><strong>抽象类：</strong></p>&#13;
<p>抽象类不能用来实例化对象，声明抽象类的唯一目的是为了将来对该类进行扩充。&#13;
</p><p>一个类不能同时被 abstract 和 final 修饰。如果一个类包含抽象方法，那么该类一定要声明为抽象类，否则将出现编译错误。&#13;
</p><p>抽象类可以包含抽象方法和非抽象方法。&#13;
</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Caravan</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">price</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">model</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">year</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">goFast</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">抽象方法</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">changeColor</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><strong>抽象方法</strong></p>&#13;
<p>&#13;
抽象方法是一种没有任何实现的方法，该方法的具体实现由子类提供。</p><p>抽象方法不能被声明成 final 和 static。&#13;
</p><p>任何继承抽象类的子类必须实现父类的所有抽象方法，除非该子类也是抽象类。&#13;
</p><p>如果一个类包含若干个抽象方法，那么该类必须声明为抽象类。抽象类可以不包含抽象方法。&#13;
</p><p>抽象方法的声明以分号结尾，例如：<strong>public abstract sample();</strong>。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SuperClass</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">抽象方法</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SubClass</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">SuperClass</span><span class="hl-brackets">{</span><span class="hl-code">
     </span><span class="hl-comment">//</span><span class="hl-comment">实现抽象方法</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">m</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
          .........
      </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>synchronized 修饰符</h3>&#13;
<p>synchronized 关键字声明的方法同一时间只能被一个线程访问。synchronized 修饰符可以应用于四个访问修饰符。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">synchronized</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">showDetails</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
.......
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>transient 修饰符</h3>&#13;
&#13;
<p>序列化的对象包含被 transient 修饰的实例变量时，java 虚拟机(JVM)跳过该特定的变量。&#13;
</p><p>该修饰符包含在定义变量的语句中，用来预处理类和变量的数据类型。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">transient</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">limit</span><span class="hl-code"> = </span><span class="hl-number">55</span><span class="hl-code">;   </span><span class="hl-comment">//</span><span class="hl-comment"> 不会持久化</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">b</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment"> 持久化</span><span class="hl-comment"/></div>&#13;
</div>&#13;
</div>&#13;
<h3>volatile 修饰符</h3>&#13;
&#13;
<p>volatile 修饰的成员变量在每次被线程访问时，都强制从共享内存中重新读取该成员变量的值。而且，当成员变量发生变化时，会强制线程将变化值回写到共享内存。这样在任何时刻，两个不同的线程总是看到某个成员变量的同一个值。</p>&#13;
<p>一个 volatile 对象引用可能是 null。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">MyRunnable</span><span class="hl-code"> </span><span class="hl-reserved">implements</span><span class="hl-code"> </span><span class="hl-identifier">Runnable</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-reserved">volatile</span><span class="hl-code"> </span><span class="hl-types">boolean</span><span class="hl-code"> </span><span class="hl-identifier">active</span><span class="hl-code">;
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">run</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">active</span><span class="hl-code"> = </span><span class="hl-reserved">true</span><span class="hl-code">;
        </span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">active</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-comment">//</span><span class="hl-comment"> 第一行</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-brackets">{</span><span class="hl-code">
            </span><span class="hl-comment">//</span><span class="hl-comment"> 代码</span><span class="hl-comment"/><span class="hl-code">
        </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">stop</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-identifier">active</span><span class="hl-code"> = </span><span class="hl-reserved">false</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment"> 第二行</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
通常情况下，在一个线程调用 run() 方法（在 Runnable 开启的线程），在另一个线程调用 stop() 方法。&#13;
如果 <strong><em>第一行</em></strong> 中缓冲区的 active 值被使用，那么在 <strong><em>第二行</em></strong> 的 active 值为 false 时循环不会停止。&#13;
</p><p>&#13;
但是以上代码中我们使用了 volatile  修饰 active，所以该循环会停止。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>