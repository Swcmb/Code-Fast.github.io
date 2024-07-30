<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 条件控制</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 条件控制</h1>&#13;
<p>Python 条件语句是通过一条或多条语句的执行结果（True 或者 False）来决定执行的代码块。</p><p>&#13;
可以通过下图来简单了解条件语句的执行过程:</p>&#13;
<p> <img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/if-condition.jpg"/> </p>&#13;
<p>代码执行过程：</p>&#13;
<p><img decoding="async" width="50%" src="https://static.jyshare.com/images/mix/python-if.webp"/></p>&#13;
<hr/>&#13;
<h2>if 语句</h2>&#13;
<p>Python中if语句的一般形式如下所示：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">condition_1</span><span class="hl-code">:
    </span><span class="hl-identifier">statement_block_1</span><span class="hl-code">
</span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">condition_2</span><span class="hl-code">:
    </span><span class="hl-identifier">statement_block_2</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
    </span><span class="hl-identifier">statement_block_3</span></div>&#13;
</div>&#13;
</div>&#13;
<ul><li>如果 "condition_1" 为 True 将执行 "statement_block_1" 块语句</li><li>如果 "condition_1" 为False，将判断 "condition_2"</li><li>如果"condition_2"&#13;
为 True 将执行 "statement_block_2" 块语句</li><li>如果 "condition_2" 为False，将执行"statement_block_3"块语句</li></ul>&#13;
&#13;
&#13;
<p>&#13;
Python 中用 <b>elif</b> 代替了 <b>else if</b>，所以if语句的关键字为：<b>if – elif – else</b>。&#13;
</p>&#13;
<p>&#13;
<strong>注意：</strong></p>&#13;
<ul><li>&#13;
1、每个条件后面要使用冒号 <span class="marked">:</span>，表示接下来是满足条件后要执行的语句块。</li><li>&#13;
2、使用缩进来划分语句块，相同缩进数的语句在一起组成一个语句块。</li><li>&#13;
3、在 Python 中没有 <span class="marked">switch...case</span> 语句，但在 Python3.10 版本添加了 <span class="marked">match...case</span>，功能也类似，详见下文。</li></ul>&#13;
<p>Gif 演示：</p>&#13;
<p><img decoding="async" width="50%" src="//www.runoob.com/wp-content/uploads/2014/05/006faQNTgw1f5wnm0mcxrg30ci07o47l.gif"/></p>&#13;
<h3>实例</h3>&#13;
<p>以下是一个简单的 if 实例：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">var1</span><span class="hl-code"> = </span><span class="hl-number">100</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">var1</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1 - if 表达式条件为 true</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">var1</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-identifier">var2</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">var2</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">2 - if 表达式条件为 true</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-identifier">var2</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Good bye!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>执行以上代码，输出结果为：</p>&#13;
<pre>&#13;
1 - if 表达式条件为 true&#13;
100&#13;
Good bye!&#13;
</pre>&#13;
<p>从结果可以看到由于变量 var2 为 0，所以对应的 if 内的语句没有执行。</p>&#13;
<p>以下实例演示了狗的年龄计算判断：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">age</span><span class="hl-code"> = </span><span class="hl-builtin">int</span><span class="hl-brackets">(</span><span class="hl-builtin">input</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">请输入你家狗狗的年龄: </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> &lt;= </span><span class="hl-number">0</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你是在逗我吧!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> == </span><span class="hl-number">1</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">相当于 14 岁的人。</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> == </span><span class="hl-number">2</span><span class="hl-code">:
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">相当于 22 岁的人。</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">age</span><span class="hl-code"> &gt; </span><span class="hl-number">2</span><span class="hl-code">:
    </span><span class="hl-identifier">human</span><span class="hl-code"> = </span><span class="hl-number">22</span><span class="hl-code"> + </span><span class="hl-brackets">(</span><span class="hl-identifier">age</span><span class="hl-code"> -</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-code">*</span><span class="hl-number">5</span><span class="hl-code">
    </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">对应人类年龄: </span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-identifier">human</span><span class="hl-brackets">)</span><span class="hl-code">
 
</span><span class="hl-comment">### 退出提示</span><span class="hl-code">
</span><span class="hl-builtin">input</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">点击 enter 键退出</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>将以上脚本保存在dog.py文件中，并执行该脚本：</p>&#13;
<pre>&#13;
$ python3 dog.py &#13;
请输入你家狗狗的年龄: 1&#13;
&#13;
相当于 14 岁的人。&#13;
点击 enter 键退出&#13;
</pre>&#13;
<p>&#13;
以下为if中常用的操作运算符:</p>&#13;
&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th>操作符</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr>&#13;
<td><code>&lt;</code></td>&#13;
<td>小于</td>&#13;
</tr>&#13;
<tr>&#13;
<td><code>&lt;=</code></td>&#13;
<td>小于或等于</td>&#13;
</tr>&#13;
<tr>&#13;
<td><code>&gt;</code></td>&#13;
<td>大于</td>&#13;
</tr>&#13;
<tr>&#13;
<td><code>&gt;=</code></td>&#13;
<td>大于或等于</td>&#13;
</tr>&#13;
<tr>&#13;
<td><code>==</code></td>&#13;
<td>等于，比较两个值是否相等</td>&#13;
</tr>&#13;
<tr>&#13;
<td><code>!=</code></td>&#13;
<td>不等于</td>&#13;
</tr>&#13;
</tbody></table>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-comment"># 程序演示了 == 操作符</span><span class="hl-code">
</span><span class="hl-comment"># 使用数字</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-number">5</span><span class="hl-code"> == </span><span class="hl-number">6</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-comment"># 使用变量</span><span class="hl-code">
</span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">
</span><span class="hl-identifier">y</span><span class="hl-code"> = </span><span class="hl-number">8</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-identifier">x</span><span class="hl-code"> == </span><span class="hl-identifier">y</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>&#13;
以上实例输出结果：&#13;
</p>&#13;
<pre>&#13;
False&#13;
False&#13;
</pre>&#13;
<p>high_low.py文件演示了数字的比较运算：</p>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">#!/usr/bin/python3 </span><span class="hl-code">
 
</span><span class="hl-comment"># 该实例演示了数字猜谜游戏</span><span class="hl-code">
</span><span class="hl-identifier">number</span><span class="hl-code"> = </span><span class="hl-number">7</span><span class="hl-code">
</span><span class="hl-identifier">guess</span><span class="hl-code"> = -</span><span class="hl-number">1</span><span class="hl-code">
</span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">数字猜谜游戏!</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">while</span><span class="hl-code"> </span><span class="hl-identifier">guess</span><span class="hl-code"> != </span><span class="hl-identifier">number</span><span class="hl-code">:
    </span><span class="hl-identifier">guess</span><span class="hl-code"> = </span><span class="hl-builtin">int</span><span class="hl-brackets">(</span><span class="hl-builtin">input</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">请输入你猜的数字：</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
 
    </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">guess</span><span class="hl-code"> == </span><span class="hl-identifier">number</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">恭喜，你猜对了！</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">guess</span><span class="hl-code"> &lt; </span><span class="hl-identifier">number</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">猜的数字小了...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">elif</span><span class="hl-code"> </span><span class="hl-identifier">guess</span><span class="hl-code"> &gt; </span><span class="hl-identifier">number</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">猜的数字大了...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>&#13;
执行以上脚本，实例输出结果如下：&#13;
</p>&#13;
<pre>&#13;
$ python3 high_low.py &#13;
数字猜谜游戏!&#13;
请输入你猜的数字：1&#13;
猜的数字小了...&#13;
请输入你猜的数字：9&#13;
猜的数字大了...&#13;
请输入你猜的数字：7&#13;
恭喜，你猜对了！&#13;
</pre>&#13;
&#13;
<hr/>&#13;
<h2>if 嵌套</h2>&#13;
<p>&#13;
在嵌套 if 语句中，可以把 if...elif...else 结构放在另外一个 if...elif...else 结构中。&#13;
</p>&#13;
<pre>&#13;
if 表达式1:&#13;
    语句&#13;
    if 表达式2:&#13;
        语句&#13;
    elif 表达式3:&#13;
        语句&#13;
    else:&#13;
        语句&#13;
elif 表达式4:&#13;
    语句&#13;
else:&#13;
    语句&#13;
</pre>&#13;
<div class="example">&#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment"># !/usr/bin/python3</span><span class="hl-code">
 
</span><span class="hl-identifier">num</span><span class="hl-code">=</span><span class="hl-builtin">int</span><span class="hl-brackets">(</span><span class="hl-builtin">input</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">输入一个数字：</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">%</span><span class="hl-number">2</span><span class="hl-code">==</span><span class="hl-number">0</span><span class="hl-code">:
    </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">%</span><span class="hl-number">3</span><span class="hl-code">==</span><span class="hl-number">0</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你输入的数字可以整除 2 和 3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">else</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你输入的数字可以整除 2，但不能整除 3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-reserved">else</span><span class="hl-code">:
    </span><span class="hl-reserved">if</span><span class="hl-code"> </span><span class="hl-identifier">num</span><span class="hl-code">%</span><span class="hl-number">3</span><span class="hl-code">==</span><span class="hl-number">0</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-code"> </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你输入的数字可以整除 3，但不能整除 2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">
    </span><span class="hl-reserved">else</span><span class="hl-code">:
        </span><span class="hl-identifier">print</span><span class="hl-code">  </span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你输入的数字不能整除 2 和 3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span></div>&#13;
</div>&#13;
</div>&#13;
&#13;
<p>将以上程序保存到 test_if.py  文件中，执行后输出结果为：</p>&#13;
<pre>&#13;
$ python3 test.py &#13;
输入一个数字：6&#13;
你输入的数字可以整除 2 和 3&#13;
</pre>&#13;
&#13;
<hr/>&#13;
<h2>match...case</h2>&#13;
<p>&#13;
Python 3.10 增加了<span class="marked"> match...case</span> 的条件判断，不需要再使用一连串的 <span class="marked">if-else</span> 来判断了。&#13;
</p>&#13;
<p>match 后的对象会依次与 case 后的内容进行匹配，如果匹配成功，则执行匹配到的表达式，否则直接跳过，<span class="marked">_</span> 可以匹配一切。</p>&#13;
<p>语法格式如下：</p>&#13;
<pre>match subject:&#13;
    case &lt;pattern_1&gt;:&#13;
        &lt;action_1&gt;&#13;
    case &lt;pattern_2&gt;:&#13;
        &lt;action_2&gt;&#13;
    case &lt;pattern_3&gt;:&#13;
        &lt;action_3&gt;&#13;
    case _:&#13;
        &lt;action_wildcard&gt;</pre><p>&#13;
<span class="marked">case _:</span> 类似于 C 和 Java 中的 <span class="marked">default:</span>，当其他 case 都无法匹配时，匹配这条，保证永远会匹配成功。</p>&#13;
&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<br/>
<span style="color: Green;font-weight:bold;">def</span> http_error<span style="color: Olive;">(</span>status<span style="color: Olive;">)</span>:<br/>
    match status:<br/>
        case <span style="color: Maroon;">400</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: #a11;">"Bad request"</span><br/>
        case <span style="color: Maroon;">404</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: #a11;">"Not found"</span><br/>
        case <span style="color: Maroon;">418</span>:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: #a11;">"I'm a teapot"</span><br/>
        case _:<br/>
            <span style="color: Green;font-weight:bold;">return</span> <span style="color: #a11;">"Something's wrong with the internet"</span><br/>
<br/>
mystatus<span style="color: Gray;">=</span><span style="color: Maroon;">400</span><br/>
<span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>http_error<span style="color: Olive;">(</span><span style="color: Maroon;">400</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上是一个输出 HTTP 状态码的实例，输出结果为：</p>&#13;
<pre>Bad request</pre><p>&#13;
一个 case 也可以设置多个匹配条件，条件使用 <span class="marked">｜</span> 隔开，例如：</p>&#13;
<pre>...&#13;
    case 401|403|404:&#13;
        return "Not allowed"</pre>&#13;
<p><span class="marked">match...case</span> 更多内容参考：<a href="https://www.runoob.com/python3/python-match-case.html" rel="noopener" target="_blank">Python match-case 语句</a>&#13;
</p>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>