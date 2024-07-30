<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C++ 标准库</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C++ <span class="color_h1">标准库</span></h1>&#13;
<p>C++ 标准库包括一组头文件，这些头文件提供了各种功能和工具，涵盖了输入输出、容器、算法、多线程、正则表达式等。</p>&#13;
<p>C++ 标准库可以分为两部分：</p>&#13;
<ul class="list">&#13;
<li><b>标准函数库：</b> 这个库是由通用的、独立的、不属于任何类的函数组成的。函数库继承自 C 语言。</li>&#13;
<li><b>面向对象类库：</b> 这个库是类及其相关函数的集合。</li>&#13;
</ul>&#13;
<p>C++ 标准库包含了所有的 C 标准库，为了支持类型安全，做了一定的添加和修改。</p>&#13;
<p>以下是 C++ 标准库的主要组件分类及对应的头文件列表：</p>&#13;
    <h3>输入输出</h3>&#13;
    <ul>&#13;
        <li><a href="/cplusplus/cpp-libs-iostream.html" rel="noopener" target="_blank"><code>&lt;iostream&gt;</code>: 标准输入输出流</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-fstream.html" rel="noopener" target="_blank"><code>&lt;fstream&gt;</code>: 文件输入输出流</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-sstream.html" rel="noopener" target="_blank"><code>&lt;sstream&gt;</code>: 字符串流</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-iomanip.html" rel="noopener" target="_blank"><code>&lt;iomanip&gt;</code>: 输入输出流格式化</a></li>&#13;
    </ul>&#13;
    <h3>容器</h3>&#13;
    <ul>&#13;
        <li><a href="/cplusplus/cpp-libs-array.html" rel="noopener" target="_blank"><code>&lt;array&gt;</code>: 定长数组容器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-vector.html" rel="noopener" target="_blank"><code>&lt;vector&gt;</code>: 动态数组容器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-deque.html" rel="noopener" target="_blank"><code>&lt;deque&gt;</code>: 双端队列容器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-list.html" rel="noopener" target="_blank"><code>&lt;list&gt;</code>: 双向链表容器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-forward_list.html" rel="noopener" target="_blank"><code>&lt;forward_list&gt;</code>: 单向链表容器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-stack.html" rel="noopener" target="_blank"><code>&lt;stack&gt;</code>: 栈容器适配器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-queue.html" rel="noopener" target="_blank"><code>&lt;queue&gt;</code>: 队列容器适配器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-priority_queue.html" rel="noopener" target="_blank"><code>&lt;priority_queue&gt;</code>: 优先队列容器适配器</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-set.html" rel="noopener" target="_blank"><code>&lt;set&gt;</code>: 集合容器（基于平衡二叉树）</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-unordered_set.html" rel="noopener" target="_blank"><code>&lt;unordered_set&gt;</code>: 无序集合容器（基于哈希表）</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-map.html" rel="noopener" target="_blank"><code>&lt;map&gt;</code>: 映射容器（键值对，基于平衡二叉树）</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-unordered_map.html" rel="noopener" target="_blank"><code>&lt;unordered_map&gt;</code>: 无序映射容器（基于哈希表）</a></li>&#13;
        <li><a href="/cplusplus/cpp-libs-bitset.html" rel="noopener" target="_blank"><code>&lt;bitset&gt;</code>: 二进制位容器</a></li>&#13;
    </ul>&#13;
    <h3>算法和迭代器</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-algorithm.html" rel="noopener" target="_blank">&lt;algorithm&gt;</a></code>: 常用算法（如排序、查找等）</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-iterator.html" rel="noopener" target="_blank">&lt;iterator&gt;</a></code>: 迭代器</li>&#13;
    </ul>&#13;
    <h3>函数对象和绑定</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-functional.html" rel="noopener" target="_blank">&lt;functional&gt;</a></code>: 定义函数对象及相关工具</li>&#13;
    </ul>&#13;
    <h3>数学和数值运算</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-numeric.html" rel="noopener" target="_blank">&lt;numeric&gt;</a></code>: 数值操作（如累计、乘积等）</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-complex.html" rel="noopener" target="_blank">&lt;complex&gt;</a></code>: 复数运算</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-valarray.html" rel="noopener" target="_blank">&lt;valarray&gt;</a></code>: 数组类及相关操作</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cmath.html" rel="noopener" target="_blank">&lt;cmath&gt;</a></code>: 数学函数</li>&#13;
    </ul>&#13;
    <h3>字符串和正则表达式</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-string.html" rel="noopener" target="_blank">&lt;string&gt;</a></code>: 标准字符串类</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-regex.html" rel="noopener" target="_blank">&lt;regex&gt;</a></code>: 正则表达式</li>&#13;
    </ul>&#13;
    <h3>时间和日期</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-ctime.html" rel="noopener" target="_blank">&lt;ctime&gt;</a></code>: 时间处理</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-chrono.html" rel="noopener" target="_blank">&lt;chrono&gt;</a></code>: 时间库</li>&#13;
    </ul>&#13;
    <h3>多线程和并发</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-thread.html" rel="noopener" target="_blank">&lt;thread&gt;</a></code>: 多线程支持</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-mutex.html" rel="noopener" target="_blank">&lt;mutex&gt;</a></code>: 互斥量</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-condition_variable.html" rel="noopener" target="_blank">&lt;condition_variable&gt;</a></code>: 条件变量</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-future.html" rel="noopener" target="_blank">&lt;future&gt;</a></code>: 异步编程支持</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-atomic.html" rel="noopener" target="_blank">&lt;atomic&gt;</a></code>: 原子操作</li>&#13;
    </ul>&#13;
    <h3>内存管理</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-memory.html" rel="noopener" target="_blank">&lt;memory&gt;</a></code>: 智能指针及动态内存管理</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-new.html" rel="noopener" target="_blank">&lt;new&gt;</a></code>: 动态内存分配</li>&#13;
    </ul>&#13;
    <h3>类型特性和运行时类型识别</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-type_traits.html" rel="noopener" target="_blank">&lt;type_traits&gt;</a></code>: 类型特性</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-typeinfo.html" rel="noopener" target="_blank">&lt;typeinfo&gt;</a></code>: 运行时类型识别</li>&#13;
    </ul>&#13;
    <h3>异常处理</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-exception.html" rel="noopener" target="_blank">&lt;exception&gt;</a></code>: 异常处理基类及相关工具</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-stdexcept.html" rel="noopener" target="_blank">&lt;stdexcept&gt;</a></code>: 常用异常类（如 <code>std::runtime_error</code> 等）</li>&#13;
    </ul>&#13;
    <h3>输入输出操作</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cstdio.html" rel="noopener" target="_blank">&lt;cstdio&gt;</a></code>: C 风格输入输出</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cstdint.html" rel="noopener" target="_blank">&lt;cstdint&gt;</a></code>: 定长整数类型</li>&#13;
    </ul>&#13;
    <h3>其他工具</h3>&#13;
    <ul>&#13;
        <li><code><a href="/cplusplus/cpp-libs-utility.html" rel="noopener" target="_blank">&lt;utility&gt;</a></code>: 通用工具（如 <code>std::pair</code> 和 <code>std::move</code> 等）</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-random.html" rel="noopener" target="_blank">&lt;random&gt;</a></code>: 随机数生成</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-locale.html" rel="noopener" target="_blank">&lt;locale&gt;</a></code>: 本地化支持</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-codecvt.html" rel="noopener" target="_blank">&lt;codecvt&gt;</a></code>: 字符编码转换</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cassert.html" rel="noopener" target="_blank">&lt;cassert&gt;</a></code>: 断言</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cctype.html" rel="noopener" target="_blank">&lt;cctype&gt;</a></code>: 字符处理</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cstring.html" rel="noopener" target="_blank">&lt;cstring&gt;</a></code>: 字符串处理</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cwchar.html" rel="noopener" target="_blank">&lt;cwchar&gt;</a></code>: 宽字符处理</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-climits.html" rel="noopener" target="_blank">&lt;climits&gt;</a></code>: 数值极限</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cfloat.html" rel="noopener" target="_blank">&lt;cfloat&gt;</a></code>: 浮点极限</li>&#13;
        <li><code><a href="/cplusplus/cpp-libs-cstdlib.html" rel="noopener" target="_blank">&lt;cstdlib&gt;</a></code>: 常用工具（如 <code>std::rand</code> 和 <code>std::abs</code> 等）</li>&#13;
    </ul>&#13;
    <p>这些头文件构成了C++标准库的基础，提供了丰富的功能，支持开发者进行各种类型的编程任务。</p>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>