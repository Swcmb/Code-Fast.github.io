<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java switch case 语句
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java switch case 语句&#13;
</h1>&#13;
&#13;
<p>switch case 语句判断一个变量与一系列值中某个值是否相等，每个值称为一个分支。</p>&#13;
<h3>语法</h3>&#13;
<p>switch case 语句语法格式如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">switch</span><span class="hl-brackets">(</span><span class="hl-identifier">expression</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-identifier">value</span><span class="hl-code"> :
       </span><span class="hl-comment">//</span><span class="hl-comment">语句</span><span class="hl-comment"/><span class="hl-code">
       </span><span class="hl-reserved">break</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">可选</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-identifier">value</span><span class="hl-code"> :
       </span><span class="hl-comment">//</span><span class="hl-comment">语句</span><span class="hl-comment"/><span class="hl-code">
       </span><span class="hl-reserved">break</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">可选</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-comment">//</span><span class="hl-comment">你可以有任意数量的case语句</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-reserved">default</span><span class="hl-code"> : </span><span class="hl-comment">//</span><span class="hl-comment">可选</span><span class="hl-comment"/><span class="hl-code">
       </span><span class="hl-comment">//</span><span class="hl-comment">语句</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2018/09/java-switch-case-flow-diagram.jpeg"/></p>&#13;
<p>&#13;
switch case 语句有如下规则：</p>&#13;
<ul>&#13;
    <li><p>switch 语句中的变量类型可以是： byte、short、int 或者 char。从 Java SE 7 开始，switch 支持字符串 String 类型了，同时 case 标签必须为字符串常量或字面量。</p></li>&#13;
    <li><p>switch 语句可以拥有多个 case 语句。每个 case 后面跟一个要比较的值和冒号。</p></li>&#13;
    <li><p>case 语句中的值的数据类型必须与变量的数据类型相同，而且只能是常量或者字面常量。</p></li>&#13;
    <li><p>当变量的值与 case 语句的值相等时，那么 case 语句之后的语句开始执行，直到 break 语句出现才会跳出 switch 语句。</p></li>&#13;
    <li><p>当遇到 break 语句时，switch 语句终止。程序跳转到 switch 语句后面的语句执行。case 语句不必须要包含 break 语句。如果没有 break 语句出现，程序会继续执行下一条 case 语句，直到出现 break 语句。</p></li>&#13;
    <li><p>switch 语句可以包含一个 default 分支，该分支一般是 switch 语句的最后一个分支（可以在任何位置，但建议在最后一个）。default 在没有 case 语句的值和变量值相等的时候执行。default 分支不需要 break 语句。</p></li>&#13;
</ul>&#13;
&#13;
<p><strong>switch case 执行时，一定会先进行匹配，匹配成功返回当前 case 的值，再根据是否有 break，判断是否继续输出，或是跳出判断。</strong></p>&#13;
<h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">//</span><span class="hl-comment">char grade = args[0].charAt(0);</span><span class="hl-comment"/><span class="hl-code">
      </span><span class="hl-types">char</span><span class="hl-code"> </span><span class="hl-identifier">grade</span><span class="hl-code"> = </span><span class="hl-quotes">'</span><span class="hl-string">C</span><span class="hl-quotes">'</span><span class="hl-code">;
 
      </span><span class="hl-reserved">switch</span><span class="hl-brackets">(</span><span class="hl-identifier">grade</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">A</span><span class="hl-quotes">'</span><span class="hl-code"> :
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">优秀</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">; 
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">B</span><span class="hl-quotes">'</span><span class="hl-code"> :
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">C</span><span class="hl-quotes">'</span><span class="hl-code"> :
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">良好</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">D</span><span class="hl-quotes">'</span><span class="hl-code"> :
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">及格</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-quotes">'</span><span class="hl-string">F</span><span class="hl-quotes">'</span><span class="hl-code"> :
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你需要再努力努力</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
            </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-reserved">default</span><span class="hl-code"> :
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">未知等级</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">你的等级是 </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">grade</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码编译运行结果如下：</p>&#13;
<pre>&#13;
良好&#13;
你的等级是 C&#13;
</pre>&#13;
&#13;
&#13;
&#13;
<p>如果 case 语句块中没有 break 语句时，JVM 并不会顺序输出每一个 case 对应的返回值，而是继续匹配，匹配不成功则返回默认 case。</p>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">5</span><span class="hl-code">;
      </span><span class="hl-reserved">switch</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">0</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">default</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">default</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码编译运行结果如下：</p>&#13;
<pre>&#13;
default&#13;
</pre>&#13;
&#13;
<p>如果 case 语句块中没有 break 语句时，匹配成功后，从当前 case 开始，后续所有 case 的值都会输出。</p>&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">1</span><span class="hl-code">;
      </span><span class="hl-reserved">switch</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">0</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">default</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">default</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码编译运行结果如下：</p>&#13;
<pre>&#13;
1&#13;
2&#13;
default&#13;
</pre>&#13;
&#13;
<p>如果当前匹配成功的 case 语句块没有 break 语句，则从当前 case 开始，后续所有 case 的值都会输出，如果后续的 case 语句块有 break 语句则会跳出判断。</p>&#13;
&#13;
&#13;
<div class="example">&#13;
<h2 class="example">Test.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Test</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">1</span><span class="hl-code">;
      </span><span class="hl-reserved">switch</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">0</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">1</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">2</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">case</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">3</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">; </span><span class="hl-reserved">break</span><span class="hl-code">;
         </span><span class="hl-reserved">default</span><span class="hl-code">:
            </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">default</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码编译运行结果如下：</p>&#13;
<pre>&#13;
1&#13;
2&#13;
3&#13;
</pre>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>