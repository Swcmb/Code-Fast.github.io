<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java Character 类</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java Character 类</h1>&#13;
<p>Character 类用于对单个字符进行操作。</p>&#13;
<p>Character 类在对象中包装一个基本类型 <strong>char</strong> 的值</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">ch</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">a</span><span class="hl-quotes">'</span><span class="hl-code">;
 
</span><span class="hl-comment">//</span><span class="hl-comment"> Unicode 字符表示形式</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">uniChar</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-special">\u</span><span class="hl-string">039A</span><span class="hl-quotes">'</span><span class="hl-code">; 
 
</span><span class="hl-comment">//</span><span class="hl-comment"> 字符数组</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">char</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">charArray</span><span class="hl-code"> =</span><span class="hl-brackets">{</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">a</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">b</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">c</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">d</span><span class="hl-quotes">'</span><span class="hl-code">, </span><span class="hl-quotes">'</span><span class="hl-string">e</span><span class="hl-quotes">'</span><span class="hl-code"> </span><span class="hl-brackets">}</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>然而，在实际开发过程中，我们经常会遇到需要使用对象，而不是内置数据类型的情况。为了解决这个问题，Java语言为内置数据类型char提供了包装类Character类。&#13;
</p><p>&#13;
Character类提供了一系列方法来操纵字符。你可以使用Character的构造方法创建一个Character类对象，例如：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-identifier">Character</span><span class="hl-code"> </span><span class="hl-identifier">ch</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Character</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">a</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
在某些情况下，Java编译器会自动创建一个Character对象。</p>&#13;
<p>例如，将一个char类型的参数传递给需要一个Character类型参数的方法时，那么编译器会自动地将char类型参数转换为Character对象。&#13;
这种特征称为装箱，反过来称为拆箱。&#13;
&#13;
</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">实例</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 原始字符 'a' 装箱到 Character 对象 ch 中</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-identifier">Character</span><span class="hl-code"> </span><span class="hl-identifier">ch</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">a</span><span class="hl-quotes">'</span><span class="hl-code">;
 
</span><span class="hl-comment">//</span><span class="hl-comment"> 原始字符 'x' 用 test 方法装箱</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-comment">//</span><span class="hl-comment"> 返回拆箱的值到 'c'</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-identifier">test</span><span class="hl-brackets">(</span><span class="hl-quotes">'</span><span class="hl-string">x</span><span class="hl-quotes">'</span><span class="hl-brackets">)</span><span class="hl-code">;</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>转义序列</h2>&#13;
<p>前面有反斜杠（\）的字符代表转义字符，它对编译器来说是有特殊含义的。&#13;
</p><p>下面列表展示了Java的转义序列：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				转义序列</th>&#13;
			<th>&#13;
				描述</th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\t</td>&#13;
			<td>&#13;
				在文中该处插入一个tab键</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\b</td>&#13;
			<td>&#13;
				在文中该处插入一个后退键</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\n</td>&#13;
			<td>&#13;
				在文中该处换行</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\r</td>&#13;
			<td>&#13;
				在文中该处插入回车</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\f</td>&#13;
			<td>&#13;
				在文中该处插入换页符</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\'</td>&#13;
			<td>&#13;
				在文中该处插入单引号</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\"</td>&#13;
			<td>&#13;
				在文中该处插入双引号</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				\\</td>&#13;
			<td>&#13;
				在文中该处插入反斜杠</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<h3>实例</h3>&#13;
<p>&#13;
当打印语句遇到一个转义序列时，编译器可以正确地对其进行解释。&#13;
</p>&#13;
<p>以下实例转义双引号并输出：</p>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">访问</span><span class="hl-special">\"</span><span class="hl-string">菜鸟教程!</span><span class="hl-special">\"</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：&#13;
</p>&#13;
<pre>&#13;
访问"菜鸟教程!"&#13;
</pre>&#13;
&#13;
<hr/>&#13;
<h2>Character 方法</h2>&#13;
<p>下面是Character类的方法：</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				序号</th>&#13;
			<th>&#13;
				方法与描述</th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<a href="character-isletter.html" target="_blank" rel="noopener">isLetter()</a><br/>&#13;
				是否是一个字母</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<a href="character-isdigit.html" target="_blank" rel="noopener">isDigit()</a><br/>&#13;
				是否是一个数字字符</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<a href="character-iswhitespace.html" target="_blank" rel="noopener">isWhitespace()</a><br/>&#13;
				是否是一个空白字符</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<a href="character-isuppercase.html" target="_blank" rel="noopener">isUpperCase()</a><br/>&#13;
				是否是大写字母</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<a href="character-islowercase.html" target="_blank" rel="noopener">isLowerCase()</a><br/>&#13;
				是否是小写字母</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				6</td>&#13;
			<td>&#13;
				<a href="character-touppercase.html" target="_blank" rel="noopener">toUpperCase()</a><br/>&#13;
				指定字母的大写形式</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				7</td>&#13;
			<td>&#13;
				<a href="character-tolowercase.html" target="_blank" rel="noopener">toLowerCase</a>()<br/>&#13;
				指定字母的小写形式</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				8</td>&#13;
			<td>&#13;
				<a href="character-tostring.html" target="_blank" rel="noopener">toString</a>()<br/>&#13;
				返回字符的字符串形式，字符串的长度仅为1</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>对于方法的完整列表，请参考的 <a href="https://www.runoob.com/manual/jdk11api/java.base/java/lang/Character.html" target="_blank" rel="noopener">java.lang.Character API</a> 规范。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>