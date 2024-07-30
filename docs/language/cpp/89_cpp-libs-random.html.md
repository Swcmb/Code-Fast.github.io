<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <random></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 &lt;random&gt;</h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;random&gt;</code> 头文件提供了一组用于生成随机数的工具。这些工具对于模拟、游戏开发、加密算法等领域非常有用。</p>&#13;
&#13;
<p>在 C++ 中，随机数生成器（Random Number Generator, RNG）可以分为两大类：</p>&#13;
<ul>&#13;
<li><strong>伪随机数生成器</strong>：它们使用确定性算法生成看似随机的数列。这些数列在理论上是可预测的，但通常对于大多数应用来说足够随机。</li>&#13;
<li><strong>真随机数生成器</strong>：它们基于物理过程（如热噪声、放射性衰变等）生成随机数，但 C++ 标准库不直接提供这类生成器。</li>&#13;
</ul>&#13;
&#13;
<p>C++ <code>&lt;random&gt;</code> 库提供了多种伪随机数生成器，包括：</p>&#13;
<ul>&#13;
<li><code>std::mt19937</code>：基于 Mersenne Twister 算法的生成器，是默认的随机数生成器。</li>&#13;
<li><code>std::minstd_rand0</code> 和 <code>std::minstd_rand</code>：基于线性同余生成器的简化版本。</li>&#13;
<li><code>std::linear_congruential_engine</code>：线性同余生成器的通用模板。</li>&#13;
<li><code>std::subtract_with_carry_engine</code>：带借位的减法生成器。</li>&#13;
</ul>&#13;
<p>此外，还有多种分布类，用于生成特定分布的随机数，如均匀分布、正态分布等。</p>&#13;
<h3>语法</h3>&#13;
<p>使用 <code>&lt;random&gt;</code> 库的基本步骤如下：</p>&#13;
<ul>&#13;
<li>包含头文件 <code>&lt;random&gt;</code>。</li>&#13;
<li>创建一个随机数生成器对象。</li>&#13;
<li>使用分布类生成随机数。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>生成基本的随机数</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;random&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 创建一个基于 Mersenne Twister 的随机数生成器</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">mt19937</span> generator<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 生成一个随机数</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Random number: "</span> <span style="color: #000080;">&lt;&lt;</span> generator<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>Random number: 3499211612</pre>&#13;
<p><strong>注意：</strong>每次运行程序时，生成的随机数可能不同。</p>&#13;
&#13;
<h3>使用均匀分布</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;random&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 创建随机数生成器</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">mt19937</span> generator<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 创建一个均匀分布的随机数生成器，范围从 1 到 10</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">uniform_int_distribution</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">int</span><span style="color: #000080;">&gt;</span> distribution<span style="color: #008000;">(</span><span style="color: #0000dd;">1</span>, <span style="color: #0000dd;">10</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 生成并打印 5 个随机数</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Random number: "</span> <span style="color: #000080;">&lt;&lt;</span> distribution<span style="color: #008000;">(</span>generator<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
&#13;
<pre>Random number: 7&#13;
Random number: 10&#13;
Random number: 6&#13;
Random number: 2&#13;
Random number: 4</pre><p>&#13;
每次运行程序时，输出的随机数序列可能不同。</p>&#13;
&#13;
<h3>使用正态分布</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;random&gt;</span><br/>
<span style="color: #060;">#include &lt;iomanip&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    <span style="color: #666666;">// 创建随机数生成器</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">mt19937</span> generator<span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 创建一个正态分布的随机数生成器，均值为 0，标准差为 1</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">normal_distribution</span><span style="color: #000080;">&lt;</span><span style="color: #05a;">double</span><span style="color: #000080;">&gt;</span> distribution<span style="color: #008000;">(</span><span style="color:#800080;">0.0</span>, <span style="color:#800080;">1.0</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 设置输出格式，保留两位小数</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">fixed</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">setprecision</span><span style="color: #008000;">(</span><span style="color: #0000dd;">2</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #666666;">// 生成并打印 5 个随机数</span><br/>
    <span style="color: #05a;">for</span> <span style="color: #008000;">(</span><span style="color: #05a;">int</span> i <span style="color: #000080;">=</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span> i <span style="color: #000080;">&lt;</span> <span style="color: #0000dd;">5</span><span style="color: #008080;">;</span> <span style="color: #000040;">++</span>i<span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Random number: "</span> <span style="color: #000080;">&lt;&lt;</span> distribution<span style="color: #008000;">(</span>generator<span style="color: #008000;">)</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
&#13;
<pre>Random number: -0.15&#13;
Random number: 0.13&#13;
Random number: -1.87&#13;
Random number: 0.46&#13;
Random number: -0.21</pre>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>