<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 枚举(enum)</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 枚举(enum)</h1>&#13;
&#13;
<p>Java 枚举是一个特殊的类，一般表示一组常量，比如一年的 4 个季节，一年的 12 个月份，一个星期的 7 天，方向有东南西北等。</p>&#13;
<p>Java 枚举类使用 enum 关键字来定义，各个常量使用逗号 <span class="marked">,</span> 来分割。</p>&#13;
<p>例如定义一个颜色的枚举类。</p>&#13;
<pre>enum Color &#13;
{ &#13;
    RED, GREEN, BLUE; &#13;
} </pre>&#13;
<p>以上枚举类 Color 颜色常量有 RED, GREEN, BLUE，分别表示红色，绿色，蓝色。</p>&#13;
<p>使用实例：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
<span style="color: #009900;">{</span> <br/>
    RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
<span style="color: #009900;">}</span> <br/>
  <br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Test <br/>
<span style="color: #009900;">{</span> <br/>
    <span style="color: #666666; font-style: italic;">// 执行输出结果</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #003399;">Color</span> c1 <span style="color: #339933;">=</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">RED</span><span style="color: #339933;">;</span> <br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>c1<span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>执行以上代码输出结果为：</p>&#13;
<pre>RED</pre>&#13;
<h3>内部类中使用枚举</h3>&#13;
<p>枚举类也可以声明在内部类中：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Test <br/>
<span style="color: #009900;">{</span> <br/>
    <span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
  <br/>
    <span style="color: #666666; font-style: italic;">// 执行输出结果</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #003399;">Color</span> c1 <span style="color: #339933;">=</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">RED</span><span style="color: #339933;">;</span> <br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>c1<span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>执行以上代码输出结果为：</p>&#13;
<pre>RED</pre>&#13;
<p>每个枚举都是通过 Class 在内部实现的，且所有的枚举值都是 public static final 的。</p>&#13;
<p>以上的枚举类 Color 转化在内部类实现：</p>&#13;
&#13;
<pre>class Color&#13;
{&#13;
     public static final Color RED = new Color();&#13;
     public static final Color BLUE = new Color();&#13;
     public static final Color GREEN = new Color();&#13;
}</pre>&#13;
<h3>迭代枚举元素</h3>&#13;
<p>可以使用 for 语句来迭代枚举元素：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
<span style="color: #009900;">{</span> <br/>
    RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
<span style="color: #009900;">}</span> <br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> MyClass <span style="color: #009900;">{</span> <br/>
  <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span> <br/>
    <span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #003399;">Color</span> myVar <span style="color: #339933;">:</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">values</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
      <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>myVar<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #009900;">}</span><br/>
  <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>执行以上代码输出结果为：</p>&#13;
<pre>RED&#13;
GREEN&#13;
BLUE</pre>&#13;
<h3>在 switch 中使用枚举类</h3>&#13;
<p>枚举类常应用于 switch 语句中：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
<span style="color: #009900;">{</span> <br/>
    RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
<span style="color: #009900;">}</span> <br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> MyClass <span style="color: #009900;">{</span><br/>
  <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #003399;">Color</span> myVar <span style="color: #339933;">=</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">BLUE</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #000000; font-weight: bold;">switch</span><span style="color: #009900;">(</span>myVar<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
      <span style="color: #000000; font-weight: bold;">case</span> RED<span style="color: #339933;">:</span><br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"红色"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #000000; font-weight: bold;">break</span><span style="color: #339933;">;</span><br/>
      <span style="color: #000000; font-weight: bold;">case</span> GREEN<span style="color: #339933;">:</span><br/>
         <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"绿色"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #000000; font-weight: bold;">break</span><span style="color: #339933;">;</span><br/>
      <span style="color: #000000; font-weight: bold;">case</span> BLUE<span style="color: #339933;">:</span><br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"蓝色"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #000000; font-weight: bold;">break</span><span style="color: #339933;">;</span><br/>
    <span style="color: #009900;">}</span><br/>
  <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>执行以上代码输出结果为：</p>&#13;
<pre>蓝色</pre><h3>&#13;
values(), ordinal() 和 valueOf() 方法</h3>&#13;
<p>enum 定义的枚举类默认继承了 java.lang.Enum 类，并实现了 java.lang.Serializable 和 java.lang.Comparable 两个接口。</p>&#13;
<p>values(), ordinal() 和 valueOf() 方法位于 java.lang.Enum 类中：</p>&#13;
<ul><li>&#13;
values() 返回枚举类中所有的值。</li><li>&#13;
ordinal()方法可以找到每个枚举常量的索引，就像数组索引一样。</li><li>&#13;
valueOf()方法返回指定字符串值的枚举常量。</li></ul>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
<span style="color: #009900;">{</span> <br/>
    RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
<span style="color: #009900;">}</span> <br/>
  <br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Test <br/>
<span style="color: #009900;">{</span> <br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #666666; font-style: italic;">// 调用 values() </span><br/>
        <span style="color: #003399;">Color</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> arr <span style="color: #339933;">=</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">values</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
  <br/>
        <span style="color: #666666; font-style: italic;">// 迭代枚举</span><br/>
        <span style="color: #000000; font-weight: bold;">for</span> <span style="color: #009900;">(</span><span style="color: #003399;">Color</span> col <span style="color: #339933;">:</span> arr<span style="color: #009900;">)</span> <br/>
        <span style="color: #009900;">{</span> <br/>
            <span style="color: #666666; font-style: italic;">// 查看索引</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>col <span style="color: #339933;">+</span> <span style="color: #0000ff;">" at index "</span> <span style="color: #339933;">+</span> col.<span style="color: #006633;">ordinal</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
        <span style="color: #009900;">}</span> <br/>
  <br/>
        <span style="color: #666666; font-style: italic;">// 使用 valueOf() 返回枚举常量，不存在的会报错 IllegalArgumentException </span><br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #003399;">Color</span>.<span style="color: #006633;">valueOf</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"RED"</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
        <span style="color: #666666; font-style: italic;">// System.out.println(Color.valueOf("WHITE")); </span><br/>
    <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span> <br/>
</div></div>&#13;
<p>执行以上代码输出结果为：</p>&#13;
<pre>RED at index 0&#13;
GREEN at index 1&#13;
BLUE at index 2&#13;
RED</pre>&#13;
<h3>枚举类成员</h3><p>&#13;
枚举跟普通类一样可以用自己的变量、方法和构造函数，构造函数只能使用 private 访问修饰符，所以外部无法调用。</p><p>&#13;
枚举既可以包含具体方法，也可以包含抽象方法。 如果枚举类具有抽象方法，则枚举类的每个实例都必须实现它。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">enum</span> <span style="color: #003399;">Color</span> <br/>
<span style="color: #009900;">{</span> <br/>
    RED, GREEN, BLUE<span style="color: #339933;">;</span> <br/>
  <br/>
    <span style="color: #666666; font-style: italic;">// 构造函数</span><br/>
    <span style="color: #000000; font-weight: bold;">private</span> <span style="color: #003399;">Color</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Constructor called for : "</span> <span style="color: #339933;">+</span> <span style="color: #000000; font-weight: bold;">this</span>.<span style="color: #006633;">toString</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
  <br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> colorInfo<span style="color: #009900;">(</span><span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Universal Color"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span> <br/>
  <br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> Test <br/>
<span style="color: #009900;">{</span>     <br/>
    <span style="color: #666666; font-style: italic;">// 输出</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <br/>
    <span style="color: #009900;">{</span> <br/>
        <span style="color: #003399;">Color</span> c1 <span style="color: #339933;">=</span> <span style="color: #003399;">Color</span>.<span style="color: #006633;">RED</span><span style="color: #339933;">;</span> <br/>
        <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>c1<span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
        c1.<span style="color: #006633;">colorInfo</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
    <span style="color: #009900;">}</span> <br/>
<span style="color: #009900;">}</span> <br/>
</div></div>&#13;
<p>执行以上代码输出结果为：</p><pre>&#13;
Constructor called for : RED&#13;
Constructor called for : GREEN&#13;
Constructor called for : BLUE&#13;
RED&#13;
Universal Color</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>