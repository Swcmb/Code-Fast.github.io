<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 抽象类</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 抽象类</h1>&#13;
<hr/>&#13;
&#13;
<p>在面向对象的概念中，所有的对象都是通过类来描绘的，但是反过来，并不是所有的类都是用来描绘对象的，如果一个类中没有包含足够的信息来描绘一个具体的对象，这样的类就是抽象类。&#13;
</p>&#13;
<p>抽象类除了不能实例化对象之外，类的其它功能依然存在，成员变量、成员方法和构造方法的访问方式和普通类一样。</p>&#13;
<p>由于抽象类不能实例化对象，所以抽象类必须被继承，才能被使用。也是因为这个原因，通常在设计阶段决定要不要设计抽象类。</p>&#13;
<p>父类包含了子类集合的常见的方法，但是由于父类本身是抽象的，所以不能使用这些方法。</p>&#13;
<p>在 Java 中抽象类表示的是一种继承关系，一个类只能继承一个抽象类，而一个类却可以实现多个接口。</p>&#13;
<hr/><h2>抽象类</h2>&#13;
<p>在 Java 语言中使用 abstract class 来定义抽象类。如下实例：</p>&#13;
&#13;
<div class="example">&#13;
<h2 class="example">Employee.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment"> 文件名 : Employee.java </span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">, </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">, </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Constructing an Employee</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">name</span><span class="hl-code"> = </span><span class="hl-identifier">name</span><span class="hl-code">;
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">address</span><span class="hl-code"> = </span><span class="hl-identifier">address</span><span class="hl-code">;
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">number</span><span class="hl-code"> = </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">computePay</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
     </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Inside Employee computePay</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
     </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-number">.0</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Mailing a check to </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">name</span><span class="hl-code">
       + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">address</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">toString</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">address</span><span class="hl-code"> + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">getAddress</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setAddress</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">newAddress</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">address</span><span class="hl-code"> = </span><span class="hl-identifier">newAddress</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getNumber</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
     </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>注意到该 Employee 类没有什么不同，尽管该类是抽象类，但是它仍然有 3 个成员变量，7 个成员方法和 1 个构造方法。&#13;
现在如果你尝试如下的例子：</p>&#13;
<div class="example">&#13;
<h2 class="example">AbstractDemo.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment"> 文件名 : AbstractDemo.java </span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">AbstractDemo</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-comment">/*</span><span class="hl-comment"> 以下是不允许的，会引发错误 </span><span class="hl-comment">*/</span><span class="hl-code">
      </span><span class="hl-identifier">Employee</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">George W.</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Houston, TX</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-number">43</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-string"> Call mailCheck using Employee reference--</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当你尝试编译 AbstractDemo 类时，会产生如下错误：</p>&#13;
<pre>&#13;
Employee.java:46: Employee is abstract; cannot be instantiated&#13;
      Employee e = new Employee("George W.", "Houston, TX", 43);&#13;
                   ^&#13;
1 error&#13;
</pre>&#13;
<hr/>&#13;
<h2>继承抽象类</h2>&#13;
<p>我们可以通过以下方式继承 Employee 类的属性：</p>&#13;
<div class="example">&#13;
<h2 class="example">Salary.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment"> 文件名 : Salary.java </span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Salary</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">salary</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment">Annual salary</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">Salary</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">, </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">, </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">, </span><span class="hl-types">double</span><span class="hl-code">
      </span><span class="hl-identifier">salary</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-reserved">super</span><span class="hl-brackets">(</span><span class="hl-identifier">name</span><span class="hl-code">, </span><span class="hl-identifier">address</span><span class="hl-code">, </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">;
       </span><span class="hl-identifier">setSalary</span><span class="hl-brackets">(</span><span class="hl-identifier">salary</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Within mailCheck of Salary class </span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Mailing check to </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
       + </span><span class="hl-quotes">"</span><span class="hl-string"> with salary </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">salary</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getSalary</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">salary</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">setSalary</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">newSalary</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">newSalary</span><span class="hl-code"> &gt;= </span><span class="hl-number">0</span><span class="hl-number">.0</span><span class="hl-brackets">)</span><span class="hl-code">
       </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">salary</span><span class="hl-code"> = </span><span class="hl-identifier">newSalary</span><span class="hl-code">;
       </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">computePay</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Computing salary pay for </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">salary</span><span class="hl-code">/</span><span class="hl-number">52</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>尽管我们不能实例化一个 Employee 类的对象，但是如果我们实例化一个 Salary 类对象，该对象将从 Employee 类继承 7 个成员方法，且通过该方法可以设置或获取三个成员变量。</p>&#13;
<div class="example">&#13;
<h2 class="example">AbstractDemo.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment"> 文件名 : AbstractDemo.java </span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">AbstractDemo</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">Salary</span><span class="hl-code"> </span><span class="hl-identifier">s</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Salary</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Mohd Mohtashim</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Ambehta, UP</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-number">3</span><span class="hl-code">, </span><span class="hl-number">3600</span><span class="hl-number">.00</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">Employee</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Salary</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">John Adams</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-quotes">"</span><span class="hl-string">Boston, MA</span><span class="hl-quotes">"</span><span class="hl-code">, </span><span class="hl-number">2</span><span class="hl-code">, </span><span class="hl-number">2400</span><span class="hl-number">.00</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Call mailCheck using Salary reference --</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">s</span><span class="hl-code">.</span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
 
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-string"> Call mailCheck using Employee reference--</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上程序编译运行结果如下：</p>&#13;
<pre>&#13;
Constructing an Employee&#13;
Constructing an Employee&#13;
Call mailCheck using  Salary reference --&#13;
Within mailCheck of Salary class&#13;
Mailing check to Mohd Mohtashim with salary 3600.0&#13;
&#13;
Call mailCheck using Employee reference--&#13;
Within mailCheck of Salary class&#13;
Mailing check to John Adams with salary 2400.&#13;
</pre>&#13;
<hr/>&#13;
<h2>抽象方法</h2>&#13;
<p>&#13;
如果你想设计这样一个类，该类包含一个特别的成员方法，该方法的具体实现由它的子类确定，那么你可以在父类中声明该方法为抽象方法。</p><p> &#13;
Abstract 关键字同样可以用来声明抽象方法，抽象方法只包含一个方法名，而没有方法体。</p><p>&#13;
抽象方法没有定义，方法名后面直接跟一个分号，而不是花括号。</p>&#13;
&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">abstract</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">computePay</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   
   </span><span class="hl-comment">//</span><span class="hl-comment">其余代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>声明抽象方法会造成以下两个结果：</p>&#13;
<ul>&#13;
	<li value="23">&#13;
		如果一个类包含抽象方法，那么该类必须是抽象类。</li>&#13;
	<li value="23">&#13;
		任何子类必须重写父类的抽象方法，或者声明自身为抽象类。</li>&#13;
</ul>&#13;
<p>继承抽象方法的子类必须重写该方法。否则，该子类也必须声明为抽象类。最终，必须有子类实现该抽象方法，否则，从最初的父类到最终的子类都不能用来实例化对象。</p>&#13;
<p>如果Salary类继承了Employee类，那么它必须实现computePay()方法：</p>&#13;
<div class="example">&#13;
<h2 class="example">Salary.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">/*</span><span class="hl-comment"> 文件名 : Salary.java </span><span class="hl-comment">*/</span><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Salary</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">salary</span><span class="hl-code">; </span><span class="hl-comment">//</span><span class="hl-comment"> Annual salary</span><span class="hl-comment"/><span class="hl-code">
  
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">computePay</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Computing salary pay for </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">getName</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">salary</span><span class="hl-code">/</span><span class="hl-number">52</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-comment">//</span><span class="hl-comment">其余代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>抽象类总结规定</h2>&#13;
&#13;
<ul><li><p>&#13;
1. 抽象类不能被实例化(初学者很容易犯的错)，如果被实例化，就会报错，编译无法通过。只有抽象类的非抽象子类可以创建对象。</p></li><li><p>&#13;
2. 抽象类中不一定包含抽象方法，但是有抽象方法的类必定是抽象类。</p></li><li><p>  &#13;
3. 抽象类中的抽象方法只是声明，不包含方法体，就是不给出方法的具体实现也就是方法的具体功能。</p></li><li><p>&#13;
4. 构造方法，类方法（用 static 修饰的方法）不能声明为抽象方法。</p></li><li><p>&#13;
5. 抽象类的子类必须给出抽象类中的抽象方法的具体实现，除非该子类也是抽象类。</p></li></ul>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>