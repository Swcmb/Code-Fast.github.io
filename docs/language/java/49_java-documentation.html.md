<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 文档注释
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 文档注释&#13;
</h1>&#13;
<p>&#13;
Java 支持三种注释方式：</p>&#13;
<ul>&#13;
<li>单行注释</li>&#13;
<li>&#13;
多行注释</li>&#13;
<li>&#13;
文档注释</li></ul>&#13;
&#13;
<p>前两种分别是 <span class="marked">//</span> 和 <span class="marked">/* */</span>，第三种被称作文档注释，它以  <span class="marked">/**</span> 开始，以 <span class="marked">*/</span> 结束。</p>&#13;
<p>前两种注释内容可以参考：<a href="/java/java-comments.html" rel="noopener" target="_blank">Java 注释</a></p>&#13;
&#13;
<p>&#13;
文档注释允许你在程序中嵌入关于程序的信息。</p><p>你可以使用 javadoc 工具软件来生成信息，并输出到 HTML 文件中。</p><p>&#13;
文档注释，使你更加方便的记录你的程序信息。</p><hr/>&#13;
<h2>&#13;
javadoc 标签</h2>&#13;
<p>&#13;
javadoc 工具软件识别以下标签：&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>标签</strong></th>&#13;
			<th style="text-align: center;">&#13;
				<strong>描述</strong></th>&#13;
			<th style="text-align: center;">&#13;
				<strong>示例</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@author</td>&#13;
			<td>&#13;
				标识一个类的作者</td>&#13;
			<td>&#13;
				@author description</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@deprecated</td>&#13;
			<td>&#13;
				指名一个过期的类或成员</td>&#13;
			<td>&#13;
				@deprecated description</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				{@docRoot}</td>&#13;
			<td>&#13;
				指明当前文档根目录的路径</td>&#13;
			<td>&#13;
				Directory Path</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@exception</td>&#13;
			<td>&#13;
				标志一个类抛出的异常</td>&#13;
			<td>&#13;
				@exception exception-name explanation</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				{@inheritDoc}</td>&#13;
			<td>&#13;
				从直接父类继承的注释</td>&#13;
			<td>&#13;
				Inherits a comment from the immediate surperclass.</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				{@link}</td>&#13;
			<td>&#13;
				插入一个到另一个主题的链接</td>&#13;
			<td>&#13;
				{@link name text}</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				{@linkplain}</td>&#13;
			<td>&#13;
				插入一个到另一个主题的链接，但是该链接显示纯文本字体</td>&#13;
			<td>&#13;
				Inserts an in-line link to another topic.</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@param</td>&#13;
			<td>&#13;
				说明一个方法的参数</td>&#13;
			<td>&#13;
				@param parameter-name explanation</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@return</td>&#13;
			<td>&#13;
				说明返回值类型</td>&#13;
			<td>&#13;
				@return explanation</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@see</td>&#13;
			<td>&#13;
				指定一个到另一个主题的链接</td>&#13;
			<td>&#13;
				@see anchor</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@serial</td>&#13;
			<td>&#13;
				说明一个序列化属性</td>&#13;
			<td>&#13;
				@serial description</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@serialData</td>&#13;
			<td>&#13;
				说明通过writeObject( ) 和 writeExternal( )方法写的数据</td>&#13;
			<td>&#13;
				@serialData description</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@serialField</td>&#13;
			<td>&#13;
				说明一个ObjectStreamField组件</td>&#13;
			<td>&#13;
				@serialField name type description</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@since</td>&#13;
			<td>&#13;
				标记当引入一个特定的变化时</td>&#13;
			<td>&#13;
				@since release</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@throws</td>&#13;
			<td>&#13;
				和 @exception标签一样.</td>&#13;
			<td>&#13;
				The @throws tag has the same meaning as the @exception tag.</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				{@value}</td>&#13;
			<td>&#13;
				显示常量的值，该常量必须是static属性。</td>&#13;
			<td>&#13;
				Displays the value of a constant, which must be a static field.</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				@version</td>&#13;
			<td>&#13;
				指定类的版本</td>&#13;
			<td>&#13;
				@version info</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/><h2>文档注释</h2>&#13;
<p>&#13;
在开始的 <strong>/**</strong> 之后，第一行或几行是关于类、变量和方法的主要描述。</p><p>&#13;
之后，你可以包含一个或多个各种各样的 <strong>@</strong> 标签。每一个 <strong>@</strong> 标签必须在一个新行的开始或者在一行的开始紧跟星号 <span class="marked">*</span>。</p><p>&#13;
多个相同类型的标签应该放成一组。例如，如果你有三个 <strong>@see</strong> 标签，可以将它们一个接一个的放在一起。</p><p>&#13;
下面是一个类的稳定注释的实例：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment">** 这个类绘制一个条形图
*</span><span class="hl-inlinedoc"> @author </span><span class="hl-comment">runoob
*</span><span class="hl-inlinedoc"> @version </span><span class="hl-comment">1.2
</span><span class="hl-comment">*/</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/><h2>&#13;
javadoc 输出什么</h2>&#13;
<p>&#13;
&#13;
javadoc 工具将你 Java 程序的源代码作为输入，输出一些包含你程序注释的HTML文件。</p><p>&#13;
每一个类的信息将在独自的HTML文件里。javadoc 也可以输出继承的树形结构和索引。</p><p>&#13;
由于 javadoc 的实现不同，工作也可能不同，你需要检查你的 Java 开发系统的版本等细节，选择合适的 Javadoc 版本。</p>&#13;
<h3>&#13;
实例</h3>&#13;
<p>&#13;
下面是一个使用说明注释的简单实例。注意每一个注释都在它描述的项目的前面。</p><p>&#13;
在经过 javadoc 处理之后，SquareNum 类的注释将在 SquareNum.html 中找到。</p>&#13;
<div class="example">&#13;
<h2 class="example">SquareNum.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-comment">/*</span><span class="hl-comment">*
* 这个类演示了文档注释
*</span><span class="hl-inlinedoc"> @author </span><span class="hl-comment">Ayan Amhed
*</span><span class="hl-inlinedoc"> @version </span><span class="hl-comment">1.2
</span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SquareNum</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">/*</span><span class="hl-comment">*
   * This method returns the square of num.
   * This is a multiline description. You can use
   * as many lines as you like.
   *</span><span class="hl-inlinedoc"> @param </span><span class="hl-comment">num The value to be squared.
   *</span><span class="hl-inlinedoc"> @return </span><span class="hl-comment">num squared.
   </span><span class="hl-comment">*/</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">square</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code"> * </span><span class="hl-identifier">num</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-comment">/*</span><span class="hl-comment">*
   * This method inputs a number from the user.
   *</span><span class="hl-inlinedoc"> @return </span><span class="hl-comment">The value input as a double.
   *</span><span class="hl-inlinedoc"> @exception </span><span class="hl-comment">IOException On input error.
   *</span><span class="hl-inlinedoc"> @see </span><span class="hl-comment">IOException
   </span><span class="hl-comment">*/</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getNumber</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">InputStreamReader</span><span class="hl-code"> </span><span class="hl-identifier">isr</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InputStreamReader</span><span class="hl-brackets">(</span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">in</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">BufferedReader</span><span class="hl-code"> </span><span class="hl-identifier">inData</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">BufferedReader</span><span class="hl-brackets">(</span><span class="hl-identifier">isr</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">str</span><span class="hl-code">;
      </span><span class="hl-identifier">str</span><span class="hl-code"> = </span><span class="hl-identifier">inData</span><span class="hl-code">.</span><span class="hl-identifier">readLine</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Double</span><span class="hl-brackets">(</span><span class="hl-identifier">str</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">.</span><span class="hl-identifier">doubleValue</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-comment">/*</span><span class="hl-comment">*
   * This method demonstrates square().
   *</span><span class="hl-inlinedoc"> @param </span><span class="hl-comment">args Unused.
   *</span><span class="hl-inlinedoc"> @return </span><span class="hl-comment">Nothing.
   *</span><span class="hl-inlinedoc"> @exception </span><span class="hl-comment">IOException On input error.
   *</span><span class="hl-inlinedoc"> @see </span><span class="hl-comment">IOException
   </span><span class="hl-comment">*/</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">SquareNum</span><span class="hl-code"> </span><span class="hl-identifier">ob</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">SquareNum</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">val</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Enter value to be squared: </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-identifier">ob</span><span class="hl-code">.</span><span class="hl-identifier">getNumber</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">val</span><span class="hl-code"> = </span><span class="hl-identifier">ob</span><span class="hl-code">.</span><span class="hl-identifier">square</span><span class="hl-brackets">(</span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Squared value is </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">val</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
如下，使用 javadoc 工具处理 SquareNum.java 文件：&#13;
</p>&#13;
<pre>&#13;
$ javadoc SquareNum.java&#13;
Loading source file SquareNum.java...&#13;
Constructing Javadoc information...&#13;
Standard Doclet version 1.5.0_13&#13;
Building tree for all the packages and classes...&#13;
Generating SquareNum.html...&#13;
SquareNum.java:39: warning - @return tag cannot be used\&#13;
                      in method with void return type.&#13;
Generating package-frame.html...&#13;
Generating package-summary.html...&#13;
Generating package-tree.html...&#13;
Generating constant-values.html...&#13;
Building index for all the packages and classes...&#13;
Generating overview-tree.html...&#13;
Generating index-all.html...&#13;
Generating deprecated-list.html...&#13;
Building index for all classes...&#13;
Generating allclasses-frame.html...&#13;
Generating allclasses-noframe.html...&#13;
Generating index.html...&#13;
Generating help-doc.html...&#13;
Generating stylesheet.css...&#13;
1 warning&#13;
$&#13;
</pre>&#13;
 			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>