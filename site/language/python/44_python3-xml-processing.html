<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 XML 解析</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 XML 解析</h1>&#13;
<hr/>&#13;
&#13;
<h2>什么是 XML？</h2>&#13;
<p>XML 指可扩展标记语言（e<b>X</b>tensible <b>M</b>arkup <b>L</b>anguage），标准通用标记语言的子集，是一种用于标记电子文件使其具有结构性的标记语言。&#13;
你可以通过本站学习 <a href="/xml/xml-tutorial.html" target="_blank" title="XML教程" rel="noopener">XML 教程</a>&#13;
</p>&#13;
<p>XML 被设计用来传输和存储数据。</p>&#13;
<p>XML 是一套定义语义标记的规则，这些标记将文档分成许多部件并对这些部件加以标识。</p>&#13;
<p>它也是元标记语言，即定义了用于定义其他与特定领域有关的、语义的、结构化的标记语言的句法语言。</p>&#13;
<hr/>&#13;
<h2>Python 对 XML 的解析</h2>&#13;
<p>常见的 XML 编程接口有 DOM 和 SAX，这两种接口处理 XML 文件的方式不同，当然使用场合也不同。</p>&#13;
<p>Python 有三种方法解析 XML：ElementTree、SAX 以及 DOM。</p>&#13;
&#13;
<h3>1. ElementTree</h3>&#13;
<p>xml.etree.ElementTree 是 Python 标准库中用于处理 XML 的模块，它提供了简单而高效的 API，用于解析和生成 XML 文档。</p>&#13;
&#13;
<h3>2.SAX (simple API for XML )</h3>&#13;
<p>Python 标准库包含 SAX 解析器，SAX 用事件驱动模型，通过在解析 XML 的过程中触发一个个的事件并调用用户定义的回调函数来处理 XML 文件。</p>&#13;
&#13;
<h3>3.DOM(Document Object Model)</h3>&#13;
<p>将 XML 数据在内存中解析成一个树，通过对树的操作来操作 XML。</p>&#13;
&#13;
&#13;
&#13;
<p>本章节使用到的 XML 实例文件 <strong>movies.xml</strong> 内容如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;collection</span> <span style="color: #000066;">shelf</span>=<span style="color: #a11;">"New Arrivals"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;movie</span> <span style="color: #000066;">title</span>=<span style="color: #a11;">"Enemy Behind"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>War, Thriller<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>DVD<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;year<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>2003<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/year<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>PG<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>10<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Talk about a US-Japan war<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/movie<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;movie</span> <span style="color: #000066;">title</span>=<span style="color: #a11;">"Transformers"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Anime, Science Fiction<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>DVD<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;year<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>1989<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/year<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>R<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>8<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>A schientific fiction<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/movie<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;movie</span> <span style="color: #000066;">title</span>=<span style="color: #a11;">"Trigun"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Anime, Action<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>DVD<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;episodes<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>4<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/episodes<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>PG<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>10<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Vash the Stampede!<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/movie<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;movie</span> <span style="color: #000066;">title</span>=<span style="color: #a11;">"Ishtar"</span><span style="color: #000000; font-weight: bold;">&gt;</span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Comedy<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/type<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>VHS<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/format<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>PG<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/rating<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>2<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/stars<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
   <span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span>Viewable boredom<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/description<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/movie<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
<span style="color: #009900;"><span style="color: #000000; font-weight: bold;">&lt;/collection<span style="color: #000000; font-weight: bold;">&gt;</span></span></span><br/>
</div></div>&#13;
<hr/>&#13;
<h2>Python 使用 ElementTree 解析 xml</h2><p>&#13;
&#13;
<span class="marked">xml.etree.ElementTree</span> 是 Python 标准库中用于处理 XML 的模块。</p><p>&#13;
以下是 xml.etree.ElementTree 模块的一些关键概念和用法：</p>&#13;
<p>&#13;
ElementTree 和 Element 对象:</p>&#13;
<ul>&#13;
	<li><strong>ElementTree</strong>： ElementTree 类是 XML 文档的树形表示。它包含一个或多个 Element 对象，代表整个 XML 文档。</li>&#13;
&#13;
&#13;
	<li><strong>Element</strong>： Element 对象是 XML 文档中元素的表示。每个元素都有一个标签、一组属性和零个或多个子元素。</li></ul>&#13;
<h3>解析 XML</h3>&#13;
<p><strong>fromstring() 方法</strong>： 使用 fromstring() 方法可以将包含XML数据的字符串转换为 Element 对象：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">etree</span>.<span style="color: #05a;">ElementTree</span> <span style="color: Green;font-weight:bold;">as</span> ET<br/>
<br/>
xml_string <span style="color: Gray;">=</span> <span style="color: #a11;">'&lt;root&gt;&lt;element&gt;Some data&lt;/element&gt;&lt;/root&gt;'</span><br/>
root <span style="color: Gray;">=</span> ET.<span style="color: #05a;">fromstring</span><span style="color: Olive;">(</span>xml_string<span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p><strong>parse() 方法</strong>： 如果XML数据存储在文件中，可以使用 parse() 方法来解析整个 XML 文档：</p>&#13;
<pre>&#13;
tree = ET.parse('example.xml')&#13;
root = tree.getroot()</pre>&#13;
<h3>遍历 XML 树</h3>&#13;
<p><strong>find() 方法</strong>： 使用 find() 方法可以查找具有指定标签的第一个子元素：</p>&#13;
<pre>&#13;
title_element = root.find('title')</pre><p>&#13;
<strong>findall() 方法</strong>： 使用 findall() 方法可以查找具有指定标签的所有子元素：</p>&#13;
<pre>&#13;
book_elements = root.findall('book')</pre>&#13;
<h3>访问元素的属性和文本内容</h3>&#13;
<p><span class="marked">attrib</span> 属性： 通过 attrib 属性可以访问元素的属性：</p>&#13;
<pre>&#13;
price = book_element.attrib['price']</pre><p>&#13;
<span class="marked">text</span> 属性： 通过 text 属性可以访问元素的文本内容：</p>&#13;
<pre>&#13;
title_text = title_element.text</pre>&#13;
<h3>创建 XML</h3><p>&#13;
<strong>Element() 构造函数</strong>： 使用 Element() 构造函数可以创建新的元素：</p>&#13;
<pre>&#13;
new_element = ET.Element('new_element')</pre><p>&#13;
<strong>SubElement() 函数</strong>： 使用 SubElement() 函数可以创建具有指定标签的子元素：</p>&#13;
<pre>&#13;
new_sub_element = ET.SubElement(root, 'new_sub_element')</pre>&#13;
<h3>修改 XML</h3><p>&#13;
修改元素的属性和文本内容： 直接修改元素的 attrib 和 text 属性。</p>&#13;
&#13;
<p>删除元素： 使用 remove() 方法可以删除元素：</p>&#13;
<pre>&#13;
root.remove(title_element)</pre>&#13;
<p>&#13;
简单读取 XML 内容：</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">etree</span>.<span style="color: #05a;">ElementTree</span> <span style="color: Green;font-weight:bold;">as</span> ET<br/>
<br/>
<span style="color: #a50"># 定义一个 XML 字符串</span><br/>
xml_string <span style="color: Gray;">=</span> <span style="color: #a11;">'''<br/>
&lt;bookstore&gt;<br/>
    &lt;book&gt;<br/>
        &lt;title&gt;Introduction to Python&lt;/title&gt;<br/>
        &lt;author&gt;John Doe&lt;/author&gt;<br/>
        &lt;price&gt;29.99&lt;/price&gt;<br/>
    &lt;/book&gt;<br/>
    &lt;book&gt;<br/>
        &lt;title&gt;Data Science with Python&lt;/title&gt;<br/>
        &lt;author&gt;Jane Smith&lt;/author&gt;<br/>
        &lt;price&gt;39.95&lt;/price&gt;<br/>
    &lt;/book&gt;<br/>
&lt;/bookstore&gt;<br/>
'''</span><br/>
<br/>
<span style="color: #a50"># 使用 ElementTree 解析 XML 字符串</span><br/>
root <span style="color: Gray;">=</span> ET.<span style="color: #05a;">fromstring</span><span style="color: Olive;">(</span>xml_string<span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 遍历 XML 树</span><br/>
<span style="color: Green;font-weight:bold;">for</span> book <span style="color: Green;font-weight:bold;">in</span> root.<span style="color: #05a;">findall</span><span style="color: Olive;">(</span><span style="color: #a11;">'book'</span><span style="color: Olive;">)</span>:<br/>
    title <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'title'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    author <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'author'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    price <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'price'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>f<span style="color: #a11;">'Title: {title}, Author: {author}, Price: {price}'</span><span style="color: Olive;">)</span><br/>
</div></div><p>&#13;
以上代码执行输出结果为：</p>&#13;
<pre>Title: Introduction to Python, Author: John Doe, Price: 29.99&#13;
Title: Data Science with Python, Author: Jane Smith, Price: 39.95</pre>&#13;
<p>&#13;
以下我们将创建一个包含书籍信息的XML文档，然后使用该模块进行解析和操作：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">etree</span>.<span style="color: #05a;">ElementTree</span> <span style="color: Green;font-weight:bold;">as</span> ET<br/>
<br/>
<span style="color: #a50"># 创建一个XML文档</span><br/>
root <span style="color: Gray;">=</span> ET.<span style="color: #05a;">Element</span><span style="color: Olive;">(</span><span style="color: #a11;">'bookstore'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 添加第一本书</span><br/>
book1 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>root<span style="color: Gray;">,</span> <span style="color: #a11;">'book'</span><span style="color: Olive;">)</span><br/>
title1 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book1<span style="color: Gray;">,</span> <span style="color: #a11;">'title'</span><span style="color: Olive;">)</span><br/>
title1.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'Introduction to Python'</span><br/>
author1 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book1<span style="color: Gray;">,</span> <span style="color: #a11;">'author'</span><span style="color: Olive;">)</span><br/>
author1.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'John Doe'</span><br/>
price1 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book1<span style="color: Gray;">,</span> <span style="color: #a11;">'price'</span><span style="color: Olive;">)</span><br/>
price1.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'29.99'</span><br/>
<br/>
<span style="color: #a50"># 添加第二本书</span><br/>
book2 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>root<span style="color: Gray;">,</span> <span style="color: #a11;">'book'</span><span style="color: Olive;">)</span><br/>
title2 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book2<span style="color: Gray;">,</span> <span style="color: #a11;">'title'</span><span style="color: Olive;">)</span><br/>
title2.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'Data Science with Python'</span><br/>
author2 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book2<span style="color: Gray;">,</span> <span style="color: #a11;">'author'</span><span style="color: Olive;">)</span><br/>
author2.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'Jane Smith'</span><br/>
price2 <span style="color: Gray;">=</span> ET.<span style="color: #05a;">SubElement</span><span style="color: Olive;">(</span>book2<span style="color: Gray;">,</span> <span style="color: #a11;">'price'</span><span style="color: Olive;">)</span><br/>
price2.<span style="color: #05a;">text</span> <span style="color: Gray;">=</span> <span style="color: #a11;">'39.95'</span><br/>
<br/>
<span style="color: #a50"># 将XML文档保存到文件</span><br/>
tree <span style="color: Gray;">=</span> ET.<span style="color: #05a;">ElementTree</span><span style="color: Olive;">(</span>root<span style="color: Olive;">)</span><br/>
tree.<span style="color: #05a;">write</span><span style="color: Olive;">(</span><span style="color: #a11;">'books.xml'</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 从文件中解析XML文档</span><br/>
parsed_tree <span style="color: Gray;">=</span> ET.<span style="color: #05a;">parse</span><span style="color: Olive;">(</span><span style="color: #a11;">'books.xml'</span><span style="color: Olive;">)</span><br/>
parsed_root <span style="color: Gray;">=</span> parsed_tree.<span style="color: #05a;">getroot</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 遍历XML树并打印书籍信息</span><br/>
<span style="color: Green;font-weight:bold;">for</span> book <span style="color: Green;font-weight:bold;">in</span> parsed_root.<span style="color: #05a;">findall</span><span style="color: Olive;">(</span><span style="color: #a11;">'book'</span><span style="color: Olive;">)</span>:<br/>
    title <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'title'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    author <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'author'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    price <span style="color: Gray;">=</span> book.<span style="color: #05a;">find</span><span style="color: Olive;">(</span><span style="color: #a11;">'price'</span><span style="color: Olive;">)</span>.<span style="color: #05a;">text</span><br/>
    <span style="color: Green;font-weight:bold;">print</span><span style="color: Olive;">(</span>f<span style="color: #a11;">'Title: {title}, Author: {author}, Price: {price}'</span><span style="color: Olive;">)</span><br/>
</div></div><p>&#13;
以上实例我们首先创建一个XML文档，其中包含两本书的信息，然后，我们将这个文档保存到文件 books.xml 中，接着，我们使用 ET.parse() 方法解析文件中的XML文档，并遍历文档树，提取并打印每本书的标题、作者和价格信息。</p>&#13;
<hr/>&#13;
<h2>Python 使用 SAX 解析 xml</h2>&#13;
<p>SAX 是一种基于事件驱动的API。</p>&#13;
<p>利用 SAX 解析 XML 文档牵涉到两个部分: <strong>解析器</strong>和<strong>事件处理器</strong>。</p>&#13;
<p>解析器负责读取 XML 文档，并向事件处理器发送事件，如元素开始跟元素结束事件。</p>&#13;
<p>而事件处理器则负责对事件作出响应，对传递的 XML 数据进行处理。&#13;
</p>&#13;
<psax>&#13;
<ul>&#13;
<li>&#13;
1、对大型文件进行处理；</li><li>&#13;
2、只需要文件的部分内容，或者只需从文件中得到特定信息。</li><li>&#13;
3、想建立自己的对象模型的时候。</li></ul>&#13;
<p>在 Python 中使用 sax 方式处理 xml 要先引入 xml.sax 中的 parse 函数，还有 xml.sax.handler 中的 ContentHandler。</p>&#13;
<h3>ContentHandler 类方法介绍</h3>&#13;
<p><strong>characters(content) 方法</strong></p>&#13;
<p>调用时机：</p>&#13;
<p>从行开始，遇到标签之前，存在字符，content 的值为这些字符串。</p>&#13;
<p>从一个标签，遇到下一个标签之前， 存在字符，content 的值为这些字符串。</p>&#13;
<p>从一个标签，遇到行结束符之前，存在字符，content 的值为这些字符串。</p>&#13;
<p>标签可以是开始标签，也可以是结束标签。</p>&#13;
&#13;
&#13;
<p><strong>startDocument() 方法</strong></p>&#13;
<p>文档启动的时候调用。</p>&#13;
&#13;
&#13;
<p><strong>endDocument() 方法</strong></p>&#13;
<p>解析器到达文档结尾时调用。</p>&#13;
&#13;
&#13;
<p><strong>startElement(name, attrs) 方法</strong></p>&#13;
<p>遇到XML开始标签时调用，name 是标签的名字，attrs 是标签的属性值字典。</p>&#13;
&#13;
&#13;
<p><strong>endElement(name) 方法</strong></p>&#13;
<p>遇到XML结束标签时调用。 </p>&#13;
<hr/>&#13;
<h2>make_parser 方法</h2>&#13;
<p>以下方法创建一个新的解析器对象并返回。</p>&#13;
<pre>&#13;
xml.sax.make_parser( [parser_list] )&#13;
</pre>&#13;
<p>参数说明:</p>&#13;
<ul>&#13;
<li><strong>parser_list</strong> - &#13;
可选参数，解析器列表</li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>parser 方法</h2>&#13;
<p>以下方法创建一个 SAX 解析器并解析xml文档：</p>&#13;
<pre>&#13;
xml.sax.parse( xmlfile, contenthandler[, errorhandler])&#13;
</pre>&#13;
<p>参数说明:</p>&#13;
<ul>&#13;
<li><strong>xmlfile</strong> - &#13;
xml文件名</li>&#13;
<li><strong>contenthandler</strong> - &#13;
必须是一个 ContentHandler 的对象</li>&#13;
<li><strong>errorhandler</strong> - &#13;
如果指定该参数，errorhandler 必须是一个 SAX ErrorHandler 对象</li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>parseString 方法</h2>&#13;
<p>parseString 方法创建一个 XML 解析器并解析 xml 字符串：</p>&#13;
<pre>&#13;
xml.sax.parseString(xmlstring, contenthandler[, errorhandler])&#13;
</pre>&#13;
<p>参数说明:</p>&#13;
<ul>&#13;
<li><strong>xmlstring</strong> - &#13;
xml字符串</li>&#13;
<li><strong>contenthandler</strong> - &#13;
必须是一个 ContentHandler 的对象</li>&#13;
<li><strong>errorhandler</strong> - &#13;
如果指定该参数，errorhandler 必须是一个  SAX ErrorHandler对象</li>&#13;
</ul>&#13;
<hr/>&#13;
<h2>Python 解析XML实例</h2>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">sax</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">class</span> MovieHandler<span style="color: Olive;">(</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">sax</span>.<span style="color: #05a;">ContentHandler</span> <span style="color: Olive;">)</span>:<br/>
   <span style="color: Green;font-weight:bold;">def</span> <span style="color: Navy;">__init__</span><span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Olive;">)</span>:<br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: Teal;">type</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">format</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">year</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">rating</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">stars</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">description</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
<br/>
   <span style="color: #a50"># 元素开始调用</span><br/>
   <span style="color: Green;font-weight:bold;">def</span> startElement<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> tag<span style="color: Gray;">,</span> attributes<span style="color: Olive;">)</span>:<br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">=</span> tag<br/>
      <span style="color: Green;font-weight:bold;">if</span> tag <span style="color: Gray;">==</span> <span style="color: #a11;">"movie"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"*****Movie*****"</span><span style="color: Olive;">)</span><br/>
         title <span style="color: Gray;">=</span> attributes<span style="color: Olive;">[</span><span style="color: #a11;">"title"</span><span style="color: Olive;">]</span><br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Title:"</span><span style="color: Gray;">,</span> title<span style="color: Olive;">)</span><br/>
<br/>
   <span style="color: #a50"># 元素结束调用</span><br/>
   <span style="color: Green;font-weight:bold;">def</span> endElement<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> tag<span style="color: Olive;">)</span>:<br/>
      <span style="color: Green;font-weight:bold;">if</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"type"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Type:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: Teal;">type</span><span style="color: Olive;">)</span><br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"format"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Format:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">format</span><span style="color: Olive;">)</span><br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"year"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Year:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">year</span><span style="color: Olive;">)</span><br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"rating"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Rating:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">rating</span><span style="color: Olive;">)</span><br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"stars"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Stars:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">stars</span><span style="color: Olive;">)</span><br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"description"</span>:<br/>
         <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Description:"</span><span style="color: Gray;">,</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">description</span><span style="color: Olive;">)</span><br/>
      <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">=</span> <span style="color: #a11;">""</span><br/>
<br/>
   <span style="color: #a50"># 读取字符时调用</span><br/>
   <span style="color: Green;font-weight:bold;">def</span> characters<span style="color: Olive;">(</span><span style="color: Teal;">self</span><span style="color: Gray;">,</span> content<span style="color: Olive;">)</span>:<br/>
      <span style="color: Green;font-weight:bold;">if</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"type"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: Teal;">type</span> <span style="color: Gray;">=</span> content<br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"format"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: #05a;">format</span> <span style="color: Gray;">=</span> content<br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"year"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: #05a;">year</span> <span style="color: Gray;">=</span> content<br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"rating"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: #05a;">rating</span> <span style="color: Gray;">=</span> content<br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"stars"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: #05a;">stars</span> <span style="color: Gray;">=</span> content<br/>
      <span style="color: Green;font-weight:bold;">elif</span> <span style="color: Teal;">self</span>.<span style="color: #05a;">CurrentData</span> <span style="color: Gray;">==</span> <span style="color: #a11;">"description"</span>:<br/>
         <span style="color: Teal;">self</span>.<span style="color: #05a;">description</span> <span style="color: Gray;">=</span> content<br/>
  <br/>
<span style="color: Green;font-weight:bold;">if</span> <span style="color: Olive;">(</span> __name__ <span style="color: Gray;">==</span> <span style="color: #a11;">"__main__"</span><span style="color: Olive;">)</span>:<br/>
   <br/>
   <span style="color: #a50"># 创建一个 XMLReader</span><br/>
   <span style="color: #05a;">parser</span> <span style="color: Gray;">=</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">sax</span>.<span style="color: #05a;">make_parser</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
   <span style="color: #a50"># 关闭命名空间</span><br/>
   <span style="color: #05a;">parser</span>.<span style="color: #05a;">setFeature</span><span style="color: Olive;">(</span><span style="color: #05a;">xml</span>.<span style="color: #05a;">sax</span>.<span style="color: #05a;">handler</span>.<span style="color: #05a;">feature_namespaces</span><span style="color: Gray;">,</span> <span style="color: Maroon;">0</span><span style="color: Olive;">)</span><br/>
<br/>
   <span style="color: #a50"># 重写 ContextHandler</span><br/>
   Handler <span style="color: Gray;">=</span> MovieHandler<span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
   <span style="color: #05a;">parser</span>.<span style="color: #05a;">setContentHandler</span><span style="color: Olive;">(</span> Handler <span style="color: Olive;">)</span><br/>
   <br/>
   <span style="color: #05a;">parser</span>.<span style="color: #05a;">parse</span><span style="color: Olive;">(</span><span style="color: #a11;">"movies.xml"</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以上代码执行结果如下：</p>&#13;
<pre>&#13;
*****Movie*****&#13;
Title: Enemy Behind&#13;
Type: War, Thriller&#13;
Format: DVD&#13;
Year: 2003&#13;
Rating: PG&#13;
Stars: 10&#13;
Description: Talk about a US-Japan war&#13;
*****Movie*****&#13;
Title: Transformers&#13;
Type: Anime, Science Fiction&#13;
Format: DVD&#13;
Year: 1989&#13;
Rating: R&#13;
Stars: 8&#13;
Description: A schientific fiction&#13;
*****Movie*****&#13;
Title: Trigun&#13;
Type: Anime, Action&#13;
Format: DVD&#13;
Rating: PG&#13;
Stars: 10&#13;
Description: Vash the Stampede!&#13;
*****Movie*****&#13;
Title: Ishtar&#13;
Type: Comedy&#13;
Format: VHS&#13;
Rating: PG&#13;
Stars: 2&#13;
Description: Viewable boredom&#13;
</pre>&#13;
<p>完整的 SAX API 文档请查阅<a href="https://docs.python.org/library/xml.sax.html" target="_blank" rel="nofollow noopener">Python SAX APIs</a></p>&#13;
<hr/>&#13;
<h2>使用xml.dom解析xml</h2>&#13;
<p>文件对象模型（Document Object Model，简称DOM），是W3C组织推荐的处理可扩展置标语言的标准编程接口。</p>&#13;
<p>一个 DOM 的解析器在解析一个 XML 文档时，一次性读取整个文档，把文档中所有元素保存在内存中的一个树结构里，之后你可以利用DOM 提供的不同的函数来读取或修改文档的内容和结构，也可以把修改过的内容写入xml文件。&#13;
</p>&#13;
<p>Python 中用 xml.dom.minidom 来解析 xml 文件，实例如下：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">from</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">dom</span>.<span style="color: #05a;">minidom</span> <span style="color: Green;font-weight:bold;">import</span> parse<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">dom</span>.<span style="color: #05a;">minidom</span><br/>
<br/>
<span style="color: #a50"># 使用minidom解析器打开 XML 文档</span><br/>
DOMTree <span style="color: Gray;">=</span> <span style="color: #05a;">xml</span>.<span style="color: #05a;">dom</span>.<span style="color: #05a;">minidom</span>.<span style="color: #05a;">parse</span><span style="color: Olive;">(</span><span style="color: #a11;">"movies.xml"</span><span style="color: Olive;">)</span><br/>
collection <span style="color: Gray;">=</span> DOMTree.<span style="color: #05a;">documentElement</span><br/>
<span style="color: Green;font-weight:bold;">if</span> collection.<span style="color: #05a;">hasAttribute</span><span style="color: Olive;">(</span><span style="color: #a11;">"shelf"</span><span style="color: Olive;">)</span>:<br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Root element : %s"</span> % collection.<span style="color: #05a;">getAttribute</span><span style="color: Olive;">(</span><span style="color: #a11;">"shelf"</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 在集合中获取所有电影</span><br/>
movies <span style="color: Gray;">=</span> collection.<span style="color: #05a;">getElementsByTagName</span><span style="color: Olive;">(</span><span style="color: #a11;">"movie"</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 打印每部电影的详细信息</span><br/>
<span style="color: Green;font-weight:bold;">for</span> movie <span style="color: Green;font-weight:bold;">in</span> movies:<br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"*****Movie*****"</span><span style="color: Olive;">)</span><br/>
   <span style="color: Green;font-weight:bold;">if</span> movie.<span style="color: #05a;">hasAttribute</span><span style="color: Olive;">(</span><span style="color: #a11;">"title"</span><span style="color: Olive;">)</span>:<br/>
      <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Title: %s"</span> % movie.<span style="color: #05a;">getAttribute</span><span style="color: Olive;">(</span><span style="color: #a11;">"title"</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
   <span style="color: Teal;">type</span> <span style="color: Gray;">=</span> movie.<span style="color: #05a;">getElementsByTagName</span><span style="color: Olive;">(</span><span style="color: #a11;">'type'</span><span style="color: Olive;">)</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Type: %s"</span> % <span style="color: Teal;">type</span>.<span style="color: #05a;">childNodes</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span>.<span style="color: #05a;">data</span><span style="color: Olive;">)</span><br/>
   format <span style="color: Gray;">=</span> movie.<span style="color: #05a;">getElementsByTagName</span><span style="color: Olive;">(</span><span style="color: #a11;">'format'</span><span style="color: Olive;">)</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Format: %s"</span> % format.<span style="color: #05a;">childNodes</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span>.<span style="color: #05a;">data</span><span style="color: Olive;">)</span><br/>
   rating <span style="color: Gray;">=</span> movie.<span style="color: #05a;">getElementsByTagName</span><span style="color: Olive;">(</span><span style="color: #a11;">'rating'</span><span style="color: Olive;">)</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Rating: %s"</span> % rating.<span style="color: #05a;">childNodes</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span>.<span style="color: #05a;">data</span><span style="color: Olive;">)</span><br/>
   description <span style="color: Gray;">=</span> movie.<span style="color: #05a;">getElementsByTagName</span><span style="color: Olive;">(</span><span style="color: #a11;">'description'</span><span style="color: Olive;">)</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span><br/>
   <span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"Description: %s"</span> % description.<span style="color: #05a;">childNodes</span><span style="color: Olive;">[</span><span style="color: Maroon;">0</span><span style="color: Olive;">]</span>.<span style="color: #05a;">data</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
<p>以上程序执行结果如下：</p>&#13;
<pre>&#13;
Root element : New Arrivals&#13;
*****Movie*****&#13;
Title: Enemy Behind&#13;
Type: War, Thriller&#13;
Format: DVD&#13;
Rating: PG&#13;
Description: Talk about a US-Japan war&#13;
*****Movie*****&#13;
Title: Transformers&#13;
Type: Anime, Science Fiction&#13;
Format: DVD&#13;
Rating: R&#13;
Description: A schientific fiction&#13;
*****Movie*****&#13;
Title: Trigun&#13;
Type: Anime, Action&#13;
Format: DVD&#13;
Rating: PG&#13;
Description: Vash the Stampede!&#13;
*****Movie*****&#13;
Title: Ishtar&#13;
Type: Comedy&#13;
Format: VHS&#13;
Rating: PG&#13;
Description: Viewable boredom&#13;
</pre>&#13;
<p>完整的  DOM API 文档请查阅<a href="http://docs.python.org/library/xml.dom.html" target="_blank" rel="nofollow noopener">Python DOM APIs</a>。</p>			<!-- 其他扩展 -->
						
			</psax></div>
			
		
</body>
</html>