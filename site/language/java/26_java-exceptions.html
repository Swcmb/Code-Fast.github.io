<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 异常处理</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 异常处理</h1>&#13;
&#13;
<p>在 Java 中，异常处理是一种重要的编程概念，用于处理程序执行过程中可能出现的错误或异常情况。</p>&#13;
<p>&#13;
异常是程序中的一些错误，但并不是所有的错误都是异常，并且错误有时候是可以避免的。&#13;
</p>&#13;
&#13;
<p>比如说，你的代码少了一个分号，那么运行出来结果是提示是错误 <span class="marked">java.lang.Error</span>，如果你用 <span class="marked">System.out.println(11/0)</span>，那么你是因为你用 <strong>0</strong> 做了除数，会抛出 <span class="marked">java.lang.ArithmeticException</span> 的异常。&#13;
 </p>&#13;
 <p>异常发生的原因有很多，通常包含以下几大类：</p>&#13;
 <ul>&#13;
	<li>用户输入了非法数据。</li>&#13;
	<li>要打开的文件不存在。</li>&#13;
	<li>网络通信时连接中断，或者JVM内存溢出。</li>&#13;
</ul>&#13;
<p>这些异常有的是因为用户错误引起，有的是程序错误引起的，还有其它一些是因为物理错误引起的。&#13;
</p><p>要理解 Java 异常处理是如何工作的，你需要掌握以下三种类型的异常：&#13;
</p><ul>&#13;
	<li><p><strong>检查性异常：</strong>最具代表的检查性异常是用户错误或问题引起的异常，这些异常在编译时强制要求程序员处理。例如要打开一个不存在文件时，一个异常就发生了，这些异常在编译时不能被简单地忽略。</p>&#13;
<p>&#13;
这类异常通常使用 <span class="marked">try-catch</span> 块来捕获并处理异常，或者在方法声明中使用 <span class="marked">throws</span> 子句声明方法可能抛出的异常。</p>&#13;
<pre>try {&#13;
    // 可能会抛出异常的代码&#13;
} catch (IOException e) {&#13;
    // 处理异常的代码&#13;
}</pre><p>或者：</p>&#13;
<pre>public void readFile() throws IOException {&#13;
    // 可能会抛出IOException的代码&#13;
}</pre>&#13;
&#13;
</li>&#13;
	<li><p><strong>运行时异常：</strong> 这些异常在编译时不强制要求处理，通常是由程序中的错误引起的，例如 NullPointerException、ArrayIndexOutOfBoundsException 等，这类异常可以选择处理，但并非强制要求。</p>&#13;
&#13;
<pre>try {&#13;
    // 可能会抛出异常的代码&#13;
} catch (NullPointerException e) {&#13;
    // 处理异常的代码&#13;
}</pre>&#13;
&#13;
</li>&#13;
	<li><p><strong>错误：</strong> 错误不是异常，而是脱离程序员控制的问题，错误在代码中通常被忽略。例如，当栈溢出时，一个错误就发生了，它们在编译也检查不到的。</p></li>&#13;
</ul>&#13;
&#13;
<p>&#13;
Java 提供了以下关键字和类来支持异常处理：</p>&#13;
<ul><li><strong>try</strong>：用于包裹可能会抛出异常的代码块。</li><li><strong>catch</strong>：用于捕获异常并处理异常的代码块。</li><li><strong>finally</strong>：用于包含无论是否发生异常都需要执行的代码块。</li><li><strong>throw</strong>：用于手动抛出异常。</li><li><strong>throws</strong>：用于在方法声明中指定方法可能抛出的异常。</li><li><strong>Exception</strong>类：是所有异常类的父类，它提供了一些方法来获取异常信息，如 <strong>getMessage()、printStackTrace()</strong> 等。</li></ul>&#13;
<hr/><h2>Exception 类的层次</h2>&#13;
&#13;
<p>所有的异常类是从 java.lang.Exception 类继承的子类。&#13;
</p><p>Exception 类是 Throwable 类的子类。除了Exception类外，Throwable还有一个子类Error 。&#13;
</p><p>Java 程序通常不捕获错误。错误一般发生在严重故障时，它们在Java程序处理的范畴之外。&#13;
</p><p>Error 用来指示运行时环境发生的错误。&#13;
</p><p>例如，JVM 内存溢出。一般地，程序不会从错误中恢复。&#13;
</p><p>异常类有两个主要的子类：IOException 类和 RuntimeException 类。</p>&#13;
<p>&#13;
<img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/12/exception-hierarchy.png"/>&#13;
</p>&#13;
<p>&#13;
在 Java 内置类中(接下来会说明)，有大部分常用检查性和非检查性异常。&#13;
</p>&#13;
<hr/>&#13;
<h2>Java 内置异常类</h2>&#13;
<p>Java 语言定义了一些异常类在 java.lang 标准包中。&#13;
</p><p>标准运行时异常类的子类是最常见的异常类。由于 java.lang 包是默认加载到所有的 Java 程序的，所以大部分从运行时异常类继承而来的异常都可以直接使用。&#13;
</p><p>Java 根据各个类库也定义了一些其他的异常，下面的表中列出了 Java 的非检查性异常。&#13;
 </p>&#13;
 <table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>异常</strong></th>&#13;
			<th>&#13;
				<strong>描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				ArithmeticException</td>&#13;
			<td>&#13;
				当出现异常的运算条件时，抛出此异常。例如，一个整数"除以零"时，抛出此类的一个实例。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				ArrayIndexOutOfBoundsException</td>&#13;
			<td>&#13;
				用非法索引访问数组时抛出的异常。如果索引为负或大于等于数组大小，则该索引为非法索引。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				ArrayStoreException</td>&#13;
			<td>&#13;
				试图将错误类型的对象存储到一个对象数组时抛出的异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				ClassCastException</td>&#13;
			<td>&#13;
				当试图将对象强制转换为不是实例的子类时，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IllegalArgumentException</td>&#13;
			<td>&#13;
				抛出的异常表明向方法传递了一个不合法或不正确的参数。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IllegalMonitorStateException</td>&#13;
			<td>&#13;
				抛出的异常表明某一线程已经试图等待对象的监视器，或者试图通知其他正在等待对象的监视器而本身没有指定监视器的线程。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IllegalStateException</td>&#13;
			<td>&#13;
				在非法或不适当的时间调用方法时产生的信号。换句话说，即 Java 环境或 Java 应用程序没有处于请求操作所要求的适当状态下。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IllegalThreadStateException</td>&#13;
			<td>&#13;
				线程没有处于请求操作所要求的适当状态时抛出的异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IndexOutOfBoundsException</td>&#13;
			<td>&#13;
				指示某排序索引（例如对数组、字符串或向量的排序）超出范围时抛出。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				NegativeArraySizeException</td>&#13;
			<td>&#13;
				如果应用程序试图创建大小为负的数组，则抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				NullPointerException</td>&#13;
			<td>&#13;
				当应用程序试图在需要对象的地方使用 <code>null</code> 时，抛出该异常</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				NumberFormatException</td>&#13;
			<td>&#13;
				当应用程序试图将字符串转换成一种数值类型，但该字符串不能转换为适当格式时，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				SecurityException</td>&#13;
			<td>&#13;
				由安全管理器抛出的异常，指示存在安全侵犯。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				StringIndexOutOfBoundsException</td>&#13;
			<td>&#13;
				此异常由 <code>String</code> 方法抛出，指示索引或者为负，或者超出字符串的大小。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				UnsupportedOperationException</td>&#13;
			<td>&#13;
				当不支持请求的操作时，抛出该异常。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<p>下面的表中列出了 Java 定义在 java.lang 包中的检查性异常类。&#13;
</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>异常</strong></th>&#13;
			<th>&#13;
				<strong>描述</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				ClassNotFoundException</td>&#13;
			<td>&#13;
				应用程序试图加载类时，找不到相应的类，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				CloneNotSupportedException</td>&#13;
			<td>&#13;
				当调用 <code>Object</code> 类中的 <code>clone</code> 方法克隆对象，但该对象的类无法实现 <code>Cloneable</code> 接口时，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				IllegalAccessException</td>&#13;
			<td>&#13;
				拒绝访问一个类的时候，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				InstantiationException</td>&#13;
			<td>&#13;
				当试图使用 <code>Class</code> 类中的 <code>newInstance</code> 方法创建一个类的实例，而指定的类对象因为是一个接口或是一个抽象类而无法实例化时，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				InterruptedException</td>&#13;
			<td>&#13;
				一个线程被另一个线程中断，抛出该异常。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				NoSuchFieldException</td>&#13;
			<td>&#13;
				请求的变量不存在</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				NoSuchMethodException</td>&#13;
			<td>&#13;
				请求的方法不存在</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/>&#13;
<h2>&#13;
异常方法&#13;
</h2>&#13;
<p>&#13;
&#13;
下面的列表是 Throwable 类的主要方法:</p>&#13;
<table class="reference">&#13;
	<tbody>&#13;
		<tr>&#13;
			<th>&#13;
				<strong>序号</strong></th>&#13;
			<th>&#13;
				<strong>方法及说明</strong></th>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				1</td>&#13;
			<td>&#13;
				<strong>public String getMessage()</strong><br/>&#13;
				返回关于发生的异常的详细信息。这个消息在Throwable 类的构造函数中初始化了。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				2</td>&#13;
			<td>&#13;
				<strong>public Throwable getCause()</strong><br/>&#13;
				返回一个 Throwable 对象代表异常原因。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				3</td>&#13;
			<td>&#13;
				<strong>public String toString()</strong><br/>&#13;
				返回此 Throwable 的简短描述。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				4</td>&#13;
			<td>&#13;
				<strong>public void printStackTrace()</strong><br/>&#13;
				将此 Throwable 及其回溯打印到标准错误流。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				5</td>&#13;
			<td>&#13;
				<strong>public StackTraceElement [] getStackTrace()</strong><br/>&#13;
				返回一个包含堆栈层次的数组。下标为0的元素代表栈顶，最后一个元素代表方法调用堆栈的栈底。</td>&#13;
		</tr>&#13;
		<tr>&#13;
			<td>&#13;
				6</td>&#13;
			<td>&#13;
				<strong>public Throwable fillInStackTrace()</strong><br/>&#13;
				用当前的调用栈层次填充Throwable 对象栈层次，添加到栈层次任何先前信息中。</td>&#13;
		</tr>&#13;
	</tbody>&#13;
</table>&#13;
<hr/>&#13;
<h2>&#13;
捕获异常</h2>&#13;
<p>&#13;
&#13;
使用 try 和 catch 关键字可以捕获异常。try/catch 代码块放在异常可能发生的地方。&#13;
</p><p>try/catch代码块中的代码称为保护代码，使用 try/catch 的语法如下：&#13;
</p>&#13;
<pre>&#13;
try&#13;
{&#13;
   // 程序代码&#13;
}catch(ExceptionName e1)&#13;
{&#13;
   //Catch 块&#13;
}&#13;
</pre>&#13;
<p>Catch 语句包含要捕获异常类型的声明。当保护代码块中发生一个异常时，try 后面的 catch 块就会被检查。&#13;
</p><p>如果发生的异常包含在 catch 块中，异常会被传递到该 catch 块，这和传递一个参数的方法是一样。&#13;
</p><h3>实例</h3>&#13;
<p>下面的例子中声明有两个元素的一个数组，当代码试图访问数组的第四个元素的时候就会抛出一个异常。</p>&#13;
<div class="example">&#13;
<h2 class="example">ExcepTest.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名 : ExcepTest.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">ExcepTest</span><span class="hl-brackets">{</span><span class="hl-code">
 
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Access element three :</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">ArrayIndexOutOfBoundsException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Exception thrown  :</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Out of the block</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上代码编译运行输出结果如下：</p>&#13;
<pre>&#13;
Exception thrown  :java.lang.ArrayIndexOutOfBoundsException: 3&#13;
Out of the block&#13;
</pre>&#13;
<hr/><h2>多重捕获块</h2>&#13;
<p>&#13;
一个 try 代码块后面跟随多个 catch 代码块的情况就叫多重捕获。&#13;
</p><p>多重捕获块的语法如下所示：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-code">异常类型</span><span class="hl-number">1</span><span class="hl-code"> 异常的变量名</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-code">异常类型</span><span class="hl-number">2</span><span class="hl-code"> 异常的变量名</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-code">异常类型</span><span class="hl-number">3</span><span class="hl-code"> 异常的变量名</span><span class="hl-number">3</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>上面的代码段包含了 3 个 catch块。&#13;
</p><p>可以在 try 语句后面添加任意数量的 catch 块。&#13;
</p><p>如果保护代码中发生异常，异常被抛给第一个 catch 块。&#13;
</p><p>如果抛出异常的数据类型与 ExceptionType1 匹配，它在这里就会被捕获。&#13;
</p><p>如果不匹配，它会被传递给第二个 catch 块。&#13;
</p><p>如此，直到异常被捕获或者通过所有的 catch 块。</p>&#13;
<h3>实例</h3>&#13;
<p>&#13;
该实例展示了怎么使用多重 try/catch。&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">try</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">file</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">FileInputStream</span><span class="hl-brackets">(</span><span class="hl-identifier">fileName</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-identifier">x</span><span class="hl-code"> = </span><span class="hl-brackets">(</span><span class="hl-types">byte</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-identifier">file</span><span class="hl-code">.</span><span class="hl-identifier">read</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">FileNotFoundException</span><span class="hl-code"> </span><span class="hl-identifier">f</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code"> </span><span class="hl-comment">//</span><span class="hl-comment"> Not valid!</span><span class="hl-comment"/><span class="hl-code">
    </span><span class="hl-identifier">f</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-reserved">return</span><span class="hl-code"> -</span><span class="hl-number">1</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code"> </span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">IOException</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">i</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-reserved">return</span><span class="hl-code"> -</span><span class="hl-number">1</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>&#13;
throws/throw 关键字&#13;
</h2>&#13;
<p>在Java中， <span class="marked">throw</span> 和 <span class="marked">throws</span> 关键字是用于处理异常的。</p><p>&#13;
<span class="marked">throw</span> 关键字用于在代码中抛出异常，而 <span class="marked">throws</span> 关键字用于在方法声明中指定可能会抛出的异常类型。</p>&#13;
<h3>throw 关键字</h3>&#13;
<p><span class="marked">throw</span> 关键字用于在当前方法中抛出一个异常。</p><p>&#13;
通常情况下，当代码执行到某个条件下无法继续正常执行时，可以使用 <span class="marked">throw</span> 关键字抛出异常，以告知调用者当前代码的执行状态。</p>&#13;
<p>&#13;
例如，下面的代码中，在方法中判断 num 是否小于 0，如果是，则抛出一个 IllegalArgumentException 异常。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> checkNumber<span style="color: #009900;">(</span><span style="color: #000066; font-weight: bold;">int</span> num<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
  <span style="color: #000000; font-weight: bold;">if</span> <span style="color: #009900;">(</span>num <span style="color: #339933;">&lt;</span> <span style="color: #cc66cc;">0</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">throw</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">IllegalArgumentException</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Number must be positive"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
  <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<h3>throws 关键字 </h3><p>&#13;
<span class="marked">throws</span> 关键字用于在方法声明中指定该方法可能抛出的异常。当方法内部抛出指定类型的异常时，该异常会被传递给调用该方法的代码，并在该代码中处理异常。</p>&#13;
<p>&#13;
例如，下面的代码中，当 readFile 方法内部发生 IOException 异常时，会将该异常传递给调用该方法的代码。在调用该方法的代码中，必须捕获或声明处理 IOException 异常。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000066; font-weight: bold;">void</span> readFile<span style="color: #009900;">(</span><span style="color: #003399;">String</span> filePath<span style="color: #009900;">)</span> <span style="color: #000000; font-weight: bold;">throws</span> <span style="color: #003399;">IOException</span> <span style="color: #009900;">{</span><br/>
  <span style="color: #003399;">BufferedReader</span> reader <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">BufferedReader</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileReader</span><span style="color: #009900;">(</span>filePath<span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
  <span style="color: #003399;">String</span> line <span style="color: #339933;">=</span> reader.<span style="color: #006633;">readLine</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
  <span style="color: #000000; font-weight: bold;">while</span> <span style="color: #009900;">(</span>line <span style="color: #339933;">!=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span>line<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
    line <span style="color: #339933;">=</span> reader.<span style="color: #006633;">readLine</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
  <span style="color: #009900;">}</span><br/>
  reader.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
&#13;
<p>一个方法可以声明抛出多个异常，多个异常之间用逗号隔开。&#13;
</p><p>例如，下面的方法声明抛出 RemoteException 和 InsufficientFundsException：&#13;
</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">className</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">withdraw</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code"> </span><span class="hl-identifier">RemoteException</span><span class="hl-code">,
                              </span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-comment">//</span><span class="hl-comment"> Method implementation</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-comment">//</span><span class="hl-comment">Remainder of class definition</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<hr/>&#13;
<h2>&#13;
finally关键字&#13;
</h2>&#13;
<p>finally 关键字用来创建在 try 代码块后面执行的代码块。&#13;
</p><p>无论是否发生异常，finally 代码块中的代码总会被执行。&#13;
</p><p>在 finally 代码块中，可以运行清理类型等收尾善后性质的语句。&#13;
</p><p>finally 代码块出现在 catch 代码块最后，语法如下：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-code">异常类型</span><span class="hl-number">1</span><span class="hl-code"> 异常的变量名</span><span class="hl-number">1</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-code">异常类型</span><span class="hl-number">2</span><span class="hl-code"> 异常的变量名</span><span class="hl-number">2</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span><span class="hl-reserved">finally</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment"> 程序代码</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
 <h3>实例</h3>&#13;
<div class="example">&#13;
<h2 class="example">ExcepTest.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">ExcepTest</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-brackets">[</span><span class="hl-number">2</span><span class="hl-brackets">]</span><span class="hl-code">;
    </span><span class="hl-reserved">try</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Access element three :</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-number">3</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">ArrayIndexOutOfBoundsException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Exception thrown  :</span><span class="hl-quotes">"</span><span class="hl-code"> + </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-reserved">finally</span><span class="hl-brackets">{</span><span class="hl-code">
       </span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-code"> = </span><span class="hl-number">6</span><span class="hl-code">;
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">First element value: </span><span class="hl-quotes">"</span><span class="hl-code"> +</span><span class="hl-identifier">a</span><span class="hl-brackets">[</span><span class="hl-number">0</span><span class="hl-brackets">]</span><span class="hl-brackets">)</span><span class="hl-code">;
       </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">The finally statement is executed</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>以上实例编译运行结果如下：</p>&#13;
<pre>&#13;
Exception thrown  :java.lang.ArrayIndexOutOfBoundsException: 3&#13;
First element value: 6&#13;
The finally statement is executed&#13;
</pre>&#13;
<p>注意下面事项：</p>&#13;
<ul>&#13;
	<li>catch 不能独立于 try 存在。</li>&#13;
	<li>在 try/catch 后面添加 finally 块并非强制性要求的。</li>&#13;
	<li>try 代码后不能既没 catch 块也没 finally 块。</li>&#13;
	<li>try, catch, finally 块之间不能添加任何代码。</li>&#13;
</ul>&#13;
&#13;
<hr/>&#13;
<h2>try-with-resources</h2>&#13;
<p>&#13;
JDK7 之后，Java 新增的 <span class="marked">try-with-resource</span> 语法结构，旨在自动管理资源，确保资源在使用后能够及时关闭，避免资源泄露 。</p>&#13;
<p>try-with-resources 是一种异常处理机制，它能够自动关闭在 try 块中声明的资源，无需显式地在 finally 块中关闭。&#13;
&#13;
</p>&#13;
<p>在 try-with-resources 语句中，你只需要在 try 关键字后面声明资源，然后跟随一个代码块。无论代码块中的操作是否成功，资源都会在 try 代码块执行完毕后自动关闭。。</p>&#13;
&#13;
<pre>try (resource declaration) {&#13;
  // 使用的资源&#13;
} catch (ExceptionType e1) {&#13;
  // 异常块&#13;
}</pre>&#13;
<p>&#13;
以上的语法中 try 用于声明和实例化资源，catch 用于处理关闭资源时可能引发的所有异常。</p>&#13;
<p><strong>注意：</strong>try-with-resources 语句关闭所有实现 AutoCloseable 接口的资源。</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.*</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
<br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
    <span style="color: #003399;">String</span> line<span style="color: #339933;">;</span><br/>
        <span style="color: #000000; font-weight: bold;">try</span><span style="color: #009900;">(</span><span style="color: #003399;">BufferedReader</span> br <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">BufferedReader</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileReader</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"test.txt"</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #000000; font-weight: bold;">while</span> <span style="color: #009900;">(</span><span style="color: #009900;">(</span>line <span style="color: #339933;">=</span> br.<span style="color: #006633;">readLine</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #339933;">!=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
                <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Line =&gt;"</span><span style="color: #339933;">+</span>line<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #009900;">}</span><br/>
        <span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">IOException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"IOException in try block =&gt;"</span> <span style="color: #339933;">+</span> e.<span style="color: #006633;">getMessage</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #009900;">}</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>&#13;
以上实例输出结果为：</p><pre>&#13;
IOException in try block =&gt;test.txt (No such file or directory)</pre>&#13;
&#13;
&#13;
<p>以上实例中，我们实例一个 BufferedReader 对象从 test.txt 文件中读取数据。</p>&#13;
<p>&#13;
在 try-with-resources 语句中声明和实例化 BufferedReader 对象，执行完毕后实例资源，不需要考虑 try 语句是正常执行还是抛出异常。</p>&#13;
<p>&#13;
如果发生异常，可以使用 catch 来处理异常。</p><p>&#13;
再看下不使用 <strong>try-with-resources</strong> 而改成 <strong>finally</strong> 来关闭资源，整体代码量多了很多，而且更复杂繁琐了：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.*</span><span style="color: #339933;">;</span><br/>
<br/>
<span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
        <span style="color: #003399;">BufferedReader</span> br <span style="color: #339933;">=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #339933;">;</span><br/>
        <span style="color: #003399;">String</span> line<span style="color: #339933;">;</span><br/>
<br/>
        <span style="color: #000000; font-weight: bold;">try</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Entering try block"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            br <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">BufferedReader</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">FileReader</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"test.txt"</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #000000; font-weight: bold;">while</span> <span style="color: #009900;">(</span><span style="color: #009900;">(</span>line <span style="color: #339933;">=</span> br.<span style="color: #006633;">readLine</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #339933;">!=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Line =&gt;"</span><span style="color: #339933;">+</span>line<span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #009900;">}</span><br/>
        <span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">IOException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"IOException in try block =&gt;"</span> <span style="color: #339933;">+</span> e.<span style="color: #006633;">getMessage</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
        <span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">finally</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"Entering finally block"</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #000000; font-weight: bold;">try</span> <span style="color: #009900;">{</span><br/>
                <span style="color: #000000; font-weight: bold;">if</span> <span style="color: #009900;">(</span>br <span style="color: #339933;">!=</span> <span style="color: #000066; font-weight: bold;">null</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
                    br.<span style="color: #006633;">close</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
                <span style="color: #009900;">}</span><br/>
            <span style="color: #009900;">}</span> <span style="color: #000000; font-weight: bold;">catch</span> <span style="color: #009900;">(</span><span style="color: #003399;">IOException</span> e<span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
                <span style="color: #003399;">System</span>.<span style="color: #006633;">out</span>.<span style="color: #006633;">println</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"IOException in finally block =&gt;"</span><span style="color: #339933;">+</span>e.<span style="color: #006633;">getMessage</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #009900;">}</span><br/>
        <span style="color: #009900;">}</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
<p>&#13;
以上实例输出结果为：</p><pre>&#13;
Entering try block&#13;
IOException in try block =&gt;test.txt (No such file or directory)&#13;
Entering finally block</pre>&#13;
&#13;
<h3>&#13;
try-with-resources 处理多个资源</h3><p>&#13;
try-with-resources 语句中可以声明多个资源，方法是使用分号 <span class="marked">;</span> 分隔各个资源：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.io.*</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">import</span> <span style="color: #006699;">java.util.*</span><span style="color: #339933;">;</span><br/>
<span style="color: #000000; font-weight: bold;">class</span> RunoobTest <span style="color: #009900;">{</span><br/>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">static</span> <span style="color: #000066; font-weight: bold;">void</span> main<span style="color: #009900;">(</span><span style="color: #003399;">String</span><span style="color: #009900;">[</span><span style="color: #009900;">]</span> args<span style="color: #009900;">)</span> <span style="color: #000000; font-weight: bold;">throws</span> <span style="color: #003399;">IOException</span><span style="color: #009900;">{</span><br/>
        <span style="color: #000000; font-weight: bold;">try</span> <span style="color: #009900;">(</span>Scanner scanner <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> Scanner<span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">File</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"testRead.txt"</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span> <br/>
            <span style="color: #003399;">PrintWriter</span> writer <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">PrintWriter</span><span style="color: #009900;">(</span><span style="color: #000000; font-weight: bold;">new</span> <span style="color: #003399;">File</span><span style="color: #009900;">(</span><span style="color: #0000ff;">"testWrite.txt"</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
            <span style="color: #000000; font-weight: bold;">while</span> <span style="color: #009900;">(</span>scanner.<span style="color: #006633;">hasNext</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span> <span style="color: #009900;">{</span><br/>
                writer.<span style="color: #006633;">print</span><span style="color: #009900;">(</span>scanner.<span style="color: #006633;">nextLine</span><span style="color: #009900;">(</span><span style="color: #009900;">)</span><span style="color: #009900;">)</span><span style="color: #339933;">;</span><br/>
            <span style="color: #009900;">}</span><br/>
        <span style="color: #009900;">}</span><br/>
    <span style="color: #009900;">}</span><br/>
<span style="color: #009900;">}</span><br/>
</div></div>&#13;
&#13;
<p>&#13;
以上实例使用 Scanner 对象从 testRead.txt 文件中读取一行并将其写入新的 testWrite.txt 文件中。</p>&#13;
&#13;
<p>多个声明资源时，<span class="marked">try-with-resources</span> 语句以相反的顺序关闭这些资源。 在本例中，PrintWriter 对象先关闭，然后 Scanner 对象关闭。</p>&#13;
&#13;
<hr/>&#13;
<h2>声明自定义异常</h2>&#13;
&#13;
&#13;
&#13;
<p>在 Java 中你可以自定义异常。编写自己的异常类时需要记住下面的几点。<br/>&#13;
</p><ul>&#13;
	<li>所有异常都必须是 Throwable 的子类。</li>&#13;
	<li>如果希望写一个检查性异常类，则需要继承 Exception 类。</li>&#13;
	<li>如果你想写一个运行时异常类，那么需要继承 RuntimeException 类。</li>&#13;
</ul>&#13;
<p>可以像下面这样定义自己的异常类：</p>&#13;
<div class="example">&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">MyException</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Exception</span><span class="hl-brackets">{</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
只继承Exception 类来创建的异常类是检查性异常类。&#13;
</p><p>下面的 InsufficientFundsException 类是用户定义的异常类，它继承自 Exception。&#13;
</p><p>一个异常类和其它任何类一样，包含有变量和方法。&#13;
</p>&#13;
<h3>实例</h3>&#13;
<p>以下实例是一个银行账户的模拟，通过银行卡的号码完成识别，可以进行存钱和取钱的操作。</p>&#13;
<div class="example">&#13;
<h2 class="example">InsufficientFundsException.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名InsufficientFundsException.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-comment">//</span><span class="hl-comment">自定义异常类，继承Exception类</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-code"> </span><span class="hl-reserved">extends</span><span class="hl-code"> </span><span class="hl-identifier">Exception</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">此处的amount用来储存当出现异常（取出钱多于余额时）所缺乏的钱</span><span class="hl-comment"/><span class="hl-code">
  </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-code">;
  </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-brackets">)</span><span class="hl-code">
  </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">amount</span><span class="hl-code"> = </span><span class="hl-identifier">amount</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code"> 
  </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getAmount</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
  </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>为了展示如何使用我们自定义的异常类，&#13;
</p><p>在下面的 CheckingAccount 类中包含一个 withdraw() 方法抛出一个 InsufficientFundsException 异常。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">CheckingAccount.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment"> 文件名称 CheckingAccount.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">import</span><span class="hl-code"> </span><span class="hl-identifier">java</span><span class="hl-code">.</span><span class="hl-identifier">io</span><span class="hl-code">.*;
 
</span><span class="hl-comment">//</span><span class="hl-comment">此类模拟银行账户</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">CheckingAccount</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">balance为余额，number为卡号</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">balance</span><span class="hl-code">;
   </span><span class="hl-reserved">private</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-identifier">CheckingAccount</span><span class="hl-brackets">(</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">this</span><span class="hl-code">.</span><span class="hl-identifier">number</span><span class="hl-code"> = </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">方法：存钱</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">deposit</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">balance</span><span class="hl-code"> += </span><span class="hl-identifier">amount</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">方法：取钱</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">withdraw</span><span class="hl-brackets">(</span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">amount</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-reserved">throws</span><span class="hl-code">
                              </span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">if</span><span class="hl-brackets">(</span><span class="hl-identifier">amount</span><span class="hl-code"> &lt;= </span><span class="hl-identifier">balance</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">balance</span><span class="hl-code"> -= </span><span class="hl-identifier">amount</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
      </span><span class="hl-reserved">else</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">needs</span><span class="hl-code"> = </span><span class="hl-identifier">amount</span><span class="hl-code"> - </span><span class="hl-identifier">balance</span><span class="hl-code">;
         </span><span class="hl-reserved">throw</span><span class="hl-code"> </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-brackets">(</span><span class="hl-identifier">needs</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
   </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">方法：返回余额</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">double</span><span class="hl-code"> </span><span class="hl-identifier">getBalance</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">balance</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
  </span><span class="hl-comment">//</span><span class="hl-comment">方法：返回卡号</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">getNumber</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-identifier">number</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>&#13;
下面的 BankDemo 程序示范了如何调用 CheckingAccount 类的 deposit() 和 withdraw() 方法。&#13;
</p>&#13;
<div class="example">&#13;
<h2 class="example">BankDemo.java 文件代码：</h2> &#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-comment">//</span><span class="hl-comment">文件名称 BankDemo.java</span><span class="hl-comment"/><span class="hl-code">
</span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-reserved">class</span><span class="hl-code"> </span><span class="hl-identifier">BankDemo</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-reserved">public</span><span class="hl-code"> </span><span class="hl-types">static</span><span class="hl-code"> </span><span class="hl-types">void</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-identifier">String</span><span class="hl-code"> </span><span class="hl-brackets">[</span><span class="hl-brackets">]</span><span class="hl-code"> </span><span class="hl-identifier">args</span><span class="hl-brackets">)</span><span class="hl-code">
   </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">CheckingAccount</span><span class="hl-code"> </span><span class="hl-identifier">c</span><span class="hl-code"> = </span><span class="hl-reserved">new</span><span class="hl-code"> </span><span class="hl-identifier">CheckingAccount</span><span class="hl-brackets">(</span><span class="hl-number">101</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Depositing $500...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-identifier">c</span><span class="hl-code">.</span><span class="hl-identifier">deposit</span><span class="hl-brackets">(</span><span class="hl-number">500</span><span class="hl-number">.00</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-reserved">try</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-string">Withdrawing $100...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">c</span><span class="hl-code">.</span><span class="hl-identifier">withdraw</span><span class="hl-brackets">(</span><span class="hl-number">100</span><span class="hl-number">.00</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-special">\n</span><span class="hl-string">Withdrawing $600...</span><span class="hl-quotes">"</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">c</span><span class="hl-code">.</span><span class="hl-identifier">withdraw</span><span class="hl-brackets">(</span><span class="hl-number">600</span><span class="hl-number">.00</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-reserved">catch</span><span class="hl-brackets">(</span><span class="hl-identifier">InsufficientFundsException</span><span class="hl-code"> </span><span class="hl-identifier">e</span><span class="hl-brackets">)</span><span class="hl-code">
      </span><span class="hl-brackets">{</span><span class="hl-code">
         </span><span class="hl-identifier">System</span><span class="hl-code">.</span><span class="hl-identifier">out</span><span class="hl-code">.</span><span class="hl-identifier">println</span><span class="hl-brackets">(</span><span class="hl-quotes">"</span><span class="hl-string">Sorry, but you are short $</span><span class="hl-quotes">"</span><span class="hl-code">
                                  + </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">getAmount</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code">;
         </span><span class="hl-identifier">e</span><span class="hl-code">.</span><span class="hl-identifier">printStackTrace</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
      </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-brackets">}</span><span class="hl-code">
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>编译上面三个文件，并运行程序 BankDemo，得到结果如下所示：&#13;
</p>&#13;
<pre>&#13;
Depositing $500...&#13;
&#13;
Withdrawing $100...&#13;
&#13;
Withdrawing $600...&#13;
Sorry, but you are short $200.0&#13;
InsufficientFundsException&#13;
        at CheckingAccount.withdraw(CheckingAccount.java:25)&#13;
        at BankDemo.main(BankDemo.java:13)&#13;
</pre>&#13;
<hr/>&#13;
<h2>通用异常</h2>&#13;
<p>在Java中定义了两种类型的异常和错误。</p>&#13;
<ul>&#13;
	<li><strong>JVM(Java</strong><strong>虚拟机</strong><strong>)</strong><strong> 异常：</strong>由 JVM 抛出的异常或错误。例如：NullPointerException 类，ArrayIndexOutOfBoundsException 类，ClassCastException 类。</li>&#13;
	<li><strong>程序级异常：</strong>由程序或者API程序抛出的异常。例如 IllegalArgumentException 类，IllegalStateException 类。</li>&#13;
</ul><hr/>&#13;
<h2>&#13;
异常处理的最佳实践</h2>&#13;
&#13;
<ul><li>在合适的位置捕获异常，并对异常进行适当的处理，以确保程序的稳定性和可靠性。</li><li>避免过度捕获异常，应该尽量精确捕获特定类型的异常。</li><li>使用finally块来释放资源，例如关闭文件或数据库连接等，以确保资源的正确释放。</li><li>优先处理受检异常，避免将受检异常转换为非受检异常。</li></ul>&#13;
<p>异常处理是编写健壮的 Java 应用程序的重要组成部分，合理地处理异常可以提高程序的可维护性和可靠性。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>