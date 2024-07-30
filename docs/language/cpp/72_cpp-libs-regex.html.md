<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库 <regex></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ 标准库 <code>&lt;regex&gt;</code></h1>&#13;
&#13;
<p>C++ 标准库中的 <code>&lt;regex&gt;</code> 头文件提供了正则表达式的功能，允许开发者使用一种非常灵活的方式来搜索、替换或分割字符串。正则表达式是一种强大的文本处理工具，广泛应用于数据验证、文本分析和模式匹配等领域。</p>&#13;
&#13;
<p>正则表达式是一种使用单个字符串来描述、匹配一系列符合某个句法规则的字符串的模式。在 C++ 中，正则表达式通过 <code>&lt;regex&gt;</code> 库实现。</p>&#13;
<h2>基本语法</h2>&#13;
<h3>正则表达式的基本组成</h3>&#13;
<ul>&#13;
<li><strong>字符类</strong>：如 <code>[abc]</code> 表示匹配 a、b 或 c 中的任意一个字符。</li>&#13;
<li><strong>量词</strong>：如 <code>*</code>（零次或多次）、<code>+</code>（一次或多次）、<code>?</code>（零次或一次）。</li>&#13;
<li><strong>边界匹配</strong>：如 <code>^</code>（行的开始）、<code>$</code>（行的结束）。</li>&#13;
<li><strong>分组</strong>：使用圆括号 <code>()</code> 来创建一个分组。</li>&#13;
</ul>&#13;
<h3>C++ <code>&lt;regex&gt;</code> 库的主要类和函数</h3>&#13;
<ul>&#13;
<li><code>std::regex</code>：表示一个正则表达式对象。</li>&#13;
<li><code>std::regex_match</code>：检查整个字符串是否与正则表达式匹配。</li>&#13;
<li><code>std::regex_search</code>：在字符串中搜索与正则表达式匹配的部分。</li>&#13;
<li><code>std::regex_replace</code>：替换字符串中与正则表达式匹配的部分。</li>&#13;
<li><code>std::sregex_iterator</code>：迭代器，用于遍历所有匹配项。</li>&#13;
</ul>&#13;
<h2>实例</h2>&#13;
<h3>1. 检查字符串是否匹配正则表达式</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;string&gt;</span><br/>
<span style="color: #060;">#include &lt;regex&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> text <span style="color: #000080;">=</span> <span style="color: #a11;">"Hello, World!"</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">regex</span> pattern<span style="color: #008000;">(</span><span style="color: #a11;">"^[a-zA-Z]+, [a-zA-Z]+!$"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">if</span> <span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">regex_match</span><span style="color: #008000;">(</span>text, pattern<span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"The string matches the pattern."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span> <span style="color: #05a;">else</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"The string does not match the pattern."</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p><pre>&#13;
&#13;
The string matches the pattern.</pre>&#13;
<h3>2. 在字符串中搜索匹配项</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;string&gt;</span><br/>
<span style="color: #060;">#include &lt;regex&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> text <span style="color: #000080;">=</span> <span style="color: #a11;">"123-456-7890 and 987-654-3210"</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">regex</span> pattern<span style="color: #008000;">(</span><span style="color: #a11;">"\d{3}-\d{3}-\d{4}"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">smatch</span> matches<span style="color: #008080;">;</span><br/>
    <span style="color: #05a;">while</span> <span style="color: #008000;">(</span>std<span style="color: #008080;">::</span><span style="color: #007788;">regex_search</span><span style="color: #008000;">(</span>text, matches, pattern<span style="color: #008000;">)</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
        std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Found: "</span> <span style="color: #000080;">&lt;&lt;</span> matches<span style="color: #008000;">[</span><span style="color: #0000dd;">0</span><span style="color: #008000;">]</span> <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
        text <span style="color: #000080;">=</span> matches.<span style="color: #007788;">suffix</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span>.<span style="color: #007788;">str</span><span style="color: #008000;">(</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    <span style="color: #008000;">}</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
<pre>&#13;
Found: 123-456-7890&#13;
Found: 987-654-3210</pre>&#13;
<h3>3. 替换字符串中的匹配项</h3>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;iostream&gt;</span><br/>
<span style="color: #060;">#include &lt;string&gt;</span><br/>
<span style="color: #060;">#include &lt;regex&gt;</span><br/>
<br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span> <span style="color: #008000;">{</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> text <span style="color: #000080;">=</span> <span style="color: #a11;">"Hello, World!"</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">regex</span> pattern<span style="color: #008000;">(</span><span style="color: #a11;">"World"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> replacement <span style="color: #000080;">=</span> <span style="color: #a11;">"Universe"</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #007788;">string</span> result <span style="color: #000080;">=</span> std<span style="color: #008080;">::</span><span style="color: #007788;">regex_replace</span><span style="color: #008000;">(</span>text, pattern, replacement<span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
<br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Original: "</span> <span style="color: #000080;">&lt;&lt;</span> text <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
    std<span style="color: #008080;">::</span><span style="color: #05a;">cout</span> <span style="color: #000080;">&lt;&lt;</span> <span style="color: #a11;">"Modified: "</span> <span style="color: #000080;">&lt;&lt;</span> result <span style="color: #000080;">&lt;&lt;</span> std<span style="color: #008080;">::</span><span style="color: #007788;">endl</span><span style="color: #008080;">;</span><br/>
<br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
<p>输出结果：</p>&#13;
&#13;
<pre>Original: Hello, World!&#13;
Modified: Hello, Universe!</pre>&#13;
&#13;
<p>C++ 的 <code>&lt;regex&gt;</code> 库为处理字符串提供了强大的工具。通过上述实例，我们可以看到如何使用正则表达式来匹配、搜索和替换字符串。掌握这些基本操作后，你可以更深入地探索正则表达式的高级用法，以解决更复杂的文本处理问题。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>