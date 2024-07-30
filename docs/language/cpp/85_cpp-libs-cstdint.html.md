<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <cstdint></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;cstdint&gt;</code></h1>&#13;
&#13;
<p><code>&lt;cstdint&gt;</code> 是 C++11 引入的一个头文件，它定义了一组固定宽度的整数类型，这些类型在不同的平台上具有相同的大小和表示范围。</p>&#13;
<h3>为什么使用 <code>&lt;cstdint&gt;</code></h3>&#13;
<p>在 C++ 中，标准整数类型（如 <code>int</code>、<code>long</code> 等）的大小和表示范围依赖于编译器和平台。这可能导致在不同平台上编译的程序行为不一致。使用 <code>&lt;cstdint&gt;</code> 中定义的固定宽度整数类型可以避免这些问题，因为它们在所有平台上具有相同的大小和表示范围。</p>&#13;
<h3>定义和语法</h3>&#13;
<p><code>&lt;cstdint&gt;</code> 定义了以下整数类型：</p>&#13;
<ul>&#13;
<li><code>int8_t</code>：8位有符号整数</li>&#13;
<li><code>uint8_t</code>：8位无符号整数</li>&#13;
<li><code>int16_t</code>：16位有符号整数</li>&#13;
<li><code>uint16_t</code>：16位无符号整数</li>&#13;
<li><code>int32_t</code>：32位有符号整数</li>&#13;
<li><code>uint32_t</code>：32位无符号整数</li>&#13;
<li><code>int64_t</code>：64位有符号整数</li>&#13;
<li><code>uint64_t</code>：64位无符号整数</li>&#13;
</ul>&#13;
<p>此外，还定义了最大宽度的整数类型：</p>&#13;
<ul>&#13;
<li><code>intmax_t</code>：最大宽度的有符号整数</li>&#13;
<li><code>uintmax_t</code>：最大宽度的无符号整数</li>&#13;
</ul>&#13;
<p>以及用于位操作的类型：</p>&#13;
<ul>&#13;
<li><code>intptr_t</code>：足够大的有符号整数，可以存储指针的值</li>&#13;
<li><code>uintptr_t</code>：足够大的无符号整数，可以存储指针的值</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<p>下面是一个使用 <code>&lt;cstdint&gt;</code> 的简单示例，展示了如何声明和使用这些类型。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 声明固定宽度的整数类型</span><br/>
    <span style="color: #05a;">int8_t</span> a <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">128</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 最小值</span><br/>
    <span style="color: #05a;">uint8_t</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">255</span><span style="color: #008080;">;</span> <span style="color: #666666;">// 最大值</span><br/>
    <span style="color: #05a;">int16_t</span> c <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">32768</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint16_t</span> d <span style="color: #000080;">=</span> <span style="color: #0000dd;">65535</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int32_t</span> e <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">2147483648</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint32_t</span> f <span style="color: #000080;">=</span> 4294967295U<span style="color: #008080;">;</span> <span style="color: #666666;">// 使用 U 后缀表示无符号常量</span><br/>
    <span style="color: #05a;">int64_t</span> g <span style="color: #000080;">=</span> <span style="color: #000040;">-</span>9223372036854775807LL<span style="color: #008080;">;</span> <span style="color: #666666;">// 使用 LL 后缀表示长长整型常量</span><br/>
    <span style="color: #05a;">uint64_t</span> h <span style="color: #000080;">=</span> 18446744073709551615ULL<span style="color: #008080;">;</span> <span style="color: #666666;">// 使用 ULL 后缀表示无符号长长整型常量</span><br/>
<br/>
    <span style="color: #666666;">// 输出结果</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"int8_t: "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>a<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"uint8_t: "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">unsigned</span> <span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>b<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"int16_t: "</span> <span style="color: #000080;">&lt;&lt;</span> c <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"uint16_t: "</span> <span style="color: #000080;">&lt;&lt;</span> d <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"int32_t: "</span> <span style="color: #000080;">&lt;&lt;</span> e <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"uint32_t: "</span> <span style="color: #000080;">&lt;&lt;</span> f <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"int64_t: "</span> <span style="color: #000080;">&lt;&lt;</span> g <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"uint64_t: "</span> <span style="color: #000080;">&lt;&lt;</span> h <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>int8_t: -128&#13;
uint8_t: 255&#13;
int16_t: -32768&#13;
uint16_t: 65535&#13;
int32_t: -2147483648&#13;
uint32_t: 4294967295&#13;
int64_t: -9223372036854775807&#13;
uint64_t: 18446744073709551615</pre>&#13;
<hr/>&#13;
&#13;
<h2>定宽整数类型</h2>&#13;
 <p>定宽整数类型确保了变量具有固定的宽度，这在需要精确控制数据大小和布局的情况下非常有用。它们的命名形式为 <code>intN_t</code> 和 <code>uintN_t</code>，其中 <code>N</code> 表示位宽。</p>&#13;
    <ul>&#13;
        <li><code>int8_t</code>, <code>int16_t</code>, <code>int32_t</code>, <code>int64_t</code>: 有符号定宽整数类型。</li>&#13;
        <li><code>uint8_t</code>, <code>uint16_t</code>, <code>uint32_t</code>, <code>uint64_t</code>: 无符号定宽整数类型。</li>&#13;
    </ul>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int8_t</span> a <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">128</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint8_t</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">255</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int32_t</span> c <span style="color: #000080;">=</span> <span style="color: #0000dd;">2147483647</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint64_t</span> d <span style="color: #000080;">=</span> 18446744073709551615U<span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"a = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>a<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"b = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">unsigned</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>b<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"c = "</span> <span style="color: #000080;">&lt;&lt;</span> c <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"d = "</span> <span style="color: #000080;">&lt;&lt;</span> d <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
  <h3>最小宽度整数类型</h3>&#13;
    <p>最小宽度整数类型确保了变量具有至少指定的位宽，这在需要最低位宽保证但不需要精确控制位宽的情况下非常有用。它们的命名形式为 <code>int_leastN_t</code> 和 <code>uint_leastN_t</code>。</p>&#13;
    <ul>&#13;
        <li><code>int_least8_t</code>, <code>int_least16_t</code>, <code>int_least32_t</code>, <code>int_least64_t</code>: 有符号最小宽度整数类型。</li>&#13;
        <li><code>uint_least8_t</code>, <code>uint_least16_t</code>, <code>uint_least32_t</code>, <code>uint_least64_t</code>: 无符号最小宽度整数类型。</li>&#13;
    </ul>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int_least8_t</span> a <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">128</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint_least8_t</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">255</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int_least32_t</span> c <span style="color: #000080;">=</span> <span style="color: #0000dd;">2147483647</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint_least64_t</span> d <span style="color: #000080;">=</span> 18446744073709551615U<span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"a = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>a<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"b = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">unsigned</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>b<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"c = "</span> <span style="color: #000080;">&lt;&lt;</span> c <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"d = "</span> <span style="color: #000080;">&lt;&lt;</span> d <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
 <h3>最快宽度整数类型</h3>&#13;
    <p>最快宽度整数类型确保了变量具有至少指定的位宽，并且在给定系统上尽可能快。它们的命名形式为 <code>int_fastN_t</code> 和 <code>uint_fastN_t</code>。</p>&#13;
    <ul>&#13;
        <li><code>int_fast8_t</code>, <code>int_fast16_t</code>, <code>int_fast32_t</code>, <code>int_fast64_t</code>: 有符号最快宽度整数类型。</li>&#13;
        <li><code>uint_fast8_t</code>, <code>uint_fast16_t</code>, <code>uint_fast32_t</code>, <code>uint_fast64_t</code>: 无符号最快宽度整数类型。</li>&#13;
    </ul>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">int_fast8_t</span> a <span style="color: #000080;">=</span> <span style="color: #000040;">-</span><span style="color: #0000dd;">128</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint_fast8_t</span> b <span style="color: #000080;">=</span> <span style="color: #0000dd;">255</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">int_fast32_t</span> c <span style="color: #000080;">=</span> <span style="color: #0000dd;">2147483647</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uint_fast64_t</span> d <span style="color: #000080;">=</span> 18446744073709551615U<span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"a = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>a<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"b = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">unsigned</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>b<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"c = "</span> <span style="color: #000080;">&lt;&lt;</span> c <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"d = "</span> <span style="color: #000080;">&lt;&lt;</span> d <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
   <h3>特殊类型</h3>&#13;
    <ul>&#13;
        <li><code>intmax_t</code>: 能够表示的最大有符号整数类型。</li>&#13;
        <li><code>uintmax_t</code>: 能够表示的最大无符号整数类型。</li>&#13;
        <li><code>intptr_t</code>: 足够大的有符号整数类型，用于存储指针。</li>&#13;
        <li><code>uintptr_t</code>: 足够大的无符号整数类型，用于存储指针。</li>&#13;
    </ul>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #05a;">intmax_t</span> max_int <span style="color: #000080;">=</span> INTMAX_MAX<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uintmax_t</span> max_uint <span style="color: #000080;">=</span> UINTMAX_MAX<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">intptr_t</span> ptr_int <span style="color: #000080;">=</span> <span style="color: #05a;">reinterpret_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">intptr_t</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span><span style="color: #000040;">&amp;</span>max_int<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">uintptr_t</span> ptr_uint <span style="color: #000080;">=</span> <span style="color: #05a;">reinterpret_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">uintptr_t</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span><span style="color: #000040;">&amp;</span>max_uint<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"max_int = "</span> <span style="color: #000080;">&lt;&lt;</span> max_int <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"max_uint = "</span> <span style="color: #000080;">&lt;&lt;</span> max_uint <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"ptr_int = "</span> <span style="color: #000080;">&lt;&lt;</span> ptr_int <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"ptr_uint = "</span> <span style="color: #000080;">&lt;&lt;</span> ptr_uint <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
  <h3>边界值宏</h3>&#13;
    <p><code>&lt;cstdint&gt;</code> 还定义了一组宏，用于表示这些类型的边界值。</p>&#13;
    <ul>&#13;
        <li><code>INT8_MIN</code>, <code>INT8_MAX</code>, <code>UINT8_MAX</code></li>&#13;
        <li><code>INT16_MIN</code>, <code>INT16_MAX</code>, <code>UINT16_MAX</code></li>&#13;
        <li><code>INT32_MIN</code>, <code>INT32_MAX</code>, <code>UINT32_MAX</code></li>&#13;
        <li><code>INT64_MIN</code>, <code>INT64_MAX</code>, <code>UINT64_MAX</code></li>&#13;
    </ul>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;cstdint&gt;</span><br/>
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"INT8_MIN = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>INT8_MIN<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"INT8_MAX = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>INT8_MAX<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"UINT8_MAX = "</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #05a;">static_cast</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">unsigned</span><span style="color: #000080;">&gt;</span><span style="color: #008000;">(</span>UINT8_MAX<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"INT32_MIN = "</span> <span style="color: #000080;">&lt;&lt;</span> INT32_MIN <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"INT32_MAX = "</span> <span style="color: #000080;">&lt;&lt;</span> INT32_MAX <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"UINT32_MAX = "</span> <span style="color: #000080;">&lt;&lt;</span> UINT32_MAX <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p><code>&lt;cstdint&gt;</code> 提供了一组固定宽度的整数类型，这些类型在不同的平台上具有相同的大小和表示范围。使用这些类型可以提高代码的可移植性和可预测性。在编写跨平台的 C++ 程序时，推荐使用 <code>&lt;cstdint&gt;</code> 中定义的类型。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>