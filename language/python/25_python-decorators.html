<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python 装饰器</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python 装饰器</h1><p>&#13;
装饰器（decorators）是 Python 中的一种高级功能，它允许你动态地修改函数或类的行为。</p><p>&#13;
装饰器是一种函数，它接受一个函数作为参数，并返回一个新的函数或修改原来的函数。</p><p>&#13;
装饰器的语法使用 <span class="marked">@decorator_name</span> 来应用在函数或方法上。</p>&#13;
<p>Python 还提供了一些内置的装饰器，比如 <span class="marked">@staticmethod</span> 和 <span class="marked">@classmethod</span>，用于定义静态方法和类方法。</p><p><strong>装饰器的应用场景：</strong></p>&#13;
<ul><li><strong>日志记录</strong>: 装饰器可用于记录函数的调用信息、参数和返回值。</li><li><strong>性能分析</strong>: 可以使用装饰器来测量函数的执行时间。</li><li><strong>权限控制</strong>: 装饰器可用于限制对某些函数的访问权限。</li><li><strong>缓存</strong>: 装饰器可用于实现函数结果的缓存，以提高性能。</li></ul>&#13;
<h3>基本语法</h3><p>&#13;
Python 装饰允许在不修改原有函数代码的基础上，动态地增加或修改函数的功能，装饰器本质上是一个接收函数作为输入并返回一个新的包装过后的函数的对象。</p>&#13;
&#13;
<div class="example"><h2 class="example">语法</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">def</span> decorator_function<span style="color: Olive;">(</span>original_function<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> wrapper<span style="color: Olive;">(</span>*args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span>:<br/>
        <span style="color: #a50"># 这里是在调用原始函数前添加的新功能</span><br/>
        before_call_code<span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <br/>
        result <span style="color: Gray;">=</span> original_function<span style="color: Olive;">(</span>*args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span><br/>
        <br/>
        <span style="color: #a50"># 这里是在调用原始函数后添加的新功能</span><br/>
        after_call_code<span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
        <br/>
        <span style="color: Green;font-weight:bold;">return</span> result<br/>
    <span style="color: Green;font-weight:bold;">return</span> wrapper<br/>
<br/>
<span style="color: #a50"># 使用装饰器</span><br/>
<span style="color: Gray;">@</span>decorator_function<br/>
<span style="color: Green;font-weight:bold;">def</span> target_function<span style="color: Olive;">(</span>arg1<span style="color: Gray;">,</span> arg2<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">pass</span>  <span style="color: #a50"># 原始函数的实现</span><br/>
</div></div>&#13;
<p><strong>解析：</strong>decorator 是一个装饰器函数，它接受一个函数 func 作为参数，并返回一个内部函数 wrapper，在 wrapper 函数内部，你可以执行一些额外的操作，然后调用原始函数 func，并返回其结果。</p>&#13;
<ul>&#13;
<li><code>decorator_function</code> 是装饰器，它接收一个函数 <code>original_function</code> 作为参数。</li>&#13;
<li><code>wrapper</code> 是内部函数，它是实际会被调用的新函数，它包裹了原始函数的调用，并在其前后增加了额外的行为。</li>&#13;
<li>当我们使用 <code>@decorator_function</code> 前缀在 <code>target_function</code> 定义前，Python会自动将 <code>target_function</code> 作为参数传递给 <code>decorator_function</code>，然后将返回的 <code>wrapper</code> 函数替换掉原来的 <code>target_function</code>。</li>&#13;
</ul>&#13;
<h3>使用装饰器</h3><p>&#13;
装饰器通过 <span class="marked">@</span> 符号应用在函数定义之前，例如：</p>&#13;
<pre>&#13;
@time_logger&#13;
def target_function():&#13;
    pass&#13;
</pre><p>等同于：</p>&#13;
&#13;
<pre>def target_function():&#13;
    pass&#13;
target_function = time_logger(target_function)</pre>&#13;
<p>这会将 target_function 函数传递给 decorator 装饰器，并将返回的函数重新赋值给 target_function。从而，每次调用 target_function 时，实际上是调用了经过装饰器处理后的函数。</p>&#13;
<p>通过装饰器，开发者可以在保持代码整洁的同时，灵活且高效地扩展程序的功能。</p>&#13;
<h3>带参数的装饰器</h3><p>&#13;
装饰器函数也可以接受参数，例如：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">def</span> repeat<span style="color: Olive;">(</span>n<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">def</span> decorator<span style="color: Olive;">(</span>func<span style="color: Olive;">)</span>:<br/>
        <span style="color: Green;font-weight:bold;">def</span> wrapper<span style="color: Olive;">(</span>*args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span>:<br/>
            <span style="color: Green;font-weight:bold;">for</span> _ <span style="color: Green;font-weight:bold;">in</span> <span style="color: Teal;">range</span><span style="color: Olive;">(</span>n<span style="color: Olive;">)</span>:<br/>
                result <span style="color: Gray;">=</span> func<span style="color: Olive;">(</span>*args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span><br/>
            <span style="color: Green;font-weight:bold;">return</span> result<br/>
        <span style="color: Green;font-weight:bold;">return</span> wrapper<br/>
    <span style="color: Green;font-weight:bold;">return</span> decorator<br/>
<br/>
<span style="color: Gray;">@</span>repeat<span style="color: Olive;">(</span><span style="color: Maroon;">3</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">def</span> greet<span style="color: Olive;">(</span>name<span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>f<span style="color: #a11;">"Hello, {name}!"</span><span style="color: Olive;">)</span><br/>
<br/>
greet<span style="color: Olive;">(</span><span style="color: #a11;">"Alice"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上代码中 repeat 函数是一个带参数的装饰器，它接受一个整数参数 n，然后返回一个装饰器函数。该装饰器函数内部定义了 wrapper 函数，在调用原始函数之前重复执行 n 次。因此，greet 函数在被 @repeat(3) 装饰后，会打印三次问候语。&#13;
</p>&#13;
&#13;
<h3>类装饰器</h3><p>&#13;
除了函数装饰器，Python 还支持类装饰器。类装饰器是包含 <span class="marked">__call__</span> 方法的类，它接受一个函数作为参数，并返回一个新的函数。</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">class</span> DecoratorClass:<br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> func<span style="color: Olive;">)</span>:<br/>
        <span style="color: Teal;">self</span>.<span style="color: #05a;">func</span> <span style="color: Gray;">=</span> func<br/>
    <br/>
    <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__call__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> *args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span>:<br/>
        <span style="color: #a50"># 在调用原始函数之前/之后执行的代码</span><br/>
        result <span style="color: Gray;">=</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">func</span><span style="color: Olive;">(</span>*args<span style="color: Gray;">,</span> **kwargs<span style="color: Olive;">)</span><br/>
        <span style="color: #a50"># 在调用原始函数之后执行的代码</span><br/>
        <span style="color: Green;font-weight:bold;">return</span> result<br/>
<br/>
<span style="color: Gray;">@</span>DecoratorClass<br/>
<span style="color: Green;font-weight:bold;">def</span> my_function<span style="color: Olive;">(</span><span style="color: Olive;">)</span>:<br/>
    <span style="color: Green;font-weight:bold;">pass</span><br/>
</div></div>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>