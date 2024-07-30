<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <typeinfo></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;typeinfo&gt;</code></h1>&#13;
&#13;
<p>在 C++ 中，<code>&lt;typeinfo&gt;</code> 是标准库的一部分，它提供了运行时类型识别（RTTI，Run-Time Type Identification）功能。RTTI 允许程序在运行时确定对象的类型。这是通过使用 <code>typeid</code> 运算符和 <code>type_info</code> 类实现的。</p>&#13;
&#13;
<p><code>type_info</code> 类是一个抽象基类，它提供了关于类型信息的接口。每个类型都有一个与之关联的 <code>type_info</code> 对象，可以通过 <code>typeid</code> 运算符访问。</p>&#13;
<h2>语法</h2><p><code>&lt;typeinfo&gt;</code> 相关的主要语法：</p>&#13;
<ul>&#13;
<li><code>typeid</code> 运算符：用于获取对象的类型信息。</li>&#13;
<li><code>type_info</code> 类：包含类型信息的类。</li>&#13;
</ul>&#13;
&#13;
<h2>类型信息类 <code>type_info</code></h2>&#13;
&#13;
  <p><code>typeinfo</code> 头文件提供了对类型信息的运行时支持。它主要包含两个核心组件：<code>std::type_info</code> 类和 <code>typeid</code> 运算符。<code>typeinfo</code> 允许程序在运行时获取对象的类型信息，这在多态和类型安全的代码中非常有用。以下是对 <code>typeinfo</code> 的详细介绍：</p>&#13;
    <h3>std::type_info 类</h3>&#13;
    <p><code>std::type_info</code> 类是 <code>typeinfo</code> 头文件的核心类，用于描述一个类型。它提供了多个成员函数用于查询类型的信息。常用成员函数如下：</p>&#13;
    <ul>&#13;
        <li>&#13;
            <p><code>const char* name() const noexcept;</code>&#13;
                返回一个指向类型名称的 C 字符串指针。注意，这个名称不一定是人类可读的类型名，其格式由编译器实现决定。</p>&#13;
        </li>&#13;
        <li>&#13;
            <p><code>bool before(const std::type_info&amp; rhs) const noexcept;</code>&#13;
                按照某种顺序比较两个 <code>type_info</code> 对象，返回当前对象是否在 <code>rhs</code> 之前。</p>&#13;
        </li>&#13;
        <li>&#13;
            <p><code>bool operator==(const std::type_info&amp; rhs) const noexcept;</code>&#13;
                比较两个 <code>type_info</code> 对象是否表示相同的类型。</p>&#13;
        </li>&#13;
        <li>&#13;
            <p><code>bool operator!=(const std::type_info&amp; rhs) const noexcept;</code>&#13;
                比较两个 <code>type_info</code> 对象是否表示不同的类型。</p>&#13;
        </li>&#13;
    </ul>&#13;
    <h3>typeid 运算符</h3>&#13;
    <p><code>typeid</code> 运算符用于在运行时获取类型信息。<code>typeid</code> 可以作用于对象（带有多态行为的指针或引用）或类型（无需实例化对象）。</p>&#13;
    <ul>&#13;
        <li><code>typeid(object)</code>：返回一个 <code>std::type_info</code> 对象，表示 <code>object</code> 的动态类型。如果 <code>object</code> 是一个多态类型（即包含虚函数），则 <code>typeid</code> 会返回该对象的实际类型。</li>&#13;
        <li><code>typeid(T)</code>：返回一个 <code>std::type_info</code> 对象，表示类型 <code>T</code>。</li>&#13;
    </ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;typeinfo&gt;</code> 的简单示例：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;typeinfo&gt;</span><br/>
<br/>
<span style="color: #05a;">class</span> Base <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">virtual</span> <span style="color: #05a;">void</span> show<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span> std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Base show"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">class</span> Derived <span style="color: #008080;">:</span> <span style="color: #05a;">public</span> Base <span style="color: #008000;">{</span><br/>
<span style="color: #05a;">public</span><span style="color: #008080;">:</span><br/>
    <span style="color: #05a;">void</span> show<span style="color: #008000;">(</span><span style="color: #008000;">)</span> override <span style="color: #008000;">{</span> std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Derived show"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span> <span style="color: #008000;">}</span><br/>
<span style="color: #008000;">}</span><span style="color: #008080;">;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    Base<span style="color: #000040;">*</span> basePtr <span style="color: #000080;">=</span> <span style="color: #05a;">new</span> Derived<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    Base<span style="color: #000040;">*</span> basePtr2 <span style="color: #000080;">=</span> <span style="color: #05a;">new</span> Base<span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Type of basePtr: "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">typeid</span><span style="color: #008000;">(</span><span style="color: #000040;">*</span>basePtr<span style="color: #008000;">)</span>.<span style="color: #007788;">name</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Type of basePtr2: "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">typeid</span><span style="color: #008000;">(</span><span style="color: #000040;">*</span>basePtr2<span style="color: #008000;">)</span>.<span style="color: #007788;">name</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span><span style="color: #05a;">typeid</span><span style="color: #008000;">(</span><span style="color: #000040;">*</span>basePtr<span style="color: #008000;">)</span> <span style="color: #000080;">==</span> <span style="color: #05a;">typeid</span><span style="color: #008000;">(</span>Derived<span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"basePtr is of type Derived"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"basePtr is not of type Derived"</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">delete</span> basePtr<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">delete</span> basePtr2<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果:</p><pre>&#13;
Type of basePtr: 9Derived  // 注意：typeid的name()返回的类型名称可能因编译器而异&#13;
Type of basePtr2: 8Base     // 同上&#13;
basePtr is of type Derived</pre>&#13;
<h3>注意事项</h3>&#13;
<ul>&#13;
<li>RTTI 功能依赖于编译器的实现，因此 <code>typeid</code> 运算符返回的类型名称可能因编译器而异。</li>&#13;
<li>使用 RTTI 可能会对程序性能产生一定影响，因为它需要在运行时进行类型检查。</li>&#13;
<li>RTTI 只适用于多态类型，即具有虚函数的类。</li>&#13;
</ul>&#13;
&#13;
<p><code>&lt;typeinfo&gt;</code> 提供了一种在运行时识别对象类型的方法，这对于实现多态和类型安全非常有用。然而，开发者应该谨慎使用 RTTI，以避免不必要的性能开销和潜在的类型错误。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>