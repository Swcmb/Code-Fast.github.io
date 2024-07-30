<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 序列化</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 序列化</h1>&#13;
&#13;
<p>Java 序列化是一种将对象转换为字节流的过程，以便可以将对象保存到磁盘上，将其传输到网络上，或者将其存储在内存中，以后再进行反序列化，将字节流重新转换为对象。</p>&#13;
<p>序列化在 Java 中是通过 <span class="marked">java.io.Serializable</span> 接口来实现的，该接口没有任何方法，只是一个标记接口，用于标识类可以被序列化。</p>&#13;
&#13;
<p>当你序列化对象时，你把它包装成一个特殊文件，可以保存、传输或存储。反序列化则是打开这个文件，读取序列化的数据，然后将其还原为对象，以便在程序中使用。</p>&#13;
&#13;
<p>序列化是一种用于保存、传输和还原对象的方法，它使得对象可以在不同的计算机之间移动和共享，这对于分布式系统、数据存储和跨平台通信非常有用。</p>&#13;
&#13;
<p>以下是 Java 序列化的基本概念和用法：</p>&#13;
&#13;
<p>实现 Serializable 接口： 要使一个类可序列化，需要让该类实现 java.io.Serializable 接口，这告诉 Java 编译器这个类可以被序列化，例如：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.Serializable</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> MyClass <span style="color: #000000; font-weight: bold;">implements</span> <span style="color: #003399;">Serializable</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #666666; font-style: italic;">// 类的成员和方法</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p><strong>序列化对象： </strong>使用 ObjectOutputStream 类来将对象序列化为字节流，以下是一个简单的实例：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
MyClass obj <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> MyClass<span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">try</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #003399;">FileOutputStream</span> fileOut <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileOutputStream</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"object.ser"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #003399;">ObjectOutputStream</span> out <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">ObjectOutputStream</span><span style="color: #009900;">(</span>fileOut<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    out.<span style="color: #006633;">writeObject</span><span style="color: #009900;">(</span>obj<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    out.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    fileOut.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">IOException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    e.<span style="color: #006633;">printStackTrace</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>上述代码将一个名为 "object.ser" 的文件中的 obj 对象序列化。</p>&#13;
&#13;
<p><strong>反序列化对象：</strong> 使用 ObjectInputStream 类来从字节流中反序列化对象，以下是一个简单的实例：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
MyClass obj <span style="color: #339933;">=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">try</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #003399;">FileInputStream</span> fileIn <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileInputStream</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"object.ser"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #003399;">ObjectInputStream</span> in <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">ObjectInputStream</span><span style="color: #009900;">(</span>fileIn<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    obj <span style="color: #339933;">=</span> <span style="color: #009900;">(</span>MyClass<span style="color: #009900;">)</span> in.<span style="color: #006633;">readObject</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    in.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    fileIn.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">IOException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    e.<span style="color: #006633;">printStackTrace</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">ClassNotFoundException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    e.<span style="color: #006633;">printStackTrace</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>上述代码从 "object.ser" 文件中读取字节流并将其反序列化为一个 MyClass 对象。</p>&#13;
&#13;
<p>类 ObjectInputStream 和 ObjectOutputStream 是高层次的数据流，它们包含反序列化和序列化对象的方法。&#13;
</p><p>ObjectOutputStream 类包含很多写方法来写各种数据类型，但是一个特别的方法例外：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">writeObject</span><span class="hl-brackets">(</span><span class="hl-identifier">Object</span><span class="hl-code"> </span><span class="hl-identifier">x</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span></div>&#13;
</div>&#13;
</div><p>&#13;
上面的方法序列化一个对象，并将它发送到输出流。相似的 ObjectInputStream 类包含如下反序列化一个对象的方法：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">final</span><span class="hl-code"> </span><span class="hl-identifier">Object</span><span class="hl-code"> </span><span class="hl-identifier">readObject</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">IOException</span><span class="hl-code">, 
                                 </span><span class="hl-identifier">ClassNotFoundException</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
该方法从流中取出下一个对象，并将对象反序列化。它的返回值为Object，因此，你需要将它转换成合适的数据类型。</p><h3>实例</h3><p>&#13;
为了演示序列化在 Java 中是怎样工作的，我将使用之前教程中提到的 Employee 类，假设我们定义了如下的 Employee 类，该类实现了Serializable 接口。</p>&#13;
<div class="example">&#13;
<h2 class="example">Employee.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-code"> </span><span class="hl-reserved">implements</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.</span><span class="hl-identifier">Serializable</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">name</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">address</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">transient</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">SSN</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">mailCheck</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Mailing a check to </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">name</span><span class="hl-code">
                           + </span><span class="hl-quotes">"</span><span class="hl-string"> </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">address</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div><p>&#13;
请注意，一个类的对象要想序列化成功，必须满足两个条件：</p><p>&#13;
该类必须实现 java.io.Serializable 接口。</p><p>&#13;
该类的所有属性必须是可序列化的。如果有一个属性不是可序列化的，则该属性必须注明是短暂的。</p><p>&#13;
如果你想知道一个 Java 标准类是否是可序列化的，请查看该类的文档。检验一个类的实例是否能序列化十分简单， 只需要查看该类有没有实现 java.io.Serializable接口。&#13;
</p>&#13;
<hr/>&#13;
<h2>&#13;
序列化对象&#13;
</h2><p>&#13;
ObjectOutputStream 类用来序列化一个对象，如下的 SerializeDemo 例子实例化了一个 Employee 对象，并将该对象序列化到一个文件中。</p><p>&#13;
该程序执行后，就创建了一个名为 employee.ser 文件。该程序没有任何输出，但是你可以通过代码研读来理解程序的作用。</p><p>&#13;
<b>注意：</b> 当序列化一个对象到文件时， 按照 Java 的标准约定是给文件一个 .ser 扩展名。</p>&#13;
<div class="example">&#13;
<h2 class="example">SerializeDemo.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">SerializeDemo</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">Employee</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">Employee</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">name</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Reyan Ali</span><span class="hl-quotes">"</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">address</span><span class="hl-code"> = </span><span class="hl-quotes">"</span><span class="hl-string">Phokka Kuan, Ambehta Peer</span><span class="hl-quotes">"</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">SSN</span><span class="hl-code"> = </span><span class="hl-number">11122333</span><span class="hl-code">;
      </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">number</span><span class="hl-code"> = </span><span class="hl-number">101</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">FileOutputStream</span><span class="hl-code"> </span><span class="hl-identifier">fileOut</span><span class="hl-code"> =
         </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileOutputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">/tmp/employee.ser</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">ObjectOutputStream</span><span class="hl-code"> </span><span class="hl-identifier">out</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">ObjectOutputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">fileOut</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">writeObject</span><span class="hl-brackets">(</span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">fileOut</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">printf</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Serialized data is saved in /tmp/employee.ser</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
          </span><span class="hl-identifier">i</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>&#13;
反序列化对象&#13;
</h2>&#13;
<p>&#13;
下面的 DeserializeDemo 程序实例了反序列化，/tmp/employee.ser 存储了 Employee 对象。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">DeserializeDemo.java 文件代码：</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">DeserializeDemo</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">Employee</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-reserved">null</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">FileInputStream</span><span class="hl-code"> </span><span class="hl-identifier">fileIn</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">/tmp/employee.ser</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">ObjectInputStream</span><span class="hl-code"> </span><span class="hl-identifier">in</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">ObjectInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">fileIn</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">e</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-identifier">Employee</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">in</span><span class="hl-code">.</span><span class="hl-identifier">readObject</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">in</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">fileIn</span><span class="hl-code">.</span><span class="hl-identifier">close</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">i</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">return</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">ClassNotFoundException</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Employee class not found</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">c</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-reserved">return</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Deserialized Employee...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Name: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">name</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Address: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">address</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">SSN: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">SSN</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Number: </span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上程序编译运行结果如下所示：</p>&#13;
<pre>&#13;
Deserialized Employee...&#13;
Name: Reyan Ali&#13;
Address:Phokka Kuan, Ambehta Peer&#13;
SSN: 0&#13;
Number:101&#13;
</pre>&#13;
<p>&#13;
这里要注意以下要点：</p><p>&#13;
readObject() 方法中的  try/catch代码块尝试捕获 ClassNotFoundException 异常。对于 JVM 可以反序列化对象，它必须是能够找到字节码的类。如果JVM在反序列化对象的过程中找不到该类，则抛出一个 ClassNotFoundException 异常。&#13;
</p><p>注意，readObject() 方法的返回值被转化成 Employee 引用。&#13;
</p><p>当对象被序列化时，属性 SSN 的值为 111222333，但是因为该属性是短暂的，该值没有被发送到输出流。所以反序列化后 Employee 对象的 SSN 属性为 0。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>