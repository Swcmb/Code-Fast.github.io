# 栈

「栈 stack」是一种遵循先入后出的逻辑的线性数据结构。

我们可以将栈类比为桌面上的一摞盘子，如果需要拿出底部的盘子，则需要先将上面的盘子依次取出。我们将盘子替换为各种类型的元素（如整数、字符、对象等），就得到了栈数据结构。

如下图所示，我们把堆叠元素的顶部称为“栈顶”，底部称为“栈底”。将把元素添加到栈顶的操作叫做“入栈”，删除栈顶元素的操作叫做“出栈”。

![栈的先入后出规则](stack.assets/stack_operations.png)

## 栈常用操作

栈的常用操作如下表所示，具体的方法名需要根据所使用的编程语言来确定。在此，我们以常见的 `push()`、`pop()`、`peek()` 命名为例。

<p align="center"> 表 <id> &nbsp; 栈的操作效率 </p>

| 方法   | 描述                   | 时间复杂度 |
| ------ | ---------------------- | ---------- |
| push() | 元素入栈（添加至栈顶） | $O(1)$     |
| pop()  | 栈顶元素出栈           | $O(1)$     |
| peek() | 访问栈顶元素           | $O(1)$     |

通常情况下，我们可以直接使用编程语言内置的栈类。然而，某些语言可能没有专门提供栈类，这时我们可以将该语言的“数组”或“链表”视作栈来使用，并在程序逻辑上忽略与栈无关的操作。

=== "Python"

    ```python title="stack.py"
    # 初始化栈
    # Python 没有内置的栈类，可以把 List 当作栈来使用 
    stack: list[int] = []
    
    # 元素入栈
    stack.append(1)
    stack.append(3)
    stack.append(2)
    stack.append(5)
    stack.append(4)
    
    # 访问栈顶元素
    peek: int = stack[-1]
    
    # 元素出栈
    pop: int = stack.pop()
    
    # 获取栈的长度
    size: int = len(stack)
    
    # 判断是否为空
    is_empty: bool = len(stack) == 0
    ```

=== "C++"

    ```cpp title="stack.cpp"
    /* 初始化栈 */
    stack<int> stack;
    
    /* 元素入栈 */
    stack.push(1);
    stack.push(3);
    stack.push(2);
    stack.push(5);
    stack.push(4);
    
    /* 访问栈顶元素 */
    int top = stack.top();
    
    /* 元素出栈 */
    stack.pop(); // 无返回值
    
    /* 获取栈的长度 */
    int size = stack.size();
    
    /* 判断是否为空 */
    bool empty = stack.empty();
    ```

=== "Java"

    ```java title="stack.java"
    /* 初始化栈 */
    Stack<Integer> stack = new Stack<>();

    /* 元素入栈 */
    stack.push(1);
    stack.push(3);
    stack.push(2);
    stack.push(5);
    stack.push(4);

    /* 访问栈顶元素 */
    int peek = stack.peek();

    /* 元素出栈 */
    int pop = stack.pop();

    /* 获取栈的长度 */
    int size = stack.size();

    /* 判断是否为空 */
    boolean isEmpty = stack.isEmpty();
    ```

=== "C#"

    ```csharp title="stack.cs"
    /* 初始化栈 */
    Stack<int> stack = new();
    
    /* 元素入栈 */
    stack.Push(1);
    stack.Push(3);
    stack.Push(2);
    stack.Push(5);
    stack.Push(4);
    
    /* 访问栈顶元素 */
    int peek = stack.Peek();
    
    /* 元素出栈 */
    int pop = stack.Pop();
    
    /* 获取栈的长度 */
    int size = stack.Count;
    
    /* 判断是否为空 */
    bool isEmpty = stack.Count == 0;
    ```

=== "Go"

    ```go title="stack_test.go"
    /* 初始化栈 */
    // 在 Go 中，推荐将 Slice 当作栈来使用
    var stack []int
    
    /* 元素入栈 */
    stack = append(stack, 1)
    stack = append(stack, 3)
    stack = append(stack, 2)
    stack = append(stack, 5)
    stack = append(stack, 4)
    
    /* 访问栈顶元素 */
    peek := stack[len(stack)-1]
    
    /* 元素出栈 */
    pop := stack[len(stack)-1]
    stack = stack[:len(stack)-1]
    
    /* 获取栈的长度 */
    size := len(stack)
    
    /* 判断是否为空 */
    isEmpty := len(stack) == 0
    ```

=== "Swift"

    ```swift title="stack.swift"
    /* 初始化栈 */
    // Swift 没有内置的栈类，可以把 Array 当作栈来使用
    var stack: [Int] = []
    
    /* 元素入栈 */
    stack.append(1)
    stack.append(3)
    stack.append(2)
    stack.append(5)
    stack.append(4)
    
    /* 访问栈顶元素 */
    let peek = stack.last!
    
    /* 元素出栈 */
    let pop = stack.removeLast()
    
    /* 获取栈的长度 */
    let size = stack.count
    
    /* 判断是否为空 */
    let isEmpty = stack.isEmpty
    ```

=== "JS"

    ```javascript title="stack.js"
    /* 初始化栈 */
    // Javascript 没有内置的栈类，可以把 Array 当作栈来使用 
    const stack = [];
    
    /* 元素入栈 */
    stack.push(1);
    stack.push(3);
    stack.push(2);
    stack.push(5);
    stack.push(4);
    
    /* 访问栈顶元素 */
    const peek = stack[stack.length-1];
    
    /* 元素出栈 */
    const pop = stack.pop();
    
    /* 获取栈的长度 */
    const size = stack.length;
    
    /* 判断是否为空 */
    const is_empty = stack.length === 0;
    ```

=== "TS"

    ```typescript title="stack.ts"
    /* 初始化栈 */
    // Typescript 没有内置的栈类，可以把 Array 当作栈来使用 
    const stack: number[] = [];
    
    /* 元素入栈 */
    stack.push(1);
    stack.push(3);
    stack.push(2);
    stack.push(5);
    stack.push(4);
    
    /* 访问栈顶元素 */
    const peek = stack[stack.length - 1];
    
    /* 元素出栈 */
    const pop = stack.pop();
    
    /* 获取栈的长度 */
    const size = stack.length;
    
    /* 判断是否为空 */
    const is_empty = stack.length === 0;
    ```

=== "Dart"

    ```dart title="stack.dart"
    /* 初始化栈 */
    // Dart 没有内置的栈类，可以把 List 当作栈来使用
    List<int> stack = [];

    /* 元素入栈 */
    stack.add(1);
    stack.add(3);
    stack.add(2);
    stack.add(5);
    stack.add(4);

    /* 访问栈顶元素 */
    int peek = stack.last;

    /* 元素出栈 */
    int pop = stack.removeLast();

    /* 获取栈的长度 */
    int size = stack.length;

    /* 判断是否为空 */
    bool isEmpty = stack.isEmpty;
    ```

=== "Rust"

    ```rust title="stack.rs"
    /* 初始化栈 */
    // 把 Vec 当作栈来使用
    let mut stack: Vec<i32> = Vec::new();

    /* 元素入栈 */
    stack.push(1);
    stack.push(3);
    stack.push(2);
    stack.push(5);
    stack.push(4);

    /* 访问栈顶元素 */
    let top = stack[stack.len() - 1];

    /* 元素出栈 */
    let pop = stack.pop().unwrap();

    /* 获取栈的长度 */
    let size = stack.len();

    /* 判断是否为空 */
    let is_empty = stack.is_empty();
    ```

=== "C"

    ```c title="stack.c"
    // C 未提供内置栈
    ```

=== "Zig"

    ```zig title="stack.zig"

    ```

## 栈的实现

为了深入了解栈的运行机制，我们来尝试自己实现一个栈类。

栈遵循先入后出的原则，因此我们只能在栈顶添加或删除元素。然而，数组和链表都可以在任意位置添加和删除元素，**因此栈可以被视为一种受限制的数组或链表**。换句话说，我们可以“屏蔽”数组或链表的部分无关操作，使其对外表现的逻辑符合栈的特性。

### 基于链表的实现

使用链表来实现栈时，我们可以将链表的头节点视为栈顶，尾节点视为栈底。

如下图所示，对于入栈操作，我们只需将元素插入链表头部，这种节点插入方法被称为“头插法”。而对于出栈操作，只需将头节点从链表中删除即可。

=== "LinkedListStack"
    ![基于链表实现栈的入栈出栈操作](stack.assets/linkedlist_stack.png)

=== "push()"
    ![linkedlist_stack_push](stack.assets/linkedlist_stack_push.png)

=== "pop()"
    ![linkedlist_stack_pop](stack.assets/linkedlist_stack_pop.png)

以下是基于链表实现栈的示例代码。

<div class="tabbed-set tabbed-alternate" data-tabs="3:14" style="--md-indicator-x: 0px; --md-indicator-width: 68px;"><input checked="checked" id="__tabbed_3_1" name="__tabbed_3" type="radio"><input id="__tabbed_3_2" name="__tabbed_3" type="radio"><input id="__tabbed_3_3" name="__tabbed_3" type="radio"><input id="__tabbed_3_4" name="__tabbed_3" type="radio"><input id="__tabbed_3_5" name="__tabbed_3" type="radio"><input id="__tabbed_3_6" name="__tabbed_3" type="radio"><input id="__tabbed_3_7" name="__tabbed_3" type="radio"><input id="__tabbed_3_8" name="__tabbed_3" type="radio"><input id="__tabbed_3_9" name="__tabbed_3" type="radio"><input id="__tabbed_3_10" name="__tabbed_3" type="radio"><input id="__tabbed_3_11" name="__tabbed_3" type="radio"><input id="__tabbed_3_12" name="__tabbed_3" type="radio"><input id="__tabbed_3_13" name="__tabbed_3" type="radio"><input id="__tabbed_3_14" name="__tabbed_3" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_3_1"><a href="#__tabbed_3_1" tabindex="-1">Python</a></label><label for="__tabbed_3_2"><a href="#__tabbed_3_2" tabindex="-1">C++</a></label><label for="__tabbed_3_3"><a href="#__tabbed_3_3" tabindex="-1">Java</a></label><label for="__tabbed_3_4"><a href="#__tabbed_3_4" tabindex="-1">C#</a></label><label for="__tabbed_3_5"><a href="#__tabbed_3_5" tabindex="-1">Go</a></label><label for="__tabbed_3_6"><a href="#__tabbed_3_6" tabindex="-1">Swift</a></label><label for="__tabbed_3_7"><a href="#__tabbed_3_7" tabindex="-1">JS</a></label><label for="__tabbed_3_8"><a href="#__tabbed_3_8" tabindex="-1">TS</a></label><label for="__tabbed_3_9"><a href="#__tabbed_3_9" tabindex="-1">Dart</a></label><label for="__tabbed_3_10"><a href="#__tabbed_3_10" tabindex="-1">Rust</a></label><label for="__tabbed_3_11"><a href="#__tabbed_3_11" tabindex="-1">C</a></label><label for="__tabbed_3_12"><a href="#__tabbed_3_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_3_13"><a href="#__tabbed_3_13" tabindex="-1">Ruby</a></label><label for="__tabbed_3_14"><a href="#__tabbed_3_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.py</span><pre id="__code_14"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_14 > code"></button><code><a id="__codelineno-14-1" name="__codelineno-14-1" href="#__codelineno-14-1"></a><span class="k">class</span> <span class="nc">LinkedListStack</span><span class="p">:</span>
<a id="__codelineno-14-2" name="__codelineno-14-2" href="#__codelineno-14-2"></a><span class="w">    </span><span class="sd">"""基于链表实现的栈"""</span>
<a id="__codelineno-14-3" name="__codelineno-14-3" href="#__codelineno-14-3"></a>
<a id="__codelineno-14-4" name="__codelineno-14-4" href="#__codelineno-14-4"></a>    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<a id="__codelineno-14-5" name="__codelineno-14-5" href="#__codelineno-14-5"></a><span class="w">        </span><span class="sd">"""构造方法"""</span>
<a id="__codelineno-14-6" name="__codelineno-14-6" href="#__codelineno-14-6"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span><span class="p">:</span> <span class="n">ListNode</span> <span class="o">|</span> <span class="kc">None</span> <span class="o">=</span> <span class="kc">None</span>
<a id="__codelineno-14-7" name="__codelineno-14-7" href="#__codelineno-14-7"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_size</span><span class="p">:</span> <span class="nb">int</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-14-8" name="__codelineno-14-8" href="#__codelineno-14-8"></a>
<a id="__codelineno-14-9" name="__codelineno-14-9" href="#__codelineno-14-9"></a>    <span class="k">def</span> <span class="nf">size</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-10" name="__codelineno-14-10" href="#__codelineno-14-10"></a><span class="w">        </span><span class="sd">"""获取栈的长度"""</span>
<a id="__codelineno-14-11" name="__codelineno-14-11" href="#__codelineno-14-11"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_size</span>
<a id="__codelineno-14-12" name="__codelineno-14-12" href="#__codelineno-14-12"></a>
<a id="__codelineno-14-13" name="__codelineno-14-13" href="#__codelineno-14-13"></a>    <span class="k">def</span> <span class="nf">is_empty</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">bool</span><span class="p">:</span>
<a id="__codelineno-14-14" name="__codelineno-14-14" href="#__codelineno-14-14"></a><span class="w">        </span><span class="sd">"""判断栈是否为空"""</span>
<a id="__codelineno-14-15" name="__codelineno-14-15" href="#__codelineno-14-15"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_size</span> <span class="o">==</span> <span class="mi">0</span>
<a id="__codelineno-14-16" name="__codelineno-14-16" href="#__codelineno-14-16"></a>
<a id="__codelineno-14-17" name="__codelineno-14-17" href="#__codelineno-14-17"></a>    <span class="k">def</span> <span class="nf">push</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-14-18" name="__codelineno-14-18" href="#__codelineno-14-18"></a><span class="w">        </span><span class="sd">"""入栈"""</span>
<a id="__codelineno-14-19" name="__codelineno-14-19" href="#__codelineno-14-19"></a>        <span class="n">node</span> <span class="o">=</span> <span class="n">ListNode</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-14-20" name="__codelineno-14-20" href="#__codelineno-14-20"></a>        <span class="n">node</span><span class="o">.</span><span class="n">next</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span>
<a id="__codelineno-14-21" name="__codelineno-14-21" href="#__codelineno-14-21"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span> <span class="o">=</span> <span class="n">node</span>
<a id="__codelineno-14-22" name="__codelineno-14-22" href="#__codelineno-14-22"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_size</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-14-23" name="__codelineno-14-23" href="#__codelineno-14-23"></a>
<a id="__codelineno-14-24" name="__codelineno-14-24" href="#__codelineno-14-24"></a>    <span class="k">def</span> <span class="nf">pop</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-25" name="__codelineno-14-25" href="#__codelineno-14-25"></a><span class="w">        </span><span class="sd">"""出栈"""</span>
<a id="__codelineno-14-26" name="__codelineno-14-26" href="#__codelineno-14-26"></a>        <span class="n">num</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">peek</span><span class="p">()</span>
<a id="__codelineno-14-27" name="__codelineno-14-27" href="#__codelineno-14-27"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span><span class="o">.</span><span class="n">next</span>
<a id="__codelineno-14-28" name="__codelineno-14-28" href="#__codelineno-14-28"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_size</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-14-29" name="__codelineno-14-29" href="#__codelineno-14-29"></a>        <span class="k">return</span> <span class="n">num</span>
<a id="__codelineno-14-30" name="__codelineno-14-30" href="#__codelineno-14-30"></a>
<a id="__codelineno-14-31" name="__codelineno-14-31" href="#__codelineno-14-31"></a>    <span class="k">def</span> <span class="nf">peek</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-32" name="__codelineno-14-32" href="#__codelineno-14-32"></a><span class="w">        </span><span class="sd">"""访问栈顶元素"""</span>
<a id="__codelineno-14-33" name="__codelineno-14-33" href="#__codelineno-14-33"></a>        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">is_empty</span><span class="p">():</span>
<a id="__codelineno-14-34" name="__codelineno-14-34" href="#__codelineno-14-34"></a>            <span class="k">raise</span> <span class="ne">IndexError</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-14-35" name="__codelineno-14-35" href="#__codelineno-14-35"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span><span class="o">.</span><span class="n">val</span>
<a id="__codelineno-14-36" name="__codelineno-14-36" href="#__codelineno-14-36"></a>
<a id="__codelineno-14-37" name="__codelineno-14-37" href="#__codelineno-14-37"></a>    <span class="k">def</span> <span class="nf">to_list</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">]:</span>
<a id="__codelineno-14-38" name="__codelineno-14-38" href="#__codelineno-14-38"></a><span class="w">        </span><span class="sd">"""转化为列表用于打印"""</span>
<a id="__codelineno-14-39" name="__codelineno-14-39" href="#__codelineno-14-39"></a>        <span class="n">arr</span> <span class="o">=</span> <span class="p">[]</span>
<a id="__codelineno-14-40" name="__codelineno-14-40" href="#__codelineno-14-40"></a>        <span class="n">node</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">_peek</span>
<a id="__codelineno-14-41" name="__codelineno-14-41" href="#__codelineno-14-41"></a>        <span class="k">while</span> <span class="n">node</span><span class="p">:</span>
<a id="__codelineno-14-42" name="__codelineno-14-42" href="#__codelineno-14-42"></a>            <span class="n">arr</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">node</span><span class="o">.</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-14-43" name="__codelineno-14-43" href="#__codelineno-14-43"></a>            <span class="n">node</span> <span class="o">=</span> <span class="n">node</span><span class="o">.</span><span class="n">next</span>
<a id="__codelineno-14-44" name="__codelineno-14-44" href="#__codelineno-14-44"></a>        <span class="n">arr</span><span class="o">.</span><span class="n">reverse</span><span class="p">()</span>
<a id="__codelineno-14-45" name="__codelineno-14-45" href="#__codelineno-14-45"></a>        <span class="k">return</span> <span class="n">arr</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.cpp</span><pre id="__code_15"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_15 > code"></button><code><a id="__codelineno-15-1" name="__codelineno-15-1" href="#__codelineno-15-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-15-2" name="__codelineno-15-2" href="#__codelineno-15-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-3" name="__codelineno-15-3" href="#__codelineno-15-3"></a><span class="w">  </span><span class="k">private</span><span class="o">:</span>
<a id="__codelineno-15-4" name="__codelineno-15-4" href="#__codelineno-15-4"></a><span class="w">    </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">stackTop</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-15-5" name="__codelineno-15-5" href="#__codelineno-15-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">stkSize</span><span class="p">;</span><span class="w">        </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-15-6" name="__codelineno-15-6" href="#__codelineno-15-6"></a>
<a id="__codelineno-15-7" name="__codelineno-15-7" href="#__codelineno-15-7"></a><span class="w">  </span><span class="k">public</span><span class="o">:</span>
<a id="__codelineno-15-8" name="__codelineno-15-8" href="#__codelineno-15-8"></a><span class="w">    </span><span class="n">LinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-9" name="__codelineno-15-9" href="#__codelineno-15-9"></a><span class="w">        </span><span class="n">stackTop</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">nullptr</span><span class="p">;</span>
<a id="__codelineno-15-10" name="__codelineno-15-10" href="#__codelineno-15-10"></a><span class="w">        </span><span class="n">stkSize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-15-11" name="__codelineno-15-11" href="#__codelineno-15-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-12" name="__codelineno-15-12" href="#__codelineno-15-12"></a>
<a id="__codelineno-15-13" name="__codelineno-15-13" href="#__codelineno-15-13"></a><span class="w">    </span><span class="o">~</span><span class="n">LinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-14" name="__codelineno-15-14" href="#__codelineno-15-14"></a><span class="w">        </span><span class="c1">// 遍历链表删除节点，释放内存</span>
<a id="__codelineno-15-15" name="__codelineno-15-15" href="#__codelineno-15-15"></a><span class="w">        </span><span class="n">freeMemoryLinkedList</span><span class="p">(</span><span class="n">stackTop</span><span class="p">);</span>
<a id="__codelineno-15-16" name="__codelineno-15-16" href="#__codelineno-15-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-17" name="__codelineno-15-17" href="#__codelineno-15-17"></a>
<a id="__codelineno-15-18" name="__codelineno-15-18" href="#__codelineno-15-18"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-15-19" name="__codelineno-15-19" href="#__codelineno-15-19"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-20" name="__codelineno-15-20" href="#__codelineno-15-20"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stkSize</span><span class="p">;</span>
<a id="__codelineno-15-21" name="__codelineno-15-21" href="#__codelineno-15-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-22" name="__codelineno-15-22" href="#__codelineno-15-22"></a>
<a id="__codelineno-15-23" name="__codelineno-15-23" href="#__codelineno-15-23"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-15-24" name="__codelineno-15-24" href="#__codelineno-15-24"></a><span class="w">    </span><span class="kt">bool</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-25" name="__codelineno-15-25" href="#__codelineno-15-25"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-15-26" name="__codelineno-15-26" href="#__codelineno-15-26"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-27" name="__codelineno-15-27" href="#__codelineno-15-27"></a>
<a id="__codelineno-15-28" name="__codelineno-15-28" href="#__codelineno-15-28"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-15-29" name="__codelineno-15-29" href="#__codelineno-15-29"></a><span class="w">    </span><span class="kt">void</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-30" name="__codelineno-15-30" href="#__codelineno-15-30"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ListNode</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-15-31" name="__codelineno-15-31" href="#__codelineno-15-31"></a><span class="w">        </span><span class="n">node</span><span class="o">-&gt;</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackTop</span><span class="p">;</span>
<a id="__codelineno-15-32" name="__codelineno-15-32" href="#__codelineno-15-32"></a><span class="w">        </span><span class="n">stackTop</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span>
<a id="__codelineno-15-33" name="__codelineno-15-33" href="#__codelineno-15-33"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-15-34" name="__codelineno-15-34" href="#__codelineno-15-34"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-35" name="__codelineno-15-35" href="#__codelineno-15-35"></a>
<a id="__codelineno-15-36" name="__codelineno-15-36" href="#__codelineno-15-36"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-15-37" name="__codelineno-15-37" href="#__codelineno-15-37"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-38" name="__codelineno-15-38" href="#__codelineno-15-38"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">top</span><span class="p">();</span>
<a id="__codelineno-15-39" name="__codelineno-15-39" href="#__codelineno-15-39"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">tmp</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackTop</span><span class="p">;</span>
<a id="__codelineno-15-40" name="__codelineno-15-40" href="#__codelineno-15-40"></a><span class="w">        </span><span class="n">stackTop</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackTop</span><span class="o">-&gt;</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-15-41" name="__codelineno-15-41" href="#__codelineno-15-41"></a><span class="w">        </span><span class="c1">// 释放内存</span>
<a id="__codelineno-15-42" name="__codelineno-15-42" href="#__codelineno-15-42"></a><span class="w">        </span><span class="k">delete</span><span class="w"> </span><span class="n">tmp</span><span class="p">;</span>
<a id="__codelineno-15-43" name="__codelineno-15-43" href="#__codelineno-15-43"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-15-44" name="__codelineno-15-44" href="#__codelineno-15-44"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-15-45" name="__codelineno-15-45" href="#__codelineno-15-45"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-46" name="__codelineno-15-46" href="#__codelineno-15-46"></a>
<a id="__codelineno-15-47" name="__codelineno-15-47" href="#__codelineno-15-47"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-15-48" name="__codelineno-15-48" href="#__codelineno-15-48"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">top</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-49" name="__codelineno-15-49" href="#__codelineno-15-49"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-15-50" name="__codelineno-15-50" href="#__codelineno-15-50"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="n">out_of_range</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-15-51" name="__codelineno-15-51" href="#__codelineno-15-51"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stackTop</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-15-52" name="__codelineno-15-52" href="#__codelineno-15-52"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-53" name="__codelineno-15-53" href="#__codelineno-15-53"></a>
<a id="__codelineno-15-54" name="__codelineno-15-54" href="#__codelineno-15-54"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-15-55" name="__codelineno-15-55" href="#__codelineno-15-55"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">toVector</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-56" name="__codelineno-15-56" href="#__codelineno-15-56"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackTop</span><span class="p">;</span>
<a id="__codelineno-15-57" name="__codelineno-15-57" href="#__codelineno-15-57"></a><span class="w">        </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">res</span><span class="p">(</span><span class="n">size</span><span class="p">());</span>
<a id="__codelineno-15-58" name="__codelineno-15-58" href="#__codelineno-15-58"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">res</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">--</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-59" name="__codelineno-15-59" href="#__codelineno-15-59"></a><span class="w">            </span><span class="n">res</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-15-60" name="__codelineno-15-60" href="#__codelineno-15-60"></a><span class="w">            </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="o">-&gt;</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-15-61" name="__codelineno-15-61" href="#__codelineno-15-61"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-15-62" name="__codelineno-15-62" href="#__codelineno-15-62"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-15-63" name="__codelineno-15-63" href="#__codelineno-15-63"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-15-64" name="__codelineno-15-64" href="#__codelineno-15-64"></a><span class="p">};</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.java</span><pre id="__code_16"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_16 > code"></button><code><a id="__codelineno-16-1" name="__codelineno-16-1" href="#__codelineno-16-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-16-2" name="__codelineno-16-2" href="#__codelineno-16-2"></a><span class="kd">class</span> <span class="nc">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-3" name="__codelineno-16-3" href="#__codelineno-16-3"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="n">ListNode</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-16-4" name="__codelineno-16-4" href="#__codelineno-16-4"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">stkSize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-16-5" name="__codelineno-16-5" href="#__codelineno-16-5"></a>
<a id="__codelineno-16-6" name="__codelineno-16-6" href="#__codelineno-16-6"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="nf">LinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-7" name="__codelineno-16-7" href="#__codelineno-16-7"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-16-8" name="__codelineno-16-8" href="#__codelineno-16-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-9" name="__codelineno-16-9" href="#__codelineno-16-9"></a>
<a id="__codelineno-16-10" name="__codelineno-16-10" href="#__codelineno-16-10"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-16-11" name="__codelineno-16-11" href="#__codelineno-16-11"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-12" name="__codelineno-16-12" href="#__codelineno-16-12"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stkSize</span><span class="p">;</span>
<a id="__codelineno-16-13" name="__codelineno-16-13" href="#__codelineno-16-13"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-14" name="__codelineno-16-14" href="#__codelineno-16-14"></a>
<a id="__codelineno-16-15" name="__codelineno-16-15" href="#__codelineno-16-15"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-16-16" name="__codelineno-16-16" href="#__codelineno-16-16"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">boolean</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-17" name="__codelineno-16-17" href="#__codelineno-16-17"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-16-18" name="__codelineno-16-18" href="#__codelineno-16-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-19" name="__codelineno-16-19" href="#__codelineno-16-19"></a>
<a id="__codelineno-16-20" name="__codelineno-16-20" href="#__codelineno-16-20"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-16-21" name="__codelineno-16-21" href="#__codelineno-16-21"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-22" name="__codelineno-16-22" href="#__codelineno-16-22"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ListNode</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-16-23" name="__codelineno-16-23" href="#__codelineno-16-23"></a><span class="w">        </span><span class="n">node</span><span class="p">.</span><span class="na">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">;</span>
<a id="__codelineno-16-24" name="__codelineno-16-24" href="#__codelineno-16-24"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span>
<a id="__codelineno-16-25" name="__codelineno-16-25" href="#__codelineno-16-25"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-16-26" name="__codelineno-16-26" href="#__codelineno-16-26"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-27" name="__codelineno-16-27" href="#__codelineno-16-27"></a>
<a id="__codelineno-16-28" name="__codelineno-16-28" href="#__codelineno-16-28"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-16-29" name="__codelineno-16-29" href="#__codelineno-16-29"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-30" name="__codelineno-16-30" href="#__codelineno-16-30"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span><span class="p">();</span>
<a id="__codelineno-16-31" name="__codelineno-16-31" href="#__codelineno-16-31"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">.</span><span class="na">next</span><span class="p">;</span>
<a id="__codelineno-16-32" name="__codelineno-16-32" href="#__codelineno-16-32"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-16-33" name="__codelineno-16-33" href="#__codelineno-16-33"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-16-34" name="__codelineno-16-34" href="#__codelineno-16-34"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-35" name="__codelineno-16-35" href="#__codelineno-16-35"></a>
<a id="__codelineno-16-36" name="__codelineno-16-36" href="#__codelineno-16-36"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-16-37" name="__codelineno-16-37" href="#__codelineno-16-37"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-38" name="__codelineno-16-38" href="#__codelineno-16-38"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-16-39" name="__codelineno-16-39" href="#__codelineno-16-39"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">();</span>
<a id="__codelineno-16-40" name="__codelineno-16-40" href="#__codelineno-16-40"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">.</span><span class="na">val</span><span class="p">;</span>
<a id="__codelineno-16-41" name="__codelineno-16-41" href="#__codelineno-16-41"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-42" name="__codelineno-16-42" href="#__codelineno-16-42"></a>
<a id="__codelineno-16-43" name="__codelineno-16-43" href="#__codelineno-16-43"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-16-44" name="__codelineno-16-44" href="#__codelineno-16-44"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="o">[]</span><span class="w"> </span><span class="nf">toArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-45" name="__codelineno-16-45" href="#__codelineno-16-45"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">;</span>
<a id="__codelineno-16-46" name="__codelineno-16-46" href="#__codelineno-16-46"></a><span class="w">        </span><span class="kt">int</span><span class="o">[]</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="kt">int</span><span class="o">[</span><span class="n">size</span><span class="p">()</span><span class="o">]</span><span class="p">;</span>
<a id="__codelineno-16-47" name="__codelineno-16-47" href="#__codelineno-16-47"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">res</span><span class="p">.</span><span class="na">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">--</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-48" name="__codelineno-16-48" href="#__codelineno-16-48"></a><span class="w">            </span><span class="n">res</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="na">val</span><span class="p">;</span>
<a id="__codelineno-16-49" name="__codelineno-16-49" href="#__codelineno-16-49"></a><span class="w">            </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="na">next</span><span class="p">;</span>
<a id="__codelineno-16-50" name="__codelineno-16-50" href="#__codelineno-16-50"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-16-51" name="__codelineno-16-51" href="#__codelineno-16-51"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-16-52" name="__codelineno-16-52" href="#__codelineno-16-52"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-16-53" name="__codelineno-16-53" href="#__codelineno-16-53"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.cs</span><pre id="__code_17"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_17 > code"></button><code><a id="__codelineno-17-1" name="__codelineno-17-1" href="#__codelineno-17-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-17-2" name="__codelineno-17-2" href="#__codelineno-17-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-3" name="__codelineno-17-3" href="#__codelineno-17-3"></a><span class="w">    </span><span class="n">ListNode</span><span class="o">?</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">;</span><span class="w">  </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-17-4" name="__codelineno-17-4" href="#__codelineno-17-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">stkSize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w">   </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-17-5" name="__codelineno-17-5" href="#__codelineno-17-5"></a>
<a id="__codelineno-17-6" name="__codelineno-17-6" href="#__codelineno-17-6"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nf">LinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-7" name="__codelineno-17-7" href="#__codelineno-17-7"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">null</span><span class="p">;</span>
<a id="__codelineno-17-8" name="__codelineno-17-8" href="#__codelineno-17-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-9" name="__codelineno-17-9" href="#__codelineno-17-9"></a>
<a id="__codelineno-17-10" name="__codelineno-17-10" href="#__codelineno-17-10"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-17-11" name="__codelineno-17-11" href="#__codelineno-17-11"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-12" name="__codelineno-17-12" href="#__codelineno-17-12"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stkSize</span><span class="p">;</span>
<a id="__codelineno-17-13" name="__codelineno-17-13" href="#__codelineno-17-13"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-14" name="__codelineno-17-14" href="#__codelineno-17-14"></a>
<a id="__codelineno-17-15" name="__codelineno-17-15" href="#__codelineno-17-15"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-17-16" name="__codelineno-17-16" href="#__codelineno-17-16"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="nf">IsEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-17" name="__codelineno-17-17" href="#__codelineno-17-17"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nf">Size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-17-18" name="__codelineno-17-18" href="#__codelineno-17-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-19" name="__codelineno-17-19" href="#__codelineno-17-19"></a>
<a id="__codelineno-17-20" name="__codelineno-17-20" href="#__codelineno-17-20"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-17-21" name="__codelineno-17-21" href="#__codelineno-17-21"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="k">void</span><span class="w"> </span><span class="nf">Push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-22" name="__codelineno-17-22" href="#__codelineno-17-22"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="p">(</span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-23" name="__codelineno-17-23" href="#__codelineno-17-23"></a><span class="w">            </span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span>
<a id="__codelineno-17-24" name="__codelineno-17-24" href="#__codelineno-17-24"></a><span class="w">        </span><span class="p">};</span>
<a id="__codelineno-17-25" name="__codelineno-17-25" href="#__codelineno-17-25"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span>
<a id="__codelineno-17-26" name="__codelineno-17-26" href="#__codelineno-17-26"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-17-27" name="__codelineno-17-27" href="#__codelineno-17-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-28" name="__codelineno-17-28" href="#__codelineno-17-28"></a>
<a id="__codelineno-17-29" name="__codelineno-17-29" href="#__codelineno-17-29"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-17-30" name="__codelineno-17-30" href="#__codelineno-17-30"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-31" name="__codelineno-17-31" href="#__codelineno-17-31"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Peek</span><span class="p">();</span>
<a id="__codelineno-17-32" name="__codelineno-17-32" href="#__codelineno-17-32"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="o">!</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-17-33" name="__codelineno-17-33" href="#__codelineno-17-33"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-17-34" name="__codelineno-17-34" href="#__codelineno-17-34"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-17-35" name="__codelineno-17-35" href="#__codelineno-17-35"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-36" name="__codelineno-17-36" href="#__codelineno-17-36"></a>
<a id="__codelineno-17-37" name="__codelineno-17-37" href="#__codelineno-17-37"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-17-38" name="__codelineno-17-38" href="#__codelineno-17-38"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-39" name="__codelineno-17-39" href="#__codelineno-17-39"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">IsEmpty</span><span class="p">())</span>
<a id="__codelineno-17-40" name="__codelineno-17-40" href="#__codelineno-17-40"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="nf">Exception</span><span class="p">();</span>
<a id="__codelineno-17-41" name="__codelineno-17-41" href="#__codelineno-17-41"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stackPeek</span><span class="o">!</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-17-42" name="__codelineno-17-42" href="#__codelineno-17-42"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-43" name="__codelineno-17-43" href="#__codelineno-17-43"></a>
<a id="__codelineno-17-44" name="__codelineno-17-44" href="#__codelineno-17-44"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-17-45" name="__codelineno-17-45" href="#__codelineno-17-45"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="nf">ToArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-46" name="__codelineno-17-46" href="#__codelineno-17-46"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">stackPeek</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="k">null</span><span class="p">)</span>
<a id="__codelineno-17-47" name="__codelineno-17-47" href="#__codelineno-17-47"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-17-48" name="__codelineno-17-48" href="#__codelineno-17-48"></a>
<a id="__codelineno-17-49" name="__codelineno-17-49" href="#__codelineno-17-49"></a><span class="w">        </span><span class="n">ListNode</span><span class="o">?</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="p">;</span>
<a id="__codelineno-17-50" name="__codelineno-17-50" href="#__codelineno-17-50"></a><span class="w">        </span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="kt">int</span><span class="p">[</span><span class="n">Size</span><span class="p">()];</span>
<a id="__codelineno-17-51" name="__codelineno-17-51" href="#__codelineno-17-51"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">res</span><span class="p">.</span><span class="n">Length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">--</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-52" name="__codelineno-17-52" href="#__codelineno-17-52"></a><span class="w">            </span><span class="n">res</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="o">!</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-17-53" name="__codelineno-17-53" href="#__codelineno-17-53"></a><span class="w">            </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-17-54" name="__codelineno-17-54" href="#__codelineno-17-54"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-17-55" name="__codelineno-17-55" href="#__codelineno-17-55"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-17-56" name="__codelineno-17-56" href="#__codelineno-17-56"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-17-57" name="__codelineno-17-57" href="#__codelineno-17-57"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.go</span><pre id="__code_18"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_18 > code"></button><code><a id="__codelineno-18-1" name="__codelineno-18-1" href="#__codelineno-18-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-18-2" name="__codelineno-18-2" href="#__codelineno-18-2"></a><span class="kd">type</span><span class="w"> </span><span class="nx">linkedListStack</span><span class="w"> </span><span class="kd">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-3" name="__codelineno-18-3" href="#__codelineno-18-3"></a><span class="w">    </span><span class="c1">// 使用内置包 list 来实现栈</span>
<a id="__codelineno-18-4" name="__codelineno-18-4" href="#__codelineno-18-4"></a><span class="w">    </span><span class="nx">data</span><span class="w"> </span><span class="o">*</span><span class="nx">list</span><span class="p">.</span><span class="nx">List</span>
<a id="__codelineno-18-5" name="__codelineno-18-5" href="#__codelineno-18-5"></a><span class="p">}</span>
<a id="__codelineno-18-6" name="__codelineno-18-6" href="#__codelineno-18-6"></a>
<a id="__codelineno-18-7" name="__codelineno-18-7" href="#__codelineno-18-7"></a><span class="cm">/* 初始化栈 */</span>
<a id="__codelineno-18-8" name="__codelineno-18-8" href="#__codelineno-18-8"></a><span class="kd">func</span><span class="w"> </span><span class="nx">newLinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-9" name="__codelineno-18-9" href="#__codelineno-18-9"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="o">&amp;</span><span class="nx">linkedListStack</span><span class="p">{</span>
<a id="__codelineno-18-10" name="__codelineno-18-10" href="#__codelineno-18-10"></a><span class="w">        </span><span class="nx">data</span><span class="p">:</span><span class="w"> </span><span class="nx">list</span><span class="p">.</span><span class="nx">New</span><span class="p">(),</span>
<a id="__codelineno-18-11" name="__codelineno-18-11" href="#__codelineno-18-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-18-12" name="__codelineno-18-12" href="#__codelineno-18-12"></a><span class="p">}</span>
<a id="__codelineno-18-13" name="__codelineno-18-13" href="#__codelineno-18-13"></a>
<a id="__codelineno-18-14" name="__codelineno-18-14" href="#__codelineno-18-14"></a><span class="cm">/* 入栈 */</span>
<a id="__codelineno-18-15" name="__codelineno-18-15" href="#__codelineno-18-15"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">push</span><span class="p">(</span><span class="nx">value</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-16" name="__codelineno-18-16" href="#__codelineno-18-16"></a><span class="w">    </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">PushBack</span><span class="p">(</span><span class="nx">value</span><span class="p">)</span>
<a id="__codelineno-18-17" name="__codelineno-18-17" href="#__codelineno-18-17"></a><span class="p">}</span>
<a id="__codelineno-18-18" name="__codelineno-18-18" href="#__codelineno-18-18"></a>
<a id="__codelineno-18-19" name="__codelineno-18-19" href="#__codelineno-18-19"></a><span class="cm">/* 出栈 */</span>
<a id="__codelineno-18-20" name="__codelineno-18-20" href="#__codelineno-18-20"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-21" name="__codelineno-18-21" href="#__codelineno-18-21"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-22" name="__codelineno-18-22" href="#__codelineno-18-22"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="kc">nil</span>
<a id="__codelineno-18-23" name="__codelineno-18-23" href="#__codelineno-18-23"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-18-24" name="__codelineno-18-24" href="#__codelineno-18-24"></a><span class="w">    </span><span class="nx">e</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">Back</span><span class="p">()</span>
<a id="__codelineno-18-25" name="__codelineno-18-25" href="#__codelineno-18-25"></a><span class="w">    </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">Remove</span><span class="p">(</span><span class="nx">e</span><span class="p">)</span>
<a id="__codelineno-18-26" name="__codelineno-18-26" href="#__codelineno-18-26"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">e</span><span class="p">.</span><span class="nx">Value</span>
<a id="__codelineno-18-27" name="__codelineno-18-27" href="#__codelineno-18-27"></a><span class="p">}</span>
<a id="__codelineno-18-28" name="__codelineno-18-28" href="#__codelineno-18-28"></a>
<a id="__codelineno-18-29" name="__codelineno-18-29" href="#__codelineno-18-29"></a><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-18-30" name="__codelineno-18-30" href="#__codelineno-18-30"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">peek</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-31" name="__codelineno-18-31" href="#__codelineno-18-31"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-32" name="__codelineno-18-32" href="#__codelineno-18-32"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="kc">nil</span>
<a id="__codelineno-18-33" name="__codelineno-18-33" href="#__codelineno-18-33"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-18-34" name="__codelineno-18-34" href="#__codelineno-18-34"></a><span class="w">    </span><span class="nx">e</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">Back</span><span class="p">()</span>
<a id="__codelineno-18-35" name="__codelineno-18-35" href="#__codelineno-18-35"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">e</span><span class="p">.</span><span class="nx">Value</span>
<a id="__codelineno-18-36" name="__codelineno-18-36" href="#__codelineno-18-36"></a><span class="p">}</span>
<a id="__codelineno-18-37" name="__codelineno-18-37" href="#__codelineno-18-37"></a>
<a id="__codelineno-18-38" name="__codelineno-18-38" href="#__codelineno-18-38"></a><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-18-39" name="__codelineno-18-39" href="#__codelineno-18-39"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-40" name="__codelineno-18-40" href="#__codelineno-18-40"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">Len</span><span class="p">()</span>
<a id="__codelineno-18-41" name="__codelineno-18-41" href="#__codelineno-18-41"></a><span class="p">}</span>
<a id="__codelineno-18-42" name="__codelineno-18-42" href="#__codelineno-18-42"></a>
<a id="__codelineno-18-43" name="__codelineno-18-43" href="#__codelineno-18-43"></a><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-18-44" name="__codelineno-18-44" href="#__codelineno-18-44"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-45" name="__codelineno-18-45" href="#__codelineno-18-45"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">.</span><span class="nx">Len</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-18-46" name="__codelineno-18-46" href="#__codelineno-18-46"></a><span class="p">}</span>
<a id="__codelineno-18-47" name="__codelineno-18-47" href="#__codelineno-18-47"></a>
<a id="__codelineno-18-48" name="__codelineno-18-48" href="#__codelineno-18-48"></a><span class="cm">/* 获取 List 用于打印 */</span>
<a id="__codelineno-18-49" name="__codelineno-18-49" href="#__codelineno-18-49"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">linkedListStack</span><span class="p">)</span><span class="w"> </span><span class="nx">toList</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="nx">list</span><span class="p">.</span><span class="nx">List</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-50" name="__codelineno-18-50" href="#__codelineno-18-50"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span>
<a id="__codelineno-18-51" name="__codelineno-18-51" href="#__codelineno-18-51"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.swift</span><pre id="__code_19"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_19 > code"></button><code><a id="__codelineno-19-1" name="__codelineno-19-1" href="#__codelineno-19-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-19-2" name="__codelineno-19-2" href="#__codelineno-19-2"></a><span class="kd">class</span> <span class="nc">LinkedListStack</span> <span class="p">{</span>
<a id="__codelineno-19-3" name="__codelineno-19-3" href="#__codelineno-19-3"></a>    <span class="kd">private</span> <span class="kd">var</span> <span class="nv">_peek</span><span class="p">:</span> <span class="n">ListNode</span><span class="p">?</span> <span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-19-4" name="__codelineno-19-4" href="#__codelineno-19-4"></a>    <span class="kd">private</span> <span class="kd">var</span> <span class="nv">_size</span><span class="p">:</span> <span class="nb">Int</span> <span class="c1">// 栈的长度</span>
<a id="__codelineno-19-5" name="__codelineno-19-5" href="#__codelineno-19-5"></a>
<a id="__codelineno-19-6" name="__codelineno-19-6" href="#__codelineno-19-6"></a>    <span class="kd">init</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-19-7" name="__codelineno-19-7" href="#__codelineno-19-7"></a>        <span class="n">_size</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-19-8" name="__codelineno-19-8" href="#__codelineno-19-8"></a>    <span class="p">}</span>
<a id="__codelineno-19-9" name="__codelineno-19-9" href="#__codelineno-19-9"></a>
<a id="__codelineno-19-10" name="__codelineno-19-10" href="#__codelineno-19-10"></a>    <span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-19-11" name="__codelineno-19-11" href="#__codelineno-19-11"></a>    <span class="kd">func</span> <span class="nf">size</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-12" name="__codelineno-19-12" href="#__codelineno-19-12"></a>        <span class="n">_size</span>
<a id="__codelineno-19-13" name="__codelineno-19-13" href="#__codelineno-19-13"></a>    <span class="p">}</span>
<a id="__codelineno-19-14" name="__codelineno-19-14" href="#__codelineno-19-14"></a>
<a id="__codelineno-19-15" name="__codelineno-19-15" href="#__codelineno-19-15"></a>    <span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-19-16" name="__codelineno-19-16" href="#__codelineno-19-16"></a>    <span class="kd">func</span> <span class="nf">isEmpty</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Bool</span> <span class="p">{</span>
<a id="__codelineno-19-17" name="__codelineno-19-17" href="#__codelineno-19-17"></a>        <span class="n">size</span><span class="p">()</span> <span class="p">==</span> <span class="mi">0</span>
<a id="__codelineno-19-18" name="__codelineno-19-18" href="#__codelineno-19-18"></a>    <span class="p">}</span>
<a id="__codelineno-19-19" name="__codelineno-19-19" href="#__codelineno-19-19"></a>
<a id="__codelineno-19-20" name="__codelineno-19-20" href="#__codelineno-19-20"></a>    <span class="cm">/* 入栈 */</span>
<a id="__codelineno-19-21" name="__codelineno-19-21" href="#__codelineno-19-21"></a>    <span class="kd">func</span> <span class="nf">push</span><span class="p">(</span><span class="n">num</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-19-22" name="__codelineno-19-22" href="#__codelineno-19-22"></a>        <span class="kd">let</span> <span class="nv">node</span> <span class="p">=</span> <span class="n">ListNode</span><span class="p">(</span><span class="n">x</span><span class="p">:</span> <span class="n">num</span><span class="p">)</span>
<a id="__codelineno-19-23" name="__codelineno-19-23" href="#__codelineno-19-23"></a>        <span class="n">node</span><span class="p">.</span><span class="n">next</span> <span class="p">=</span> <span class="n">_peek</span>
<a id="__codelineno-19-24" name="__codelineno-19-24" href="#__codelineno-19-24"></a>        <span class="n">_peek</span> <span class="p">=</span> <span class="n">node</span>
<a id="__codelineno-19-25" name="__codelineno-19-25" href="#__codelineno-19-25"></a>        <span class="n">_size</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-19-26" name="__codelineno-19-26" href="#__codelineno-19-26"></a>    <span class="p">}</span>
<a id="__codelineno-19-27" name="__codelineno-19-27" href="#__codelineno-19-27"></a>
<a id="__codelineno-19-28" name="__codelineno-19-28" href="#__codelineno-19-28"></a>    <span class="cm">/* 出栈 */</span>
<a id="__codelineno-19-29" name="__codelineno-19-29" href="#__codelineno-19-29"></a>    <span class="p">@</span><span class="n">discardableResult</span>
<a id="__codelineno-19-30" name="__codelineno-19-30" href="#__codelineno-19-30"></a>    <span class="kd">func</span> <span class="nf">pop</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-31" name="__codelineno-19-31" href="#__codelineno-19-31"></a>        <span class="kd">let</span> <span class="nv">num</span> <span class="p">=</span> <span class="n">peek</span><span class="p">()</span>
<a id="__codelineno-19-32" name="__codelineno-19-32" href="#__codelineno-19-32"></a>        <span class="n">_peek</span> <span class="p">=</span> <span class="n">_peek</span><span class="p">?.</span><span class="n">next</span>
<a id="__codelineno-19-33" name="__codelineno-19-33" href="#__codelineno-19-33"></a>        <span class="n">_size</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-19-34" name="__codelineno-19-34" href="#__codelineno-19-34"></a>        <span class="k">return</span> <span class="n">num</span>
<a id="__codelineno-19-35" name="__codelineno-19-35" href="#__codelineno-19-35"></a>    <span class="p">}</span>
<a id="__codelineno-19-36" name="__codelineno-19-36" href="#__codelineno-19-36"></a>
<a id="__codelineno-19-37" name="__codelineno-19-37" href="#__codelineno-19-37"></a>    <span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-19-38" name="__codelineno-19-38" href="#__codelineno-19-38"></a>    <span class="kd">func</span> <span class="nf">peek</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-39" name="__codelineno-19-39" href="#__codelineno-19-39"></a>        <span class="k">if</span> <span class="bp">isEmpty</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-19-40" name="__codelineno-19-40" href="#__codelineno-19-40"></a>            <span class="bp">fatalError</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-19-41" name="__codelineno-19-41" href="#__codelineno-19-41"></a>        <span class="p">}</span>
<a id="__codelineno-19-42" name="__codelineno-19-42" href="#__codelineno-19-42"></a>        <span class="k">return</span> <span class="n">_peek</span><span class="p">!.</span><span class="n">val</span>
<a id="__codelineno-19-43" name="__codelineno-19-43" href="#__codelineno-19-43"></a>    <span class="p">}</span>
<a id="__codelineno-19-44" name="__codelineno-19-44" href="#__codelineno-19-44"></a>
<a id="__codelineno-19-45" name="__codelineno-19-45" href="#__codelineno-19-45"></a>    <span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-19-46" name="__codelineno-19-46" href="#__codelineno-19-46"></a>    <span class="kd">func</span> <span class="nf">toArray</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="p">[</span><span class="nb">Int</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-19-47" name="__codelineno-19-47" href="#__codelineno-19-47"></a>        <span class="kd">var</span> <span class="nv">node</span> <span class="p">=</span> <span class="n">_peek</span>
<a id="__codelineno-19-48" name="__codelineno-19-48" href="#__codelineno-19-48"></a>        <span class="kd">var</span> <span class="nv">res</span> <span class="p">=</span> <span class="nb">Array</span><span class="p">(</span><span class="n">repeating</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="bp">count</span><span class="p">:</span> <span class="n">size</span><span class="p">())</span>
<a id="__codelineno-19-49" name="__codelineno-19-49" href="#__codelineno-19-49"></a>        <span class="k">for</span> <span class="n">i</span> <span class="k">in</span> <span class="n">res</span><span class="p">.</span><span class="bp">indices</span><span class="p">.</span><span class="n">reversed</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-19-50" name="__codelineno-19-50" href="#__codelineno-19-50"></a>            <span class="n">res</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="p">=</span> <span class="n">node</span><span class="p">!.</span><span class="n">val</span>
<a id="__codelineno-19-51" name="__codelineno-19-51" href="#__codelineno-19-51"></a>            <span class="n">node</span> <span class="p">=</span> <span class="n">node</span><span class="p">?.</span><span class="n">next</span>
<a id="__codelineno-19-52" name="__codelineno-19-52" href="#__codelineno-19-52"></a>        <span class="p">}</span>
<a id="__codelineno-19-53" name="__codelineno-19-53" href="#__codelineno-19-53"></a>        <span class="k">return</span> <span class="n">res</span>
<a id="__codelineno-19-54" name="__codelineno-19-54" href="#__codelineno-19-54"></a>    <span class="p">}</span>
<a id="__codelineno-19-55" name="__codelineno-19-55" href="#__codelineno-19-55"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.js</span><pre id="__code_20"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_20 > code"></button><code><a id="__codelineno-20-1" name="__codelineno-20-1" href="#__codelineno-20-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-20-2" name="__codelineno-20-2" href="#__codelineno-20-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-3" name="__codelineno-20-3" href="#__codelineno-20-3"></a><span class="w">    </span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-20-4" name="__codelineno-20-4" href="#__codelineno-20-4"></a><span class="w">    </span><span class="err">#</span><span class="nx">stkSize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-20-5" name="__codelineno-20-5" href="#__codelineno-20-5"></a>
<a id="__codelineno-20-6" name="__codelineno-20-6" href="#__codelineno-20-6"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-7" name="__codelineno-20-7" href="#__codelineno-20-7"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-20-8" name="__codelineno-20-8" href="#__codelineno-20-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-9" name="__codelineno-20-9" href="#__codelineno-20-9"></a>
<a id="__codelineno-20-10" name="__codelineno-20-10" href="#__codelineno-20-10"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-20-11" name="__codelineno-20-11" href="#__codelineno-20-11"></a><span class="w">    </span><span class="nx">get</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-12" name="__codelineno-20-12" href="#__codelineno-20-12"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stkSize</span><span class="p">;</span>
<a id="__codelineno-20-13" name="__codelineno-20-13" href="#__codelineno-20-13"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-14" name="__codelineno-20-14" href="#__codelineno-20-14"></a>
<a id="__codelineno-20-15" name="__codelineno-20-15" href="#__codelineno-20-15"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-20-16" name="__codelineno-20-16" href="#__codelineno-20-16"></a><span class="w">    </span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-17" name="__codelineno-20-17" href="#__codelineno-20-17"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-20-18" name="__codelineno-20-18" href="#__codelineno-20-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-19" name="__codelineno-20-19" href="#__codelineno-20-19"></a>
<a id="__codelineno-20-20" name="__codelineno-20-20" href="#__codelineno-20-20"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-20-21" name="__codelineno-20-21" href="#__codelineno-20-21"></a><span class="w">    </span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-22" name="__codelineno-20-22" href="#__codelineno-20-22"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nx">ListNode</span><span class="p">(</span><span class="nx">num</span><span class="p">);</span>
<a id="__codelineno-20-23" name="__codelineno-20-23" href="#__codelineno-20-23"></a><span class="w">        </span><span class="nx">node</span><span class="p">.</span><span class="nx">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">;</span>
<a id="__codelineno-20-24" name="__codelineno-20-24" href="#__codelineno-20-24"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="p">;</span>
<a id="__codelineno-20-25" name="__codelineno-20-25" href="#__codelineno-20-25"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-20-26" name="__codelineno-20-26" href="#__codelineno-20-26"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-27" name="__codelineno-20-27" href="#__codelineno-20-27"></a>
<a id="__codelineno-20-28" name="__codelineno-20-28" href="#__codelineno-20-28"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-20-29" name="__codelineno-20-29" href="#__codelineno-20-29"></a><span class="w">    </span><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-30" name="__codelineno-20-30" href="#__codelineno-20-30"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">peek</span><span class="p">();</span>
<a id="__codelineno-20-31" name="__codelineno-20-31" href="#__codelineno-20-31"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">.</span><span class="nx">next</span><span class="p">;</span>
<a id="__codelineno-20-32" name="__codelineno-20-32" href="#__codelineno-20-32"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-20-33" name="__codelineno-20-33" href="#__codelineno-20-33"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">num</span><span class="p">;</span>
<a id="__codelineno-20-34" name="__codelineno-20-34" href="#__codelineno-20-34"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-35" name="__codelineno-20-35" href="#__codelineno-20-35"></a>
<a id="__codelineno-20-36" name="__codelineno-20-36" href="#__codelineno-20-36"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-20-37" name="__codelineno-20-37" href="#__codelineno-20-37"></a><span class="w">    </span><span class="nx">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-38" name="__codelineno-20-38" href="#__codelineno-20-38"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="o">!</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">)</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-20-39" name="__codelineno-20-39" href="#__codelineno-20-39"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-20-40" name="__codelineno-20-40" href="#__codelineno-20-40"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-41" name="__codelineno-20-41" href="#__codelineno-20-41"></a>
<a id="__codelineno-20-42" name="__codelineno-20-42" href="#__codelineno-20-42"></a><span class="w">    </span><span class="cm">/* 将链表转化为 Array 并返回 */</span>
<a id="__codelineno-20-43" name="__codelineno-20-43" href="#__codelineno-20-43"></a><span class="w">    </span><span class="nx">toArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-44" name="__codelineno-20-44" href="#__codelineno-20-44"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stackPeek</span><span class="p">;</span>
<a id="__codelineno-20-45" name="__codelineno-20-45" href="#__codelineno-20-45"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nb">Array</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">);</span>
<a id="__codelineno-20-46" name="__codelineno-20-46" href="#__codelineno-20-46"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">res</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">--</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-47" name="__codelineno-20-47" href="#__codelineno-20-47"></a><span class="w">            </span><span class="nx">res</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-20-48" name="__codelineno-20-48" href="#__codelineno-20-48"></a><span class="w">            </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="p">.</span><span class="nx">next</span><span class="p">;</span>
<a id="__codelineno-20-49" name="__codelineno-20-49" href="#__codelineno-20-49"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-20-50" name="__codelineno-20-50" href="#__codelineno-20-50"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">res</span><span class="p">;</span>
<a id="__codelineno-20-51" name="__codelineno-20-51" href="#__codelineno-20-51"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-20-52" name="__codelineno-20-52" href="#__codelineno-20-52"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.ts</span><pre id="__code_21"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_21 > code"></button><code><a id="__codelineno-21-1" name="__codelineno-21-1" href="#__codelineno-21-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-21-2" name="__codelineno-21-2" href="#__codelineno-21-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-3" name="__codelineno-21-3" href="#__codelineno-21-3"></a><span class="w">    </span><span class="k">private</span><span class="w"> </span><span class="nx">stackPeek</span><span class="o">:</span><span class="w"> </span><span class="kt">ListNode</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-21-4" name="__codelineno-21-4" href="#__codelineno-21-4"></a><span class="w">    </span><span class="k">private</span><span class="w"> </span><span class="nx">stkSize</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-21-5" name="__codelineno-21-5" href="#__codelineno-21-5"></a>
<a id="__codelineno-21-6" name="__codelineno-21-6" href="#__codelineno-21-6"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-7" name="__codelineno-21-7" href="#__codelineno-21-7"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-21-8" name="__codelineno-21-8" href="#__codelineno-21-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-9" name="__codelineno-21-9" href="#__codelineno-21-9"></a>
<a id="__codelineno-21-10" name="__codelineno-21-10" href="#__codelineno-21-10"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-21-11" name="__codelineno-21-11" href="#__codelineno-21-11"></a><span class="w">    </span><span class="nx">get</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-12" name="__codelineno-21-12" href="#__codelineno-21-12"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stkSize</span><span class="p">;</span>
<a id="__codelineno-21-13" name="__codelineno-21-13" href="#__codelineno-21-13"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-14" name="__codelineno-21-14" href="#__codelineno-21-14"></a>
<a id="__codelineno-21-15" name="__codelineno-21-15" href="#__codelineno-21-15"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-21-16" name="__codelineno-21-16" href="#__codelineno-21-16"></a><span class="w">    </span><span class="nx">isEmpty</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">boolean</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-17" name="__codelineno-21-17" href="#__codelineno-21-17"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-21-18" name="__codelineno-21-18" href="#__codelineno-21-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-19" name="__codelineno-21-19" href="#__codelineno-21-19"></a>
<a id="__codelineno-21-20" name="__codelineno-21-20" href="#__codelineno-21-20"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-21-21" name="__codelineno-21-21" href="#__codelineno-21-21"></a><span class="w">    </span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="ow">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-22" name="__codelineno-21-22" href="#__codelineno-21-22"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nx">ListNode</span><span class="p">(</span><span class="nx">num</span><span class="p">);</span>
<a id="__codelineno-21-23" name="__codelineno-21-23" href="#__codelineno-21-23"></a><span class="w">        </span><span class="nx">node</span><span class="p">.</span><span class="nx">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">;</span>
<a id="__codelineno-21-24" name="__codelineno-21-24" href="#__codelineno-21-24"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="p">;</span>
<a id="__codelineno-21-25" name="__codelineno-21-25" href="#__codelineno-21-25"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-21-26" name="__codelineno-21-26" href="#__codelineno-21-26"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-27" name="__codelineno-21-27" href="#__codelineno-21-27"></a>
<a id="__codelineno-21-28" name="__codelineno-21-28" href="#__codelineno-21-28"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-21-29" name="__codelineno-21-29" href="#__codelineno-21-29"></a><span class="w">    </span><span class="nx">pop</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-30" name="__codelineno-21-30" href="#__codelineno-21-30"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">peek</span><span class="p">();</span>
<a id="__codelineno-21-31" name="__codelineno-21-31" href="#__codelineno-21-31"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="o">!</span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">)</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-21-32" name="__codelineno-21-32" href="#__codelineno-21-32"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">.</span><span class="nx">next</span><span class="p">;</span>
<a id="__codelineno-21-33" name="__codelineno-21-33" href="#__codelineno-21-33"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-21-34" name="__codelineno-21-34" href="#__codelineno-21-34"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">num</span><span class="p">;</span>
<a id="__codelineno-21-35" name="__codelineno-21-35" href="#__codelineno-21-35"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-36" name="__codelineno-21-36" href="#__codelineno-21-36"></a>
<a id="__codelineno-21-37" name="__codelineno-21-37" href="#__codelineno-21-37"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-21-38" name="__codelineno-21-38" href="#__codelineno-21-38"></a><span class="w">    </span><span class="nx">peek</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-39" name="__codelineno-21-39" href="#__codelineno-21-39"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="o">!</span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">)</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-21-40" name="__codelineno-21-40" href="#__codelineno-21-40"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-21-41" name="__codelineno-21-41" href="#__codelineno-21-41"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-42" name="__codelineno-21-42" href="#__codelineno-21-42"></a>
<a id="__codelineno-21-43" name="__codelineno-21-43" href="#__codelineno-21-43"></a><span class="w">    </span><span class="cm">/* 将链表转化为 Array 并返回 */</span>
<a id="__codelineno-21-44" name="__codelineno-21-44" href="#__codelineno-21-44"></a><span class="w">    </span><span class="nx">toArray</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">[]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-45" name="__codelineno-21-45" href="#__codelineno-21-45"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stackPeek</span><span class="p">;</span>
<a id="__codelineno-21-46" name="__codelineno-21-46" href="#__codelineno-21-46"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nb">Array</span><span class="o">&lt;</span><span class="kt">number</span><span class="o">&gt;</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">);</span>
<a id="__codelineno-21-47" name="__codelineno-21-47" href="#__codelineno-21-47"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">res</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&gt;=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">--</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-48" name="__codelineno-21-48" href="#__codelineno-21-48"></a><span class="w">            </span><span class="nx">res</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="o">!</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-21-49" name="__codelineno-21-49" href="#__codelineno-21-49"></a><span class="w">            </span><span class="nx">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">node</span><span class="o">!</span><span class="p">.</span><span class="nx">next</span><span class="p">;</span>
<a id="__codelineno-21-50" name="__codelineno-21-50" href="#__codelineno-21-50"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-21-51" name="__codelineno-21-51" href="#__codelineno-21-51"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">res</span><span class="p">;</span>
<a id="__codelineno-21-52" name="__codelineno-21-52" href="#__codelineno-21-52"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-21-53" name="__codelineno-21-53" href="#__codelineno-21-53"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.dart</span><pre id="__code_22"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_22 > code"></button><code><a id="__codelineno-22-1" name="__codelineno-22-1" href="#__codelineno-22-1"></a><span class="cm">/* 基于链表类实现的栈 */</span>
<a id="__codelineno-22-2" name="__codelineno-22-2" href="#__codelineno-22-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">LinkedListStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-3" name="__codelineno-22-3" href="#__codelineno-22-3"></a><span class="w">  </span><span class="n">ListNode</span><span class="o">?</span><span class="w"> </span><span class="n">_stackPeek</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-22-4" name="__codelineno-22-4" href="#__codelineno-22-4"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">_stkSize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-22-5" name="__codelineno-22-5" href="#__codelineno-22-5"></a>
<a id="__codelineno-22-6" name="__codelineno-22-6" href="#__codelineno-22-6"></a><span class="w">  </span><span class="n">LinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-7" name="__codelineno-22-7" href="#__codelineno-22-7"></a><span class="w">    </span><span class="n">_stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-22-8" name="__codelineno-22-8" href="#__codelineno-22-8"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-9" name="__codelineno-22-9" href="#__codelineno-22-9"></a>
<a id="__codelineno-22-10" name="__codelineno-22-10" href="#__codelineno-22-10"></a><span class="w">  </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-22-11" name="__codelineno-22-11" href="#__codelineno-22-11"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-12" name="__codelineno-22-12" href="#__codelineno-22-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stkSize</span><span class="p">;</span>
<a id="__codelineno-22-13" name="__codelineno-22-13" href="#__codelineno-22-13"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-14" name="__codelineno-22-14" href="#__codelineno-22-14"></a>
<a id="__codelineno-22-15" name="__codelineno-22-15" href="#__codelineno-22-15"></a><span class="w">  </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-22-16" name="__codelineno-22-16" href="#__codelineno-22-16"></a><span class="w">  </span><span class="kt">bool</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-17" name="__codelineno-22-17" href="#__codelineno-22-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stkSize</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-22-18" name="__codelineno-22-18" href="#__codelineno-22-18"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-19" name="__codelineno-22-19" href="#__codelineno-22-19"></a>
<a id="__codelineno-22-20" name="__codelineno-22-20" href="#__codelineno-22-20"></a><span class="w">  </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-22-21" name="__codelineno-22-21" href="#__codelineno-22-21"></a><span class="w">  </span><span class="kt">void</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">_num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-22" name="__codelineno-22-22" href="#__codelineno-22-22"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="n">ListNode</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ListNode</span><span class="p">(</span><span class="n">_num</span><span class="p">);</span>
<a id="__codelineno-22-23" name="__codelineno-22-23" href="#__codelineno-22-23"></a><span class="w">    </span><span class="n">node</span><span class="p">.</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_stackPeek</span><span class="p">;</span>
<a id="__codelineno-22-24" name="__codelineno-22-24" href="#__codelineno-22-24"></a><span class="w">    </span><span class="n">_stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span>
<a id="__codelineno-22-25" name="__codelineno-22-25" href="#__codelineno-22-25"></a><span class="w">    </span><span class="n">_stkSize</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-22-26" name="__codelineno-22-26" href="#__codelineno-22-26"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-27" name="__codelineno-22-27" href="#__codelineno-22-27"></a>
<a id="__codelineno-22-28" name="__codelineno-22-28" href="#__codelineno-22-28"></a><span class="w">  </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-22-29" name="__codelineno-22-29" href="#__codelineno-22-29"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-30" name="__codelineno-22-30" href="#__codelineno-22-30"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">_num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span><span class="p">();</span>
<a id="__codelineno-22-31" name="__codelineno-22-31" href="#__codelineno-22-31"></a><span class="w">    </span><span class="n">_stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_stackPeek</span><span class="o">!</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-22-32" name="__codelineno-22-32" href="#__codelineno-22-32"></a><span class="w">    </span><span class="n">_stkSize</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-22-33" name="__codelineno-22-33" href="#__codelineno-22-33"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_num</span><span class="p">;</span>
<a id="__codelineno-22-34" name="__codelineno-22-34" href="#__codelineno-22-34"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-35" name="__codelineno-22-35" href="#__codelineno-22-35"></a>
<a id="__codelineno-22-36" name="__codelineno-22-36" href="#__codelineno-22-36"></a><span class="w">  </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-22-37" name="__codelineno-22-37" href="#__codelineno-22-37"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-38" name="__codelineno-22-38" href="#__codelineno-22-38"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">_stackPeek</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-39" name="__codelineno-22-39" href="#__codelineno-22-39"></a><span class="w">      </span><span class="k">throw</span><span class="w"> </span><span class="n">Exception</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-22-40" name="__codelineno-22-40" href="#__codelineno-22-40"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-22-41" name="__codelineno-22-41" href="#__codelineno-22-41"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stackPeek</span><span class="o">!</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-22-42" name="__codelineno-22-42" href="#__codelineno-22-42"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-43" name="__codelineno-22-43" href="#__codelineno-22-43"></a>
<a id="__codelineno-22-44" name="__codelineno-22-44" href="#__codelineno-22-44"></a><span class="w">  </span><span class="cm">/* 将链表转化为 List 并返回 */</span>
<a id="__codelineno-22-45" name="__codelineno-22-45" href="#__codelineno-22-45"></a><span class="w">  </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">toList</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-46" name="__codelineno-22-46" href="#__codelineno-22-46"></a><span class="w">    </span><span class="n">ListNode</span><span class="o">?</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_stackPeek</span><span class="p">;</span>
<a id="__codelineno-22-47" name="__codelineno-22-47" href="#__codelineno-22-47"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">list</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-22-48" name="__codelineno-22-48" href="#__codelineno-22-48"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">node</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-49" name="__codelineno-22-49" href="#__codelineno-22-49"></a><span class="w">      </span><span class="n">list</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">node</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-22-50" name="__codelineno-22-50" href="#__codelineno-22-50"></a><span class="w">      </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-22-51" name="__codelineno-22-51" href="#__codelineno-22-51"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-22-52" name="__codelineno-22-52" href="#__codelineno-22-52"></a><span class="w">    </span><span class="n">list</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">list</span><span class="p">.</span><span class="n">reversed</span><span class="p">.</span><span class="n">toList</span><span class="p">();</span>
<a id="__codelineno-22-53" name="__codelineno-22-53" href="#__codelineno-22-53"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">list</span><span class="p">;</span>
<a id="__codelineno-22-54" name="__codelineno-22-54" href="#__codelineno-22-54"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-22-55" name="__codelineno-22-55" href="#__codelineno-22-55"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.rs</span><pre id="__code_23"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_23 > code"></button><code><a id="__codelineno-23-1" name="__codelineno-23-1" href="#__codelineno-23-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-23-2" name="__codelineno-23-2" href="#__codelineno-23-2"></a><span class="cp">#[allow(dead_code)]</span>
<a id="__codelineno-23-3" name="__codelineno-23-3" href="#__codelineno-23-3"></a><span class="k">pub</span><span class="w"> </span><span class="k">struct</span> <span class="nc">LinkedListStack</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-4" name="__codelineno-23-4" href="#__codelineno-23-4"></a><span class="w">    </span><span class="n">stack_peek</span>: <span class="nb">Option</span><span class="o">&lt;</span><span class="n">Rc</span><span class="o">&lt;</span><span class="n">RefCell</span><span class="o">&lt;</span><span class="n">ListNode</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;&gt;&gt;&gt;</span><span class="p">,</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-23-5" name="__codelineno-23-5" href="#__codelineno-23-5"></a><span class="w">    </span><span class="n">stk_size</span>: <span class="kt">usize</span><span class="p">,</span><span class="w">                              </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-23-6" name="__codelineno-23-6" href="#__codelineno-23-6"></a><span class="p">}</span>
<a id="__codelineno-23-7" name="__codelineno-23-7" href="#__codelineno-23-7"></a>
<a id="__codelineno-23-8" name="__codelineno-23-8" href="#__codelineno-23-8"></a><span class="k">impl</span><span class="o">&lt;</span><span class="n">T</span>: <span class="nb">Copy</span><span class="o">&gt;</span><span class="w"> </span><span class="n">LinkedListStack</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-9" name="__codelineno-23-9" href="#__codelineno-23-9"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">new</span><span class="p">()</span><span class="w"> </span>-&gt; <span class="nc">Self</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-10" name="__codelineno-23-10" href="#__codelineno-23-10"></a><span class="w">        </span><span class="bp">Self</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-11" name="__codelineno-23-11" href="#__codelineno-23-11"></a><span class="w">            </span><span class="n">stack_peek</span>: <span class="nb">None</span><span class="p">,</span>
<a id="__codelineno-23-12" name="__codelineno-23-12" href="#__codelineno-23-12"></a><span class="w">            </span><span class="n">stk_size</span>: <span class="mi">0</span><span class="p">,</span>
<a id="__codelineno-23-13" name="__codelineno-23-13" href="#__codelineno-23-13"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-23-14" name="__codelineno-23-14" href="#__codelineno-23-14"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-15" name="__codelineno-23-15" href="#__codelineno-23-15"></a>
<a id="__codelineno-23-16" name="__codelineno-23-16" href="#__codelineno-23-16"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-23-17" name="__codelineno-23-17" href="#__codelineno-23-17"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">size</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-23-18" name="__codelineno-23-18" href="#__codelineno-23-18"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">stk_size</span><span class="p">;</span>
<a id="__codelineno-23-19" name="__codelineno-23-19" href="#__codelineno-23-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-20" name="__codelineno-23-20" href="#__codelineno-23-20"></a>
<a id="__codelineno-23-21" name="__codelineno-23-21" href="#__codelineno-23-21"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-23-22" name="__codelineno-23-22" href="#__codelineno-23-22"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">is_empty</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">bool</span> <span class="p">{</span>
<a id="__codelineno-23-23" name="__codelineno-23-23" href="#__codelineno-23-23"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-23-24" name="__codelineno-23-24" href="#__codelineno-23-24"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-25" name="__codelineno-23-25" href="#__codelineno-23-25"></a>
<a id="__codelineno-23-26" name="__codelineno-23-26" href="#__codelineno-23-26"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-23-27" name="__codelineno-23-27" href="#__codelineno-23-27"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">push</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">num</span>: <span class="nc">T</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-28" name="__codelineno-23-28" href="#__codelineno-23-28"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ListNode</span>::<span class="n">new</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-23-29" name="__codelineno-23-29" href="#__codelineno-23-29"></a><span class="w">        </span><span class="n">node</span><span class="p">.</span><span class="n">borrow_mut</span><span class="p">().</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="p">.</span><span class="n">take</span><span class="p">();</span>
<a id="__codelineno-23-30" name="__codelineno-23-30" href="#__codelineno-23-30"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Some</span><span class="p">(</span><span class="n">node</span><span class="p">);</span>
<a id="__codelineno-23-31" name="__codelineno-23-31" href="#__codelineno-23-31"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stk_size</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-23-32" name="__codelineno-23-32" href="#__codelineno-23-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-33" name="__codelineno-23-33" href="#__codelineno-23-33"></a>
<a id="__codelineno-23-34" name="__codelineno-23-34" href="#__codelineno-23-34"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-23-35" name="__codelineno-23-35" href="#__codelineno-23-35"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">pop</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-36" name="__codelineno-23-36" href="#__codelineno-23-36"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="p">.</span><span class="n">take</span><span class="p">().</span><span class="n">map</span><span class="p">(</span><span class="o">|</span><span class="n">old_head</span><span class="o">|</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-37" name="__codelineno-23-37" href="#__codelineno-23-37"></a><span class="w">            </span><span class="k">match</span><span class="w"> </span><span class="n">old_head</span><span class="p">.</span><span class="n">borrow_mut</span><span class="p">().</span><span class="n">next</span><span class="p">.</span><span class="n">take</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-38" name="__codelineno-23-38" href="#__codelineno-23-38"></a><span class="w">                </span><span class="nb">Some</span><span class="p">(</span><span class="n">new_head</span><span class="p">)</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-39" name="__codelineno-23-39" href="#__codelineno-23-39"></a><span class="w">                    </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Some</span><span class="p">(</span><span class="n">new_head</span><span class="p">);</span>
<a id="__codelineno-23-40" name="__codelineno-23-40" href="#__codelineno-23-40"></a><span class="w">                </span><span class="p">}</span>
<a id="__codelineno-23-41" name="__codelineno-23-41" href="#__codelineno-23-41"></a><span class="w">                </span><span class="nb">None</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-42" name="__codelineno-23-42" href="#__codelineno-23-42"></a><span class="w">                    </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">None</span><span class="p">;</span>
<a id="__codelineno-23-43" name="__codelineno-23-43" href="#__codelineno-23-43"></a><span class="w">                </span><span class="p">}</span>
<a id="__codelineno-23-44" name="__codelineno-23-44" href="#__codelineno-23-44"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-23-45" name="__codelineno-23-45" href="#__codelineno-23-45"></a><span class="w">            </span><span class="bp">self</span><span class="p">.</span><span class="n">stk_size</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-23-46" name="__codelineno-23-46" href="#__codelineno-23-46"></a><span class="w">            </span><span class="n">Rc</span>::<span class="n">try_unwrap</span><span class="p">(</span><span class="n">old_head</span><span class="p">).</span><span class="n">ok</span><span class="p">().</span><span class="n">unwrap</span><span class="p">().</span><span class="n">into_inner</span><span class="p">().</span><span class="n">val</span>
<a id="__codelineno-23-47" name="__codelineno-23-47" href="#__codelineno-23-47"></a><span class="w">        </span><span class="p">})</span>
<a id="__codelineno-23-48" name="__codelineno-23-48" href="#__codelineno-23-48"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-49" name="__codelineno-23-49" href="#__codelineno-23-49"></a>
<a id="__codelineno-23-50" name="__codelineno-23-50" href="#__codelineno-23-50"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-23-51" name="__codelineno-23-51" href="#__codelineno-23-51"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">peek</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;&amp;</span><span class="n">Rc</span><span class="o">&lt;</span><span class="n">RefCell</span><span class="o">&lt;</span><span class="n">ListNode</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;&gt;&gt;&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-52" name="__codelineno-23-52" href="#__codelineno-23-52"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack_peek</span><span class="p">.</span><span class="n">as_ref</span><span class="p">()</span>
<a id="__codelineno-23-53" name="__codelineno-23-53" href="#__codelineno-23-53"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-54" name="__codelineno-23-54" href="#__codelineno-23-54"></a>
<a id="__codelineno-23-55" name="__codelineno-23-55" href="#__codelineno-23-55"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-23-56" name="__codelineno-23-56" href="#__codelineno-23-56"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">to_array</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">head</span>: <span class="nb">Option</span><span class="o">&lt;&amp;</span><span class="n">Rc</span><span class="o">&lt;</span><span class="n">RefCell</span><span class="o">&lt;</span><span class="n">ListNode</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;&gt;&gt;&gt;</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Vec</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-57" name="__codelineno-23-57" href="#__codelineno-23-57"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="kd">let</span><span class="w"> </span><span class="nb">Some</span><span class="p">(</span><span class="n">node</span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">head</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-23-58" name="__codelineno-23-58" href="#__codelineno-23-58"></a><span class="w">            </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">nums</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">to_array</span><span class="p">(</span><span class="n">node</span><span class="p">.</span><span class="n">borrow</span><span class="p">().</span><span class="n">next</span><span class="p">.</span><span class="n">as_ref</span><span class="p">());</span>
<a id="__codelineno-23-59" name="__codelineno-23-59" href="#__codelineno-23-59"></a><span class="w">            </span><span class="n">nums</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">node</span><span class="p">.</span><span class="n">borrow</span><span class="p">().</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-23-60" name="__codelineno-23-60" href="#__codelineno-23-60"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">nums</span><span class="p">;</span>
<a id="__codelineno-23-61" name="__codelineno-23-61" href="#__codelineno-23-61"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-23-62" name="__codelineno-23-62" href="#__codelineno-23-62"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nb">Vec</span>::<span class="n">new</span><span class="p">();</span>
<a id="__codelineno-23-63" name="__codelineno-23-63" href="#__codelineno-23-63"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-23-64" name="__codelineno-23-64" href="#__codelineno-23-64"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.c</span><pre id="__code_24"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_24 > code"></button><code><a id="__codelineno-24-1" name="__codelineno-24-1" href="#__codelineno-24-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-24-2" name="__codelineno-24-2" href="#__codelineno-24-2"></a><span class="k">typedef</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-3" name="__codelineno-24-3" href="#__codelineno-24-3"></a><span class="w">    </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">top</span><span class="p">;</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-24-4" name="__codelineno-24-4" href="#__codelineno-24-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">;</span><span class="w">      </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-24-5" name="__codelineno-24-5" href="#__codelineno-24-5"></a><span class="p">}</span><span class="w"> </span><span class="n">LinkedListStack</span><span class="p">;</span>
<a id="__codelineno-24-6" name="__codelineno-24-6" href="#__codelineno-24-6"></a>
<a id="__codelineno-24-7" name="__codelineno-24-7" href="#__codelineno-24-7"></a><span class="cm">/* 构造函数 */</span>
<a id="__codelineno-24-8" name="__codelineno-24-8" href="#__codelineno-24-8"></a><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="nf">newLinkedListStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-9" name="__codelineno-24-9" href="#__codelineno-24-9"></a><span class="w">    </span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="p">));</span>
<a id="__codelineno-24-10" name="__codelineno-24-10" href="#__codelineno-24-10"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">;</span>
<a id="__codelineno-24-11" name="__codelineno-24-11" href="#__codelineno-24-11"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-24-12" name="__codelineno-24-12" href="#__codelineno-24-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">s</span><span class="p">;</span>
<a id="__codelineno-24-13" name="__codelineno-24-13" href="#__codelineno-24-13"></a><span class="p">}</span>
<a id="__codelineno-24-14" name="__codelineno-24-14" href="#__codelineno-24-14"></a>
<a id="__codelineno-24-15" name="__codelineno-24-15" href="#__codelineno-24-15"></a><span class="cm">/* 析构函数 */</span>
<a id="__codelineno-24-16" name="__codelineno-24-16" href="#__codelineno-24-16"></a><span class="kt">void</span><span class="w"> </span><span class="nf">delLinkedListStack</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-17" name="__codelineno-24-17" href="#__codelineno-24-17"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-18" name="__codelineno-24-18" href="#__codelineno-24-18"></a><span class="w">        </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">n</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="o">-&gt;</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-24-19" name="__codelineno-24-19" href="#__codelineno-24-19"></a><span class="w">        </span><span class="n">free</span><span class="p">(</span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="p">);</span>
<a id="__codelineno-24-20" name="__codelineno-24-20" href="#__codelineno-24-20"></a><span class="w">        </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">n</span><span class="p">;</span>
<a id="__codelineno-24-21" name="__codelineno-24-21" href="#__codelineno-24-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-24-22" name="__codelineno-24-22" href="#__codelineno-24-22"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">s</span><span class="p">);</span>
<a id="__codelineno-24-23" name="__codelineno-24-23" href="#__codelineno-24-23"></a><span class="p">}</span>
<a id="__codelineno-24-24" name="__codelineno-24-24" href="#__codelineno-24-24"></a>
<a id="__codelineno-24-25" name="__codelineno-24-25" href="#__codelineno-24-25"></a><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-24-26" name="__codelineno-24-26" href="#__codelineno-24-26"></a><span class="kt">int</span><span class="w"> </span><span class="nf">size</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-27" name="__codelineno-24-27" href="#__codelineno-24-27"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">size</span><span class="p">;</span>
<a id="__codelineno-24-28" name="__codelineno-24-28" href="#__codelineno-24-28"></a><span class="p">}</span>
<a id="__codelineno-24-29" name="__codelineno-24-29" href="#__codelineno-24-29"></a>
<a id="__codelineno-24-30" name="__codelineno-24-30" href="#__codelineno-24-30"></a><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-24-31" name="__codelineno-24-31" href="#__codelineno-24-31"></a><span class="kt">bool</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-32" name="__codelineno-24-32" href="#__codelineno-24-32"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-24-33" name="__codelineno-24-33" href="#__codelineno-24-33"></a><span class="p">}</span>
<a id="__codelineno-24-34" name="__codelineno-24-34" href="#__codelineno-24-34"></a>
<a id="__codelineno-24-35" name="__codelineno-24-35" href="#__codelineno-24-35"></a><span class="cm">/* 入栈 */</span>
<a id="__codelineno-24-36" name="__codelineno-24-36" href="#__codelineno-24-36"></a><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-37" name="__codelineno-24-37" href="#__codelineno-24-37"></a><span class="w">    </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="p">)</span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">ListNode</span><span class="p">));</span>
<a id="__codelineno-24-38" name="__codelineno-24-38" href="#__codelineno-24-38"></a><span class="w">    </span><span class="n">node</span><span class="o">-&gt;</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="p">;</span><span class="w"> </span><span class="c1">// 更新新加节点指针域</span>
<a id="__codelineno-24-39" name="__codelineno-24-39" href="#__codelineno-24-39"></a><span class="w">    </span><span class="n">node</span><span class="o">-&gt;</span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">num</span><span class="p">;</span><span class="w">     </span><span class="c1">// 更新新加节点数据域</span>
<a id="__codelineno-24-40" name="__codelineno-24-40" href="#__codelineno-24-40"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span><span class="w">       </span><span class="c1">// 更新栈顶</span>
<a id="__codelineno-24-41" name="__codelineno-24-41" href="#__codelineno-24-41"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">++</span><span class="p">;</span><span class="w">           </span><span class="c1">// 更新栈大小</span>
<a id="__codelineno-24-42" name="__codelineno-24-42" href="#__codelineno-24-42"></a><span class="p">}</span>
<a id="__codelineno-24-43" name="__codelineno-24-43" href="#__codelineno-24-43"></a>
<a id="__codelineno-24-44" name="__codelineno-24-44" href="#__codelineno-24-44"></a><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-24-45" name="__codelineno-24-45" href="#__codelineno-24-45"></a><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-46" name="__codelineno-24-46" href="#__codelineno-24-46"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">s</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-47" name="__codelineno-24-47" href="#__codelineno-24-47"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"栈为空</span><span class="se">\n</span><span class="s">"</span><span class="p">);</span>
<a id="__codelineno-24-48" name="__codelineno-24-48" href="#__codelineno-24-48"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">INT_MAX</span><span class="p">;</span>
<a id="__codelineno-24-49" name="__codelineno-24-49" href="#__codelineno-24-49"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-24-50" name="__codelineno-24-50" href="#__codelineno-24-50"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-24-51" name="__codelineno-24-51" href="#__codelineno-24-51"></a><span class="p">}</span>
<a id="__codelineno-24-52" name="__codelineno-24-52" href="#__codelineno-24-52"></a>
<a id="__codelineno-24-53" name="__codelineno-24-53" href="#__codelineno-24-53"></a><span class="cm">/* 出栈 */</span>
<a id="__codelineno-24-54" name="__codelineno-24-54" href="#__codelineno-24-54"></a><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">(</span><span class="n">LinkedListStack</span><span class="w"> </span><span class="o">*</span><span class="n">s</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-55" name="__codelineno-24-55" href="#__codelineno-24-55"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span><span class="p">(</span><span class="n">s</span><span class="p">);</span>
<a id="__codelineno-24-56" name="__codelineno-24-56" href="#__codelineno-24-56"></a><span class="w">    </span><span class="n">ListNode</span><span class="w"> </span><span class="o">*</span><span class="n">tmp</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="p">;</span>
<a id="__codelineno-24-57" name="__codelineno-24-57" href="#__codelineno-24-57"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">top</span><span class="o">-&gt;</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-24-58" name="__codelineno-24-58" href="#__codelineno-24-58"></a><span class="w">    </span><span class="c1">// 释放内存</span>
<a id="__codelineno-24-59" name="__codelineno-24-59" href="#__codelineno-24-59"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">tmp</span><span class="p">);</span>
<a id="__codelineno-24-60" name="__codelineno-24-60" href="#__codelineno-24-60"></a><span class="w">    </span><span class="n">s</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-24-61" name="__codelineno-24-61" href="#__codelineno-24-61"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-24-62" name="__codelineno-24-62" href="#__codelineno-24-62"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.kt</span><pre id="__code_25"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_25 > code"></button><code><a id="__codelineno-25-1" name="__codelineno-25-1" href="#__codelineno-25-1"></a><span class="cm">/* 基于链表实现的栈 */</span>
<a id="__codelineno-25-2" name="__codelineno-25-2" href="#__codelineno-25-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">LinkedListStack</span><span class="p">(</span>
<a id="__codelineno-25-3" name="__codelineno-25-3" href="#__codelineno-25-3"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kd">var</span><span class="w"> </span><span class="nv">stackPeek</span><span class="p">:</span><span class="w"> </span><span class="n">ListNode? </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">,</span><span class="w"> </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-25-4" name="__codelineno-25-4" href="#__codelineno-25-4"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kd">var</span><span class="w"> </span><span class="nv">stkSize</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-25-5" name="__codelineno-25-5" href="#__codelineno-25-5"></a><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-6" name="__codelineno-25-6" href="#__codelineno-25-6"></a>
<a id="__codelineno-25-7" name="__codelineno-25-7" href="#__codelineno-25-7"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-25-8" name="__codelineno-25-8" href="#__codelineno-25-8"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">size</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-9" name="__codelineno-25-9" href="#__codelineno-25-9"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stkSize</span>
<a id="__codelineno-25-10" name="__codelineno-25-10" href="#__codelineno-25-10"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-11" name="__codelineno-25-11" href="#__codelineno-25-11"></a>
<a id="__codelineno-25-12" name="__codelineno-25-12" href="#__codelineno-25-12"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-25-13" name="__codelineno-25-13" href="#__codelineno-25-13"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">():</span><span class="w"> </span><span class="kt">Boolean</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-14" name="__codelineno-25-14" href="#__codelineno-25-14"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-25-15" name="__codelineno-25-15" href="#__codelineno-25-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-16" name="__codelineno-25-16" href="#__codelineno-25-16"></a>
<a id="__codelineno-25-17" name="__codelineno-25-17" href="#__codelineno-25-17"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-25-18" name="__codelineno-25-18" href="#__codelineno-25-18"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">num</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-19" name="__codelineno-25-19" href="#__codelineno-25-19"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ListNode</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<a id="__codelineno-25-20" name="__codelineno-25-20" href="#__codelineno-25-20"></a><span class="w">        </span><span class="n">node</span><span class="p">.</span><span class="na">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span>
<a id="__codelineno-25-21" name="__codelineno-25-21" href="#__codelineno-25-21"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span>
<a id="__codelineno-25-22" name="__codelineno-25-22" href="#__codelineno-25-22"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">++</span>
<a id="__codelineno-25-23" name="__codelineno-25-23" href="#__codelineno-25-23"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-24" name="__codelineno-25-24" href="#__codelineno-25-24"></a>
<a id="__codelineno-25-25" name="__codelineno-25-25" href="#__codelineno-25-25"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-25-26" name="__codelineno-25-26" href="#__codelineno-25-26"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">pop</span><span class="p">():</span><span class="w"> </span><span class="kt">Int?</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-27" name="__codelineno-25-27" href="#__codelineno-25-27"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span><span class="p">()</span>
<a id="__codelineno-25-28" name="__codelineno-25-28" href="#__codelineno-25-28"></a><span class="w">        </span><span class="n">stackPeek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span><span class="o">?.</span><span class="na">next</span>
<a id="__codelineno-25-29" name="__codelineno-25-29" href="#__codelineno-25-29"></a><span class="w">        </span><span class="n">stkSize</span><span class="o">--</span>
<a id="__codelineno-25-30" name="__codelineno-25-30" href="#__codelineno-25-30"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">num</span>
<a id="__codelineno-25-31" name="__codelineno-25-31" href="#__codelineno-25-31"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-32" name="__codelineno-25-32" href="#__codelineno-25-32"></a>
<a id="__codelineno-25-33" name="__codelineno-25-33" href="#__codelineno-25-33"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-25-34" name="__codelineno-25-34" href="#__codelineno-25-34"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">peek</span><span class="p">():</span><span class="w"> </span><span class="kt">Int?</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-35" name="__codelineno-25-35" href="#__codelineno-25-35"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">()</span>
<a id="__codelineno-25-36" name="__codelineno-25-36" href="#__codelineno-25-36"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stackPeek</span><span class="o">?.</span><span class="na">_val</span>
<a id="__codelineno-25-37" name="__codelineno-25-37" href="#__codelineno-25-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-38" name="__codelineno-25-38" href="#__codelineno-25-38"></a>
<a id="__codelineno-25-39" name="__codelineno-25-39" href="#__codelineno-25-39"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-25-40" name="__codelineno-25-40" href="#__codelineno-25-40"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">toArray</span><span class="p">():</span><span class="w"> </span><span class="n">IntArray</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-41" name="__codelineno-25-41" href="#__codelineno-25-41"></a><span class="w">        </span><span class="kd">var</span><span class="w"> </span><span class="nv">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">stackPeek</span>
<a id="__codelineno-25-42" name="__codelineno-25-42" href="#__codelineno-25-42"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">IntArray</span><span class="p">(</span><span class="n">size</span><span class="p">())</span>
<a id="__codelineno-25-43" name="__codelineno-25-43" href="#__codelineno-25-43"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">res</span><span class="p">.</span><span class="na">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="w"> </span><span class="n">downTo</span><span class="w"> </span><span class="m">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-44" name="__codelineno-25-44" href="#__codelineno-25-44"></a><span class="w">            </span><span class="n">res</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="o">?.</span><span class="na">_val</span><span class="o">!!</span>
<a id="__codelineno-25-45" name="__codelineno-25-45" href="#__codelineno-25-45"></a><span class="w">            </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="na">next</span>
<a id="__codelineno-25-46" name="__codelineno-25-46" href="#__codelineno-25-46"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-25-47" name="__codelineno-25-47" href="#__codelineno-25-47"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">res</span>
<a id="__codelineno-25-48" name="__codelineno-25-48" href="#__codelineno-25-48"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-25-49" name="__codelineno-25-49" href="#__codelineno-25-49"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.rb</span><pre id="__code_26"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_26 > code"></button><code><a id="__codelineno-26-1" name="__codelineno-26-1" href="#__codelineno-26-1"></a><span class="c1">### 基于链表实现的栈 ###</span>
<a id="__codelineno-26-2" name="__codelineno-26-2" href="#__codelineno-26-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">LinkedListStack</span>
<a id="__codelineno-26-3" name="__codelineno-26-3" href="#__codelineno-26-3"></a><span class="w">  </span><span class="kp">attr_reader</span><span class="w"> </span><span class="ss">:size</span>
<a id="__codelineno-26-4" name="__codelineno-26-4" href="#__codelineno-26-4"></a>
<a id="__codelineno-26-5" name="__codelineno-26-5" href="#__codelineno-26-5"></a><span class="w">  </span><span class="c1">### 构造方法 ###</span>
<a id="__codelineno-26-6" name="__codelineno-26-6" href="#__codelineno-26-6"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">initialize</span>
<a id="__codelineno-26-7" name="__codelineno-26-7" href="#__codelineno-26-7"></a><span class="w">    </span><span class="vi">@size</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-26-8" name="__codelineno-26-8" href="#__codelineno-26-8"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-9" name="__codelineno-26-9" href="#__codelineno-26-9"></a>
<a id="__codelineno-26-10" name="__codelineno-26-10" href="#__codelineno-26-10"></a><span class="w">  </span><span class="c1">### 判断栈是否为空 ###</span>
<a id="__codelineno-26-11" name="__codelineno-26-11" href="#__codelineno-26-11"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">is_empty?</span>
<a id="__codelineno-26-12" name="__codelineno-26-12" href="#__codelineno-26-12"></a><span class="w">    </span><span class="vi">@peek</span><span class="o">.</span><span class="n">nil?</span>
<a id="__codelineno-26-13" name="__codelineno-26-13" href="#__codelineno-26-13"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-14" name="__codelineno-26-14" href="#__codelineno-26-14"></a>
<a id="__codelineno-26-15" name="__codelineno-26-15" href="#__codelineno-26-15"></a><span class="w">  </span><span class="c1">### 入栈 ###</span>
<a id="__codelineno-26-16" name="__codelineno-26-16" href="#__codelineno-26-16"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-26-17" name="__codelineno-26-17" href="#__codelineno-26-17"></a><span class="w">    </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="no">ListNode</span><span class="o">.</span><span class="n">new</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-26-18" name="__codelineno-26-18" href="#__codelineno-26-18"></a><span class="w">    </span><span class="n">node</span><span class="o">.</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="vi">@peek</span>
<a id="__codelineno-26-19" name="__codelineno-26-19" href="#__codelineno-26-19"></a><span class="w">    </span><span class="vi">@peek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span>
<a id="__codelineno-26-20" name="__codelineno-26-20" href="#__codelineno-26-20"></a><span class="w">    </span><span class="vi">@size</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-26-21" name="__codelineno-26-21" href="#__codelineno-26-21"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-22" name="__codelineno-26-22" href="#__codelineno-26-22"></a>
<a id="__codelineno-26-23" name="__codelineno-26-23" href="#__codelineno-26-23"></a><span class="w">  </span><span class="c1">### 出栈 ###</span>
<a id="__codelineno-26-24" name="__codelineno-26-24" href="#__codelineno-26-24"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">pop</span>
<a id="__codelineno-26-25" name="__codelineno-26-25" href="#__codelineno-26-25"></a><span class="w">    </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span>
<a id="__codelineno-26-26" name="__codelineno-26-26" href="#__codelineno-26-26"></a><span class="w">    </span><span class="vi">@peek</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="vi">@peek</span><span class="o">.</span><span class="n">next</span>
<a id="__codelineno-26-27" name="__codelineno-26-27" href="#__codelineno-26-27"></a><span class="w">    </span><span class="vi">@size</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-26-28" name="__codelineno-26-28" href="#__codelineno-26-28"></a><span class="w">    </span><span class="n">num</span>
<a id="__codelineno-26-29" name="__codelineno-26-29" href="#__codelineno-26-29"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-30" name="__codelineno-26-30" href="#__codelineno-26-30"></a>
<a id="__codelineno-26-31" name="__codelineno-26-31" href="#__codelineno-26-31"></a><span class="w">  </span><span class="c1">### 访问栈顶元素 ###</span>
<a id="__codelineno-26-32" name="__codelineno-26-32" href="#__codelineno-26-32"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">peek</span>
<a id="__codelineno-26-33" name="__codelineno-26-33" href="#__codelineno-26-33"></a><span class="w">    </span><span class="k">raise</span><span class="w"> </span><span class="no">IndexError</span><span class="p">,</span><span class="w"> </span><span class="s1">'栈为空'</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">is_empty?</span>
<a id="__codelineno-26-34" name="__codelineno-26-34" href="#__codelineno-26-34"></a>
<a id="__codelineno-26-35" name="__codelineno-26-35" href="#__codelineno-26-35"></a><span class="w">    </span><span class="vi">@peek</span><span class="o">.</span><span class="n">val</span>
<a id="__codelineno-26-36" name="__codelineno-26-36" href="#__codelineno-26-36"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-37" name="__codelineno-26-37" href="#__codelineno-26-37"></a>
<a id="__codelineno-26-38" name="__codelineno-26-38" href="#__codelineno-26-38"></a><span class="w">  </span><span class="c1">### 将链表转化为 Array 并反回 ###</span>
<a id="__codelineno-26-39" name="__codelineno-26-39" href="#__codelineno-26-39"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">to_array</span>
<a id="__codelineno-26-40" name="__codelineno-26-40" href="#__codelineno-26-40"></a><span class="w">    </span><span class="n">arr</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[]</span>
<a id="__codelineno-26-41" name="__codelineno-26-41" href="#__codelineno-26-41"></a><span class="w">    </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="vi">@peek</span>
<a id="__codelineno-26-42" name="__codelineno-26-42" href="#__codelineno-26-42"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="n">node</span>
<a id="__codelineno-26-43" name="__codelineno-26-43" href="#__codelineno-26-43"></a><span class="w">      </span><span class="n">arr</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">node</span><span class="o">.</span><span class="n">val</span>
<a id="__codelineno-26-44" name="__codelineno-26-44" href="#__codelineno-26-44"></a><span class="w">      </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="o">.</span><span class="n">next</span>
<a id="__codelineno-26-45" name="__codelineno-26-45" href="#__codelineno-26-45"></a><span class="w">    </span><span class="k">end</span>
<a id="__codelineno-26-46" name="__codelineno-26-46" href="#__codelineno-26-46"></a><span class="w">    </span><span class="n">arr</span><span class="o">.</span><span class="n">reverse</span>
<a id="__codelineno-26-47" name="__codelineno-26-47" href="#__codelineno-26-47"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-26-48" name="__codelineno-26-48" href="#__codelineno-26-48"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">linkedlist_stack.zig</span><pre id="__code_27"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_27 > code"></button><code><a id="__codelineno-27-1" name="__codelineno-27-1" href="#__codelineno-27-1"></a><span class="c1">// 基于链表实现的栈</span>
<a id="__codelineno-27-2" name="__codelineno-27-2" href="#__codelineno-27-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">LinkedListStack</span><span class="p">(</span><span class="kr">comptime</span><span class="w"> </span><span class="n">T</span><span class="o">:</span><span class="w"> </span><span class="kt">type</span><span class="p">)</span><span class="w"> </span><span class="kt">type</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-3" name="__codelineno-27-3" href="#__codelineno-27-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-4" name="__codelineno-27-4" href="#__codelineno-27-4"></a><span class="w">        </span><span class="kr">const</span><span class="w"> </span><span class="n">Self</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">@This</span><span class="p">();</span>
<a id="__codelineno-27-5" name="__codelineno-27-5" href="#__codelineno-27-5"></a>
<a id="__codelineno-27-6" name="__codelineno-27-6" href="#__codelineno-27-6"></a><span class="w">        </span><span class="n">stack_top</span><span class="o">:</span><span class="w"> </span><span class="o">?*</span><span class="n">inc</span><span class="p">.</span><span class="n">ListNode</span><span class="p">(</span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">,</span><span class="w">             </span><span class="c1">// 将头节点作为栈顶</span>
<a id="__codelineno-27-7" name="__codelineno-27-7" href="#__codelineno-27-7"></a><span class="w">        </span><span class="n">stk_size</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w">                             </span><span class="c1">// 栈的长度</span>
<a id="__codelineno-27-8" name="__codelineno-27-8" href="#__codelineno-27-8"></a><span class="w">        </span><span class="n">mem_arena</span><span class="o">:</span><span class="w"> </span><span class="o">?</span><span class="n">std</span><span class="p">.</span><span class="n">heap</span><span class="p">.</span><span class="n">ArenaAllocator</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">,</span>
<a id="__codelineno-27-9" name="__codelineno-27-9" href="#__codelineno-27-9"></a><span class="w">        </span><span class="n">mem_allocator</span><span class="o">:</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">mem</span><span class="p">.</span><span class="n">Allocator</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">undefined</span><span class="p">,</span><span class="w">    </span><span class="c1">// 内存分配器</span>
<a id="__codelineno-27-10" name="__codelineno-27-10" href="#__codelineno-27-10"></a>
<a id="__codelineno-27-11" name="__codelineno-27-11" href="#__codelineno-27-11"></a><span class="w">        </span><span class="c1">// 构造函数（分配内存+初始化栈）</span>
<a id="__codelineno-27-12" name="__codelineno-27-12" href="#__codelineno-27-12"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">allocator</span><span class="o">:</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">mem</span><span class="p">.</span><span class="n">Allocator</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-13" name="__codelineno-27-13" href="#__codelineno-27-13"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_arena</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-14" name="__codelineno-27-14" href="#__codelineno-27-14"></a><span class="w">                </span><span class="n">self</span><span class="p">.</span><span class="n">mem_arena</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">heap</span><span class="p">.</span><span class="n">ArenaAllocator</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="n">allocator</span><span class="p">);</span>
<a id="__codelineno-27-15" name="__codelineno-27-15" href="#__codelineno-27-15"></a><span class="w">                </span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">mem_arena</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">allocator</span><span class="p">();</span>
<a id="__codelineno-27-16" name="__codelineno-27-16" href="#__codelineno-27-16"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-27-17" name="__codelineno-27-17" href="#__codelineno-27-17"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-27-18" name="__codelineno-27-18" href="#__codelineno-27-18"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stk_size</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-27-19" name="__codelineno-27-19" href="#__codelineno-27-19"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-27-20" name="__codelineno-27-20" href="#__codelineno-27-20"></a>
<a id="__codelineno-27-21" name="__codelineno-27-21" href="#__codelineno-27-21"></a><span class="w">        </span><span class="c1">// 析构函数（释放内存）</span>
<a id="__codelineno-27-22" name="__codelineno-27-22" href="#__codelineno-27-22"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">deinit</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-23" name="__codelineno-27-23" href="#__codelineno-27-23"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_arena</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">return</span><span class="p">;</span>
<a id="__codelineno-27-24" name="__codelineno-27-24" href="#__codelineno-27-24"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">mem_arena</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">deinit</span><span class="p">();</span>
<a id="__codelineno-27-25" name="__codelineno-27-25" href="#__codelineno-27-25"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-27-26" name="__codelineno-27-26" href="#__codelineno-27-26"></a>
<a id="__codelineno-27-27" name="__codelineno-27-27" href="#__codelineno-27-27"></a><span class="w">        </span><span class="c1">// 获取栈的长度</span>
<a id="__codelineno-27-28" name="__codelineno-27-28" href="#__codelineno-27-28"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-29" name="__codelineno-27-29" href="#__codelineno-27-29"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stk_size</span><span class="p">;</span>
<a id="__codelineno-27-30" name="__codelineno-27-30" href="#__codelineno-27-30"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-27-31" name="__codelineno-27-31" href="#__codelineno-27-31"></a>
<a id="__codelineno-27-32" name="__codelineno-27-32" href="#__codelineno-27-32"></a><span class="w">        </span><span class="c1">// 判断栈是否为空</span>
<a id="__codelineno-27-33" name="__codelineno-27-33" href="#__codelineno-27-33"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-34" name="__codelineno-27-34" href="#__codelineno-27-34"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-27-35" name="__codelineno-27-35" href="#__codelineno-27-35"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-27-36" name="__codelineno-27-36" href="#__codelineno-27-36"></a>
<a id="__codelineno-27-37" name="__codelineno-27-37" href="#__codelineno-27-37"></a><span class="w">        </span><span class="c1">// 访问栈顶元素</span>
<a id="__codelineno-27-38" name="__codelineno-27-38" href="#__codelineno-27-38"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">peek</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-39" name="__codelineno-27-39" href="#__codelineno-27-39"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="nb">@panic</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-27-40" name="__codelineno-27-40" href="#__codelineno-27-40"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-27-41" name="__codelineno-27-41" href="#__codelineno-27-41"></a><span class="w">        </span><span class="p">}</span><span class="w">  </span>
<a id="__codelineno-27-42" name="__codelineno-27-42" href="#__codelineno-27-42"></a>
<a id="__codelineno-27-43" name="__codelineno-27-43" href="#__codelineno-27-43"></a><span class="w">        </span><span class="c1">// 入栈</span>
<a id="__codelineno-27-44" name="__codelineno-27-44" href="#__codelineno-27-44"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">num</span><span class="o">:</span><span class="w"> </span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-45" name="__codelineno-27-45" href="#__codelineno-27-45"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">.</span><span class="n">create</span><span class="p">(</span><span class="n">inc</span><span class="p">.</span><span class="n">ListNode</span><span class="p">(</span><span class="n">T</span><span class="p">));</span>
<a id="__codelineno-27-46" name="__codelineno-27-46" href="#__codelineno-27-46"></a><span class="w">            </span><span class="n">node</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-27-47" name="__codelineno-27-47" href="#__codelineno-27-47"></a><span class="w">            </span><span class="n">node</span><span class="p">.</span><span class="n">next</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="p">;</span>
<a id="__codelineno-27-48" name="__codelineno-27-48" href="#__codelineno-27-48"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">;</span>
<a id="__codelineno-27-49" name="__codelineno-27-49" href="#__codelineno-27-49"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stk_size</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-27-50" name="__codelineno-27-50" href="#__codelineno-27-50"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span>
<a id="__codelineno-27-51" name="__codelineno-27-51" href="#__codelineno-27-51"></a>
<a id="__codelineno-27-52" name="__codelineno-27-52" href="#__codelineno-27-52"></a><span class="w">        </span><span class="c1">// 出栈</span>
<a id="__codelineno-27-53" name="__codelineno-27-53" href="#__codelineno-27-53"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">pop</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-54" name="__codelineno-27-54" href="#__codelineno-27-54"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">peek</span><span class="p">();</span>
<a id="__codelineno-27-55" name="__codelineno-27-55" href="#__codelineno-27-55"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-27-56" name="__codelineno-27-56" href="#__codelineno-27-56"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stk_size</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-27-57" name="__codelineno-27-57" href="#__codelineno-27-57"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-27-58" name="__codelineno-27-58" href="#__codelineno-27-58"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span>
<a id="__codelineno-27-59" name="__codelineno-27-59" href="#__codelineno-27-59"></a>
<a id="__codelineno-27-60" name="__codelineno-27-60" href="#__codelineno-27-60"></a><span class="w">        </span><span class="c1">// 将栈转换为数组</span>
<a id="__codelineno-27-61" name="__codelineno-27-61" href="#__codelineno-27-61"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">toArray</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="p">[]</span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-62" name="__codelineno-27-62" href="#__codelineno-27-62"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack_top</span><span class="p">;</span>
<a id="__codelineno-27-63" name="__codelineno-27-63" href="#__codelineno-27-63"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">.</span><span class="n">alloc</span><span class="p">(</span><span class="n">T</span><span class="p">,</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">());</span>
<a id="__codelineno-27-64" name="__codelineno-27-64" href="#__codelineno-27-64"></a><span class="w">            </span><span class="nb">@memset</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="nb">@as</span><span class="p">(</span><span class="n">T</span><span class="p">,</span><span class="w"> </span><span class="mi">0</span><span class="p">));</span>
<a id="__codelineno-27-65" name="__codelineno-27-65" href="#__codelineno-27-65"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">i</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-27-66" name="__codelineno-27-66" href="#__codelineno-27-66"></a><span class="w">            </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">res</span><span class="p">.</span><span class="n">len</span><span class="p">)</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-67" name="__codelineno-27-67" href="#__codelineno-27-67"></a><span class="w">                </span><span class="n">res</span><span class="p">[</span><span class="n">res</span><span class="p">.</span><span class="n">len</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-27-68" name="__codelineno-27-68" href="#__codelineno-27-68"></a><span class="w">                </span><span class="n">node</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">node</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">next</span><span class="p">;</span>
<a id="__codelineno-27-69" name="__codelineno-27-69" href="#__codelineno-27-69"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-27-70" name="__codelineno-27-70" href="#__codelineno-27-70"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-27-71" name="__codelineno-27-71" href="#__codelineno-27-71"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-27-72" name="__codelineno-27-72" href="#__codelineno-27-72"></a><span class="w">    </span><span class="p">};</span>
<a id="__codelineno-27-73" name="__codelineno-27-73" href="#__codelineno-27-73"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
### 基于数组的实现

使用数组实现栈时，我们可以将数组的尾部作为栈顶。如下图所示，入栈与出栈操作分别对应在数组尾部添加元素与删除元素，时间复杂度都为 $O(1)$ 。

=== "ArrayStack"
    ![基于数组实现栈的入栈出栈操作](stack.assets/array_stack.png)

=== "push()"
    ![array_stack_push](stack.assets/array_stack_push.png)

=== "pop()"
    ![array_stack_pop](stack.assets/array_stack_pop.png)

由于入栈的元素可能会源源不断地增加，因此我们可以使用动态数组，这样就无须自行处理数组扩容问题。以下为示例代码。

<div class="tabbed-set tabbed-alternate" data-tabs="5:14" style="--md-indicator-x: 0px; --md-indicator-width: 68px;"><input checked="checked" id="__tabbed_5_1" name="__tabbed_5" type="radio"><input id="__tabbed_5_2" name="__tabbed_5" type="radio"><input id="__tabbed_5_3" name="__tabbed_5" type="radio"><input id="__tabbed_5_4" name="__tabbed_5" type="radio"><input id="__tabbed_5_5" name="__tabbed_5" type="radio"><input id="__tabbed_5_6" name="__tabbed_5" type="radio"><input id="__tabbed_5_7" name="__tabbed_5" type="radio"><input id="__tabbed_5_8" name="__tabbed_5" type="radio"><input id="__tabbed_5_9" name="__tabbed_5" type="radio"><input id="__tabbed_5_10" name="__tabbed_5" type="radio"><input id="__tabbed_5_11" name="__tabbed_5" type="radio"><input id="__tabbed_5_12" name="__tabbed_5" type="radio"><input id="__tabbed_5_13" name="__tabbed_5" type="radio"><input id="__tabbed_5_14" name="__tabbed_5" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_5_1"><a href="#__tabbed_5_1" tabindex="-1">Python</a></label><label for="__tabbed_5_2"><a href="#__tabbed_5_2" tabindex="-1">C++</a></label><label for="__tabbed_5_3"><a href="#__tabbed_5_3" tabindex="-1">Java</a></label><label for="__tabbed_5_4"><a href="#__tabbed_5_4" tabindex="-1">C#</a></label><label for="__tabbed_5_5"><a href="#__tabbed_5_5" tabindex="-1">Go</a></label><label for="__tabbed_5_6"><a href="#__tabbed_5_6" tabindex="-1">Swift</a></label><label for="__tabbed_5_7"><a href="#__tabbed_5_7" tabindex="-1">JS</a></label><label for="__tabbed_5_8"><a href="#__tabbed_5_8" tabindex="-1">TS</a></label><label for="__tabbed_5_9"><a href="#__tabbed_5_9" tabindex="-1">Dart</a></label><label for="__tabbed_5_10"><a href="#__tabbed_5_10" tabindex="-1">Rust</a></label><label for="__tabbed_5_11"><a href="#__tabbed_5_11" tabindex="-1">C</a></label><label for="__tabbed_5_12"><a href="#__tabbed_5_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_5_13"><a href="#__tabbed_5_13" tabindex="-1">Ruby</a></label><label for="__tabbed_5_14"><a href="#__tabbed_5_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.py</span><pre id="__code_28"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_28 > code"></button><code><a id="__codelineno-28-1" name="__codelineno-28-1" href="#__codelineno-28-1"></a><span class="k">class</span> <span class="nc">ArrayStack</span><span class="p">:</span>
<a id="__codelineno-28-2" name="__codelineno-28-2" href="#__codelineno-28-2"></a><span class="w">    </span><span class="sd">"""基于数组实现的栈"""</span>
<a id="__codelineno-28-3" name="__codelineno-28-3" href="#__codelineno-28-3"></a>
<a id="__codelineno-28-4" name="__codelineno-28-4" href="#__codelineno-28-4"></a>    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<a id="__codelineno-28-5" name="__codelineno-28-5" href="#__codelineno-28-5"></a><span class="w">        </span><span class="sd">"""构造方法"""</span>
<a id="__codelineno-28-6" name="__codelineno-28-6" href="#__codelineno-28-6"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_stack</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">]</span> <span class="o">=</span> <span class="p">[]</span>
<a id="__codelineno-28-7" name="__codelineno-28-7" href="#__codelineno-28-7"></a>
<a id="__codelineno-28-8" name="__codelineno-28-8" href="#__codelineno-28-8"></a>    <span class="k">def</span> <span class="nf">size</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-28-9" name="__codelineno-28-9" href="#__codelineno-28-9"></a><span class="w">        </span><span class="sd">"""获取栈的长度"""</span>
<a id="__codelineno-28-10" name="__codelineno-28-10" href="#__codelineno-28-10"></a>        <span class="k">return</span> <span class="nb">len</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">_stack</span><span class="p">)</span>
<a id="__codelineno-28-11" name="__codelineno-28-11" href="#__codelineno-28-11"></a>
<a id="__codelineno-28-12" name="__codelineno-28-12" href="#__codelineno-28-12"></a>    <span class="k">def</span> <span class="nf">is_empty</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">bool</span><span class="p">:</span>
<a id="__codelineno-28-13" name="__codelineno-28-13" href="#__codelineno-28-13"></a><span class="w">        </span><span class="sd">"""判断栈是否为空"""</span>
<a id="__codelineno-28-14" name="__codelineno-28-14" href="#__codelineno-28-14"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">size</span><span class="p">()</span> <span class="o">==</span> <span class="mi">0</span>
<a id="__codelineno-28-15" name="__codelineno-28-15" href="#__codelineno-28-15"></a>
<a id="__codelineno-28-16" name="__codelineno-28-16" href="#__codelineno-28-16"></a>    <span class="k">def</span> <span class="nf">push</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">item</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-28-17" name="__codelineno-28-17" href="#__codelineno-28-17"></a><span class="w">        </span><span class="sd">"""入栈"""</span>
<a id="__codelineno-28-18" name="__codelineno-28-18" href="#__codelineno-28-18"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">_stack</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">item</span><span class="p">)</span>
<a id="__codelineno-28-19" name="__codelineno-28-19" href="#__codelineno-28-19"></a>
<a id="__codelineno-28-20" name="__codelineno-28-20" href="#__codelineno-28-20"></a>    <span class="k">def</span> <span class="nf">pop</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-28-21" name="__codelineno-28-21" href="#__codelineno-28-21"></a><span class="w">        </span><span class="sd">"""出栈"""</span>
<a id="__codelineno-28-22" name="__codelineno-28-22" href="#__codelineno-28-22"></a>        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">is_empty</span><span class="p">():</span>
<a id="__codelineno-28-23" name="__codelineno-28-23" href="#__codelineno-28-23"></a>            <span class="k">raise</span> <span class="ne">IndexError</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-28-24" name="__codelineno-28-24" href="#__codelineno-28-24"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_stack</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>
<a id="__codelineno-28-25" name="__codelineno-28-25" href="#__codelineno-28-25"></a>
<a id="__codelineno-28-26" name="__codelineno-28-26" href="#__codelineno-28-26"></a>    <span class="k">def</span> <span class="nf">peek</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-28-27" name="__codelineno-28-27" href="#__codelineno-28-27"></a><span class="w">        </span><span class="sd">"""访问栈顶元素"""</span>
<a id="__codelineno-28-28" name="__codelineno-28-28" href="#__codelineno-28-28"></a>        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">is_empty</span><span class="p">():</span>
<a id="__codelineno-28-29" name="__codelineno-28-29" href="#__codelineno-28-29"></a>            <span class="k">raise</span> <span class="ne">IndexError</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-28-30" name="__codelineno-28-30" href="#__codelineno-28-30"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_stack</span><span class="p">[</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<a id="__codelineno-28-31" name="__codelineno-28-31" href="#__codelineno-28-31"></a>
<a id="__codelineno-28-32" name="__codelineno-28-32" href="#__codelineno-28-32"></a>    <span class="k">def</span> <span class="nf">to_list</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">]:</span>
<a id="__codelineno-28-33" name="__codelineno-28-33" href="#__codelineno-28-33"></a><span class="w">        </span><span class="sd">"""返回列表用于打印"""</span>
<a id="__codelineno-28-34" name="__codelineno-28-34" href="#__codelineno-28-34"></a>        <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">_stack</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.cpp</span><pre id="__code_29"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_29 > code"></button><code><a id="__codelineno-29-1" name="__codelineno-29-1" href="#__codelineno-29-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-29-2" name="__codelineno-29-2" href="#__codelineno-29-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-3" name="__codelineno-29-3" href="#__codelineno-29-3"></a><span class="w">  </span><span class="k">private</span><span class="o">:</span>
<a id="__codelineno-29-4" name="__codelineno-29-4" href="#__codelineno-29-4"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">stack</span><span class="p">;</span>
<a id="__codelineno-29-5" name="__codelineno-29-5" href="#__codelineno-29-5"></a>
<a id="__codelineno-29-6" name="__codelineno-29-6" href="#__codelineno-29-6"></a><span class="w">  </span><span class="k">public</span><span class="o">:</span>
<a id="__codelineno-29-7" name="__codelineno-29-7" href="#__codelineno-29-7"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-29-8" name="__codelineno-29-8" href="#__codelineno-29-8"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-9" name="__codelineno-29-9" href="#__codelineno-29-9"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="n">size</span><span class="p">();</span>
<a id="__codelineno-29-10" name="__codelineno-29-10" href="#__codelineno-29-10"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-11" name="__codelineno-29-11" href="#__codelineno-29-11"></a>
<a id="__codelineno-29-12" name="__codelineno-29-12" href="#__codelineno-29-12"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-29-13" name="__codelineno-29-13" href="#__codelineno-29-13"></a><span class="w">    </span><span class="kt">bool</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-14" name="__codelineno-29-14" href="#__codelineno-29-14"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-29-15" name="__codelineno-29-15" href="#__codelineno-29-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-16" name="__codelineno-29-16" href="#__codelineno-29-16"></a>
<a id="__codelineno-29-17" name="__codelineno-29-17" href="#__codelineno-29-17"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-29-18" name="__codelineno-29-18" href="#__codelineno-29-18"></a><span class="w">    </span><span class="kt">void</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-19" name="__codelineno-29-19" href="#__codelineno-29-19"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="n">push_back</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-29-20" name="__codelineno-29-20" href="#__codelineno-29-20"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-21" name="__codelineno-29-21" href="#__codelineno-29-21"></a>
<a id="__codelineno-29-22" name="__codelineno-29-22" href="#__codelineno-29-22"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-29-23" name="__codelineno-29-23" href="#__codelineno-29-23"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-24" name="__codelineno-29-24" href="#__codelineno-29-24"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">top</span><span class="p">();</span>
<a id="__codelineno-29-25" name="__codelineno-29-25" href="#__codelineno-29-25"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="n">pop_back</span><span class="p">();</span>
<a id="__codelineno-29-26" name="__codelineno-29-26" href="#__codelineno-29-26"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-29-27" name="__codelineno-29-27" href="#__codelineno-29-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-28" name="__codelineno-29-28" href="#__codelineno-29-28"></a>
<a id="__codelineno-29-29" name="__codelineno-29-29" href="#__codelineno-29-29"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-29-30" name="__codelineno-29-30" href="#__codelineno-29-30"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">top</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-31" name="__codelineno-29-31" href="#__codelineno-29-31"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-29-32" name="__codelineno-29-32" href="#__codelineno-29-32"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="n">out_of_range</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-29-33" name="__codelineno-29-33" href="#__codelineno-29-33"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="n">back</span><span class="p">();</span>
<a id="__codelineno-29-34" name="__codelineno-29-34" href="#__codelineno-29-34"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-35" name="__codelineno-29-35" href="#__codelineno-29-35"></a>
<a id="__codelineno-29-36" name="__codelineno-29-36" href="#__codelineno-29-36"></a><span class="w">    </span><span class="cm">/* 返回 Vector */</span>
<a id="__codelineno-29-37" name="__codelineno-29-37" href="#__codelineno-29-37"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">toVector</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-38" name="__codelineno-29-38" href="#__codelineno-29-38"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">;</span>
<a id="__codelineno-29-39" name="__codelineno-29-39" href="#__codelineno-29-39"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-29-40" name="__codelineno-29-40" href="#__codelineno-29-40"></a><span class="p">};</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.java</span><pre id="__code_30"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_30 > code"></button><code><a id="__codelineno-30-1" name="__codelineno-30-1" href="#__codelineno-30-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-30-2" name="__codelineno-30-2" href="#__codelineno-30-2"></a><span class="kd">class</span> <span class="nc">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-3" name="__codelineno-30-3" href="#__codelineno-30-3"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;</span><span class="n">Integer</span><span class="o">&gt;</span><span class="w"> </span><span class="n">stack</span><span class="p">;</span>
<a id="__codelineno-30-4" name="__codelineno-30-4" href="#__codelineno-30-4"></a>
<a id="__codelineno-30-5" name="__codelineno-30-5" href="#__codelineno-30-5"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="nf">ArrayStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-6" name="__codelineno-30-6" href="#__codelineno-30-6"></a><span class="w">        </span><span class="c1">// 初始化列表（动态数组）</span>
<a id="__codelineno-30-7" name="__codelineno-30-7" href="#__codelineno-30-7"></a><span class="w">        </span><span class="n">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;&gt;</span><span class="p">();</span>
<a id="__codelineno-30-8" name="__codelineno-30-8" href="#__codelineno-30-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-9" name="__codelineno-30-9" href="#__codelineno-30-9"></a>
<a id="__codelineno-30-10" name="__codelineno-30-10" href="#__codelineno-30-10"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-30-11" name="__codelineno-30-11" href="#__codelineno-30-11"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-12" name="__codelineno-30-12" href="#__codelineno-30-12"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">size</span><span class="p">();</span>
<a id="__codelineno-30-13" name="__codelineno-30-13" href="#__codelineno-30-13"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-14" name="__codelineno-30-14" href="#__codelineno-30-14"></a>
<a id="__codelineno-30-15" name="__codelineno-30-15" href="#__codelineno-30-15"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-30-16" name="__codelineno-30-16" href="#__codelineno-30-16"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">boolean</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-17" name="__codelineno-30-17" href="#__codelineno-30-17"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-30-18" name="__codelineno-30-18" href="#__codelineno-30-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-19" name="__codelineno-30-19" href="#__codelineno-30-19"></a>
<a id="__codelineno-30-20" name="__codelineno-30-20" href="#__codelineno-30-20"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-30-21" name="__codelineno-30-21" href="#__codelineno-30-21"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-22" name="__codelineno-30-22" href="#__codelineno-30-22"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-30-23" name="__codelineno-30-23" href="#__codelineno-30-23"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-24" name="__codelineno-30-24" href="#__codelineno-30-24"></a>
<a id="__codelineno-30-25" name="__codelineno-30-25" href="#__codelineno-30-25"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-30-26" name="__codelineno-30-26" href="#__codelineno-30-26"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-27" name="__codelineno-30-27" href="#__codelineno-30-27"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-30-28" name="__codelineno-30-28" href="#__codelineno-30-28"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">();</span>
<a id="__codelineno-30-29" name="__codelineno-30-29" href="#__codelineno-30-29"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">remove</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-30-30" name="__codelineno-30-30" href="#__codelineno-30-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-31" name="__codelineno-30-31" href="#__codelineno-30-31"></a>
<a id="__codelineno-30-32" name="__codelineno-30-32" href="#__codelineno-30-32"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-30-33" name="__codelineno-30-33" href="#__codelineno-30-33"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-34" name="__codelineno-30-34" href="#__codelineno-30-34"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-30-35" name="__codelineno-30-35" href="#__codelineno-30-35"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">();</span>
<a id="__codelineno-30-36" name="__codelineno-30-36" href="#__codelineno-30-36"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-30-37" name="__codelineno-30-37" href="#__codelineno-30-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-38" name="__codelineno-30-38" href="#__codelineno-30-38"></a>
<a id="__codelineno-30-39" name="__codelineno-30-39" href="#__codelineno-30-39"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-30-40" name="__codelineno-30-40" href="#__codelineno-30-40"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">Object</span><span class="o">[]</span><span class="w"> </span><span class="nf">toArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-41" name="__codelineno-30-41" href="#__codelineno-30-41"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">toArray</span><span class="p">();</span>
<a id="__codelineno-30-42" name="__codelineno-30-42" href="#__codelineno-30-42"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-43" name="__codelineno-30-43" href="#__codelineno-30-43"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.cs</span><pre id="__code_31"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_31 > code"></button><code><a id="__codelineno-31-1" name="__codelineno-31-1" href="#__codelineno-31-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-31-2" name="__codelineno-31-2" href="#__codelineno-31-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-3" name="__codelineno-31-3" href="#__codelineno-31-3"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">stack</span><span class="p">;</span>
<a id="__codelineno-31-4" name="__codelineno-31-4" href="#__codelineno-31-4"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nf">ArrayStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-5" name="__codelineno-31-5" href="#__codelineno-31-5"></a><span class="w">        </span><span class="c1">// 初始化列表（动态数组）</span>
<a id="__codelineno-31-6" name="__codelineno-31-6" href="#__codelineno-31-6"></a><span class="w">        </span><span class="n">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-31-7" name="__codelineno-31-7" href="#__codelineno-31-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-8" name="__codelineno-31-8" href="#__codelineno-31-8"></a>
<a id="__codelineno-31-9" name="__codelineno-31-9" href="#__codelineno-31-9"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-31-10" name="__codelineno-31-10" href="#__codelineno-31-10"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-11" name="__codelineno-31-11" href="#__codelineno-31-11"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="n">Count</span><span class="p">;</span>
<a id="__codelineno-31-12" name="__codelineno-31-12" href="#__codelineno-31-12"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-13" name="__codelineno-31-13" href="#__codelineno-31-13"></a>
<a id="__codelineno-31-14" name="__codelineno-31-14" href="#__codelineno-31-14"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-31-15" name="__codelineno-31-15" href="#__codelineno-31-15"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="nf">IsEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-16" name="__codelineno-31-16" href="#__codelineno-31-16"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nf">Size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-31-17" name="__codelineno-31-17" href="#__codelineno-31-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-18" name="__codelineno-31-18" href="#__codelineno-31-18"></a>
<a id="__codelineno-31-19" name="__codelineno-31-19" href="#__codelineno-31-19"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-31-20" name="__codelineno-31-20" href="#__codelineno-31-20"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="k">void</span><span class="w"> </span><span class="nf">Push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-21" name="__codelineno-31-21" href="#__codelineno-31-21"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-31-22" name="__codelineno-31-22" href="#__codelineno-31-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-23" name="__codelineno-31-23" href="#__codelineno-31-23"></a>
<a id="__codelineno-31-24" name="__codelineno-31-24" href="#__codelineno-31-24"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-31-25" name="__codelineno-31-25" href="#__codelineno-31-25"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-26" name="__codelineno-31-26" href="#__codelineno-31-26"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">IsEmpty</span><span class="p">())</span>
<a id="__codelineno-31-27" name="__codelineno-31-27" href="#__codelineno-31-27"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="nf">Exception</span><span class="p">();</span>
<a id="__codelineno-31-28" name="__codelineno-31-28" href="#__codelineno-31-28"></a><span class="w">        </span><span class="kt">var</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Peek</span><span class="p">();</span>
<a id="__codelineno-31-29" name="__codelineno-31-29" href="#__codelineno-31-29"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="n">RemoveAt</span><span class="p">(</span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-31-30" name="__codelineno-31-30" href="#__codelineno-31-30"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-31-31" name="__codelineno-31-31" href="#__codelineno-31-31"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-32" name="__codelineno-31-32" href="#__codelineno-31-32"></a>
<a id="__codelineno-31-33" name="__codelineno-31-33" href="#__codelineno-31-33"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-31-34" name="__codelineno-31-34" href="#__codelineno-31-34"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">Peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-35" name="__codelineno-31-35" href="#__codelineno-31-35"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">IsEmpty</span><span class="p">())</span>
<a id="__codelineno-31-36" name="__codelineno-31-36" href="#__codelineno-31-36"></a><span class="w">            </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="nf">Exception</span><span class="p">();</span>
<a id="__codelineno-31-37" name="__codelineno-31-37" href="#__codelineno-31-37"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">[</span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">];</span>
<a id="__codelineno-31-38" name="__codelineno-31-38" href="#__codelineno-31-38"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-39" name="__codelineno-31-39" href="#__codelineno-31-39"></a>
<a id="__codelineno-31-40" name="__codelineno-31-40" href="#__codelineno-31-40"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-31-41" name="__codelineno-31-41" href="#__codelineno-31-41"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="nf">ToArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-42" name="__codelineno-31-42" href="#__codelineno-31-42"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="p">[..</span><span class="w"> </span><span class="n">stack</span><span class="p">];</span>
<a id="__codelineno-31-43" name="__codelineno-31-43" href="#__codelineno-31-43"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-44" name="__codelineno-31-44" href="#__codelineno-31-44"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.go</span><pre id="__code_32"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_32 > code"></button><code><a id="__codelineno-32-1" name="__codelineno-32-1" href="#__codelineno-32-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-32-2" name="__codelineno-32-2" href="#__codelineno-32-2"></a><span class="kd">type</span><span class="w"> </span><span class="nx">arrayStack</span><span class="w"> </span><span class="kd">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-3" name="__codelineno-32-3" href="#__codelineno-32-3"></a><span class="w">    </span><span class="nx">data</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="w"> </span><span class="c1">// 数据</span>
<a id="__codelineno-32-4" name="__codelineno-32-4" href="#__codelineno-32-4"></a><span class="p">}</span>
<a id="__codelineno-32-5" name="__codelineno-32-5" href="#__codelineno-32-5"></a>
<a id="__codelineno-32-6" name="__codelineno-32-6" href="#__codelineno-32-6"></a><span class="cm">/* 初始化栈 */</span>
<a id="__codelineno-32-7" name="__codelineno-32-7" href="#__codelineno-32-7"></a><span class="kd">func</span><span class="w"> </span><span class="nx">newArrayStack</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-8" name="__codelineno-32-8" href="#__codelineno-32-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="o">&amp;</span><span class="nx">arrayStack</span><span class="p">{</span>
<a id="__codelineno-32-9" name="__codelineno-32-9" href="#__codelineno-32-9"></a><span class="w">        </span><span class="c1">// 设置栈的长度为 0，容量为 16</span>
<a id="__codelineno-32-10" name="__codelineno-32-10" href="#__codelineno-32-10"></a><span class="w">        </span><span class="nx">data</span><span class="p">:</span><span class="w"> </span><span class="nb">make</span><span class="p">([]</span><span class="kt">int</span><span class="p">,</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="mi">16</span><span class="p">),</span>
<a id="__codelineno-32-11" name="__codelineno-32-11" href="#__codelineno-32-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-12" name="__codelineno-32-12" href="#__codelineno-32-12"></a><span class="p">}</span>
<a id="__codelineno-32-13" name="__codelineno-32-13" href="#__codelineno-32-13"></a>
<a id="__codelineno-32-14" name="__codelineno-32-14" href="#__codelineno-32-14"></a><span class="cm">/* 栈的长度 */</span>
<a id="__codelineno-32-15" name="__codelineno-32-15" href="#__codelineno-32-15"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-16" name="__codelineno-32-16" href="#__codelineno-32-16"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">len</span><span class="p">(</span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span>
<a id="__codelineno-32-17" name="__codelineno-32-17" href="#__codelineno-32-17"></a><span class="p">}</span>
<a id="__codelineno-32-18" name="__codelineno-32-18" href="#__codelineno-32-18"></a>
<a id="__codelineno-32-19" name="__codelineno-32-19" href="#__codelineno-32-19"></a><span class="cm">/* 栈是否为空 */</span>
<a id="__codelineno-32-20" name="__codelineno-32-20" href="#__codelineno-32-20"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-21" name="__codelineno-32-21" href="#__codelineno-32-21"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-32-22" name="__codelineno-32-22" href="#__codelineno-32-22"></a><span class="p">}</span>
<a id="__codelineno-32-23" name="__codelineno-32-23" href="#__codelineno-32-23"></a>
<a id="__codelineno-32-24" name="__codelineno-32-24" href="#__codelineno-32-24"></a><span class="cm">/* 入栈 */</span>
<a id="__codelineno-32-25" name="__codelineno-32-25" href="#__codelineno-32-25"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">push</span><span class="p">(</span><span class="nx">v</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-26" name="__codelineno-32-26" href="#__codelineno-32-26"></a><span class="w">    </span><span class="c1">// 切片会自动扩容</span>
<a id="__codelineno-32-27" name="__codelineno-32-27" href="#__codelineno-32-27"></a><span class="w">    </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">append</span><span class="p">(</span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">,</span><span class="w"> </span><span class="nx">v</span><span class="p">)</span>
<a id="__codelineno-32-28" name="__codelineno-32-28" href="#__codelineno-32-28"></a><span class="p">}</span>
<a id="__codelineno-32-29" name="__codelineno-32-29" href="#__codelineno-32-29"></a>
<a id="__codelineno-32-30" name="__codelineno-32-30" href="#__codelineno-32-30"></a><span class="cm">/* 出栈 */</span>
<a id="__codelineno-32-31" name="__codelineno-32-31" href="#__codelineno-32-31"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-32" name="__codelineno-32-32" href="#__codelineno-32-32"></a><span class="w">    </span><span class="nx">val</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">peek</span><span class="p">()</span>
<a id="__codelineno-32-33" name="__codelineno-32-33" href="#__codelineno-32-33"></a><span class="w">    </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">[:</span><span class="nb">len</span><span class="p">(</span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<a id="__codelineno-32-34" name="__codelineno-32-34" href="#__codelineno-32-34"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">val</span>
<a id="__codelineno-32-35" name="__codelineno-32-35" href="#__codelineno-32-35"></a><span class="p">}</span>
<a id="__codelineno-32-36" name="__codelineno-32-36" href="#__codelineno-32-36"></a>
<a id="__codelineno-32-37" name="__codelineno-32-37" href="#__codelineno-32-37"></a><span class="cm">/* 获取栈顶元素 */</span>
<a id="__codelineno-32-38" name="__codelineno-32-38" href="#__codelineno-32-38"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">peek</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-39" name="__codelineno-32-39" href="#__codelineno-32-39"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-40" name="__codelineno-32-40" href="#__codelineno-32-40"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="kc">nil</span>
<a id="__codelineno-32-41" name="__codelineno-32-41" href="#__codelineno-32-41"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-42" name="__codelineno-32-42" href="#__codelineno-32-42"></a><span class="w">    </span><span class="nx">val</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nb">len</span><span class="p">(</span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<a id="__codelineno-32-43" name="__codelineno-32-43" href="#__codelineno-32-43"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">val</span>
<a id="__codelineno-32-44" name="__codelineno-32-44" href="#__codelineno-32-44"></a><span class="p">}</span>
<a id="__codelineno-32-45" name="__codelineno-32-45" href="#__codelineno-32-45"></a>
<a id="__codelineno-32-46" name="__codelineno-32-46" href="#__codelineno-32-46"></a><span class="cm">/* 获取 Slice 用于打印 */</span>
<a id="__codelineno-32-47" name="__codelineno-32-47" href="#__codelineno-32-47"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">s</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayStack</span><span class="p">)</span><span class="w"> </span><span class="nx">toSlice</span><span class="p">()</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-48" name="__codelineno-32-48" href="#__codelineno-32-48"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">s</span><span class="p">.</span><span class="nx">data</span>
<a id="__codelineno-32-49" name="__codelineno-32-49" href="#__codelineno-32-49"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.swift</span><pre id="__code_33"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_33 > code"></button><code><a id="__codelineno-33-1" name="__codelineno-33-1" href="#__codelineno-33-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-33-2" name="__codelineno-33-2" href="#__codelineno-33-2"></a><span class="kd">class</span> <span class="nc">ArrayStack</span> <span class="p">{</span>
<a id="__codelineno-33-3" name="__codelineno-33-3" href="#__codelineno-33-3"></a>    <span class="kd">private</span> <span class="kd">var</span> <span class="nv">stack</span><span class="p">:</span> <span class="p">[</span><span class="nb">Int</span><span class="p">]</span>
<a id="__codelineno-33-4" name="__codelineno-33-4" href="#__codelineno-33-4"></a>
<a id="__codelineno-33-5" name="__codelineno-33-5" href="#__codelineno-33-5"></a>    <span class="kd">init</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-33-6" name="__codelineno-33-6" href="#__codelineno-33-6"></a>        <span class="c1">// 初始化列表（动态数组）</span>
<a id="__codelineno-33-7" name="__codelineno-33-7" href="#__codelineno-33-7"></a>        <span class="n">stack</span> <span class="p">=</span> <span class="p">[]</span>
<a id="__codelineno-33-8" name="__codelineno-33-8" href="#__codelineno-33-8"></a>    <span class="p">}</span>
<a id="__codelineno-33-9" name="__codelineno-33-9" href="#__codelineno-33-9"></a>
<a id="__codelineno-33-10" name="__codelineno-33-10" href="#__codelineno-33-10"></a>    <span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-33-11" name="__codelineno-33-11" href="#__codelineno-33-11"></a>    <span class="kd">func</span> <span class="nf">size</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-33-12" name="__codelineno-33-12" href="#__codelineno-33-12"></a>        <span class="n">stack</span><span class="p">.</span><span class="bp">count</span>
<a id="__codelineno-33-13" name="__codelineno-33-13" href="#__codelineno-33-13"></a>    <span class="p">}</span>
<a id="__codelineno-33-14" name="__codelineno-33-14" href="#__codelineno-33-14"></a>
<a id="__codelineno-33-15" name="__codelineno-33-15" href="#__codelineno-33-15"></a>    <span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-33-16" name="__codelineno-33-16" href="#__codelineno-33-16"></a>    <span class="kd">func</span> <span class="nf">isEmpty</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Bool</span> <span class="p">{</span>
<a id="__codelineno-33-17" name="__codelineno-33-17" href="#__codelineno-33-17"></a>        <span class="n">stack</span><span class="p">.</span><span class="bp">isEmpty</span>
<a id="__codelineno-33-18" name="__codelineno-33-18" href="#__codelineno-33-18"></a>    <span class="p">}</span>
<a id="__codelineno-33-19" name="__codelineno-33-19" href="#__codelineno-33-19"></a>
<a id="__codelineno-33-20" name="__codelineno-33-20" href="#__codelineno-33-20"></a>    <span class="cm">/* 入栈 */</span>
<a id="__codelineno-33-21" name="__codelineno-33-21" href="#__codelineno-33-21"></a>    <span class="kd">func</span> <span class="nf">push</span><span class="p">(</span><span class="n">num</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-33-22" name="__codelineno-33-22" href="#__codelineno-33-22"></a>        <span class="n">stack</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<a id="__codelineno-33-23" name="__codelineno-33-23" href="#__codelineno-33-23"></a>    <span class="p">}</span>
<a id="__codelineno-33-24" name="__codelineno-33-24" href="#__codelineno-33-24"></a>
<a id="__codelineno-33-25" name="__codelineno-33-25" href="#__codelineno-33-25"></a>    <span class="cm">/* 出栈 */</span>
<a id="__codelineno-33-26" name="__codelineno-33-26" href="#__codelineno-33-26"></a>    <span class="p">@</span><span class="n">discardableResult</span>
<a id="__codelineno-33-27" name="__codelineno-33-27" href="#__codelineno-33-27"></a>    <span class="kd">func</span> <span class="nf">pop</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-33-28" name="__codelineno-33-28" href="#__codelineno-33-28"></a>        <span class="k">if</span> <span class="bp">isEmpty</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-33-29" name="__codelineno-33-29" href="#__codelineno-33-29"></a>            <span class="bp">fatalError</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-33-30" name="__codelineno-33-30" href="#__codelineno-33-30"></a>        <span class="p">}</span>
<a id="__codelineno-33-31" name="__codelineno-33-31" href="#__codelineno-33-31"></a>        <span class="k">return</span> <span class="n">stack</span><span class="p">.</span><span class="bp">removeLast</span><span class="p">()</span>
<a id="__codelineno-33-32" name="__codelineno-33-32" href="#__codelineno-33-32"></a>    <span class="p">}</span>
<a id="__codelineno-33-33" name="__codelineno-33-33" href="#__codelineno-33-33"></a>
<a id="__codelineno-33-34" name="__codelineno-33-34" href="#__codelineno-33-34"></a>    <span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-33-35" name="__codelineno-33-35" href="#__codelineno-33-35"></a>    <span class="kd">func</span> <span class="nf">peek</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-33-36" name="__codelineno-33-36" href="#__codelineno-33-36"></a>        <span class="k">if</span> <span class="bp">isEmpty</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-33-37" name="__codelineno-33-37" href="#__codelineno-33-37"></a>            <span class="bp">fatalError</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-33-38" name="__codelineno-33-38" href="#__codelineno-33-38"></a>        <span class="p">}</span>
<a id="__codelineno-33-39" name="__codelineno-33-39" href="#__codelineno-33-39"></a>        <span class="k">return</span> <span class="n">stack</span><span class="p">.</span><span class="bp">last</span><span class="p">!</span>
<a id="__codelineno-33-40" name="__codelineno-33-40" href="#__codelineno-33-40"></a>    <span class="p">}</span>
<a id="__codelineno-33-41" name="__codelineno-33-41" href="#__codelineno-33-41"></a>
<a id="__codelineno-33-42" name="__codelineno-33-42" href="#__codelineno-33-42"></a>    <span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-33-43" name="__codelineno-33-43" href="#__codelineno-33-43"></a>    <span class="kd">func</span> <span class="nf">toArray</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="p">[</span><span class="nb">Int</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-33-44" name="__codelineno-33-44" href="#__codelineno-33-44"></a>        <span class="n">stack</span>
<a id="__codelineno-33-45" name="__codelineno-33-45" href="#__codelineno-33-45"></a>    <span class="p">}</span>
<a id="__codelineno-33-46" name="__codelineno-33-46" href="#__codelineno-33-46"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.js</span><pre id="__code_34"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_34 > code"></button><code><a id="__codelineno-34-1" name="__codelineno-34-1" href="#__codelineno-34-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-34-2" name="__codelineno-34-2" href="#__codelineno-34-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-3" name="__codelineno-34-3" href="#__codelineno-34-3"></a><span class="w">    </span><span class="err">#</span><span class="nx">stack</span><span class="p">;</span>
<a id="__codelineno-34-4" name="__codelineno-34-4" href="#__codelineno-34-4"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-5" name="__codelineno-34-5" href="#__codelineno-34-5"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-34-6" name="__codelineno-34-6" href="#__codelineno-34-6"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-7" name="__codelineno-34-7" href="#__codelineno-34-7"></a>
<a id="__codelineno-34-8" name="__codelineno-34-8" href="#__codelineno-34-8"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-34-9" name="__codelineno-34-9" href="#__codelineno-34-9"></a><span class="w">    </span><span class="nx">get</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-10" name="__codelineno-34-10" href="#__codelineno-34-10"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span>
<a id="__codelineno-34-11" name="__codelineno-34-11" href="#__codelineno-34-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-12" name="__codelineno-34-12" href="#__codelineno-34-12"></a>
<a id="__codelineno-34-13" name="__codelineno-34-13" href="#__codelineno-34-13"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-34-14" name="__codelineno-34-14" href="#__codelineno-34-14"></a><span class="w">    </span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-15" name="__codelineno-34-15" href="#__codelineno-34-15"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-34-16" name="__codelineno-34-16" href="#__codelineno-34-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-17" name="__codelineno-34-17" href="#__codelineno-34-17"></a>
<a id="__codelineno-34-18" name="__codelineno-34-18" href="#__codelineno-34-18"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-34-19" name="__codelineno-34-19" href="#__codelineno-34-19"></a><span class="w">    </span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-20" name="__codelineno-34-20" href="#__codelineno-34-20"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="p">);</span>
<a id="__codelineno-34-21" name="__codelineno-34-21" href="#__codelineno-34-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-22" name="__codelineno-34-22" href="#__codelineno-34-22"></a>
<a id="__codelineno-34-23" name="__codelineno-34-23" href="#__codelineno-34-23"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-34-24" name="__codelineno-34-24" href="#__codelineno-34-24"></a><span class="w">    </span><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-25" name="__codelineno-34-25" href="#__codelineno-34-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-34-26" name="__codelineno-34-26" href="#__codelineno-34-26"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">.</span><span class="nx">pop</span><span class="p">();</span>
<a id="__codelineno-34-27" name="__codelineno-34-27" href="#__codelineno-34-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-28" name="__codelineno-34-28" href="#__codelineno-34-28"></a>
<a id="__codelineno-34-29" name="__codelineno-34-29" href="#__codelineno-34-29"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-34-30" name="__codelineno-34-30" href="#__codelineno-34-30"></a><span class="w">    </span><span class="nx">top</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-31" name="__codelineno-34-31" href="#__codelineno-34-31"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-34-32" name="__codelineno-34-32" href="#__codelineno-34-32"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">[</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">];</span>
<a id="__codelineno-34-33" name="__codelineno-34-33" href="#__codelineno-34-33"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-34" name="__codelineno-34-34" href="#__codelineno-34-34"></a>
<a id="__codelineno-34-35" name="__codelineno-34-35" href="#__codelineno-34-35"></a><span class="w">    </span><span class="cm">/* 返回 Array */</span>
<a id="__codelineno-34-36" name="__codelineno-34-36" href="#__codelineno-34-36"></a><span class="w">    </span><span class="nx">toArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-37" name="__codelineno-34-37" href="#__codelineno-34-37"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">stack</span><span class="p">;</span>
<a id="__codelineno-34-38" name="__codelineno-34-38" href="#__codelineno-34-38"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-34-39" name="__codelineno-34-39" href="#__codelineno-34-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.ts</span><pre id="__code_35"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_35 > code"></button><code><a id="__codelineno-35-1" name="__codelineno-35-1" href="#__codelineno-35-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-35-2" name="__codelineno-35-2" href="#__codelineno-35-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-3" name="__codelineno-35-3" href="#__codelineno-35-3"></a><span class="w">    </span><span class="k">private</span><span class="w"> </span><span class="nx">stack</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">[];</span>
<a id="__codelineno-35-4" name="__codelineno-35-4" href="#__codelineno-35-4"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-5" name="__codelineno-35-5" href="#__codelineno-35-5"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-35-6" name="__codelineno-35-6" href="#__codelineno-35-6"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-7" name="__codelineno-35-7" href="#__codelineno-35-7"></a>
<a id="__codelineno-35-8" name="__codelineno-35-8" href="#__codelineno-35-8"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-35-9" name="__codelineno-35-9" href="#__codelineno-35-9"></a><span class="w">    </span><span class="nx">get</span><span class="w"> </span><span class="nx">size</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-10" name="__codelineno-35-10" href="#__codelineno-35-10"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span>
<a id="__codelineno-35-11" name="__codelineno-35-11" href="#__codelineno-35-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-12" name="__codelineno-35-12" href="#__codelineno-35-12"></a>
<a id="__codelineno-35-13" name="__codelineno-35-13" href="#__codelineno-35-13"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-35-14" name="__codelineno-35-14" href="#__codelineno-35-14"></a><span class="w">    </span><span class="nx">isEmpty</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">boolean</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-15" name="__codelineno-35-15" href="#__codelineno-35-15"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-35-16" name="__codelineno-35-16" href="#__codelineno-35-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-17" name="__codelineno-35-17" href="#__codelineno-35-17"></a>
<a id="__codelineno-35-18" name="__codelineno-35-18" href="#__codelineno-35-18"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-35-19" name="__codelineno-35-19" href="#__codelineno-35-19"></a><span class="w">    </span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="ow">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-20" name="__codelineno-35-20" href="#__codelineno-35-20"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="nx">num</span><span class="p">);</span>
<a id="__codelineno-35-21" name="__codelineno-35-21" href="#__codelineno-35-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-22" name="__codelineno-35-22" href="#__codelineno-35-22"></a>
<a id="__codelineno-35-23" name="__codelineno-35-23" href="#__codelineno-35-23"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-35-24" name="__codelineno-35-24" href="#__codelineno-35-24"></a><span class="w">    </span><span class="nx">pop</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-25" name="__codelineno-35-25" href="#__codelineno-35-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-35-26" name="__codelineno-35-26" href="#__codelineno-35-26"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">.</span><span class="nx">pop</span><span class="p">();</span>
<a id="__codelineno-35-27" name="__codelineno-35-27" href="#__codelineno-35-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-28" name="__codelineno-35-28" href="#__codelineno-35-28"></a>
<a id="__codelineno-35-29" name="__codelineno-35-29" href="#__codelineno-35-29"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-35-30" name="__codelineno-35-30" href="#__codelineno-35-30"></a><span class="w">    </span><span class="nx">top</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-31" name="__codelineno-35-31" href="#__codelineno-35-31"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'栈为空'</span><span class="p">);</span>
<a id="__codelineno-35-32" name="__codelineno-35-32" href="#__codelineno-35-32"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">[</span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">];</span>
<a id="__codelineno-35-33" name="__codelineno-35-33" href="#__codelineno-35-33"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-34" name="__codelineno-35-34" href="#__codelineno-35-34"></a>
<a id="__codelineno-35-35" name="__codelineno-35-35" href="#__codelineno-35-35"></a><span class="w">    </span><span class="cm">/* 返回 Array */</span>
<a id="__codelineno-35-36" name="__codelineno-35-36" href="#__codelineno-35-36"></a><span class="w">    </span><span class="nx">toArray</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-37" name="__codelineno-35-37" href="#__codelineno-35-37"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">stack</span><span class="p">;</span>
<a id="__codelineno-35-38" name="__codelineno-35-38" href="#__codelineno-35-38"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-39" name="__codelineno-35-39" href="#__codelineno-35-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.dart</span><pre id="__code_36"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_36 > code"></button><code><a id="__codelineno-36-1" name="__codelineno-36-1" href="#__codelineno-36-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-36-2" name="__codelineno-36-2" href="#__codelineno-36-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-3" name="__codelineno-36-3" href="#__codelineno-36-3"></a><span class="w">  </span><span class="kd">late</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">_stack</span><span class="p">;</span>
<a id="__codelineno-36-4" name="__codelineno-36-4" href="#__codelineno-36-4"></a><span class="w">  </span><span class="n">ArrayStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-5" name="__codelineno-36-5" href="#__codelineno-36-5"></a><span class="w">    </span><span class="n">_stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-36-6" name="__codelineno-36-6" href="#__codelineno-36-6"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-7" name="__codelineno-36-7" href="#__codelineno-36-7"></a>
<a id="__codelineno-36-8" name="__codelineno-36-8" href="#__codelineno-36-8"></a><span class="w">  </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-36-9" name="__codelineno-36-9" href="#__codelineno-36-9"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-10" name="__codelineno-36-10" href="#__codelineno-36-10"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stack</span><span class="p">.</span><span class="n">length</span><span class="p">;</span>
<a id="__codelineno-36-11" name="__codelineno-36-11" href="#__codelineno-36-11"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-12" name="__codelineno-36-12" href="#__codelineno-36-12"></a>
<a id="__codelineno-36-13" name="__codelineno-36-13" href="#__codelineno-36-13"></a><span class="w">  </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-36-14" name="__codelineno-36-14" href="#__codelineno-36-14"></a><span class="w">  </span><span class="kt">bool</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-15" name="__codelineno-36-15" href="#__codelineno-36-15"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stack</span><span class="p">.</span><span class="n">isEmpty</span><span class="p">;</span>
<a id="__codelineno-36-16" name="__codelineno-36-16" href="#__codelineno-36-16"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-17" name="__codelineno-36-17" href="#__codelineno-36-17"></a>
<a id="__codelineno-36-18" name="__codelineno-36-18" href="#__codelineno-36-18"></a><span class="w">  </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-36-19" name="__codelineno-36-19" href="#__codelineno-36-19"></a><span class="w">  </span><span class="kt">void</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">_num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-20" name="__codelineno-36-20" href="#__codelineno-36-20"></a><span class="w">    </span><span class="n">_stack</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">_num</span><span class="p">);</span>
<a id="__codelineno-36-21" name="__codelineno-36-21" href="#__codelineno-36-21"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-22" name="__codelineno-36-22" href="#__codelineno-36-22"></a>
<a id="__codelineno-36-23" name="__codelineno-36-23" href="#__codelineno-36-23"></a><span class="w">  </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-36-24" name="__codelineno-36-24" href="#__codelineno-36-24"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-25" name="__codelineno-36-25" href="#__codelineno-36-25"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-26" name="__codelineno-36-26" href="#__codelineno-36-26"></a><span class="w">      </span><span class="k">throw</span><span class="w"> </span><span class="n">Exception</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-36-27" name="__codelineno-36-27" href="#__codelineno-36-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-28" name="__codelineno-36-28" href="#__codelineno-36-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stack</span><span class="p">.</span><span class="n">removeLast</span><span class="p">();</span>
<a id="__codelineno-36-29" name="__codelineno-36-29" href="#__codelineno-36-29"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-30" name="__codelineno-36-30" href="#__codelineno-36-30"></a>
<a id="__codelineno-36-31" name="__codelineno-36-31" href="#__codelineno-36-31"></a><span class="w">  </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-36-32" name="__codelineno-36-32" href="#__codelineno-36-32"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-33" name="__codelineno-36-33" href="#__codelineno-36-33"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-34" name="__codelineno-36-34" href="#__codelineno-36-34"></a><span class="w">      </span><span class="k">throw</span><span class="w"> </span><span class="n">Exception</span><span class="p">(</span><span class="s2">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-36-35" name="__codelineno-36-35" href="#__codelineno-36-35"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-36" name="__codelineno-36-36" href="#__codelineno-36-36"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_stack</span><span class="p">.</span><span class="n">last</span><span class="p">;</span>
<a id="__codelineno-36-37" name="__codelineno-36-37" href="#__codelineno-36-37"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-36-38" name="__codelineno-36-38" href="#__codelineno-36-38"></a>
<a id="__codelineno-36-39" name="__codelineno-36-39" href="#__codelineno-36-39"></a><span class="w">  </span><span class="cm">/* 将栈转化为 Array 并返回 */</span>
<a id="__codelineno-36-40" name="__codelineno-36-40" href="#__codelineno-36-40"></a><span class="w">  </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">toArray</span><span class="p">()</span><span class="w"> </span><span class="o">=&gt;</span><span class="w"> </span><span class="n">_stack</span><span class="p">;</span>
<a id="__codelineno-36-41" name="__codelineno-36-41" href="#__codelineno-36-41"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.rs</span><pre id="__code_37"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_37 > code"></button><code><a id="__codelineno-37-1" name="__codelineno-37-1" href="#__codelineno-37-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-37-2" name="__codelineno-37-2" href="#__codelineno-37-2"></a><span class="k">struct</span> <span class="nc">ArrayStack</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-3" name="__codelineno-37-3" href="#__codelineno-37-3"></a><span class="w">    </span><span class="n">stack</span>: <span class="nb">Vec</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="p">,</span>
<a id="__codelineno-37-4" name="__codelineno-37-4" href="#__codelineno-37-4"></a><span class="p">}</span>
<a id="__codelineno-37-5" name="__codelineno-37-5" href="#__codelineno-37-5"></a>
<a id="__codelineno-37-6" name="__codelineno-37-6" href="#__codelineno-37-6"></a><span class="k">impl</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="n">ArrayStack</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-7" name="__codelineno-37-7" href="#__codelineno-37-7"></a><span class="w">    </span><span class="cm">/* 初始化栈 */</span>
<a id="__codelineno-37-8" name="__codelineno-37-8" href="#__codelineno-37-8"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">new</span><span class="p">()</span><span class="w"> </span>-&gt; <span class="nc">ArrayStack</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-9" name="__codelineno-37-9" href="#__codelineno-37-9"></a><span class="w">        </span><span class="n">ArrayStack</span>::<span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-10" name="__codelineno-37-10" href="#__codelineno-37-10"></a><span class="w">            </span><span class="n">stack</span>: <span class="nb">Vec</span>::<span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span>::<span class="n">new</span><span class="p">(),</span>
<a id="__codelineno-37-11" name="__codelineno-37-11" href="#__codelineno-37-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-37-12" name="__codelineno-37-12" href="#__codelineno-37-12"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-13" name="__codelineno-37-13" href="#__codelineno-37-13"></a>
<a id="__codelineno-37-14" name="__codelineno-37-14" href="#__codelineno-37-14"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-37-15" name="__codelineno-37-15" href="#__codelineno-37-15"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">size</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-37-16" name="__codelineno-37-16" href="#__codelineno-37-16"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="n">len</span><span class="p">()</span>
<a id="__codelineno-37-17" name="__codelineno-37-17" href="#__codelineno-37-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-18" name="__codelineno-37-18" href="#__codelineno-37-18"></a>
<a id="__codelineno-37-19" name="__codelineno-37-19" href="#__codelineno-37-19"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-37-20" name="__codelineno-37-20" href="#__codelineno-37-20"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">is_empty</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">bool</span> <span class="p">{</span>
<a id="__codelineno-37-21" name="__codelineno-37-21" href="#__codelineno-37-21"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-37-22" name="__codelineno-37-22" href="#__codelineno-37-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-23" name="__codelineno-37-23" href="#__codelineno-37-23"></a>
<a id="__codelineno-37-24" name="__codelineno-37-24" href="#__codelineno-37-24"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-37-25" name="__codelineno-37-25" href="#__codelineno-37-25"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">push</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">num</span>: <span class="nc">T</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-26" name="__codelineno-37-26" href="#__codelineno-37-26"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-37-27" name="__codelineno-37-27" href="#__codelineno-37-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-28" name="__codelineno-37-28" href="#__codelineno-37-28"></a>
<a id="__codelineno-37-29" name="__codelineno-37-29" href="#__codelineno-37-29"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-37-30" name="__codelineno-37-30" href="#__codelineno-37-30"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">pop</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-31" name="__codelineno-37-31" href="#__codelineno-37-31"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="n">pop</span><span class="p">()</span>
<a id="__codelineno-37-32" name="__codelineno-37-32" href="#__codelineno-37-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-33" name="__codelineno-37-33" href="#__codelineno-37-33"></a>
<a id="__codelineno-37-34" name="__codelineno-37-34" href="#__codelineno-37-34"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-37-35" name="__codelineno-37-35" href="#__codelineno-37-35"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">peek</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;&amp;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-36" name="__codelineno-37-36" href="#__codelineno-37-36"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">is_empty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-37" name="__codelineno-37-37" href="#__codelineno-37-37"></a><span class="w">            </span><span class="fm">panic!</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">)</span>
<a id="__codelineno-37-38" name="__codelineno-37-38" href="#__codelineno-37-38"></a><span class="w">        </span><span class="p">};</span>
<a id="__codelineno-37-39" name="__codelineno-37-39" href="#__codelineno-37-39"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="n">last</span><span class="p">()</span>
<a id="__codelineno-37-40" name="__codelineno-37-40" href="#__codelineno-37-40"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-41" name="__codelineno-37-41" href="#__codelineno-37-41"></a>
<a id="__codelineno-37-42" name="__codelineno-37-42" href="#__codelineno-37-42"></a><span class="w">    </span><span class="cm">/* 返回 &amp;Vec */</span>
<a id="__codelineno-37-43" name="__codelineno-37-43" href="#__codelineno-37-43"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">to_array</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kp">&amp;</span><span class="nb">Vec</span><span class="o">&lt;</span><span class="n">T</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-44" name="__codelineno-37-44" href="#__codelineno-37-44"></a><span class="w">        </span><span class="o">&amp;</span><span class="bp">self</span><span class="p">.</span><span class="n">stack</span>
<a id="__codelineno-37-45" name="__codelineno-37-45" href="#__codelineno-37-45"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-46" name="__codelineno-37-46" href="#__codelineno-37-46"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.c</span><pre id="__code_38"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_38 > code"></button><code><a id="__codelineno-38-1" name="__codelineno-38-1" href="#__codelineno-38-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-38-2" name="__codelineno-38-2" href="#__codelineno-38-2"></a><span class="k">typedef</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-3" name="__codelineno-38-3" href="#__codelineno-38-3"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="o">*</span><span class="n">data</span><span class="p">;</span>
<a id="__codelineno-38-4" name="__codelineno-38-4" href="#__codelineno-38-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">;</span>
<a id="__codelineno-38-5" name="__codelineno-38-5" href="#__codelineno-38-5"></a><span class="p">}</span><span class="w"> </span><span class="n">ArrayStack</span><span class="p">;</span>
<a id="__codelineno-38-6" name="__codelineno-38-6" href="#__codelineno-38-6"></a>
<a id="__codelineno-38-7" name="__codelineno-38-7" href="#__codelineno-38-7"></a><span class="cm">/* 构造函数 */</span>
<a id="__codelineno-38-8" name="__codelineno-38-8" href="#__codelineno-38-8"></a><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="nf">newArrayStack</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-9" name="__codelineno-38-9" href="#__codelineno-38-9"></a><span class="w">    </span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">ArrayStack</span><span class="p">));</span>
<a id="__codelineno-38-10" name="__codelineno-38-10" href="#__codelineno-38-10"></a><span class="w">    </span><span class="c1">// 初始化一个大容量，避免扩容</span>
<a id="__codelineno-38-11" name="__codelineno-38-11" href="#__codelineno-38-11"></a><span class="w">    </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">data</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">);</span>
<a id="__codelineno-38-12" name="__codelineno-38-12" href="#__codelineno-38-12"></a><span class="w">    </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-38-13" name="__codelineno-38-13" href="#__codelineno-38-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">;</span>
<a id="__codelineno-38-14" name="__codelineno-38-14" href="#__codelineno-38-14"></a><span class="p">}</span>
<a id="__codelineno-38-15" name="__codelineno-38-15" href="#__codelineno-38-15"></a>
<a id="__codelineno-38-16" name="__codelineno-38-16" href="#__codelineno-38-16"></a><span class="cm">/* 析构函数 */</span>
<a id="__codelineno-38-17" name="__codelineno-38-17" href="#__codelineno-38-17"></a><span class="kt">void</span><span class="w"> </span><span class="nf">delArrayStack</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-18" name="__codelineno-38-18" href="#__codelineno-38-18"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">);</span>
<a id="__codelineno-38-19" name="__codelineno-38-19" href="#__codelineno-38-19"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">stack</span><span class="p">);</span>
<a id="__codelineno-38-20" name="__codelineno-38-20" href="#__codelineno-38-20"></a><span class="p">}</span>
<a id="__codelineno-38-21" name="__codelineno-38-21" href="#__codelineno-38-21"></a>
<a id="__codelineno-38-22" name="__codelineno-38-22" href="#__codelineno-38-22"></a><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-38-23" name="__codelineno-38-23" href="#__codelineno-38-23"></a><span class="kt">int</span><span class="w"> </span><span class="nf">size</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-24" name="__codelineno-38-24" href="#__codelineno-38-24"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="p">;</span>
<a id="__codelineno-38-25" name="__codelineno-38-25" href="#__codelineno-38-25"></a><span class="p">}</span>
<a id="__codelineno-38-26" name="__codelineno-38-26" href="#__codelineno-38-26"></a>
<a id="__codelineno-38-27" name="__codelineno-38-27" href="#__codelineno-38-27"></a><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-38-28" name="__codelineno-38-28" href="#__codelineno-38-28"></a><span class="kt">bool</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-29" name="__codelineno-38-29" href="#__codelineno-38-29"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-38-30" name="__codelineno-38-30" href="#__codelineno-38-30"></a><span class="p">}</span>
<a id="__codelineno-38-31" name="__codelineno-38-31" href="#__codelineno-38-31"></a>
<a id="__codelineno-38-32" name="__codelineno-38-32" href="#__codelineno-38-32"></a><span class="cm">/* 入栈 */</span>
<a id="__codelineno-38-33" name="__codelineno-38-33" href="#__codelineno-38-33"></a><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">num</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-34" name="__codelineno-38-34" href="#__codelineno-38-34"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-35" name="__codelineno-38-35" href="#__codelineno-38-35"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"栈已满</span><span class="se">\n</span><span class="s">"</span><span class="p">);</span>
<a id="__codelineno-38-36" name="__codelineno-38-36" href="#__codelineno-38-36"></a><span class="w">        </span><span class="k">return</span><span class="p">;</span>
<a id="__codelineno-38-37" name="__codelineno-38-37" href="#__codelineno-38-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-38" name="__codelineno-38-38" href="#__codelineno-38-38"></a><span class="w">    </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-38-39" name="__codelineno-38-39" href="#__codelineno-38-39"></a><span class="w">    </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-38-40" name="__codelineno-38-40" href="#__codelineno-38-40"></a><span class="p">}</span>
<a id="__codelineno-38-41" name="__codelineno-38-41" href="#__codelineno-38-41"></a>
<a id="__codelineno-38-42" name="__codelineno-38-42" href="#__codelineno-38-42"></a><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-38-43" name="__codelineno-38-43" href="#__codelineno-38-43"></a><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-44" name="__codelineno-38-44" href="#__codelineno-38-44"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-45" name="__codelineno-38-45" href="#__codelineno-38-45"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"栈为空</span><span class="se">\n</span><span class="s">"</span><span class="p">);</span>
<a id="__codelineno-38-46" name="__codelineno-38-46" href="#__codelineno-38-46"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">INT_MAX</span><span class="p">;</span>
<a id="__codelineno-38-47" name="__codelineno-38-47" href="#__codelineno-38-47"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-48" name="__codelineno-38-48" href="#__codelineno-38-48"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">];</span>
<a id="__codelineno-38-49" name="__codelineno-38-49" href="#__codelineno-38-49"></a><span class="p">}</span>
<a id="__codelineno-38-50" name="__codelineno-38-50" href="#__codelineno-38-50"></a>
<a id="__codelineno-38-51" name="__codelineno-38-51" href="#__codelineno-38-51"></a><span class="cm">/* 出栈 */</span>
<a id="__codelineno-38-52" name="__codelineno-38-52" href="#__codelineno-38-52"></a><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">(</span><span class="n">ArrayStack</span><span class="w"> </span><span class="o">*</span><span class="n">stack</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-53" name="__codelineno-38-53" href="#__codelineno-38-53"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">peek</span><span class="p">(</span><span class="n">stack</span><span class="p">);</span>
<a id="__codelineno-38-54" name="__codelineno-38-54" href="#__codelineno-38-54"></a><span class="w">    </span><span class="n">stack</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-38-55" name="__codelineno-38-55" href="#__codelineno-38-55"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-38-56" name="__codelineno-38-56" href="#__codelineno-38-56"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.kt</span><pre id="__code_39"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_39 > code"></button><code><a id="__codelineno-39-1" name="__codelineno-39-1" href="#__codelineno-39-1"></a><span class="cm">/* 基于数组实现的栈 */</span>
<a id="__codelineno-39-2" name="__codelineno-39-2" href="#__codelineno-39-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">ArrayStack</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-3" name="__codelineno-39-3" href="#__codelineno-39-3"></a><span class="w">    </span><span class="c1">// 初始化列表（动态数组）</span>
<a id="__codelineno-39-4" name="__codelineno-39-4" href="#__codelineno-39-4"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kd">val</span><span class="w"> </span><span class="nv">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">mutableListOf</span><span class="o">&lt;</span><span class="kt">Int</span><span class="o">&gt;</span><span class="p">()</span>
<a id="__codelineno-39-5" name="__codelineno-39-5" href="#__codelineno-39-5"></a>
<a id="__codelineno-39-6" name="__codelineno-39-6" href="#__codelineno-39-6"></a><span class="w">    </span><span class="cm">/* 获取栈的长度 */</span>
<a id="__codelineno-39-7" name="__codelineno-39-7" href="#__codelineno-39-7"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">size</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-8" name="__codelineno-39-8" href="#__codelineno-39-8"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">size</span>
<a id="__codelineno-39-9" name="__codelineno-39-9" href="#__codelineno-39-9"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-10" name="__codelineno-39-10" href="#__codelineno-39-10"></a>
<a id="__codelineno-39-11" name="__codelineno-39-11" href="#__codelineno-39-11"></a><span class="w">    </span><span class="cm">/* 判断栈是否为空 */</span>
<a id="__codelineno-39-12" name="__codelineno-39-12" href="#__codelineno-39-12"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">isEmpty</span><span class="p">():</span><span class="w"> </span><span class="kt">Boolean</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-13" name="__codelineno-39-13" href="#__codelineno-39-13"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-39-14" name="__codelineno-39-14" href="#__codelineno-39-14"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-15" name="__codelineno-39-15" href="#__codelineno-39-15"></a>
<a id="__codelineno-39-16" name="__codelineno-39-16" href="#__codelineno-39-16"></a><span class="w">    </span><span class="cm">/* 入栈 */</span>
<a id="__codelineno-39-17" name="__codelineno-39-17" href="#__codelineno-39-17"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">num</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-18" name="__codelineno-39-18" href="#__codelineno-39-18"></a><span class="w">        </span><span class="n">stack</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">num</span><span class="p">)</span>
<a id="__codelineno-39-19" name="__codelineno-39-19" href="#__codelineno-39-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-20" name="__codelineno-39-20" href="#__codelineno-39-20"></a>
<a id="__codelineno-39-21" name="__codelineno-39-21" href="#__codelineno-39-21"></a><span class="w">    </span><span class="cm">/* 出栈 */</span>
<a id="__codelineno-39-22" name="__codelineno-39-22" href="#__codelineno-39-22"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">pop</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-23" name="__codelineno-39-23" href="#__codelineno-39-23"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">()</span>
<a id="__codelineno-39-24" name="__codelineno-39-24" href="#__codelineno-39-24"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">removeAt</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span>
<a id="__codelineno-39-25" name="__codelineno-39-25" href="#__codelineno-39-25"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-26" name="__codelineno-39-26" href="#__codelineno-39-26"></a>
<a id="__codelineno-39-27" name="__codelineno-39-27" href="#__codelineno-39-27"></a><span class="w">    </span><span class="cm">/* 访问栈顶元素 */</span>
<a id="__codelineno-39-28" name="__codelineno-39-28" href="#__codelineno-39-28"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">peek</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-29" name="__codelineno-39-29" href="#__codelineno-39-29"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">()</span>
<a id="__codelineno-39-30" name="__codelineno-39-30" href="#__codelineno-39-30"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="o">[</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="o">]</span>
<a id="__codelineno-39-31" name="__codelineno-39-31" href="#__codelineno-39-31"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-32" name="__codelineno-39-32" href="#__codelineno-39-32"></a>
<a id="__codelineno-39-33" name="__codelineno-39-33" href="#__codelineno-39-33"></a><span class="w">    </span><span class="cm">/* 将 List 转化为 Array 并返回 */</span>
<a id="__codelineno-39-34" name="__codelineno-39-34" href="#__codelineno-39-34"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">toArray</span><span class="p">():</span><span class="w"> </span><span class="n">Array</span><span class="o">&lt;</span><span class="kt">Any</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-35" name="__codelineno-39-35" href="#__codelineno-39-35"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">stack</span><span class="p">.</span><span class="na">toTypedArray</span><span class="p">()</span>
<a id="__codelineno-39-36" name="__codelineno-39-36" href="#__codelineno-39-36"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-37" name="__codelineno-39-37" href="#__codelineno-39-37"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.rb</span><pre id="__code_40"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_40 > code"></button><code><a id="__codelineno-40-1" name="__codelineno-40-1" href="#__codelineno-40-1"></a><span class="c1">### 基于数组实现的栈 ###</span>
<a id="__codelineno-40-2" name="__codelineno-40-2" href="#__codelineno-40-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayStack</span>
<a id="__codelineno-40-3" name="__codelineno-40-3" href="#__codelineno-40-3"></a><span class="w">  </span><span class="c1">### 构造方法 ###</span>
<a id="__codelineno-40-4" name="__codelineno-40-4" href="#__codelineno-40-4"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">initialize</span>
<a id="__codelineno-40-5" name="__codelineno-40-5" href="#__codelineno-40-5"></a><span class="w">    </span><span class="vi">@stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[]</span>
<a id="__codelineno-40-6" name="__codelineno-40-6" href="#__codelineno-40-6"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-7" name="__codelineno-40-7" href="#__codelineno-40-7"></a>
<a id="__codelineno-40-8" name="__codelineno-40-8" href="#__codelineno-40-8"></a><span class="w">  </span><span class="c1">### 获取栈的长度 ###</span>
<a id="__codelineno-40-9" name="__codelineno-40-9" href="#__codelineno-40-9"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">size</span>
<a id="__codelineno-40-10" name="__codelineno-40-10" href="#__codelineno-40-10"></a><span class="w">    </span><span class="vi">@stack</span><span class="o">.</span><span class="n">length</span>
<a id="__codelineno-40-11" name="__codelineno-40-11" href="#__codelineno-40-11"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-12" name="__codelineno-40-12" href="#__codelineno-40-12"></a>
<a id="__codelineno-40-13" name="__codelineno-40-13" href="#__codelineno-40-13"></a><span class="w">  </span><span class="c1">### 判断栈是否为空 ###</span>
<a id="__codelineno-40-14" name="__codelineno-40-14" href="#__codelineno-40-14"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">is_empty?</span>
<a id="__codelineno-40-15" name="__codelineno-40-15" href="#__codelineno-40-15"></a><span class="w">    </span><span class="vi">@stack</span><span class="o">.</span><span class="n">empty?</span>
<a id="__codelineno-40-16" name="__codelineno-40-16" href="#__codelineno-40-16"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-17" name="__codelineno-40-17" href="#__codelineno-40-17"></a>
<a id="__codelineno-40-18" name="__codelineno-40-18" href="#__codelineno-40-18"></a><span class="w">  </span><span class="c1">### 入栈 ###</span>
<a id="__codelineno-40-19" name="__codelineno-40-19" href="#__codelineno-40-19"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">item</span><span class="p">)</span>
<a id="__codelineno-40-20" name="__codelineno-40-20" href="#__codelineno-40-20"></a><span class="w">    </span><span class="vi">@stack</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">item</span>
<a id="__codelineno-40-21" name="__codelineno-40-21" href="#__codelineno-40-21"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-22" name="__codelineno-40-22" href="#__codelineno-40-22"></a>
<a id="__codelineno-40-23" name="__codelineno-40-23" href="#__codelineno-40-23"></a><span class="w">  </span><span class="c1">### 出栈 ###</span>
<a id="__codelineno-40-24" name="__codelineno-40-24" href="#__codelineno-40-24"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">pop</span>
<a id="__codelineno-40-25" name="__codelineno-40-25" href="#__codelineno-40-25"></a><span class="w">    </span><span class="k">raise</span><span class="w"> </span><span class="no">IndexError</span><span class="p">,</span><span class="w"> </span><span class="s1">'栈为空'</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">is_empty?</span>
<a id="__codelineno-40-26" name="__codelineno-40-26" href="#__codelineno-40-26"></a>
<a id="__codelineno-40-27" name="__codelineno-40-27" href="#__codelineno-40-27"></a><span class="w">    </span><span class="vi">@stack</span><span class="o">.</span><span class="n">pop</span>
<a id="__codelineno-40-28" name="__codelineno-40-28" href="#__codelineno-40-28"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-29" name="__codelineno-40-29" href="#__codelineno-40-29"></a>
<a id="__codelineno-40-30" name="__codelineno-40-30" href="#__codelineno-40-30"></a><span class="w">  </span><span class="c1">### 访问栈顶元素 ###</span>
<a id="__codelineno-40-31" name="__codelineno-40-31" href="#__codelineno-40-31"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">peek</span>
<a id="__codelineno-40-32" name="__codelineno-40-32" href="#__codelineno-40-32"></a><span class="w">    </span><span class="k">raise</span><span class="w"> </span><span class="no">IndexError</span><span class="p">,</span><span class="w"> </span><span class="s1">'栈为空'</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">is_empty?</span>
<a id="__codelineno-40-33" name="__codelineno-40-33" href="#__codelineno-40-33"></a>
<a id="__codelineno-40-34" name="__codelineno-40-34" href="#__codelineno-40-34"></a><span class="w">    </span><span class="vi">@stack</span><span class="o">.</span><span class="n">last</span>
<a id="__codelineno-40-35" name="__codelineno-40-35" href="#__codelineno-40-35"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-36" name="__codelineno-40-36" href="#__codelineno-40-36"></a>
<a id="__codelineno-40-37" name="__codelineno-40-37" href="#__codelineno-40-37"></a><span class="w">  </span><span class="c1">### 返回列表用于打印 ###</span>
<a id="__codelineno-40-38" name="__codelineno-40-38" href="#__codelineno-40-38"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">to_array</span>
<a id="__codelineno-40-39" name="__codelineno-40-39" href="#__codelineno-40-39"></a><span class="w">    </span><span class="vi">@stack</span>
<a id="__codelineno-40-40" name="__codelineno-40-40" href="#__codelineno-40-40"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-40-41" name="__codelineno-40-41" href="#__codelineno-40-41"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_stack.zig</span><pre id="__code_41"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_41 > code"></button><code><a id="__codelineno-41-1" name="__codelineno-41-1" href="#__codelineno-41-1"></a><span class="c1">// 基于数组实现的栈</span>
<a id="__codelineno-41-2" name="__codelineno-41-2" href="#__codelineno-41-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">ArrayStack</span><span class="p">(</span><span class="kr">comptime</span><span class="w"> </span><span class="n">T</span><span class="o">:</span><span class="w"> </span><span class="kt">type</span><span class="p">)</span><span class="w"> </span><span class="kt">type</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-3" name="__codelineno-41-3" href="#__codelineno-41-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-4" name="__codelineno-41-4" href="#__codelineno-41-4"></a><span class="w">        </span><span class="kr">const</span><span class="w"> </span><span class="n">Self</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">@This</span><span class="p">();</span>
<a id="__codelineno-41-5" name="__codelineno-41-5" href="#__codelineno-41-5"></a>
<a id="__codelineno-41-6" name="__codelineno-41-6" href="#__codelineno-41-6"></a><span class="w">        </span><span class="n">stack</span><span class="o">:</span><span class="w"> </span><span class="o">?</span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">,</span><span class="w">     </span>
<a id="__codelineno-41-7" name="__codelineno-41-7" href="#__codelineno-41-7"></a>
<a id="__codelineno-41-8" name="__codelineno-41-8" href="#__codelineno-41-8"></a><span class="w">        </span><span class="c1">// 构造方法（分配内存+初始化栈）</span>
<a id="__codelineno-41-9" name="__codelineno-41-9" href="#__codelineno-41-9"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">allocator</span><span class="o">:</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">mem</span><span class="p">.</span><span class="n">Allocator</span><span class="p">)</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-10" name="__codelineno-41-10" href="#__codelineno-41-10"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-11" name="__codelineno-41-11" href="#__codelineno-41-11"></a><span class="w">                </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="n">T</span><span class="p">).</span><span class="n">init</span><span class="p">(</span><span class="n">allocator</span><span class="p">);</span>
<a id="__codelineno-41-12" name="__codelineno-41-12" href="#__codelineno-41-12"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-41-13" name="__codelineno-41-13" href="#__codelineno-41-13"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-41-14" name="__codelineno-41-14" href="#__codelineno-41-14"></a>
<a id="__codelineno-41-15" name="__codelineno-41-15" href="#__codelineno-41-15"></a><span class="w">        </span><span class="c1">// 析构方法（释放内存）</span>
<a id="__codelineno-41-16" name="__codelineno-41-16" href="#__codelineno-41-16"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">deinit</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-17" name="__codelineno-41-17" href="#__codelineno-41-17"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">return</span><span class="p">;</span>
<a id="__codelineno-41-18" name="__codelineno-41-18" href="#__codelineno-41-18"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">deinit</span><span class="p">();</span>
<a id="__codelineno-41-19" name="__codelineno-41-19" href="#__codelineno-41-19"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-41-20" name="__codelineno-41-20" href="#__codelineno-41-20"></a>
<a id="__codelineno-41-21" name="__codelineno-41-21" href="#__codelineno-41-21"></a><span class="w">        </span><span class="c1">// 获取栈的长度</span>
<a id="__codelineno-41-22" name="__codelineno-41-22" href="#__codelineno-41-22"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-23" name="__codelineno-41-23" href="#__codelineno-41-23"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">.</span><span class="n">len</span><span class="p">;</span>
<a id="__codelineno-41-24" name="__codelineno-41-24" href="#__codelineno-41-24"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-41-25" name="__codelineno-41-25" href="#__codelineno-41-25"></a>
<a id="__codelineno-41-26" name="__codelineno-41-26" href="#__codelineno-41-26"></a><span class="w">        </span><span class="c1">// 判断栈是否为空</span>
<a id="__codelineno-41-27" name="__codelineno-41-27" href="#__codelineno-41-27"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">isEmpty</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">bool</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-28" name="__codelineno-41-28" href="#__codelineno-41-28"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-41-29" name="__codelineno-41-29" href="#__codelineno-41-29"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-41-30" name="__codelineno-41-30" href="#__codelineno-41-30"></a>
<a id="__codelineno-41-31" name="__codelineno-41-31" href="#__codelineno-41-31"></a><span class="w">        </span><span class="c1">// 访问栈顶元素</span>
<a id="__codelineno-41-32" name="__codelineno-41-32" href="#__codelineno-41-32"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">peek</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-33" name="__codelineno-41-33" href="#__codelineno-41-33"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="nb">@panic</span><span class="p">(</span><span class="s">"栈为空"</span><span class="p">);</span>
<a id="__codelineno-41-34" name="__codelineno-41-34" href="#__codelineno-41-34"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">];</span>
<a id="__codelineno-41-35" name="__codelineno-41-35" href="#__codelineno-41-35"></a><span class="w">        </span><span class="p">}</span><span class="w">  </span>
<a id="__codelineno-41-36" name="__codelineno-41-36" href="#__codelineno-41-36"></a>
<a id="__codelineno-41-37" name="__codelineno-41-37" href="#__codelineno-41-37"></a><span class="w">        </span><span class="c1">// 入栈</span>
<a id="__codelineno-41-38" name="__codelineno-41-38" href="#__codelineno-41-38"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">num</span><span class="o">:</span><span class="w"> </span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-39" name="__codelineno-41-39" href="#__codelineno-41-39"></a><span class="w">            </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">num</span><span class="p">);</span>
<a id="__codelineno-41-40" name="__codelineno-41-40" href="#__codelineno-41-40"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span>
<a id="__codelineno-41-41" name="__codelineno-41-41" href="#__codelineno-41-41"></a>
<a id="__codelineno-41-42" name="__codelineno-41-42" href="#__codelineno-41-42"></a><span class="w">        </span><span class="c1">// 出栈</span>
<a id="__codelineno-41-43" name="__codelineno-41-43" href="#__codelineno-41-43"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">pop</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-44" name="__codelineno-41-44" href="#__codelineno-41-44"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">pop</span><span class="p">();</span>
<a id="__codelineno-41-45" name="__codelineno-41-45" href="#__codelineno-41-45"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">num</span><span class="p">;</span>
<a id="__codelineno-41-46" name="__codelineno-41-46" href="#__codelineno-41-46"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span>
<a id="__codelineno-41-47" name="__codelineno-41-47" href="#__codelineno-41-47"></a>
<a id="__codelineno-41-48" name="__codelineno-41-48" href="#__codelineno-41-48"></a><span class="w">        </span><span class="c1">// 返回 ArrayList</span>
<a id="__codelineno-41-49" name="__codelineno-41-49" href="#__codelineno-41-49"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">toList</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-50" name="__codelineno-41-50" href="#__codelineno-41-50"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">stack</span><span class="p">.</span><span class="o">?</span><span class="p">;</span>
<a id="__codelineno-41-51" name="__codelineno-41-51" href="#__codelineno-41-51"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-41-52" name="__codelineno-41-52" href="#__codelineno-41-52"></a><span class="w">    </span><span class="p">};</span>
<a id="__codelineno-41-53" name="__codelineno-41-53" href="#__codelineno-41-53"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
## 两种实现对比

**支持操作**

两种实现都支持栈定义中的各项操作。数组实现额外支持随机访问，但这已超出了栈的定义范畴，因此一般不会用到。

**时间效率**

在基于数组的实现中，入栈和出栈操作都是在预先分配好的连续内存中进行，具有很好的缓存本地性，因此效率较高。然而，如果入栈时超出数组容量，会触发扩容机制，导致该次入栈操作的时间复杂度变为 $O(n)$ 。

在链表实现中，链表的扩容非常灵活，不存在上述数组扩容时效率降低的问题。但是，入栈操作需要初始化节点对象并修改指针，因此效率相对较低。不过，如果入栈元素本身就是节点对象，那么可以省去初始化步骤，从而提高效率。

综上所述，当入栈与出栈操作的元素是基本数据类型时，例如 `int` 或 `double` ，我们可以得出以下结论。

- 基于数组实现的栈在触发扩容时效率会降低，但由于扩容是低频操作，因此平均效率更高。
- 基于链表实现的栈可以提供更加稳定的效率表现。

**空间效率**

在初始化列表时，系统会为列表分配“初始容量”，该容量可能超过实际需求。并且，扩容机制通常是按照特定倍率（例如 2 倍）进行扩容，扩容后的容量也可能超出实际需求。因此，**基于数组实现的栈可能造成一定的空间浪费**。

然而，由于链表节点需要额外存储指针，**因此链表节点占用的空间相对较大**。

综上，我们不能简单地确定哪种实现更加节省内存，需要针对具体情况进行分析。

## 栈典型应用

- **浏览器中的后退与前进、软件中的撤销与反撤销**。每当我们打开新的网页，浏览器就会将上一个网页执行入栈，这样我们就可以通过后退操作回到上一页面。后退操作实际上是在执行出栈。如果要同时支持后退和前进，那么需要两个栈来配合实现。
- **程序内存管理**。每次调用函数时，系统都会在栈顶添加一个栈帧，用于记录函数的上下文信息。在递归函数中，向下递推阶段会不断执行入栈操作，而向上回溯阶段则会执行出栈操作。
