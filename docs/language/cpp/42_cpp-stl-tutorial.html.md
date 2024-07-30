<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ STL 教程</title>
</head>
<body>
<div class="article-intro" id="content">
			
			
<h1>C++ <span class="color_h1">STL 教程</span></h1>&#13;
&#13;
<p>C++ 标准模板库（Standard Template Library，STL）是一套功能强大的 C++ 模板类和函数的集合，它提供了一系列通用的、可复用的算法和数据结构。</p><p>STL 的设计基于泛型编程，这意味着使用模板可以编写出独立于任何特定数据类型的代码。</p><p>&#13;
STL 分为多个组件，包括容器（Containers）、迭代器（Iterators）、算法（Algorithms）、函数对象（Function Objects）和适配器（Adapters）等。</p>&#13;
<p>使用 STL 的好处:</p>&#13;
<ul>&#13;
<li><strong>代码复用</strong>：STL 提供了大量的通用数据结构和算法，可以减少重复编写代码的工作。</li>&#13;
<li><strong>性能优化</strong>：STL 中的算法和数据结构都经过了优化，以提供最佳的性能。</li>&#13;
<li><strong>泛型编程</strong>：使用模板，STL 支持泛型编程，使得算法和数据结构可以适用于任何数据类型。</li>&#13;
<li><strong>易于维护</strong>：STL 的设计使得代码更加模块化，易于阅读和维护。</li>&#13;
</ul>&#13;
<p>C++ 标准模板库的核心包括以下重要组件组件：</p>&#13;
<table class="reference">&#13;
<tr>&#13;
<th width="30%">组件</th>&#13;
<th>描述</th>&#13;
</tr>&#13;
<tr>&#13;
<td>容器（Containers）</td>&#13;
<td><p>容器是 STL 中最基本的组件之一，提供了各种数据结构，包括向量（vector）、链表（list）、队列（queue）、栈（stack）、集合（set）、映射（map）等。这些容器具有不同的特性和用途，可以根据实际需求选择合适的容器。</p>&#13;
&#13;
</td>&#13;
</tr>&#13;
<tr>&#13;
<td>算法（Algorithms）</td>&#13;
<td>STL 提供了大量的算法，用于对容器中的元素进行各种操作，包括排序、搜索、复制、移动、变换等。这些算法在使用时不需要关心容器的具体类型，只需要指定要操作的范围即可。</td>&#13;
</tr>&#13;
<tr>&#13;
<td>迭代器（iterators）</td>&#13;
<td>迭代器用于遍历容器中的元素，允许以统一的方式访问容器中的元素，而不用关心容器的内部实现细节。STL 提供了多种类型的迭代器，包括随机访问迭代器、双向迭代器、前向迭代器和输入输出迭代器等。</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>函数对象（Function Objects）</td>&#13;
<td>函数对象是可以像函数一样调用的对象，可以用于算法中的各种操作。STL 提供了多种函数对象，包括一元函数对象、二元函数对象、谓词等，可以满足不同的需求。</td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>适配器（Adapters）</td>&#13;
<td>适配器用于将一种容器或迭代器适配成另一种容器或迭代器，以满足特定的需求。STL 提供了多种适配器，包括栈适配器（stack adapter）、队列适配器（queue adapter）和优先队列适配器（priority queue adapter）等。</td>&#13;
</tr>&#13;
&#13;
</table>&#13;
<p>这些个组件都带有丰富的预定义函数，帮助我们通过简单的方式处理复杂的任务。</p>&#13;
&#13;
<hr/><h2>容器</h2><p>&#13;
容器是用来存储数据的序列，它们提供了不同的存储方式和访问模式。</p><p>STL 中的容器可以分为三类：</p>&#13;
<p>&#13;
1、序列容器：存储元素的序列，允许双向遍历。</p>&#13;
<ul><li>&#13;
std::vector：动态数组，支持快速随机访问。</li><li>&#13;
std::deque：双端队列，支持快速插入和删除。</li><li>&#13;
std::list：链表，支持快速插入和删除，但不支持随机访问。</li></ul><p>&#13;
2、关联容器：存储键值对，每个元素都有一个键（key）和一个值（value），并且通过键来组织元素。</p>&#13;
<ul><li>&#13;
std::set：集合，不允许重复元素。</li><li>&#13;
std::multiset：多重集合，允许多个元素具有相同的键。</li><li>&#13;
std::map：映射，每个键映射到一个值。</li><li>&#13;
std::multimap：多重映射，允许多个键映射到相同的值。</li></ul><p>&#13;
3、无序容器（C++11 引入）：哈希表，支持快速的查找、插入和删除。</p>&#13;
<ul><li>&#13;
std::unordered_set：无序集合。</li><li>&#13;
std::unordered_multiset：无序多重集合。</li><li>&#13;
std::unordered_map：无序映射。</li><li>&#13;
std::unordered_multimap：无序多重映射。</li></ul>&#13;
&#13;
<p>下面的程序演示了向量容器（一个 C++ 标准的模板），它与数组十分相似，唯一不同的是，向量在需要扩展大小的时候，会自动处理它自己的存储需求：</p>&#13;
<div class="example"> &#13;
<h2 class="example">实例</h2>&#13;
<div class="example_code">&#13;
<div class="hl-main"><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">iostream</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-prepro">#include</span><span class="hl-prepro"> </span><span class="hl-quotes">&lt;</span><span class="hl-string">vector</span><span class="hl-quotes">&gt;</span><span class="hl-prepro"/><span class="hl-code">
</span><span class="hl-reserved">using</span><span class="hl-code"> </span><span class="hl-types">namespace</span><span class="hl-code"> </span><span class="hl-identifier">std</span><span class="hl-code">;
 
</span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">main</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">
</span><span class="hl-brackets">{</span><span class="hl-code">
   </span><span class="hl-comment">// 创建一个向量存储 int</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">vector</span><span class="hl-code">&lt;</span><span class="hl-types">int</span><span class="hl-code">&gt; </span><span class="hl-identifier">vec</span><span class="hl-code">; 
   </span><span class="hl-types">int</span><span class="hl-code"> </span><span class="hl-identifier">i</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 显示 vec 的原始大小</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">vector size = </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">vec</span><span class="hl-code">.</span><span class="hl-identifier">size</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 推入 5 个值到向量中</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">5</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">vec</span><span class="hl-code">.</span><span class="hl-identifier">push_back</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-comment">// 显示 vec 扩展后的大小</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">extended vector size = </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">vec</span><span class="hl-code">.</span><span class="hl-identifier">size</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
 
   </span><span class="hl-comment">// 访问向量中的 5 个值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-reserved">for</span><span class="hl-brackets">(</span><span class="hl-identifier">i</span><span class="hl-code"> = </span><span class="hl-number">0</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt; </span><span class="hl-number">5</span><span class="hl-code">; </span><span class="hl-identifier">i</span><span class="hl-code">++</span><span class="hl-brackets">)</span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">value of vec [</span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">i</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">] = </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">vec</span><span class="hl-brackets">[</span><span class="hl-identifier">i</span><span class="hl-brackets">]</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-comment">// 使用迭代器 iterator 访问值</span><span class="hl-comment"/><span class="hl-code">
   </span><span class="hl-identifier">vector</span><span class="hl-code">&lt;</span><span class="hl-types">int</span><span class="hl-code">&gt;::</span><span class="hl-identifier">iterator</span><span class="hl-code"> </span><span class="hl-identifier">v</span><span class="hl-code"> = </span><span class="hl-identifier">vec</span><span class="hl-code">.</span><span class="hl-identifier">begin</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-code">;
   </span><span class="hl-reserved">while</span><span class="hl-brackets">(</span><span class="hl-code"> </span><span class="hl-identifier">v</span><span class="hl-code"> != </span><span class="hl-identifier">vec</span><span class="hl-code">.</span><span class="hl-identifier">end</span><span class="hl-brackets">(</span><span class="hl-brackets">)</span><span class="hl-brackets">)</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
      </span><span class="hl-identifier">cout</span><span class="hl-code"> &lt;&lt; </span><span class="hl-quotes">"</span><span class="hl-string">value of v = </span><span class="hl-quotes">"</span><span class="hl-code"> &lt;&lt; *</span><span class="hl-identifier">v</span><span class="hl-code"> &lt;&lt; </span><span class="hl-identifier">endl</span><span class="hl-code">;
      </span><span class="hl-identifier">v</span><span class="hl-code">++;
   </span><span class="hl-brackets">}</span><span class="hl-code">
 
   </span><span class="hl-reserved">return</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span></div>&#13;
</div>&#13;
</div>&#13;
<p>当上面的代码被编译和执行时，它会产生下列结果：</p>&#13;
<pre>&#13;
vector size = 0&#13;
extended vector size = 5&#13;
value of vec [0] = 0&#13;
value of vec [1] = 1&#13;
value of vec [2] = 2&#13;
value of vec [3] = 3&#13;
value of vec [4] = 4&#13;
value of v = 0&#13;
value of v = 1&#13;
value of v = 2&#13;
value of v = 3&#13;
value of v = 4&#13;
</pre>&#13;
<p>关于上面实例中所使用的各种函数，有几点要注意：</p>&#13;
<ul class="list">&#13;
<li>push_back( ) 成员函数在向量的末尾插入值，如果有必要会扩展向量的大小。</li>&#13;
<li>size( ) 函数显示向量的大小。</li>&#13;
<li>begin( ) 函数返回一个指向向量开头的迭代器。</li>&#13;
<li>end( ) 函数返回一个指向向量末尾的迭代器。</li>&#13;
</ul>&#13;
&#13;
<p>&#13;
STL 是 C++ 编程中不可或缺的一部分，它极大地扩展了 C++ 的功能，使得程序员能够编写出更加高效、可读性更强的代码。</p><p>掌握 STL 的使用对于任何 C++ 程序员来说都是非常重要的。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>