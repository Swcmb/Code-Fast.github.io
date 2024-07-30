<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 数组</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 数组</h1>&#13;
<p>&#13;
数组对于每一门编程语言来说都是重要的数据结构之一，当然不同语言对数组的实现及处理也不尽相同。&#13;
</p>&#13;
<p>Java 语言中提供的数组是用来存储固定大小的同类型元素。</p>&#13;
<p>你可以声明一个数组变量，如 numbers[100] 来代替直接声明 100 个独立变量 number0，number1，....，number99。&#13;
</p>&#13;
<p>本教程将为大家介绍 Java 数组的声明、创建和初始化，并给出其对应的代码。</p>&#13;
<hr/>&#13;
<h2>声明数组变量</h2>&#13;
<p>首先必须声明数组变量，才能在程序中使用数组。下面是声明数组变量的语法：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">dataType</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">arrayRefVar</span><span class="hl-code">;   </span><span class="hl-comment">//</span><span class="hl-comment"> 首选的方法</span><span class="hl-comment"/><span class="hl-code">
 
或
 
</span><span class="hl-identifier">dataType</span><span class="hl-code"> </span><span class="hl-identifier">arrayRefVar</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code">;  </span><span class="hl-comment">//</span><span class="hl-comment"> 效果相同，但不是首选方法</span><span class="hl-comment"/></div>&#13;
</div>&#13;
</div>&#13;
<p><strong>&#13;
注意:</strong> 建议使用 <strong>dataType[] arrayRefVar</strong> 的声明风格声明数组变量。&#13;
dataType arrayRefVar[] 风格是来自 C/C++ 语言 ，在Java中采用是为了让 C/C++ 程序员能够快速理解java语言。&#13;
</p>&#13;
<h3>实例</h3>&#13;
<p>下面是这两种语法的代码示例：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">double</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">myList</span><span class="hl-code">;         </span><span class="hl-comment">//</span><span class="hl-comment"> 首选的方法</span><span class="hl-comment"/><span class="hl-code">
 
或
 
</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code">;         </span><span class="hl-comment">//</span><span class="hl-comment">  效果相同，但不是首选方法</span><span class="hl-comment"/></div>&#13;
</div>&#13;
</div><hr/>&#13;
<h2>创建数组</h2>&#13;
<p>Java语言使用new操作符来创建数组，语法如下：</p>&#13;
<pre>&#13;
arrayRefVar = new dataType[arraySize];&#13;
</pre>&#13;
<p>上面的语法语句做了两件事：</p>&#13;
<ul><li>&#13;
一、使用 dataType[arraySize] 创建了一个数组。</li>&#13;
<li>二、把新创建的数组的引用赋值给变量 arrayRefVar。</li></ul>&#13;
<p>数组变量的声明，和创建数组可以用一条语句完成，如下所示：</p>&#13;
<pre>&#13;
dataType[] arrayRefVar = new dataType[arraySize];&#13;
</pre>&#13;
<p>另外，你还可以使用如下的方式创建数组。</p>&#13;
<pre>&#13;
dataType[] arrayRefVar = {value0, value1, ..., valuek};&#13;
</pre>&#13;
<p>数组的元素是通过索引访问的。数组索引从 0 开始，所以索引值从 0 到 arrayRefVar.length-1。</p>&#13;
<h3>实例</h3>&#13;
<p>&#13;
下面的语句首先声明了一个数组变量 myList，接着创建了一个包含 10 个 double 类型元素的数组，并且把它的引用赋值给 myList 变量。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">TestArray.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">TestArray</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment"> 数组大小</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">size</span><span class="hl-code"> = </span><span class="hl-number">10</span><span class="hl-code">;
      </span><span class="hl-comment">//</span><span class="hl-comment"> 定义数组</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">myList</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-brackets">[</span><span class="hl-identifier">size</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-number">.6</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">4</span><span class="hl-number">.5</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">3</span><span class="hl-number">.3</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">13</span><span class="hl-number">.2</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">4</span><span class="hl-number">.0</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">5</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">34</span><span class="hl-number">.33</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">6</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">34</span><span class="hl-number">.0</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">7</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">45</span><span class="hl-number">.45</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">8</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">99</span><span class="hl-number">.993</span><span class="hl-code">;
      </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">9</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">11123</span><span class="hl-code">;
      </span><span class="hl-comment">//</span><span class="hl-comment"> 计算所有元素的总和</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">total</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">size</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">total</span><span class="hl-code"> += </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">总和为： </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">total</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例输出结果为：</p>&#13;
<pre>&#13;
总和为： 11367.373&#13;
</pre>&#13;
<p>下面的图片描绘了数组 myList。这里 myList 数组里有 10 个 double 元素，它的下标从 0 到 9。</p>&#13;
<p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2013/12/12-130Q0221Q5602.jpg" alt="java数组结构说明"/></p><hr/>&#13;
<h2>处理数组</h2>&#13;
<p>数组的元素类型和数组的大小都是确定的，所以当处理数组元素时候，我们通常使用基本循环或者 For-Each 循环。</p>&#13;
<h3>示例</h3>&#13;
<p>&#13;
该实例完整地展示了如何创建、初始化和操纵数组：</p>&#13;
<div class="example">&#13;
<h2 class="example">TestArray.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">TestArray</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">myList</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-number">1</span><span class="hl-number">.9</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-number">.9</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-number">.4</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-number">.5</span><span class="hl-brackets">}</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 打印所有数组元素</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">myList</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment"> 计算所有元素的总和</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">total</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">;
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">myList</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">total</span><span class="hl-code"> += </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Total is </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">total</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-comment">//</span><span class="hl-comment"> 查找最大元素</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">max</span><span class="hl-code"> = </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">1</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">myList</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> &gt; </span><span class="hl-identifier">max</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">max</span><span class="hl-code"> = </span><span class="hl-identifier">myList</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Max is </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">max</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
1.9&#13;
2.9&#13;
3.4&#13;
3.5&#13;
Total is 11.7&#13;
Max is 3.5&#13;
</pre>&#13;
<hr/>&#13;
<h2>For-Each 循环</h2>&#13;
<p>JDK 1.5 引进了一种新的循环类型，被称为 For-Each 循环或者加强型循环，它能在不使用下标的情况下遍历数组。</p>&#13;
<p>语法格式如下：</p>&#13;
<pre>for(type element: array)&#13;
{&#13;
    System.out.println(element);&#13;
}</pre>&#13;
<h3>&#13;
实例</h3><p>&#13;
该实例用来显示数组 myList 中的所有元素：</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">TestArray.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">TestArray</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">double</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">myList</span><span class="hl-code"> = </span><span class="hl-brackets">{</span><span class="hl-number">1</span><span class="hl-number">.9</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-number">.9</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-number">.4</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-number">.5</span><span class="hl-brackets">}</span><span class="hl-code">;
 
      </span><span class="hl-comment">//</span><span class="hl-comment"> 打印所有数组元素</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">element</span><span class="hl-code">: </span><span class="hl-identifier">myList</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-identifier">element</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
1.9&#13;
2.9&#13;
3.4&#13;
3.5&#13;
</pre><hr/>&#13;
<h2>数组作为函数的参数</h2>&#13;
<p>数组可以作为参数传递给方法。</p><p>例如，下面的例子就是一个打印 int 数组中元素的方法:</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">printArray</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">array</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">array</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">array</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>下面例子调用 printArray 方法打印出 3，1，2，6，4 和 2：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">printArray</span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">{</span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">1</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">6</span><span class="hl-code">, </span><span class="hl-number">4</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-brackets">}</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div><hr/>&#13;
<h2>数组作为函数的返回值</h2>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">reverse</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">list</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">result</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-identifier">list</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-brackets">]</span><span class="hl-code">;
 
  </span><span class="hl-reserved">for</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">, </span><span class="hl-identifier">j</span><span class="hl-code"> = </span><span class="hl-identifier">result</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code"> - </span><span class="hl-number">1</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-identifier">list</span><span class="hl-code">.</span><span class="hl-identifier">length</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++, </span><span class="hl-identifier">j</span><span class="hl-code">--</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">result</span><span class="hl-brackets">[</span><span class="hl-identifier">j</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-identifier">list</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">result</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例中 result 数组作为函数的返回值。</p>&#13;
&#13;
<hr/>&#13;
<h2>多维数组</h2>&#13;
<p>多维数组可以看成是数组的数组，比如二维数组就是一个特殊的一维数组，其每一个元素都是一个一维数组，例如：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">str</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">4</span><span class="hl-brackets">]</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<h3>多维数组的动态初始化（以二维数组为例）</h3>&#13;
&#13;
<p>1. 直接为每一维分配空间，格式如下： </p> &#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">type</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">typeName</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">type</span><span class="hl-brackets">[</span><span class="hl-identifier">typeLength1</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-identifier">typeLength2</span><span class="hl-brackets">]</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>type 可以为基本数据类型和复合数据类型，typeLength1 和 typeLength2 必须为正整数，typeLength1 为行数，typeLength2 为列数。</p>&#13;
<p>例如：</p>  &#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>解析：</p>&#13;
<p>二维数组 a 可以看成一个两行三列的数组。</p>&#13;
<p>2. 从最高维开始，分别为每一维分配空间，例如：  &#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Good</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Luck</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">to</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">you</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-identifier">s</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>解析：  &#13;
</p><p>&#13;
<strong>s[0]=new String[2]</strong> 和 <strong>s[1]=new String[3]</strong> 是为最高维分配引用空间，也就是为最高维限制其能保存数据的最长的长度，然后再为其每个数组元素单独分配空间 <strong>s0=new String("Good")</strong> 等操作。&#13;
</p>&#13;
<h3>多维数组的引用（以二维数组为例）</h3>&#13;
<p>对二维数组中的每个元素，引用方式为 <strong>arrayName[index1][index2]</strong>，例如：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">num</span><span class="hl-brackets">[</span><span class="hl-number">1</span><span class="hl-brackets">]</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>Arrays 类</h2>&#13;
<p>&#13;
java.util.Arrays 类能方便地操作数组，它提供的所有方法都是静态的。</p><p>具有以下功能：</p>&#13;
<ul>&#13;
<li>给数组赋值：通过 fill 方法。</li>&#13;
<li>对数组排序：通过 sort 方法,按升序。</li>&#13;
<li>比较数组：通过 equals 方法比较数组中元素值是否相等。</li>&#13;
<li>查找数组元素：通过 binarySearch 方法能对排序好的数组进行二分查找法操作。</li>&#13;
</ul>&#13;
<p>具体说明请查看下表：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th style="width:76px;">&#13;
				序号</th>&#13;
			<th style="width:501px;">&#13;
				方法和说明</th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:76px;">&#13;
				1</td>&#13;
			<td style="width:501px;">&#13;
				<strong>public static int binarySearch(Object[] a, Object key)</strong><br/>&#13;
				用二分查找算法在给定数组中搜索给定值的对象(Byte,Int,double等)。数组在调用前必须排序好的。如果查找值包含在数组中，则返回搜索键的索引；否则返回 (-(<em>插入点</em>) - 1)。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:76px;">&#13;
				2</td>&#13;
			<td style="width:501px;">&#13;
				<strong>public static boolean equals(long[] a, long[] a2)</strong><br/>&#13;
				如果两个指定的 long 型数组彼此<em>相等</em>，则返回 true。如果两个数组包含相同数量的元素，并且两个数组中的所有相应元素对都是相等的，则认为这两个数组是相等的。换句话说，如果两个数组以相同顺序包含相同的元素，则两个数组是相等的。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:76px;">&#13;
				3</td>&#13;
			<td style="width:501px;">&#13;
				<strong>public static void fill(int[] a, int val)</strong><br/>&#13;
				将指定的 int 值分配给指定 int 型数组指定范围中的每个元素。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td style="width:76px;">&#13;
				4</td>&#13;
			<td style="width:501px;">&#13;
				<strong>public static void sort(Object[] a)</strong><br/>&#13;
				对指定对象数组根据其元素的自然顺序进行升序排列。同样的方法适用于所有的其他基本数据类型（Byte，short，Int等）。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
&#13;
&#13;
&#13;
<blockquote><h3>练习</h3>&#13;
<p><a href="https://c.runoob.com/quiz/5571" rel="noopener noreferrer" target="_blank">Java 数组测验</a></p></blockquote>&#13;
&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>