# 堆

「堆 heap」是一种满足特定条件的完全二叉树，主要可分为下图所示的两种类型。

- 「大顶堆 max heap」：任意节点的值 $\geq$ 其子节点的值。
- 「小顶堆 min heap」：任意节点的值 $\leq$ 其子节点的值。

![小顶堆与大顶堆](heap.assets/min_heap_and_max_heap.png)

堆作为完全二叉树的一个特例，具有以下特性。

- 最底层节点靠左填充，其他层的节点都被填满。
- 我们将二叉树的根节点称为“堆顶”，将底层最靠右的节点称为“堆底”。
- 对于大顶堆（小顶堆），堆顶元素（即根节点）的值分别是最大（最小）的。

## 堆常用操作

需要指出的是，许多编程语言提供的是「优先队列 priority queue」，这是一种抽象数据结构，定义为具有优先级排序的队列。

实际上，**堆通常用作实现优先队列，大顶堆相当于元素按从大到小顺序出队的优先队列**。从使用角度来看，我们可以将“优先队列”和“堆”看作等价的数据结构。因此，本书对两者不做特别区分，统一使用“堆“来命名。

堆的常用操作见下表，方法名需要根据编程语言来确定。

<p align="center"> 表 <id> &nbsp; 堆的操作效率 </p>

| 方法名    | 描述                                         | 时间复杂度  |
| --------- | -------------------------------------------- | ----------- |
| push()    | 元素入堆                                     | $O(\log n)$ |
| pop()     | 堆顶元素出堆                                 | $O(\log n)$ |
| peek()    | 访问堆顶元素（大 / 小顶堆分别为最大 / 小值） | $O(1)$      |
| size()    | 获取堆的元素数量                             | $O(1)$      |
| isEmpty() | 判断堆是否为空                               | $O(1)$      |

在实际应用中，我们可以直接使用编程语言提供的堆类（或优先队列类）。

!!! tip

    类似于排序算法中的“从小到大排列”和“从大到小排列”，我们可以通过修改 Comparator 来实现“小顶堆”与“大顶堆”之间的转换。

=== "Python"

    ```python title="heap.py"
    # 初始化小顶堆
    min_heap, flag = [], 1
    # 初始化大顶堆
    max_heap, flag = [], -1

    # Python 的 heapq 模块默认实现小顶堆
    # 考虑将“元素取负”后再入堆，这样就可以将大小关系颠倒，从而实现大顶堆
    # 在本示例中，flag = 1 时对应小顶堆，flag = -1 时对应大顶堆

    # 元素入堆
    heapq.heappush(max_heap, flag * 1)
    heapq.heappush(max_heap, flag * 3)
    heapq.heappush(max_heap, flag * 2)
    heapq.heappush(max_heap, flag * 5)
    heapq.heappush(max_heap, flag * 4)

    # 获取堆顶元素
    peek: int = flag * max_heap[0] # 5

    # 堆顶元素出堆
    # 出堆元素会形成一个从大到小的序列
    val = flag * heapq.heappop(max_heap) # 5
    val = flag * heapq.heappop(max_heap) # 4
    val = flag * heapq.heappop(max_heap) # 3
    val = flag * heapq.heappop(max_heap) # 2
    val = flag * heapq.heappop(max_heap) # 1

    # 获取堆大小
    size: int = len(max_heap)

    # 判断堆是否为空
    is_empty: bool = not max_heap

    # 输入列表并建堆
    min_heap: list[int] = [1, 3, 2, 5, 4]
    heapq.heapify(min_heap)
    ```

=== "C++"

    ```cpp title="heap.cpp"
    /* 初始化堆 */
    // 初始化小顶堆
    priority_queue<int, vector<int>, greater<int>> minHeap;
    // 初始化大顶堆
    priority_queue<int, vector<int>, less<int>> maxHeap;

    /* 元素入堆 */
    maxHeap.push(1);
    maxHeap.push(3);
    maxHeap.push(2);
    maxHeap.push(5);
    maxHeap.push(4);

    /* 获取堆顶元素 */
    int peek = maxHeap.top(); // 5

    /* 堆顶元素出堆 */
    // 出堆元素会形成一个从大到小的序列
    maxHeap.pop(); // 5
    maxHeap.pop(); // 4
    maxHeap.pop(); // 3
    maxHeap.pop(); // 2
    maxHeap.pop(); // 1

    /* 获取堆大小 */
    int size = maxHeap.size();

    /* 判断堆是否为空 */
    bool isEmpty = maxHeap.empty();

    /* 输入列表并建堆 */
    vector<int> input{1, 3, 2, 5, 4};
    priority_queue<int, vector<int>, greater<int>> minHeap(input.begin(), input.end());
    ```

=== "Java"

    ```java title="heap.java"
    /* 初始化堆 */
    // 初始化小顶堆
    Queue<Integer> minHeap = new PriorityQueue<>();
    // 初始化大顶堆（使用 lambda 表达式修改 Comparator 即可）
    Queue<Integer> maxHeap = new PriorityQueue<>((a, b) -> b - a);
    
    /* 元素入堆 */
    maxHeap.offer(1);
    maxHeap.offer(3);
    maxHeap.offer(2);
    maxHeap.offer(5);
    maxHeap.offer(4);
    
    /* 获取堆顶元素 */
    int peek = maxHeap.peek(); // 5
    
    /* 堆顶元素出堆 */
    // 出堆元素会形成一个从大到小的序列
    peek = maxHeap.poll(); // 5
    peek = maxHeap.poll(); // 4
    peek = maxHeap.poll(); // 3
    peek = maxHeap.poll(); // 2
    peek = maxHeap.poll(); // 1
    
    /* 获取堆大小 */
    int size = maxHeap.size();
    
    /* 判断堆是否为空 */
    boolean isEmpty = maxHeap.isEmpty();
    
    /* 输入列表并建堆 */
    minHeap = new PriorityQueue<>(Arrays.asList(1, 3, 2, 5, 4));
    ```

=== "C#"

    ```csharp title="heap.cs"
    /* 初始化堆 */
    // 初始化小顶堆
    PriorityQueue<int, int> minHeap = new();
    // 初始化大顶堆（使用 lambda 表达式修改 Comparator 即可）
    PriorityQueue<int, int> maxHeap = new(Comparer<int>.Create((x, y) => y - x));

    /* 元素入堆 */
    maxHeap.Enqueue(1, 1);
    maxHeap.Enqueue(3, 3);
    maxHeap.Enqueue(2, 2);
    maxHeap.Enqueue(5, 5);
    maxHeap.Enqueue(4, 4);

    /* 获取堆顶元素 */
    int peek = maxHeap.Peek();//5

    /* 堆顶元素出堆 */
    // 出堆元素会形成一个从大到小的序列
    peek = maxHeap.Dequeue();  // 5
    peek = maxHeap.Dequeue();  // 4
    peek = maxHeap.Dequeue();  // 3
    peek = maxHeap.Dequeue();  // 2
    peek = maxHeap.Dequeue();  // 1

    /* 获取堆大小 */
    int size = maxHeap.Count;

    /* 判断堆是否为空 */
    bool isEmpty = maxHeap.Count == 0;

    /* 输入列表并建堆 */
    minHeap = new PriorityQueue<int, int>(new List<(int, int)> { (1, 1), (3, 3), (2, 2), (5, 5), (4, 4), });
    ```

=== "Go"

    ```go title="heap.go"
    // Go 语言中可以通过实现 heap.Interface 来构建整数大顶堆
    // 实现 heap.Interface 需要同时实现 sort.Interface
    type intHeap []any

    // Push heap.Interface 的方法，实现推入元素到堆
    func (h *intHeap) Push(x any) {
        // Push 和 Pop 使用 pointer receiver 作为参数
        // 因为它们不仅会对切片的内容进行调整，还会修改切片的长度。
        *h = append(*h, x.(int))
    }

    // Pop heap.Interface 的方法，实现弹出堆顶元素
    func (h *intHeap) Pop() any {
        // 待出堆元素存放在最后
        last := (*h)[len(*h)-1]
        *h = (*h)[:len(*h)-1]
        return last
    }

    // Len sort.Interface 的方法
    func (h *intHeap) Len() int {
        return len(*h)
    }

    // Less sort.Interface 的方法
    func (h *intHeap) Less(i, j int) bool {
        // 如果实现小顶堆，则需要调整为小于号
        return (*h)[i].(int) > (*h)[j].(int)
    }

    // Swap sort.Interface 的方法
    func (h *intHeap) Swap(i, j int) {
        (*h)[i], (*h)[j] = (*h)[j], (*h)[i]
    }

    // Top 获取堆顶元素
    func (h *intHeap) Top() any {
        return (*h)[0]
    }

    /* Driver Code */
    func TestHeap(t *testing.T) {
        /* 初始化堆 */
        // 初始化大顶堆
        maxHeap := &intHeap{}
        heap.Init(maxHeap)
        /* 元素入堆 */
        // 调用 heap.Interface 的方法，来添加元素
        heap.Push(maxHeap, 1)
        heap.Push(maxHeap, 3)
        heap.Push(maxHeap, 2)
        heap.Push(maxHeap, 4)
        heap.Push(maxHeap, 5)

        /* 获取堆顶元素 */
        top := maxHeap.Top()
        fmt.Printf("堆顶元素为 %d\n", top)

        /* 堆顶元素出堆 */
        // 调用 heap.Interface 的方法，来移除元素
        heap.Pop(maxHeap) // 5
        heap.Pop(maxHeap) // 4
        heap.Pop(maxHeap) // 3
        heap.Pop(maxHeap) // 2
        heap.Pop(maxHeap) // 1

        /* 获取堆大小 */
        size := len(*maxHeap)
        fmt.Printf("堆元素数量为 %d\n", size)

        /* 判断堆是否为空 */
        isEmpty := len(*maxHeap) == 0
        fmt.Printf("堆是否为空 %t\n", isEmpty)
    }
    ```

=== "Swift"

    ```swift title="heap.swift"
    // Swift 未提供内置 Heap 类
    ```

=== "JS"

    ```javascript title="heap.js"
    // JavaScript 未提供内置 Heap 类
    ```

=== "TS"

    ```typescript title="heap.ts"
    // TypeScript 未提供内置 Heap 类
    ```

=== "Dart"

    ```dart title="heap.dart"
    // Dart 未提供内置 Heap 类
    ```

=== "Rust"

    ```rust title="heap.rs"
    use std::collections::BinaryHeap;
    use std::cmp::Reverse;

    /* 初始化堆 */
    // 初始化小顶堆
    let mut min_heap = BinaryHeap::<Reverse<i32>>::new();
    // 初始化大顶堆
    let mut max_heap = BinaryHeap::new();

    /* 元素入堆 */
    max_heap.push(1);
    max_heap.push(3);
    max_heap.push(2);
    max_heap.push(5);
    max_heap.push(4);
    
    /* 获取堆顶元素 */
    let peek = max_heap.peek().unwrap();  // 5

    /* 堆顶元素出堆 */
    // 出堆元素会形成一个从大到小的序列
    let peek = max_heap.pop().unwrap();   // 5
    let peek = max_heap.pop().unwrap();   // 4
    let peek = max_heap.pop().unwrap();   // 3
    let peek = max_heap.pop().unwrap();   // 2
    let peek = max_heap.pop().unwrap();   // 1

    /* 获取堆大小 */
    let size = max_heap.len();

    /* 判断堆是否为空 */
    let is_empty = max_heap.is_empty();

    /* 输入列表并建堆 */
    let min_heap = BinaryHeap::from(vec![Reverse(1), Reverse(3), Reverse(2), Reverse(5), Reverse(4)]);
    ```

=== "C"

    ```c title="heap.c"
    // C 未提供内置 Heap 类
    ```

=== "Zig"

    ```zig title="heap.zig"

    ```

## 堆的实现

下文实现的是大顶堆。若要将其转换为小顶堆，只需将所有大小逻辑判断取逆（例如，将 $\geq$ 替换为 $\leq$ ）。感兴趣的读者可以自行实现。

### 堆的存储与表示

我们在二叉树章节中学习到，完全二叉树非常适合用数组来表示。由于堆正是一种完全二叉树，**我们将采用数组来存储堆**。

当使用数组表示二叉树时，元素代表节点值，索引代表节点在二叉树中的位置。**节点指针通过索引映射公式来实现**。

如下图所示，给定索引 $i$ ，其左子节点索引为 $2i + 1$ ，右子节点索引为 $2i + 2$ ，父节点索引为 $(i - 1) / 2$（向下取整）。当索引越界时，表示空节点或节点不存在。

![堆的表示与存储](heap.assets/representation_of_heap.png)

我们可以将索引映射公式封装成函数，方便后续使用。

<div class="tabbed-set tabbed-alternate" data-tabs="2:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_2_1" name="__tabbed_2" type="radio"><input id="__tabbed_2_2" name="__tabbed_2" type="radio"><input id="__tabbed_2_3" name="__tabbed_2" type="radio"><input id="__tabbed_2_4" name="__tabbed_2" type="radio"><input id="__tabbed_2_5" name="__tabbed_2" type="radio"><input id="__tabbed_2_6" name="__tabbed_2" type="radio"><input id="__tabbed_2_7" name="__tabbed_2" type="radio"><input id="__tabbed_2_8" name="__tabbed_2" type="radio"><input id="__tabbed_2_9" name="__tabbed_2" type="radio"><input id="__tabbed_2_10" name="__tabbed_2" type="radio"><input id="__tabbed_2_11" name="__tabbed_2" type="radio"><input id="__tabbed_2_12" name="__tabbed_2" type="radio"><input id="__tabbed_2_13" name="__tabbed_2" type="radio"><input id="__tabbed_2_14" name="__tabbed_2" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_2_1"><a href="#__tabbed_2_1" tabindex="-1">Python</a></label><label for="__tabbed_2_2"><a href="#__tabbed_2_2" tabindex="-1">C++</a></label><label for="__tabbed_2_3"><a href="#__tabbed_2_3" tabindex="-1">Java</a></label><label for="__tabbed_2_4"><a href="#__tabbed_2_4" tabindex="-1">C#</a></label><label for="__tabbed_2_5"><a href="#__tabbed_2_5" tabindex="-1">Go</a></label><label for="__tabbed_2_6"><a href="#__tabbed_2_6" tabindex="-1">Swift</a></label><label for="__tabbed_2_7"><a href="#__tabbed_2_7" tabindex="-1">JS</a></label><label for="__tabbed_2_8"><a href="#__tabbed_2_8" tabindex="-1">TS</a></label><label for="__tabbed_2_9"><a href="#__tabbed_2_9" tabindex="-1">Dart</a></label><label for="__tabbed_2_10"><a href="#__tabbed_2_10" tabindex="-1">Rust</a></label><label for="__tabbed_2_11"><a href="#__tabbed_2_11" tabindex="-1">C</a></label><label for="__tabbed_2_12"><a href="#__tabbed_2_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_2_13"><a href="#__tabbed_2_13" tabindex="-1">Ruby</a></label><label for="__tabbed_2_14"><a href="#__tabbed_2_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.py</span><pre id="__code_14"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_14 > code"></button><code><a id="__codelineno-14-1" name="__codelineno-14-1" href="#__codelineno-14-1"></a><span class="k">def</span> <span class="nf">left</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">i</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-2" name="__codelineno-14-2" href="#__codelineno-14-2"></a><span class="w">    </span><span class="sd">"""获取左子节点的索引"""</span>
<a id="__codelineno-14-3" name="__codelineno-14-3" href="#__codelineno-14-3"></a>    <span class="k">return</span> <span class="mi">2</span> <span class="o">*</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">1</span>
<a id="__codelineno-14-4" name="__codelineno-14-4" href="#__codelineno-14-4"></a>
<a id="__codelineno-14-5" name="__codelineno-14-5" href="#__codelineno-14-5"></a><span class="k">def</span> <span class="nf">right</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">i</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-6" name="__codelineno-14-6" href="#__codelineno-14-6"></a><span class="w">    </span><span class="sd">"""获取右子节点的索引"""</span>
<a id="__codelineno-14-7" name="__codelineno-14-7" href="#__codelineno-14-7"></a>    <span class="k">return</span> <span class="mi">2</span> <span class="o">*</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">2</span>
<a id="__codelineno-14-8" name="__codelineno-14-8" href="#__codelineno-14-8"></a>
<a id="__codelineno-14-9" name="__codelineno-14-9" href="#__codelineno-14-9"></a><span class="k">def</span> <span class="nf">parent</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">i</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-10" name="__codelineno-14-10" href="#__codelineno-14-10"></a><span class="w">    </span><span class="sd">"""获取父节点的索引"""</span>
<a id="__codelineno-14-11" name="__codelineno-14-11" href="#__codelineno-14-11"></a>    <span class="k">return</span> <span class="p">(</span><span class="n">i</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span> <span class="o">//</span> <span class="mi">2</span>  <span class="c1"># 向下整除</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cpp</span><pre id="__code_15"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_15 > code"></button><code><a id="__codelineno-15-1" name="__codelineno-15-1" href="#__codelineno-15-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-15-2" name="__codelineno-15-2" href="#__codelineno-15-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">left</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-3" name="__codelineno-15-3" href="#__codelineno-15-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-15-4" name="__codelineno-15-4" href="#__codelineno-15-4"></a><span class="p">}</span>
<a id="__codelineno-15-5" name="__codelineno-15-5" href="#__codelineno-15-5"></a>
<a id="__codelineno-15-6" name="__codelineno-15-6" href="#__codelineno-15-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-15-7" name="__codelineno-15-7" href="#__codelineno-15-7"></a><span class="kt">int</span><span class="w"> </span><span class="nf">right</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-8" name="__codelineno-15-8" href="#__codelineno-15-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span>
<a id="__codelineno-15-9" name="__codelineno-15-9" href="#__codelineno-15-9"></a><span class="p">}</span>
<a id="__codelineno-15-10" name="__codelineno-15-10" href="#__codelineno-15-10"></a>
<a id="__codelineno-15-11" name="__codelineno-15-11" href="#__codelineno-15-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-15-12" name="__codelineno-15-12" href="#__codelineno-15-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">parent</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-13" name="__codelineno-15-13" href="#__codelineno-15-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-15-14" name="__codelineno-15-14" href="#__codelineno-15-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.java</span><pre id="__code_16"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_16 > code"></button><code><a id="__codelineno-16-1" name="__codelineno-16-1" href="#__codelineno-16-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-16-2" name="__codelineno-16-2" href="#__codelineno-16-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">left</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-3" name="__codelineno-16-3" href="#__codelineno-16-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-16-4" name="__codelineno-16-4" href="#__codelineno-16-4"></a><span class="p">}</span>
<a id="__codelineno-16-5" name="__codelineno-16-5" href="#__codelineno-16-5"></a>
<a id="__codelineno-16-6" name="__codelineno-16-6" href="#__codelineno-16-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-16-7" name="__codelineno-16-7" href="#__codelineno-16-7"></a><span class="kt">int</span><span class="w"> </span><span class="nf">right</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-8" name="__codelineno-16-8" href="#__codelineno-16-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span>
<a id="__codelineno-16-9" name="__codelineno-16-9" href="#__codelineno-16-9"></a><span class="p">}</span>
<a id="__codelineno-16-10" name="__codelineno-16-10" href="#__codelineno-16-10"></a>
<a id="__codelineno-16-11" name="__codelineno-16-11" href="#__codelineno-16-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-16-12" name="__codelineno-16-12" href="#__codelineno-16-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">parent</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-13" name="__codelineno-16-13" href="#__codelineno-16-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-16-14" name="__codelineno-16-14" href="#__codelineno-16-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cs</span><pre id="__code_17"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_17 > code"></button><code><a id="__codelineno-17-1" name="__codelineno-17-1" href="#__codelineno-17-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-17-2" name="__codelineno-17-2" href="#__codelineno-17-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">Left</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-3" name="__codelineno-17-3" href="#__codelineno-17-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-17-4" name="__codelineno-17-4" href="#__codelineno-17-4"></a><span class="p">}</span>
<a id="__codelineno-17-5" name="__codelineno-17-5" href="#__codelineno-17-5"></a>
<a id="__codelineno-17-6" name="__codelineno-17-6" href="#__codelineno-17-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-17-7" name="__codelineno-17-7" href="#__codelineno-17-7"></a><span class="kt">int</span><span class="w"> </span><span class="nf">Right</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-8" name="__codelineno-17-8" href="#__codelineno-17-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">2</span><span class="p">;</span>
<a id="__codelineno-17-9" name="__codelineno-17-9" href="#__codelineno-17-9"></a><span class="p">}</span>
<a id="__codelineno-17-10" name="__codelineno-17-10" href="#__codelineno-17-10"></a>
<a id="__codelineno-17-11" name="__codelineno-17-11" href="#__codelineno-17-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-17-12" name="__codelineno-17-12" href="#__codelineno-17-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">Parent</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-13" name="__codelineno-17-13" href="#__codelineno-17-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="m">2</span><span class="p">;</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-17-14" name="__codelineno-17-14" href="#__codelineno-17-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.go</span><pre id="__code_18"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_18 > code"></button><code><a id="__codelineno-18-1" name="__codelineno-18-1" href="#__codelineno-18-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-18-2" name="__codelineno-18-2" href="#__codelineno-18-2"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-3" name="__codelineno-18-3" href="#__codelineno-18-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="o">*</span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-18-4" name="__codelineno-18-4" href="#__codelineno-18-4"></a><span class="p">}</span>
<a id="__codelineno-18-5" name="__codelineno-18-5" href="#__codelineno-18-5"></a>
<a id="__codelineno-18-6" name="__codelineno-18-6" href="#__codelineno-18-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-18-7" name="__codelineno-18-7" href="#__codelineno-18-7"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-8" name="__codelineno-18-8" href="#__codelineno-18-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="o">*</span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span>
<a id="__codelineno-18-9" name="__codelineno-18-9" href="#__codelineno-18-9"></a><span class="p">}</span>
<a id="__codelineno-18-10" name="__codelineno-18-10" href="#__codelineno-18-10"></a>
<a id="__codelineno-18-11" name="__codelineno-18-11" href="#__codelineno-18-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-18-12" name="__codelineno-18-12" href="#__codelineno-18-12"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-13" name="__codelineno-18-13" href="#__codelineno-18-13"></a><span class="w">    </span><span class="c1">// 向下整除</span>
<a id="__codelineno-18-14" name="__codelineno-18-14" href="#__codelineno-18-14"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span>
<a id="__codelineno-18-15" name="__codelineno-18-15" href="#__codelineno-18-15"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.swift</span><pre id="__code_19"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_19 > code"></button><code><a id="__codelineno-19-1" name="__codelineno-19-1" href="#__codelineno-19-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-19-2" name="__codelineno-19-2" href="#__codelineno-19-2"></a><span class="kd">func</span> <span class="nf">left</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-3" name="__codelineno-19-3" href="#__codelineno-19-3"></a>    <span class="mi">2</span> <span class="o">*</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">1</span>
<a id="__codelineno-19-4" name="__codelineno-19-4" href="#__codelineno-19-4"></a><span class="p">}</span>
<a id="__codelineno-19-5" name="__codelineno-19-5" href="#__codelineno-19-5"></a>
<a id="__codelineno-19-6" name="__codelineno-19-6" href="#__codelineno-19-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-19-7" name="__codelineno-19-7" href="#__codelineno-19-7"></a><span class="kd">func</span> <span class="nf">right</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-8" name="__codelineno-19-8" href="#__codelineno-19-8"></a>    <span class="mi">2</span> <span class="o">*</span> <span class="n">i</span> <span class="o">+</span> <span class="mi">2</span>
<a id="__codelineno-19-9" name="__codelineno-19-9" href="#__codelineno-19-9"></a><span class="p">}</span>
<a id="__codelineno-19-10" name="__codelineno-19-10" href="#__codelineno-19-10"></a>
<a id="__codelineno-19-11" name="__codelineno-19-11" href="#__codelineno-19-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-19-12" name="__codelineno-19-12" href="#__codelineno-19-12"></a><span class="kd">func</span> <span class="nf">parent</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-13" name="__codelineno-19-13" href="#__codelineno-19-13"></a>    <span class="p">(</span><span class="n">i</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span> <span class="o">/</span> <span class="mi">2</span> <span class="c1">// 向下整除</span>
<a id="__codelineno-19-14" name="__codelineno-19-14" href="#__codelineno-19-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.js</span><pre id="__code_20"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_20 > code"></button><code><a id="__codelineno-20-1" name="__codelineno-20-1" href="#__codelineno-20-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-20-2" name="__codelineno-20-2" href="#__codelineno-20-2"></a><span class="err">#</span><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-3" name="__codelineno-20-3" href="#__codelineno-20-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mf">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-20-4" name="__codelineno-20-4" href="#__codelineno-20-4"></a><span class="p">}</span>
<a id="__codelineno-20-5" name="__codelineno-20-5" href="#__codelineno-20-5"></a>
<a id="__codelineno-20-6" name="__codelineno-20-6" href="#__codelineno-20-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-20-7" name="__codelineno-20-7" href="#__codelineno-20-7"></a><span class="err">#</span><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-8" name="__codelineno-20-8" href="#__codelineno-20-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mf">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mf">2</span><span class="p">;</span>
<a id="__codelineno-20-9" name="__codelineno-20-9" href="#__codelineno-20-9"></a><span class="p">}</span>
<a id="__codelineno-20-10" name="__codelineno-20-10" href="#__codelineno-20-10"></a>
<a id="__codelineno-20-11" name="__codelineno-20-11" href="#__codelineno-20-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-20-12" name="__codelineno-20-12" href="#__codelineno-20-12"></a><span class="err">#</span><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-13" name="__codelineno-20-13" href="#__codelineno-20-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">floor</span><span class="p">((</span><span class="nx">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mf">2</span><span class="p">);</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-20-14" name="__codelineno-20-14" href="#__codelineno-20-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.ts</span><pre id="__code_21"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_21 > code"></button><code><a id="__codelineno-21-1" name="__codelineno-21-1" href="#__codelineno-21-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-21-2" name="__codelineno-21-2" href="#__codelineno-21-2"></a><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-3" name="__codelineno-21-3" href="#__codelineno-21-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mf">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-21-4" name="__codelineno-21-4" href="#__codelineno-21-4"></a><span class="p">}</span>
<a id="__codelineno-21-5" name="__codelineno-21-5" href="#__codelineno-21-5"></a>
<a id="__codelineno-21-6" name="__codelineno-21-6" href="#__codelineno-21-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-21-7" name="__codelineno-21-7" href="#__codelineno-21-7"></a><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-8" name="__codelineno-21-8" href="#__codelineno-21-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mf">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mf">2</span><span class="p">;</span>
<a id="__codelineno-21-9" name="__codelineno-21-9" href="#__codelineno-21-9"></a><span class="p">}</span>
<a id="__codelineno-21-10" name="__codelineno-21-10" href="#__codelineno-21-10"></a>
<a id="__codelineno-21-11" name="__codelineno-21-11" href="#__codelineno-21-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-21-12" name="__codelineno-21-12" href="#__codelineno-21-12"></a><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-13" name="__codelineno-21-13" href="#__codelineno-21-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">floor</span><span class="p">((</span><span class="nx">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mf">2</span><span class="p">);</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-21-14" name="__codelineno-21-14" href="#__codelineno-21-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.dart</span><pre id="__code_22"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_22 > code"></button><code><a id="__codelineno-22-1" name="__codelineno-22-1" href="#__codelineno-22-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-22-2" name="__codelineno-22-2" href="#__codelineno-22-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">_left</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-3" name="__codelineno-22-3" href="#__codelineno-22-3"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-22-4" name="__codelineno-22-4" href="#__codelineno-22-4"></a><span class="p">}</span>
<a id="__codelineno-22-5" name="__codelineno-22-5" href="#__codelineno-22-5"></a>
<a id="__codelineno-22-6" name="__codelineno-22-6" href="#__codelineno-22-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-22-7" name="__codelineno-22-7" href="#__codelineno-22-7"></a><span class="kt">int</span><span class="w"> </span><span class="n">_right</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-8" name="__codelineno-22-8" href="#__codelineno-22-8"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">2</span><span class="p">;</span>
<a id="__codelineno-22-9" name="__codelineno-22-9" href="#__codelineno-22-9"></a><span class="p">}</span>
<a id="__codelineno-22-10" name="__codelineno-22-10" href="#__codelineno-22-10"></a>
<a id="__codelineno-22-11" name="__codelineno-22-11" href="#__codelineno-22-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-22-12" name="__codelineno-22-12" href="#__codelineno-22-12"></a><span class="kt">int</span><span class="w"> </span><span class="n">_parent</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-13" name="__codelineno-22-13" href="#__codelineno-22-13"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span><span class="w"> </span><span class="o">~/</span><span class="w"> </span><span class="m">2</span><span class="p">;</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-22-14" name="__codelineno-22-14" href="#__codelineno-22-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rs</span><pre id="__code_23"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_23 > code"></button><code><a id="__codelineno-23-1" name="__codelineno-23-1" href="#__codelineno-23-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-23-2" name="__codelineno-23-2" href="#__codelineno-23-2"></a><span class="k">fn</span> <span class="nf">left</span><span class="p">(</span><span class="n">i</span>: <span class="kt">usize</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-23-3" name="__codelineno-23-3" href="#__codelineno-23-3"></a><span class="w">    </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-23-4" name="__codelineno-23-4" href="#__codelineno-23-4"></a><span class="p">}</span>
<a id="__codelineno-23-5" name="__codelineno-23-5" href="#__codelineno-23-5"></a>
<a id="__codelineno-23-6" name="__codelineno-23-6" href="#__codelineno-23-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-23-7" name="__codelineno-23-7" href="#__codelineno-23-7"></a><span class="k">fn</span> <span class="nf">right</span><span class="p">(</span><span class="n">i</span>: <span class="kt">usize</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-23-8" name="__codelineno-23-8" href="#__codelineno-23-8"></a><span class="w">    </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span>
<a id="__codelineno-23-9" name="__codelineno-23-9" href="#__codelineno-23-9"></a><span class="p">}</span>
<a id="__codelineno-23-10" name="__codelineno-23-10" href="#__codelineno-23-10"></a>
<a id="__codelineno-23-11" name="__codelineno-23-11" href="#__codelineno-23-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-23-12" name="__codelineno-23-12" href="#__codelineno-23-12"></a><span class="k">fn</span> <span class="nf">parent</span><span class="p">(</span><span class="n">i</span>: <span class="kt">usize</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-23-13" name="__codelineno-23-13" href="#__codelineno-23-13"></a><span class="w">    </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-23-14" name="__codelineno-23-14" href="#__codelineno-23-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.c</span><pre id="__code_24"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_24 > code"></button><code><a id="__codelineno-24-1" name="__codelineno-24-1" href="#__codelineno-24-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-24-2" name="__codelineno-24-2" href="#__codelineno-24-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">left</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-3" name="__codelineno-24-3" href="#__codelineno-24-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-24-4" name="__codelineno-24-4" href="#__codelineno-24-4"></a><span class="p">}</span>
<a id="__codelineno-24-5" name="__codelineno-24-5" href="#__codelineno-24-5"></a>
<a id="__codelineno-24-6" name="__codelineno-24-6" href="#__codelineno-24-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-24-7" name="__codelineno-24-7" href="#__codelineno-24-7"></a><span class="kt">int</span><span class="w"> </span><span class="nf">right</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-8" name="__codelineno-24-8" href="#__codelineno-24-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span>
<a id="__codelineno-24-9" name="__codelineno-24-9" href="#__codelineno-24-9"></a><span class="p">}</span>
<a id="__codelineno-24-10" name="__codelineno-24-10" href="#__codelineno-24-10"></a>
<a id="__codelineno-24-11" name="__codelineno-24-11" href="#__codelineno-24-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-24-12" name="__codelineno-24-12" href="#__codelineno-24-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">parent</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-13" name="__codelineno-24-13" href="#__codelineno-24-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span><span class="w"> </span><span class="c1">// 向下取整</span>
<a id="__codelineno-24-14" name="__codelineno-24-14" href="#__codelineno-24-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.kt</span><pre id="__code_25"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_25 > code"></button><code><a id="__codelineno-25-1" name="__codelineno-25-1" href="#__codelineno-25-1"></a><span class="cm">/* 获取左子节点的索引 */</span>
<a id="__codelineno-25-2" name="__codelineno-25-2" href="#__codelineno-25-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">left</span><span class="p">(</span><span class="n">i</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-3" name="__codelineno-25-3" href="#__codelineno-25-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">1</span>
<a id="__codelineno-25-4" name="__codelineno-25-4" href="#__codelineno-25-4"></a><span class="p">}</span>
<a id="__codelineno-25-5" name="__codelineno-25-5" href="#__codelineno-25-5"></a>
<a id="__codelineno-25-6" name="__codelineno-25-6" href="#__codelineno-25-6"></a><span class="cm">/* 获取右子节点的索引 */</span>
<a id="__codelineno-25-7" name="__codelineno-25-7" href="#__codelineno-25-7"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">right</span><span class="p">(</span><span class="n">i</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-8" name="__codelineno-25-8" href="#__codelineno-25-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="m">2</span>
<a id="__codelineno-25-9" name="__codelineno-25-9" href="#__codelineno-25-9"></a><span class="p">}</span>
<a id="__codelineno-25-10" name="__codelineno-25-10" href="#__codelineno-25-10"></a>
<a id="__codelineno-25-11" name="__codelineno-25-11" href="#__codelineno-25-11"></a><span class="cm">/* 获取父节点的索引 */</span>
<a id="__codelineno-25-12" name="__codelineno-25-12" href="#__codelineno-25-12"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">parent</span><span class="p">(</span><span class="n">i</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-13" name="__codelineno-25-13" href="#__codelineno-25-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="m">2</span><span class="w"> </span><span class="c1">// 向下整除</span>
<a id="__codelineno-25-14" name="__codelineno-25-14" href="#__codelineno-25-14"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rb</span><pre id="__code_26"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_26 > code"></button><code><a id="__codelineno-26-1" name="__codelineno-26-1" href="#__codelineno-26-1"></a><span class="c1">### 获取左子节点的索引 ###</span>
<a id="__codelineno-26-2" name="__codelineno-26-2" href="#__codelineno-26-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">left</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-26-3" name="__codelineno-26-3" href="#__codelineno-26-3"></a><span class="w">  </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-26-4" name="__codelineno-26-4" href="#__codelineno-26-4"></a><span class="k">end</span>
<a id="__codelineno-26-5" name="__codelineno-26-5" href="#__codelineno-26-5"></a>
<a id="__codelineno-26-6" name="__codelineno-26-6" href="#__codelineno-26-6"></a><span class="c1">### 获取右子节点的索引 ###</span>
<a id="__codelineno-26-7" name="__codelineno-26-7" href="#__codelineno-26-7"></a><span class="k">def</span><span class="w"> </span><span class="nf">right</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-26-8" name="__codelineno-26-8" href="#__codelineno-26-8"></a><span class="w">  </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span>
<a id="__codelineno-26-9" name="__codelineno-26-9" href="#__codelineno-26-9"></a><span class="k">end</span>
<a id="__codelineno-26-10" name="__codelineno-26-10" href="#__codelineno-26-10"></a>
<a id="__codelineno-26-11" name="__codelineno-26-11" href="#__codelineno-26-11"></a><span class="c1">### 获取父节点的索引 ###</span>
<a id="__codelineno-26-12" name="__codelineno-26-12" href="#__codelineno-26-12"></a><span class="k">def</span><span class="w"> </span><span class="nf">parent</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-26-13" name="__codelineno-26-13" href="#__codelineno-26-13"></a><span class="w">  </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="o">/</span><span class="w"> </span><span class="mi">2</span><span class="w">     </span><span class="c1"># 向下整除</span>
<a id="__codelineno-26-14" name="__codelineno-26-14" href="#__codelineno-26-14"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.zig</span><pre id="__code_27"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_27 > code"></button><code><a id="__codelineno-27-1" name="__codelineno-27-1" href="#__codelineno-27-1"></a><span class="c1">// 获取左子节点的索引</span>
<a id="__codelineno-27-2" name="__codelineno-27-2" href="#__codelineno-27-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-3" name="__codelineno-27-3" href="#__codelineno-27-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-27-4" name="__codelineno-27-4" href="#__codelineno-27-4"></a><span class="p">}</span>
<a id="__codelineno-27-5" name="__codelineno-27-5" href="#__codelineno-27-5"></a>
<a id="__codelineno-27-6" name="__codelineno-27-6" href="#__codelineno-27-6"></a><span class="c1">// 获取右子节点的索引</span>
<a id="__codelineno-27-7" name="__codelineno-27-7" href="#__codelineno-27-7"></a><span class="k">fn</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-8" name="__codelineno-27-8" href="#__codelineno-27-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="mi">2</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">2</span><span class="p">;</span>
<a id="__codelineno-27-9" name="__codelineno-27-9" href="#__codelineno-27-9"></a><span class="p">}</span>
<a id="__codelineno-27-10" name="__codelineno-27-10" href="#__codelineno-27-10"></a>
<a id="__codelineno-27-11" name="__codelineno-27-11" href="#__codelineno-27-11"></a><span class="c1">// 获取父节点的索引</span>
<a id="__codelineno-27-12" name="__codelineno-27-12" href="#__codelineno-27-12"></a><span class="k">fn</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-13" name="__codelineno-27-13" href="#__codelineno-27-13"></a><span class="w">    </span><span class="c1">// return (i - 1) / 2; // 向下整除</span>
<a id="__codelineno-27-14" name="__codelineno-27-14" href="#__codelineno-27-14"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">@divFloor</span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">,</span><span class="w"> </span><span class="mi">2</span><span class="p">);</span>
<a id="__codelineno-27-15" name="__codelineno-27-15" href="#__codelineno-27-15"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
### 访问堆顶元素

堆顶元素即为二叉树的根节点，也就是列表的首个元素。

<div class="tabbed-set tabbed-alternate" data-tabs="3:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_3_1" name="__tabbed_3" type="radio"><input id="__tabbed_3_2" name="__tabbed_3" type="radio"><input id="__tabbed_3_3" name="__tabbed_3" type="radio"><input id="__tabbed_3_4" name="__tabbed_3" type="radio"><input id="__tabbed_3_5" name="__tabbed_3" type="radio"><input id="__tabbed_3_6" name="__tabbed_3" type="radio"><input id="__tabbed_3_7" name="__tabbed_3" type="radio"><input id="__tabbed_3_8" name="__tabbed_3" type="radio"><input id="__tabbed_3_9" name="__tabbed_3" type="radio"><input id="__tabbed_3_10" name="__tabbed_3" type="radio"><input id="__tabbed_3_11" name="__tabbed_3" type="radio"><input id="__tabbed_3_12" name="__tabbed_3" type="radio"><input id="__tabbed_3_13" name="__tabbed_3" type="radio"><input id="__tabbed_3_14" name="__tabbed_3" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_3_1"><a href="#__tabbed_3_1" tabindex="-1">Python</a></label><label for="__tabbed_3_2"><a href="#__tabbed_3_2" tabindex="-1">C++</a></label><label for="__tabbed_3_3"><a href="#__tabbed_3_3" tabindex="-1">Java</a></label><label for="__tabbed_3_4"><a href="#__tabbed_3_4" tabindex="-1">C#</a></label><label for="__tabbed_3_5"><a href="#__tabbed_3_5" tabindex="-1">Go</a></label><label for="__tabbed_3_6"><a href="#__tabbed_3_6" tabindex="-1">Swift</a></label><label for="__tabbed_3_7"><a href="#__tabbed_3_7" tabindex="-1">JS</a></label><label for="__tabbed_3_8"><a href="#__tabbed_3_8" tabindex="-1">TS</a></label><label for="__tabbed_3_9"><a href="#__tabbed_3_9" tabindex="-1">Dart</a></label><label for="__tabbed_3_10"><a href="#__tabbed_3_10" tabindex="-1">Rust</a></label><label for="__tabbed_3_11"><a href="#__tabbed_3_11" tabindex="-1">C</a></label><label for="__tabbed_3_12"><a href="#__tabbed_3_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_3_13"><a href="#__tabbed_3_13" tabindex="-1">Ruby</a></label><label for="__tabbed_3_14"><a href="#__tabbed_3_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.py</span><pre id="__code_28"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_28 > code"></button><code><a id="__codelineno-28-1" name="__codelineno-28-1" href="#__codelineno-28-1"></a><span class="k">def</span> <span class="nf">peek</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-28-2" name="__codelineno-28-2" href="#__codelineno-28-2"></a><span class="w">    </span><span class="sd">"""访问堆顶元素"""</span>
<a id="__codelineno-28-3" name="__codelineno-28-3" href="#__codelineno-28-3"></a>    <span class="k">return</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cpp</span><pre id="__code_29"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_29 > code"></button><code><a id="__codelineno-29-1" name="__codelineno-29-1" href="#__codelineno-29-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-29-2" name="__codelineno-29-2" href="#__codelineno-29-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-29-3" name="__codelineno-29-3" href="#__codelineno-29-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="mi">0</span><span class="p">];</span>
<a id="__codelineno-29-4" name="__codelineno-29-4" href="#__codelineno-29-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.java</span><pre id="__code_30"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_30 > code"></button><code><a id="__codelineno-30-1" name="__codelineno-30-1" href="#__codelineno-30-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-30-2" name="__codelineno-30-2" href="#__codelineno-30-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-3" name="__codelineno-30-3" href="#__codelineno-30-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-30-4" name="__codelineno-30-4" href="#__codelineno-30-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cs</span><pre id="__code_31"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_31 > code"></button><code><a id="__codelineno-31-1" name="__codelineno-31-1" href="#__codelineno-31-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-31-2" name="__codelineno-31-2" href="#__codelineno-31-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">Peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-3" name="__codelineno-31-3" href="#__codelineno-31-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="m">0</span><span class="p">];</span>
<a id="__codelineno-31-4" name="__codelineno-31-4" href="#__codelineno-31-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.go</span><pre id="__code_32"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_32 > code"></button><code><a id="__codelineno-32-1" name="__codelineno-32-1" href="#__codelineno-32-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-32-2" name="__codelineno-32-2" href="#__codelineno-32-2"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">peek</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-3" name="__codelineno-32-3" href="#__codelineno-32-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<a id="__codelineno-32-4" name="__codelineno-32-4" href="#__codelineno-32-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.swift</span><pre id="__code_33"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_33 > code"></button><code><a id="__codelineno-33-1" name="__codelineno-33-1" href="#__codelineno-33-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-33-2" name="__codelineno-33-2" href="#__codelineno-33-2"></a><span class="kd">func</span> <span class="nf">peek</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-33-3" name="__codelineno-33-3" href="#__codelineno-33-3"></a>    <span class="n">maxHeap</span><span class="p">[</span><span class="mi">0</span><span class="p">]</span>
<a id="__codelineno-33-4" name="__codelineno-33-4" href="#__codelineno-33-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.js</span><pre id="__code_34"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_34 > code"></button><code><a id="__codelineno-34-1" name="__codelineno-34-1" href="#__codelineno-34-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-34-2" name="__codelineno-34-2" href="#__codelineno-34-2"></a><span class="nx">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-34-3" name="__codelineno-34-3" href="#__codelineno-34-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="mf">0</span><span class="p">];</span>
<a id="__codelineno-34-4" name="__codelineno-34-4" href="#__codelineno-34-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.ts</span><pre id="__code_35"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_35 > code"></button><code><a id="__codelineno-35-1" name="__codelineno-35-1" href="#__codelineno-35-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-35-2" name="__codelineno-35-2" href="#__codelineno-35-2"></a><span class="nx">peek</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-3" name="__codelineno-35-3" href="#__codelineno-35-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="mf">0</span><span class="p">];</span>
<a id="__codelineno-35-4" name="__codelineno-35-4" href="#__codelineno-35-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.dart</span><pre id="__code_36"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_36 > code"></button><code><a id="__codelineno-36-1" name="__codelineno-36-1" href="#__codelineno-36-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-36-2" name="__codelineno-36-2" href="#__codelineno-36-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">peek</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-3" name="__codelineno-36-3" href="#__codelineno-36-3"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="m">0</span><span class="p">];</span>
<a id="__codelineno-36-4" name="__codelineno-36-4" href="#__codelineno-36-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rs</span><pre id="__code_37"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_37 > code"></button><code><a id="__codelineno-37-1" name="__codelineno-37-1" href="#__codelineno-37-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-37-2" name="__codelineno-37-2" href="#__codelineno-37-2"></a><span class="k">fn</span> <span class="nf">peek</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;</span><span class="kt">i32</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-3" name="__codelineno-37-3" href="#__codelineno-37-3"></a><span class="w">    </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="n">first</span><span class="p">().</span><span class="n">copied</span><span class="p">()</span>
<a id="__codelineno-37-4" name="__codelineno-37-4" href="#__codelineno-37-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.c</span><pre id="__code_38"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_38 > code"></button><code><a id="__codelineno-38-1" name="__codelineno-38-1" href="#__codelineno-38-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-38-2" name="__codelineno-38-2" href="#__codelineno-38-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">peek</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-3" name="__codelineno-38-3" href="#__codelineno-38-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="mi">0</span><span class="p">];</span>
<a id="__codelineno-38-4" name="__codelineno-38-4" href="#__codelineno-38-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.kt</span><pre id="__code_39"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_39 > code"></button><code><a id="__codelineno-39-1" name="__codelineno-39-1" href="#__codelineno-39-1"></a><span class="cm">/* 访问堆顶元素 */</span>
<a id="__codelineno-39-2" name="__codelineno-39-2" href="#__codelineno-39-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">peek</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-3" name="__codelineno-39-3" href="#__codelineno-39-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="m">0</span><span class="o">]</span>
<a id="__codelineno-39-4" name="__codelineno-39-4" href="#__codelineno-39-4"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rb</span><pre id="__code_40"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_40 > code"></button><code><a id="__codelineno-40-1" name="__codelineno-40-1" href="#__codelineno-40-1"></a><span class="c1">### 访问堆顶元素 ###</span>
<a id="__codelineno-40-2" name="__codelineno-40-2" href="#__codelineno-40-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">peek</span>
<a id="__codelineno-40-3" name="__codelineno-40-3" href="#__codelineno-40-3"></a><span class="w">  </span><span class="vi">@max_heap</span><span class="o">[</span><span class="mi">0</span><span class="o">]</span>
<a id="__codelineno-40-4" name="__codelineno-40-4" href="#__codelineno-40-4"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.zig</span><pre id="__code_41"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_41 > code"></button><code><a id="__codelineno-41-1" name="__codelineno-41-1" href="#__codelineno-41-1"></a><span class="c1">// 访问堆顶元素</span>
<a id="__codelineno-41-2" name="__codelineno-41-2" href="#__codelineno-41-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">peek</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-41-3" name="__codelineno-41-3" href="#__codelineno-41-3"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="mi">0</span><span class="p">];</span>
<a id="__codelineno-41-4" name="__codelineno-41-4" href="#__codelineno-41-4"></a><span class="p">}</span><span class="w">  </span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
### 元素入堆

给定元素 `val` ，我们首先将其添加到堆底。添加之后，由于 val 可能大于堆中其他元素，堆的成立条件可能已被破坏。因此，**需要修复从插入节点到根节点的路径上的各个节点**，这个操作被称为「堆化 heapify」。

考虑从入堆节点开始，**从底至顶执行堆化**。如下图所示，我们比较插入节点与其父节点的值，如果插入节点更大，则将它们交换。然后继续执行此操作，从底至顶修复堆中的各个节点，直至越过根节点或遇到无须交换的节点时结束。

=== "<1>"
    ![元素入堆步骤](heap.assets/heap_push_step1.png)

=== "<2>"
    ![heap_push_step2](heap.assets/heap_push_step2.png)

=== "<3>"
    ![heap_push_step3](heap.assets/heap_push_step3.png)

=== "<4>"
    ![heap_push_step4](heap.assets/heap_push_step4.png)

=== "<5>"
    ![heap_push_step5](heap.assets/heap_push_step5.png)

=== "<6>"
    ![heap_push_step6](heap.assets/heap_push_step6.png)

=== "<7>"
    ![heap_push_step7](heap.assets/heap_push_step7.png)

=== "<8>"
    ![heap_push_step8](heap.assets/heap_push_step8.png)

=== "<9>"
    ![heap_push_step9](heap.assets/heap_push_step9.png)

设节点总数为 $n$ ，则树的高度为 $O(\log n)$ 。由此可知，堆化操作的循环轮数最多为 $O(\log n)$ ，**元素入堆操作的时间复杂度为 $O(\log n)$** 。

<div class="tabbed-set tabbed-alternate" data-tabs="5:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_5_1" name="__tabbed_5" type="radio"><input id="__tabbed_5_2" name="__tabbed_5" type="radio"><input id="__tabbed_5_3" name="__tabbed_5" type="radio"><input id="__tabbed_5_4" name="__tabbed_5" type="radio"><input id="__tabbed_5_5" name="__tabbed_5" type="radio"><input id="__tabbed_5_6" name="__tabbed_5" type="radio"><input id="__tabbed_5_7" name="__tabbed_5" type="radio"><input id="__tabbed_5_8" name="__tabbed_5" type="radio"><input id="__tabbed_5_9" name="__tabbed_5" type="radio"><input id="__tabbed_5_10" name="__tabbed_5" type="radio"><input id="__tabbed_5_11" name="__tabbed_5" type="radio"><input id="__tabbed_5_12" name="__tabbed_5" type="radio"><input id="__tabbed_5_13" name="__tabbed_5" type="radio"><input id="__tabbed_5_14" name="__tabbed_5" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_5_1"><a href="#__tabbed_5_1" tabindex="-1">Python</a></label><label for="__tabbed_5_2"><a href="#__tabbed_5_2" tabindex="-1">C++</a></label><label for="__tabbed_5_3"><a href="#__tabbed_5_3" tabindex="-1">Java</a></label><label for="__tabbed_5_4"><a href="#__tabbed_5_4" tabindex="-1">C#</a></label><label for="__tabbed_5_5"><a href="#__tabbed_5_5" tabindex="-1">Go</a></label><label for="__tabbed_5_6"><a href="#__tabbed_5_6" tabindex="-1">Swift</a></label><label for="__tabbed_5_7"><a href="#__tabbed_5_7" tabindex="-1">JS</a></label><label for="__tabbed_5_8"><a href="#__tabbed_5_8" tabindex="-1">TS</a></label><label for="__tabbed_5_9"><a href="#__tabbed_5_9" tabindex="-1">Dart</a></label><label for="__tabbed_5_10"><a href="#__tabbed_5_10" tabindex="-1">Rust</a></label><label for="__tabbed_5_11"><a href="#__tabbed_5_11" tabindex="-1">C</a></label><label for="__tabbed_5_12"><a href="#__tabbed_5_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_5_13"><a href="#__tabbed_5_13" tabindex="-1">Ruby</a></label><label for="__tabbed_5_14"><a href="#__tabbed_5_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.py</span><pre id="__code_42"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_42 > code"></button><code><a id="__codelineno-42-1" name="__codelineno-42-1" href="#__codelineno-42-1"></a><span class="k">def</span> <span class="nf">push</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-42-2" name="__codelineno-42-2" href="#__codelineno-42-2"></a><span class="w">    </span><span class="sd">"""元素入堆"""</span>
<a id="__codelineno-42-3" name="__codelineno-42-3" href="#__codelineno-42-3"></a>    <span class="c1"># 添加节点</span>
<a id="__codelineno-42-4" name="__codelineno-42-4" href="#__codelineno-42-4"></a>    <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-42-5" name="__codelineno-42-5" href="#__codelineno-42-5"></a>    <span class="c1"># 从底至顶堆化</span>
<a id="__codelineno-42-6" name="__codelineno-42-6" href="#__codelineno-42-6"></a>    <span class="bp">self</span><span class="o">.</span><span class="n">sift_up</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">size</span><span class="p">()</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-42-7" name="__codelineno-42-7" href="#__codelineno-42-7"></a>
<a id="__codelineno-42-8" name="__codelineno-42-8" href="#__codelineno-42-8"></a><span class="k">def</span> <span class="nf">sift_up</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">i</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-42-9" name="__codelineno-42-9" href="#__codelineno-42-9"></a><span class="w">    </span><span class="sd">"""从节点 i 开始，从底至顶堆化"""</span>
<a id="__codelineno-42-10" name="__codelineno-42-10" href="#__codelineno-42-10"></a>    <span class="k">while</span> <span class="kc">True</span><span class="p">:</span>
<a id="__codelineno-42-11" name="__codelineno-42-11" href="#__codelineno-42-11"></a>        <span class="c1"># 获取节点 i 的父节点</span>
<a id="__codelineno-42-12" name="__codelineno-42-12" href="#__codelineno-42-12"></a>        <span class="n">p</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-42-13" name="__codelineno-42-13" href="#__codelineno-42-13"></a>        <span class="c1"># 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-42-14" name="__codelineno-42-14" href="#__codelineno-42-14"></a>        <span class="k">if</span> <span class="n">p</span> <span class="o">&lt;</span> <span class="mi">0</span> <span class="ow">or</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&lt;=</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">p</span><span class="p">]:</span>
<a id="__codelineno-42-15" name="__codelineno-42-15" href="#__codelineno-42-15"></a>            <span class="k">break</span>
<a id="__codelineno-42-16" name="__codelineno-42-16" href="#__codelineno-42-16"></a>        <span class="c1"># 交换两节点</span>
<a id="__codelineno-42-17" name="__codelineno-42-17" href="#__codelineno-42-17"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span> <span class="n">p</span><span class="p">)</span>
<a id="__codelineno-42-18" name="__codelineno-42-18" href="#__codelineno-42-18"></a>        <span class="c1"># 循环向上堆化</span>
<a id="__codelineno-42-19" name="__codelineno-42-19" href="#__codelineno-42-19"></a>        <span class="n">i</span> <span class="o">=</span> <span class="n">p</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cpp</span><pre id="__code_43"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_43 > code"></button><code><a id="__codelineno-43-1" name="__codelineno-43-1" href="#__codelineno-43-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-43-2" name="__codelineno-43-2" href="#__codelineno-43-2"></a><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-43-3" name="__codelineno-43-3" href="#__codelineno-43-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-43-4" name="__codelineno-43-4" href="#__codelineno-43-4"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="n">push_back</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-43-5" name="__codelineno-43-5" href="#__codelineno-43-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-43-6" name="__codelineno-43-6" href="#__codelineno-43-6"></a><span class="w">    </span><span class="n">siftUp</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-43-7" name="__codelineno-43-7" href="#__codelineno-43-7"></a><span class="p">}</span>
<a id="__codelineno-43-8" name="__codelineno-43-8" href="#__codelineno-43-8"></a>
<a id="__codelineno-43-9" name="__codelineno-43-9" href="#__codelineno-43-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-43-10" name="__codelineno-43-10" href="#__codelineno-43-10"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftUp</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-43-11" name="__codelineno-43-11" href="#__codelineno-43-11"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nb">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-43-12" name="__codelineno-43-12" href="#__codelineno-43-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-43-13" name="__codelineno-43-13" href="#__codelineno-43-13"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-43-14" name="__codelineno-43-14" href="#__codelineno-43-14"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-43-15" name="__codelineno-43-15" href="#__codelineno-43-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">p</span><span class="p">])</span>
<a id="__codelineno-43-16" name="__codelineno-43-16" href="#__codelineno-43-16"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-43-17" name="__codelineno-43-17" href="#__codelineno-43-17"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-43-18" name="__codelineno-43-18" href="#__codelineno-43-18"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">p</span><span class="p">]);</span>
<a id="__codelineno-43-19" name="__codelineno-43-19" href="#__codelineno-43-19"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-43-20" name="__codelineno-43-20" href="#__codelineno-43-20"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-43-21" name="__codelineno-43-21" href="#__codelineno-43-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-43-22" name="__codelineno-43-22" href="#__codelineno-43-22"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.java</span><pre id="__code_44"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_44 > code"></button><code><a id="__codelineno-44-1" name="__codelineno-44-1" href="#__codelineno-44-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-44-2" name="__codelineno-44-2" href="#__codelineno-44-2"></a><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-44-3" name="__codelineno-44-3" href="#__codelineno-44-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-44-4" name="__codelineno-44-4" href="#__codelineno-44-4"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-44-5" name="__codelineno-44-5" href="#__codelineno-44-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-44-6" name="__codelineno-44-6" href="#__codelineno-44-6"></a><span class="w">    </span><span class="n">siftUp</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-44-7" name="__codelineno-44-7" href="#__codelineno-44-7"></a><span class="p">}</span>
<a id="__codelineno-44-8" name="__codelineno-44-8" href="#__codelineno-44-8"></a>
<a id="__codelineno-44-9" name="__codelineno-44-9" href="#__codelineno-44-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-44-10" name="__codelineno-44-10" href="#__codelineno-44-10"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftUp</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-44-11" name="__codelineno-44-11" href="#__codelineno-44-11"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-44-12" name="__codelineno-44-12" href="#__codelineno-44-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-44-13" name="__codelineno-44-13" href="#__codelineno-44-13"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-44-14" name="__codelineno-44-14" href="#__codelineno-44-14"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-44-15" name="__codelineno-44-15" href="#__codelineno-44-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">p</span><span class="p">))</span>
<a id="__codelineno-44-16" name="__codelineno-44-16" href="#__codelineno-44-16"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-44-17" name="__codelineno-44-17" href="#__codelineno-44-17"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-44-18" name="__codelineno-44-18" href="#__codelineno-44-18"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-44-19" name="__codelineno-44-19" href="#__codelineno-44-19"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-44-20" name="__codelineno-44-20" href="#__codelineno-44-20"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-44-21" name="__codelineno-44-21" href="#__codelineno-44-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-44-22" name="__codelineno-44-22" href="#__codelineno-44-22"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cs</span><pre id="__code_45"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_45 > code"></button><code><a id="__codelineno-45-1" name="__codelineno-45-1" href="#__codelineno-45-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-45-2" name="__codelineno-45-2" href="#__codelineno-45-2"></a><span class="k">void</span><span class="w"> </span><span class="nf">Push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-45-3" name="__codelineno-45-3" href="#__codelineno-45-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-45-4" name="__codelineno-45-4" href="#__codelineno-45-4"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-45-5" name="__codelineno-45-5" href="#__codelineno-45-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-45-6" name="__codelineno-45-6" href="#__codelineno-45-6"></a><span class="w">    </span><span class="n">SiftUp</span><span class="p">(</span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-45-7" name="__codelineno-45-7" href="#__codelineno-45-7"></a><span class="p">}</span>
<a id="__codelineno-45-8" name="__codelineno-45-8" href="#__codelineno-45-8"></a>
<a id="__codelineno-45-9" name="__codelineno-45-9" href="#__codelineno-45-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-45-10" name="__codelineno-45-10" href="#__codelineno-45-10"></a><span class="k">void</span><span class="w"> </span><span class="nf">SiftUp</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-45-11" name="__codelineno-45-11" href="#__codelineno-45-11"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="k">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-45-12" name="__codelineno-45-12" href="#__codelineno-45-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-45-13" name="__codelineno-45-13" href="#__codelineno-45-13"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-45-14" name="__codelineno-45-14" href="#__codelineno-45-14"></a><span class="w">        </span><span class="c1">// 若“越过根节点”或“节点无须修复”，则结束堆化</span>
<a id="__codelineno-45-15" name="__codelineno-45-15" href="#__codelineno-45-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">p</span><span class="p">])</span>
<a id="__codelineno-45-16" name="__codelineno-45-16" href="#__codelineno-45-16"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-45-17" name="__codelineno-45-17" href="#__codelineno-45-17"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-45-18" name="__codelineno-45-18" href="#__codelineno-45-18"></a><span class="w">        </span><span class="n">Swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-45-19" name="__codelineno-45-19" href="#__codelineno-45-19"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-45-20" name="__codelineno-45-20" href="#__codelineno-45-20"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-45-21" name="__codelineno-45-21" href="#__codelineno-45-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-45-22" name="__codelineno-45-22" href="#__codelineno-45-22"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.go</span><pre id="__code_46"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_46 > code"></button><code><a id="__codelineno-46-1" name="__codelineno-46-1" href="#__codelineno-46-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-46-2" name="__codelineno-46-2" href="#__codelineno-46-2"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">push</span><span class="p">(</span><span class="nx">val</span><span class="w"> </span><span class="kt">any</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-46-3" name="__codelineno-46-3" href="#__codelineno-46-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-46-4" name="__codelineno-46-4" href="#__codelineno-46-4"></a><span class="w">    </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">append</span><span class="p">(</span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">)</span>
<a id="__codelineno-46-5" name="__codelineno-46-5" href="#__codelineno-46-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-46-6" name="__codelineno-46-6" href="#__codelineno-46-6"></a><span class="w">    </span><span class="nx">h</span><span class="p">.</span><span class="nx">siftUp</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-46-7" name="__codelineno-46-7" href="#__codelineno-46-7"></a><span class="p">}</span>
<a id="__codelineno-46-8" name="__codelineno-46-8" href="#__codelineno-46-8"></a>
<a id="__codelineno-46-9" name="__codelineno-46-9" href="#__codelineno-46-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-46-10" name="__codelineno-46-10" href="#__codelineno-46-10"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">siftUp</span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-46-11" name="__codelineno-46-11" href="#__codelineno-46-11"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="kc">true</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-46-12" name="__codelineno-46-12" href="#__codelineno-46-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-46-13" name="__codelineno-46-13" href="#__codelineno-46-13"></a><span class="w">        </span><span class="nx">p</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span>
<a id="__codelineno-46-14" name="__codelineno-46-14" href="#__codelineno-46-14"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-46-15" name="__codelineno-46-15" href="#__codelineno-46-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">p</span><span class="w"> </span><span class="p">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">i</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">p</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-46-16" name="__codelineno-46-16" href="#__codelineno-46-16"></a><span class="w">            </span><span class="k">break</span>
<a id="__codelineno-46-17" name="__codelineno-46-17" href="#__codelineno-46-17"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-46-18" name="__codelineno-46-18" href="#__codelineno-46-18"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-46-19" name="__codelineno-46-19" href="#__codelineno-46-19"></a><span class="w">        </span><span class="nx">h</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">p</span><span class="p">)</span>
<a id="__codelineno-46-20" name="__codelineno-46-20" href="#__codelineno-46-20"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-46-21" name="__codelineno-46-21" href="#__codelineno-46-21"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">p</span>
<a id="__codelineno-46-22" name="__codelineno-46-22" href="#__codelineno-46-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-46-23" name="__codelineno-46-23" href="#__codelineno-46-23"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.swift</span><pre id="__code_47"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_47 > code"></button><code><a id="__codelineno-47-1" name="__codelineno-47-1" href="#__codelineno-47-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-47-2" name="__codelineno-47-2" href="#__codelineno-47-2"></a><span class="kd">func</span> <span class="nf">push</span><span class="p">(</span><span class="n">val</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-47-3" name="__codelineno-47-3" href="#__codelineno-47-3"></a>    <span class="c1">// 添加节点</span>
<a id="__codelineno-47-4" name="__codelineno-47-4" href="#__codelineno-47-4"></a>    <span class="n">maxHeap</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-47-5" name="__codelineno-47-5" href="#__codelineno-47-5"></a>    <span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-47-6" name="__codelineno-47-6" href="#__codelineno-47-6"></a>    <span class="n">siftUp</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">size</span><span class="p">()</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-47-7" name="__codelineno-47-7" href="#__codelineno-47-7"></a><span class="p">}</span>
<a id="__codelineno-47-8" name="__codelineno-47-8" href="#__codelineno-47-8"></a>
<a id="__codelineno-47-9" name="__codelineno-47-9" href="#__codelineno-47-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-47-10" name="__codelineno-47-10" href="#__codelineno-47-10"></a><span class="kd">func</span> <span class="nf">siftUp</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-47-11" name="__codelineno-47-11" href="#__codelineno-47-11"></a>    <span class="kd">var</span> <span class="nv">i</span> <span class="p">=</span> <span class="n">i</span>
<a id="__codelineno-47-12" name="__codelineno-47-12" href="#__codelineno-47-12"></a>    <span class="k">while</span> <span class="kc">true</span> <span class="p">{</span>
<a id="__codelineno-47-13" name="__codelineno-47-13" href="#__codelineno-47-13"></a>        <span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-47-14" name="__codelineno-47-14" href="#__codelineno-47-14"></a>        <span class="kd">let</span> <span class="nv">p</span> <span class="p">=</span> <span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">i</span><span class="p">)</span>
<a id="__codelineno-47-15" name="__codelineno-47-15" href="#__codelineno-47-15"></a>        <span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-47-16" name="__codelineno-47-16" href="#__codelineno-47-16"></a>        <span class="k">if</span> <span class="n">p</span> <span class="o">&lt;</span> <span class="mi">0</span> <span class="o">||</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&lt;=</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">p</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-47-17" name="__codelineno-47-17" href="#__codelineno-47-17"></a>            <span class="k">break</span>
<a id="__codelineno-47-18" name="__codelineno-47-18" href="#__codelineno-47-18"></a>        <span class="p">}</span>
<a id="__codelineno-47-19" name="__codelineno-47-19" href="#__codelineno-47-19"></a>        <span class="c1">// 交换两节点</span>
<a id="__codelineno-47-20" name="__codelineno-47-20" href="#__codelineno-47-20"></a>        <span class="bp">swap</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">:</span> <span class="n">p</span><span class="p">)</span>
<a id="__codelineno-47-21" name="__codelineno-47-21" href="#__codelineno-47-21"></a>        <span class="c1">// 循环向上堆化</span>
<a id="__codelineno-47-22" name="__codelineno-47-22" href="#__codelineno-47-22"></a>        <span class="n">i</span> <span class="p">=</span> <span class="n">p</span>
<a id="__codelineno-47-23" name="__codelineno-47-23" href="#__codelineno-47-23"></a>    <span class="p">}</span>
<a id="__codelineno-47-24" name="__codelineno-47-24" href="#__codelineno-47-24"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.js</span><pre id="__code_48"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_48 > code"></button><code><a id="__codelineno-48-1" name="__codelineno-48-1" href="#__codelineno-48-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-48-2" name="__codelineno-48-2" href="#__codelineno-48-2"></a><span class="nx">push</span><span class="p">(</span><span class="nx">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-48-3" name="__codelineno-48-3" href="#__codelineno-48-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-48-4" name="__codelineno-48-4" href="#__codelineno-48-4"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-48-5" name="__codelineno-48-5" href="#__codelineno-48-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-48-6" name="__codelineno-48-6" href="#__codelineno-48-6"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">siftUp</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">);</span>
<a id="__codelineno-48-7" name="__codelineno-48-7" href="#__codelineno-48-7"></a><span class="p">}</span>
<a id="__codelineno-48-8" name="__codelineno-48-8" href="#__codelineno-48-8"></a>
<a id="__codelineno-48-9" name="__codelineno-48-9" href="#__codelineno-48-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-48-10" name="__codelineno-48-10" href="#__codelineno-48-10"></a><span class="err">#</span><span class="nx">siftUp</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-48-11" name="__codelineno-48-11" href="#__codelineno-48-11"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-48-12" name="__codelineno-48-12" href="#__codelineno-48-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-48-13" name="__codelineno-48-13" href="#__codelineno-48-13"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-48-14" name="__codelineno-48-14" href="#__codelineno-48-14"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-48-15" name="__codelineno-48-15" href="#__codelineno-48-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">p</span><span class="p">])</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-48-16" name="__codelineno-48-16" href="#__codelineno-48-16"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-48-17" name="__codelineno-48-17" href="#__codelineno-48-17"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">p</span><span class="p">);</span>
<a id="__codelineno-48-18" name="__codelineno-48-18" href="#__codelineno-48-18"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-48-19" name="__codelineno-48-19" href="#__codelineno-48-19"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">p</span><span class="p">;</span>
<a id="__codelineno-48-20" name="__codelineno-48-20" href="#__codelineno-48-20"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-48-21" name="__codelineno-48-21" href="#__codelineno-48-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.ts</span><pre id="__code_49"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_49 > code"></button><code><a id="__codelineno-49-1" name="__codelineno-49-1" href="#__codelineno-49-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-49-2" name="__codelineno-49-2" href="#__codelineno-49-2"></a><span class="nx">push</span><span class="p">(</span><span class="nx">val</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="ow">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-49-3" name="__codelineno-49-3" href="#__codelineno-49-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-49-4" name="__codelineno-49-4" href="#__codelineno-49-4"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-49-5" name="__codelineno-49-5" href="#__codelineno-49-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-49-6" name="__codelineno-49-6" href="#__codelineno-49-6"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="nx">siftUp</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">);</span>
<a id="__codelineno-49-7" name="__codelineno-49-7" href="#__codelineno-49-7"></a><span class="p">}</span>
<a id="__codelineno-49-8" name="__codelineno-49-8" href="#__codelineno-49-8"></a>
<a id="__codelineno-49-9" name="__codelineno-49-9" href="#__codelineno-49-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-49-10" name="__codelineno-49-10" href="#__codelineno-49-10"></a><span class="nx">siftUp</span><span class="p">(</span><span class="nx">i</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="ow">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-49-11" name="__codelineno-49-11" href="#__codelineno-49-11"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-49-12" name="__codelineno-49-12" href="#__codelineno-49-12"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-49-13" name="__codelineno-49-13" href="#__codelineno-49-13"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">parent</span><span class="p">(</span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-49-14" name="__codelineno-49-14" href="#__codelineno-49-14"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-49-15" name="__codelineno-49-15" href="#__codelineno-49-15"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">p</span><span class="p">])</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-49-16" name="__codelineno-49-16" href="#__codelineno-49-16"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-49-17" name="__codelineno-49-17" href="#__codelineno-49-17"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">p</span><span class="p">);</span>
<a id="__codelineno-49-18" name="__codelineno-49-18" href="#__codelineno-49-18"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-49-19" name="__codelineno-49-19" href="#__codelineno-49-19"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">p</span><span class="p">;</span>
<a id="__codelineno-49-20" name="__codelineno-49-20" href="#__codelineno-49-20"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-49-21" name="__codelineno-49-21" href="#__codelineno-49-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.dart</span><pre id="__code_50"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_50 > code"></button><code><a id="__codelineno-50-1" name="__codelineno-50-1" href="#__codelineno-50-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-50-2" name="__codelineno-50-2" href="#__codelineno-50-2"></a><span class="kt">void</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-50-3" name="__codelineno-50-3" href="#__codelineno-50-3"></a><span class="w">  </span><span class="c1">// 添加节点</span>
<a id="__codelineno-50-4" name="__codelineno-50-4" href="#__codelineno-50-4"></a><span class="w">  </span><span class="n">_maxHeap</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-50-5" name="__codelineno-50-5" href="#__codelineno-50-5"></a><span class="w">  </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-50-6" name="__codelineno-50-6" href="#__codelineno-50-6"></a><span class="w">  </span><span class="n">siftUp</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-50-7" name="__codelineno-50-7" href="#__codelineno-50-7"></a><span class="p">}</span>
<a id="__codelineno-50-8" name="__codelineno-50-8" href="#__codelineno-50-8"></a>
<a id="__codelineno-50-9" name="__codelineno-50-9" href="#__codelineno-50-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-50-10" name="__codelineno-50-10" href="#__codelineno-50-10"></a><span class="kt">void</span><span class="w"> </span><span class="n">siftUp</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-50-11" name="__codelineno-50-11" href="#__codelineno-50-11"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-50-12" name="__codelineno-50-12" href="#__codelineno-50-12"></a><span class="w">    </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-50-13" name="__codelineno-50-13" href="#__codelineno-50-13"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-50-14" name="__codelineno-50-14" href="#__codelineno-50-14"></a><span class="w">    </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-50-15" name="__codelineno-50-15" href="#__codelineno-50-15"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">p</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-50-16" name="__codelineno-50-16" href="#__codelineno-50-16"></a><span class="w">      </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-50-17" name="__codelineno-50-17" href="#__codelineno-50-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-50-18" name="__codelineno-50-18" href="#__codelineno-50-18"></a><span class="w">    </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-50-19" name="__codelineno-50-19" href="#__codelineno-50-19"></a><span class="w">    </span><span class="n">_swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-50-20" name="__codelineno-50-20" href="#__codelineno-50-20"></a><span class="w">    </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-50-21" name="__codelineno-50-21" href="#__codelineno-50-21"></a><span class="w">    </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-50-22" name="__codelineno-50-22" href="#__codelineno-50-22"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-50-23" name="__codelineno-50-23" href="#__codelineno-50-23"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rs</span><pre id="__code_51"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_51 > code"></button><code><a id="__codelineno-51-1" name="__codelineno-51-1" href="#__codelineno-51-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-51-2" name="__codelineno-51-2" href="#__codelineno-51-2"></a><span class="k">fn</span> <span class="nf">push</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">val</span>: <span class="kt">i32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-51-3" name="__codelineno-51-3" href="#__codelineno-51-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-51-4" name="__codelineno-51-4" href="#__codelineno-51-4"></a><span class="w">    </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="n">push</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-51-5" name="__codelineno-51-5" href="#__codelineno-51-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-51-6" name="__codelineno-51-6" href="#__codelineno-51-6"></a><span class="w">    </span><span class="bp">self</span><span class="p">.</span><span class="n">sift_up</span><span class="p">(</span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-51-7" name="__codelineno-51-7" href="#__codelineno-51-7"></a><span class="p">}</span>
<a id="__codelineno-51-8" name="__codelineno-51-8" href="#__codelineno-51-8"></a>
<a id="__codelineno-51-9" name="__codelineno-51-9" href="#__codelineno-51-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-51-10" name="__codelineno-51-10" href="#__codelineno-51-10"></a><span class="k">fn</span> <span class="nf">sift_up</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">i</span>: <span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-51-11" name="__codelineno-51-11" href="#__codelineno-51-11"></a><span class="w">    </span><span class="k">loop</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-51-12" name="__codelineno-51-12" href="#__codelineno-51-12"></a><span class="w">        </span><span class="c1">// 节点 i 已经是堆顶节点了，结束堆化</span>
<a id="__codelineno-51-13" name="__codelineno-51-13" href="#__codelineno-51-13"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-51-14" name="__codelineno-51-14" href="#__codelineno-51-14"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-51-15" name="__codelineno-51-15" href="#__codelineno-51-15"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-51-16" name="__codelineno-51-16" href="#__codelineno-51-16"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-51-17" name="__codelineno-51-17" href="#__codelineno-51-17"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">Self</span>::<span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-51-18" name="__codelineno-51-18" href="#__codelineno-51-18"></a><span class="w">        </span><span class="c1">// 当“节点无须修复”时，结束堆化</span>
<a id="__codelineno-51-19" name="__codelineno-51-19" href="#__codelineno-51-19"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">p</span><span class="p">]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-51-20" name="__codelineno-51-20" href="#__codelineno-51-20"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-51-21" name="__codelineno-51-21" href="#__codelineno-51-21"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-51-22" name="__codelineno-51-22" href="#__codelineno-51-22"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-51-23" name="__codelineno-51-23" href="#__codelineno-51-23"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-51-24" name="__codelineno-51-24" href="#__codelineno-51-24"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-51-25" name="__codelineno-51-25" href="#__codelineno-51-25"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-51-26" name="__codelineno-51-26" href="#__codelineno-51-26"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-51-27" name="__codelineno-51-27" href="#__codelineno-51-27"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.c</span><pre id="__code_52"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_52 > code"></button><code><a id="__codelineno-52-1" name="__codelineno-52-1" href="#__codelineno-52-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-52-2" name="__codelineno-52-2" href="#__codelineno-52-2"></a><span class="kt">void</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-52-3" name="__codelineno-52-3" href="#__codelineno-52-3"></a><span class="w">    </span><span class="c1">// 默认情况下，不应该添加这么多节点</span>
<a id="__codelineno-52-4" name="__codelineno-52-4" href="#__codelineno-52-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-52-5" name="__codelineno-52-5" href="#__codelineno-52-5"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"heap is full!"</span><span class="p">);</span>
<a id="__codelineno-52-6" name="__codelineno-52-6" href="#__codelineno-52-6"></a><span class="w">        </span><span class="k">return</span><span class="p">;</span>
<a id="__codelineno-52-7" name="__codelineno-52-7" href="#__codelineno-52-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-52-8" name="__codelineno-52-8" href="#__codelineno-52-8"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-52-9" name="__codelineno-52-9" href="#__codelineno-52-9"></a><span class="w">    </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-52-10" name="__codelineno-52-10" href="#__codelineno-52-10"></a><span class="w">    </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-52-11" name="__codelineno-52-11" href="#__codelineno-52-11"></a>
<a id="__codelineno-52-12" name="__codelineno-52-12" href="#__codelineno-52-12"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-52-13" name="__codelineno-52-13" href="#__codelineno-52-13"></a><span class="w">    </span><span class="n">siftUp</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-52-14" name="__codelineno-52-14" href="#__codelineno-52-14"></a><span class="p">}</span>
<a id="__codelineno-52-15" name="__codelineno-52-15" href="#__codelineno-52-15"></a>
<a id="__codelineno-52-16" name="__codelineno-52-16" href="#__codelineno-52-16"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-52-17" name="__codelineno-52-17" href="#__codelineno-52-17"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftUp</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-52-18" name="__codelineno-52-18" href="#__codelineno-52-18"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nb">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-52-19" name="__codelineno-52-19" href="#__codelineno-52-19"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-52-20" name="__codelineno-52-20" href="#__codelineno-52-20"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-52-21" name="__codelineno-52-21" href="#__codelineno-52-21"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-52-22" name="__codelineno-52-22" href="#__codelineno-52-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">p</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-52-23" name="__codelineno-52-23" href="#__codelineno-52-23"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-52-24" name="__codelineno-52-24" href="#__codelineno-52-24"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-52-25" name="__codelineno-52-25" href="#__codelineno-52-25"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-52-26" name="__codelineno-52-26" href="#__codelineno-52-26"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-52-27" name="__codelineno-52-27" href="#__codelineno-52-27"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-52-28" name="__codelineno-52-28" href="#__codelineno-52-28"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-52-29" name="__codelineno-52-29" href="#__codelineno-52-29"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-52-30" name="__codelineno-52-30" href="#__codelineno-52-30"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.kt</span><pre id="__code_53"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_53 > code"></button><code><a id="__codelineno-53-1" name="__codelineno-53-1" href="#__codelineno-53-1"></a><span class="cm">/* 元素入堆 */</span>
<a id="__codelineno-53-2" name="__codelineno-53-2" href="#__codelineno-53-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">_val</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-53-3" name="__codelineno-53-3" href="#__codelineno-53-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-53-4" name="__codelineno-53-4" href="#__codelineno-53-4"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">_val</span><span class="p">)</span>
<a id="__codelineno-53-5" name="__codelineno-53-5" href="#__codelineno-53-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-53-6" name="__codelineno-53-6" href="#__codelineno-53-6"></a><span class="w">    </span><span class="n">siftUp</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span>
<a id="__codelineno-53-7" name="__codelineno-53-7" href="#__codelineno-53-7"></a><span class="p">}</span>
<a id="__codelineno-53-8" name="__codelineno-53-8" href="#__codelineno-53-8"></a>
<a id="__codelineno-53-9" name="__codelineno-53-9" href="#__codelineno-53-9"></a><span class="cm">/* 从节点 i 开始，从底至顶堆化 */</span>
<a id="__codelineno-53-10" name="__codelineno-53-10" href="#__codelineno-53-10"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">siftUp</span><span class="p">(</span><span class="nb">it</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-53-11" name="__codelineno-53-11" href="#__codelineno-53-11"></a><span class="w">    </span><span class="c1">// Kotlin的函数参数不可变，因此创建临时变量</span>
<a id="__codelineno-53-12" name="__codelineno-53-12" href="#__codelineno-53-12"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">it</span>
<a id="__codelineno-53-13" name="__codelineno-53-13" href="#__codelineno-53-13"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-53-14" name="__codelineno-53-14" href="#__codelineno-53-14"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-53-15" name="__codelineno-53-15" href="#__codelineno-53-15"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-53-16" name="__codelineno-53-16" href="#__codelineno-53-16"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-53-17" name="__codelineno-53-17" href="#__codelineno-53-17"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">p</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="k">break</span>
<a id="__codelineno-53-18" name="__codelineno-53-18" href="#__codelineno-53-18"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-53-19" name="__codelineno-53-19" href="#__codelineno-53-19"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">)</span>
<a id="__codelineno-53-20" name="__codelineno-53-20" href="#__codelineno-53-20"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-53-21" name="__codelineno-53-21" href="#__codelineno-53-21"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span>
<a id="__codelineno-53-22" name="__codelineno-53-22" href="#__codelineno-53-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-53-23" name="__codelineno-53-23" href="#__codelineno-53-23"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rb</span><pre id="__code_54"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_54 > code"></button><code><a id="__codelineno-54-1" name="__codelineno-54-1" href="#__codelineno-54-1"></a><span class="c1">### 元素入堆 ###</span>
<a id="__codelineno-54-2" name="__codelineno-54-2" href="#__codelineno-54-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">push</span><span class="p">(</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-54-3" name="__codelineno-54-3" href="#__codelineno-54-3"></a><span class="w">  </span><span class="c1"># 添加节点</span>
<a id="__codelineno-54-4" name="__codelineno-54-4" href="#__codelineno-54-4"></a><span class="w">  </span><span class="vi">@max_heap</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">val</span>
<a id="__codelineno-54-5" name="__codelineno-54-5" href="#__codelineno-54-5"></a><span class="w">  </span><span class="c1"># 从底至顶堆化</span>
<a id="__codelineno-54-6" name="__codelineno-54-6" href="#__codelineno-54-6"></a><span class="w">  </span><span class="n">sift_up</span><span class="p">(</span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-54-7" name="__codelineno-54-7" href="#__codelineno-54-7"></a><span class="k">end</span>
<a id="__codelineno-54-8" name="__codelineno-54-8" href="#__codelineno-54-8"></a>
<a id="__codelineno-54-9" name="__codelineno-54-9" href="#__codelineno-54-9"></a><span class="c1">### 从节点 i 开始，从底至顶堆化 ###</span>
<a id="__codelineno-54-10" name="__codelineno-54-10" href="#__codelineno-54-10"></a><span class="k">def</span><span class="w"> </span><span class="nf">sift_up</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-54-11" name="__codelineno-54-11" href="#__codelineno-54-11"></a><span class="w">  </span><span class="kp">loop</span><span class="w"> </span><span class="k">do</span>
<a id="__codelineno-54-12" name="__codelineno-54-12" href="#__codelineno-54-12"></a><span class="w">    </span><span class="c1"># 获取节点 i 的父节点</span>
<a id="__codelineno-54-13" name="__codelineno-54-13" href="#__codelineno-54-13"></a><span class="w">    </span><span class="nb">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-54-14" name="__codelineno-54-14" href="#__codelineno-54-14"></a><span class="w">    </span><span class="c1"># 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-54-15" name="__codelineno-54-15" href="#__codelineno-54-15"></a><span class="w">    </span><span class="k">break</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="nb">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">||</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="nb">p</span><span class="o">]</span>
<a id="__codelineno-54-16" name="__codelineno-54-16" href="#__codelineno-54-16"></a><span class="w">    </span><span class="c1"># 交换两节点</span>
<a id="__codelineno-54-17" name="__codelineno-54-17" href="#__codelineno-54-17"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="nb">p</span><span class="p">)</span>
<a id="__codelineno-54-18" name="__codelineno-54-18" href="#__codelineno-54-18"></a><span class="w">    </span><span class="c1"># 循环向上堆化</span>
<a id="__codelineno-54-19" name="__codelineno-54-19" href="#__codelineno-54-19"></a><span class="w">    </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">p</span>
<a id="__codelineno-54-20" name="__codelineno-54-20" href="#__codelineno-54-20"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-54-21" name="__codelineno-54-21" href="#__codelineno-54-21"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.zig</span><pre id="__code_55"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_55 > code"></button><code><a id="__codelineno-55-1" name="__codelineno-55-1" href="#__codelineno-55-1"></a><span class="c1">// 元素入堆</span>
<a id="__codelineno-55-2" name="__codelineno-55-2" href="#__codelineno-55-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">push</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="o">:</span><span class="w"> </span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-55-3" name="__codelineno-55-3" href="#__codelineno-55-3"></a><span class="w">    </span><span class="c1">// 添加节点</span>
<a id="__codelineno-55-4" name="__codelineno-55-4" href="#__codelineno-55-4"></a><span class="w">    </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-55-5" name="__codelineno-55-5" href="#__codelineno-55-5"></a><span class="w">    </span><span class="c1">// 从底至顶堆化</span>
<a id="__codelineno-55-6" name="__codelineno-55-6" href="#__codelineno-55-6"></a><span class="w">    </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">siftUp</span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-55-7" name="__codelineno-55-7" href="#__codelineno-55-7"></a><span class="p">}</span><span class="w">  </span>
<a id="__codelineno-55-8" name="__codelineno-55-8" href="#__codelineno-55-8"></a>
<a id="__codelineno-55-9" name="__codelineno-55-9" href="#__codelineno-55-9"></a><span class="c1">// 从节点 i 开始，从底至顶堆化</span>
<a id="__codelineno-55-10" name="__codelineno-55-10" href="#__codelineno-55-10"></a><span class="k">fn</span><span class="w"> </span><span class="n">siftUp</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">i_</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-55-11" name="__codelineno-55-11" href="#__codelineno-55-11"></a><span class="w">    </span><span class="kr">var</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i_</span><span class="p">;</span>
<a id="__codelineno-55-12" name="__codelineno-55-12" href="#__codelineno-55-12"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-55-13" name="__codelineno-55-13" href="#__codelineno-55-13"></a><span class="w">        </span><span class="c1">// 获取节点 i 的父节点</span>
<a id="__codelineno-55-14" name="__codelineno-55-14" href="#__codelineno-55-14"></a><span class="w">        </span><span class="kr">var</span><span class="w"> </span><span class="n">p</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">parent</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-55-15" name="__codelineno-55-15" href="#__codelineno-55-15"></a><span class="w">        </span><span class="c1">// 当“越过根节点”或“节点无须修复”时，结束堆化</span>
<a id="__codelineno-55-16" name="__codelineno-55-16" href="#__codelineno-55-16"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">p</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="k">or</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">p</span><span class="p">])</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-55-17" name="__codelineno-55-17" href="#__codelineno-55-17"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-55-18" name="__codelineno-55-18" href="#__codelineno-55-18"></a><span class="w">        </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">p</span><span class="p">);</span>
<a id="__codelineno-55-19" name="__codelineno-55-19" href="#__codelineno-55-19"></a><span class="w">        </span><span class="c1">// 循环向上堆化</span>
<a id="__codelineno-55-20" name="__codelineno-55-20" href="#__codelineno-55-20"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">p</span><span class="p">;</span>
<a id="__codelineno-55-21" name="__codelineno-55-21" href="#__codelineno-55-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-55-22" name="__codelineno-55-22" href="#__codelineno-55-22"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
### 堆顶元素出堆

堆顶元素是二叉树的根节点，即列表首元素。如果我们直接从列表中删除首元素，那么二叉树中所有节点的索引都会发生变化，这将使得后续使用堆化修复变得困难。为了尽量减少元素索引的变动，我们采用以下操作步骤。

1. 交换堆顶元素与堆底元素（即交换根节点与最右叶节点）。
2. 交换完成后，将堆底从列表中删除（注意，由于已经交换，实际上删除的是原来的堆顶元素）。
3. 从根节点开始，**从顶至底执行堆化**。

如下图所示，**“从顶至底堆化”的操作方向与“从底至顶堆化”相反**，我们将根节点的值与其两个子节点的值进行比较，将最大的子节点与根节点交换。然后循环执行此操作，直到越过叶节点或遇到无须交换的节点时结束。

=== "<1>"
    ![堆顶元素出堆步骤](heap.assets/heap_pop_step1.png)

=== "<2>"
    ![heap_pop_step2](heap.assets/heap_pop_step2.png)

=== "<3>"
    ![heap_pop_step3](heap.assets/heap_pop_step3.png)

=== "<4>"
    ![heap_pop_step4](heap.assets/heap_pop_step4.png)

=== "<5>"
    ![heap_pop_step5](heap.assets/heap_pop_step5.png)

=== "<6>"
    ![heap_pop_step6](heap.assets/heap_pop_step6.png)

=== "<7>"
    ![heap_pop_step7](heap.assets/heap_pop_step7.png)

=== "<8>"
    ![heap_pop_step8](heap.assets/heap_pop_step8.png)

=== "<9>"
    ![heap_pop_step9](heap.assets/heap_pop_step9.png)

=== "<10>"
    ![heap_pop_step10](heap.assets/heap_pop_step10.png)

与元素入堆操作相似，堆顶元素出堆操作的时间复杂度也为 $O(\log n)$ 。

<div class="tabbed-set tabbed-alternate" data-tabs="7:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_7_1" name="__tabbed_7" type="radio"><input id="__tabbed_7_2" name="__tabbed_7" type="radio"><input id="__tabbed_7_3" name="__tabbed_7" type="radio"><input id="__tabbed_7_4" name="__tabbed_7" type="radio"><input id="__tabbed_7_5" name="__tabbed_7" type="radio"><input id="__tabbed_7_6" name="__tabbed_7" type="radio"><input id="__tabbed_7_7" name="__tabbed_7" type="radio"><input id="__tabbed_7_8" name="__tabbed_7" type="radio"><input id="__tabbed_7_9" name="__tabbed_7" type="radio"><input id="__tabbed_7_10" name="__tabbed_7" type="radio"><input id="__tabbed_7_11" name="__tabbed_7" type="radio"><input id="__tabbed_7_12" name="__tabbed_7" type="radio"><input id="__tabbed_7_13" name="__tabbed_7" type="radio"><input id="__tabbed_7_14" name="__tabbed_7" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_7_1"><a href="#__tabbed_7_1" tabindex="-1">Python</a></label><label for="__tabbed_7_2"><a href="#__tabbed_7_2" tabindex="-1">C++</a></label><label for="__tabbed_7_3"><a href="#__tabbed_7_3" tabindex="-1">Java</a></label><label for="__tabbed_7_4"><a href="#__tabbed_7_4" tabindex="-1">C#</a></label><label for="__tabbed_7_5"><a href="#__tabbed_7_5" tabindex="-1">Go</a></label><label for="__tabbed_7_6"><a href="#__tabbed_7_6" tabindex="-1">Swift</a></label><label for="__tabbed_7_7"><a href="#__tabbed_7_7" tabindex="-1">JS</a></label><label for="__tabbed_7_8"><a href="#__tabbed_7_8" tabindex="-1">TS</a></label><label for="__tabbed_7_9"><a href="#__tabbed_7_9" tabindex="-1">Dart</a></label><label for="__tabbed_7_10"><a href="#__tabbed_7_10" tabindex="-1">Rust</a></label><label for="__tabbed_7_11"><a href="#__tabbed_7_11" tabindex="-1">C</a></label><label for="__tabbed_7_12"><a href="#__tabbed_7_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_7_13"><a href="#__tabbed_7_13" tabindex="-1">Ruby</a></label><label for="__tabbed_7_14"><a href="#__tabbed_7_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.py</span><pre id="__code_56"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_56 > code"></button><code><a id="__codelineno-56-1" name="__codelineno-56-1" href="#__codelineno-56-1"></a><span class="k">def</span> <span class="nf">pop</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-56-2" name="__codelineno-56-2" href="#__codelineno-56-2"></a><span class="w">    </span><span class="sd">"""元素出堆"""</span>
<a id="__codelineno-56-3" name="__codelineno-56-3" href="#__codelineno-56-3"></a>    <span class="c1"># 判空处理</span>
<a id="__codelineno-56-4" name="__codelineno-56-4" href="#__codelineno-56-4"></a>    <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">is_empty</span><span class="p">():</span>
<a id="__codelineno-56-5" name="__codelineno-56-5" href="#__codelineno-56-5"></a>        <span class="k">raise</span> <span class="ne">IndexError</span><span class="p">(</span><span class="s2">"堆为空"</span><span class="p">)</span>
<a id="__codelineno-56-6" name="__codelineno-56-6" href="#__codelineno-56-6"></a>    <span class="c1"># 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-56-7" name="__codelineno-56-7" href="#__codelineno-56-7"></a>    <span class="bp">self</span><span class="o">.</span><span class="n">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="bp">self</span><span class="o">.</span><span class="n">size</span><span class="p">()</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-56-8" name="__codelineno-56-8" href="#__codelineno-56-8"></a>    <span class="c1"># 删除节点</span>
<a id="__codelineno-56-9" name="__codelineno-56-9" href="#__codelineno-56-9"></a>    <span class="n">val</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="o">.</span><span class="n">pop</span><span class="p">()</span>
<a id="__codelineno-56-10" name="__codelineno-56-10" href="#__codelineno-56-10"></a>    <span class="c1"># 从顶至底堆化</span>
<a id="__codelineno-56-11" name="__codelineno-56-11" href="#__codelineno-56-11"></a>    <span class="bp">self</span><span class="o">.</span><span class="n">sift_down</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<a id="__codelineno-56-12" name="__codelineno-56-12" href="#__codelineno-56-12"></a>    <span class="c1"># 返回堆顶元素</span>
<a id="__codelineno-56-13" name="__codelineno-56-13" href="#__codelineno-56-13"></a>    <span class="k">return</span> <span class="n">val</span>
<a id="__codelineno-56-14" name="__codelineno-56-14" href="#__codelineno-56-14"></a>
<a id="__codelineno-56-15" name="__codelineno-56-15" href="#__codelineno-56-15"></a><span class="k">def</span> <span class="nf">sift_down</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">i</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-56-16" name="__codelineno-56-16" href="#__codelineno-56-16"></a><span class="w">    </span><span class="sd">"""从节点 i 开始，从顶至底堆化"""</span>
<a id="__codelineno-56-17" name="__codelineno-56-17" href="#__codelineno-56-17"></a>    <span class="k">while</span> <span class="kc">True</span><span class="p">:</span>
<a id="__codelineno-56-18" name="__codelineno-56-18" href="#__codelineno-56-18"></a>        <span class="c1"># 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-56-19" name="__codelineno-56-19" href="#__codelineno-56-19"></a>        <span class="n">l</span><span class="p">,</span> <span class="n">r</span><span class="p">,</span> <span class="n">ma</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span> <span class="bp">self</span><span class="o">.</span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span> <span class="n">i</span>
<a id="__codelineno-56-20" name="__codelineno-56-20" href="#__codelineno-56-20"></a>        <span class="k">if</span> <span class="n">l</span> <span class="o">&lt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">size</span><span class="p">()</span> <span class="ow">and</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">ma</span><span class="p">]:</span>
<a id="__codelineno-56-21" name="__codelineno-56-21" href="#__codelineno-56-21"></a>            <span class="n">ma</span> <span class="o">=</span> <span class="n">l</span>
<a id="__codelineno-56-22" name="__codelineno-56-22" href="#__codelineno-56-22"></a>        <span class="k">if</span> <span class="n">r</span> <span class="o">&lt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">size</span><span class="p">()</span> <span class="ow">and</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span> <span class="o">&gt;</span> <span class="bp">self</span><span class="o">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">ma</span><span class="p">]:</span>
<a id="__codelineno-56-23" name="__codelineno-56-23" href="#__codelineno-56-23"></a>            <span class="n">ma</span> <span class="o">=</span> <span class="n">r</span>
<a id="__codelineno-56-24" name="__codelineno-56-24" href="#__codelineno-56-24"></a>        <span class="c1"># 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-56-25" name="__codelineno-56-25" href="#__codelineno-56-25"></a>        <span class="k">if</span> <span class="n">ma</span> <span class="o">==</span> <span class="n">i</span><span class="p">:</span>
<a id="__codelineno-56-26" name="__codelineno-56-26" href="#__codelineno-56-26"></a>            <span class="k">break</span>
<a id="__codelineno-56-27" name="__codelineno-56-27" href="#__codelineno-56-27"></a>        <span class="c1"># 交换两节点</span>
<a id="__codelineno-56-28" name="__codelineno-56-28" href="#__codelineno-56-28"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span> <span class="n">ma</span><span class="p">)</span>
<a id="__codelineno-56-29" name="__codelineno-56-29" href="#__codelineno-56-29"></a>        <span class="c1"># 循环向下堆化</span>
<a id="__codelineno-56-30" name="__codelineno-56-30" href="#__codelineno-56-30"></a>        <span class="n">i</span> <span class="o">=</span> <span class="n">ma</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cpp</span><pre id="__code_57"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_57 > code"></button><code><a id="__codelineno-57-1" name="__codelineno-57-1" href="#__codelineno-57-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-57-2" name="__codelineno-57-2" href="#__codelineno-57-2"></a><span class="kt">void</span><span class="w"> </span><span class="nf">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-57-3" name="__codelineno-57-3" href="#__codelineno-57-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-57-4" name="__codelineno-57-4" href="#__codelineno-57-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-57-5" name="__codelineno-57-5" href="#__codelineno-57-5"></a><span class="w">        </span><span class="k">throw</span><span class="w"> </span><span class="n">out_of_range</span><span class="p">(</span><span class="s">"堆为空"</span><span class="p">);</span>
<a id="__codelineno-57-6" name="__codelineno-57-6" href="#__codelineno-57-6"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-57-7" name="__codelineno-57-7" href="#__codelineno-57-7"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-57-8" name="__codelineno-57-8" href="#__codelineno-57-8"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">[</span><span class="mi">0</span><span class="p">],</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">]);</span>
<a id="__codelineno-57-9" name="__codelineno-57-9" href="#__codelineno-57-9"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-57-10" name="__codelineno-57-10" href="#__codelineno-57-10"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="n">pop_back</span><span class="p">();</span>
<a id="__codelineno-57-11" name="__codelineno-57-11" href="#__codelineno-57-11"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-57-12" name="__codelineno-57-12" href="#__codelineno-57-12"></a><span class="w">    </span><span class="n">siftDown</span><span class="p">(</span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-57-13" name="__codelineno-57-13" href="#__codelineno-57-13"></a><span class="p">}</span>
<a id="__codelineno-57-14" name="__codelineno-57-14" href="#__codelineno-57-14"></a>
<a id="__codelineno-57-15" name="__codelineno-57-15" href="#__codelineno-57-15"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-57-16" name="__codelineno-57-16" href="#__codelineno-57-16"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftDown</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-57-17" name="__codelineno-57-17" href="#__codelineno-57-17"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nb">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-57-18" name="__codelineno-57-18" href="#__codelineno-57-18"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-57-19" name="__codelineno-57-19" href="#__codelineno-57-19"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-57-20" name="__codelineno-57-20" href="#__codelineno-57-20"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span>
<a id="__codelineno-57-21" name="__codelineno-57-21" href="#__codelineno-57-21"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-57-22" name="__codelineno-57-22" href="#__codelineno-57-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span>
<a id="__codelineno-57-23" name="__codelineno-57-23" href="#__codelineno-57-23"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-57-24" name="__codelineno-57-24" href="#__codelineno-57-24"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-57-25" name="__codelineno-57-25" href="#__codelineno-57-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-57-26" name="__codelineno-57-26" href="#__codelineno-57-26"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-57-27" name="__codelineno-57-27" href="#__codelineno-57-27"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">]);</span>
<a id="__codelineno-57-28" name="__codelineno-57-28" href="#__codelineno-57-28"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-57-29" name="__codelineno-57-29" href="#__codelineno-57-29"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-57-30" name="__codelineno-57-30" href="#__codelineno-57-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-57-31" name="__codelineno-57-31" href="#__codelineno-57-31"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.java</span><pre id="__code_58"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_58 > code"></button><code><a id="__codelineno-58-1" name="__codelineno-58-1" href="#__codelineno-58-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-58-2" name="__codelineno-58-2" href="#__codelineno-58-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-58-3" name="__codelineno-58-3" href="#__codelineno-58-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-58-4" name="__codelineno-58-4" href="#__codelineno-58-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span>
<a id="__codelineno-58-5" name="__codelineno-58-5" href="#__codelineno-58-5"></a><span class="w">        </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">();</span>
<a id="__codelineno-58-6" name="__codelineno-58-6" href="#__codelineno-58-6"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-58-7" name="__codelineno-58-7" href="#__codelineno-58-7"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-58-8" name="__codelineno-58-8" href="#__codelineno-58-8"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-58-9" name="__codelineno-58-9" href="#__codelineno-58-9"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">remove</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-58-10" name="__codelineno-58-10" href="#__codelineno-58-10"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-58-11" name="__codelineno-58-11" href="#__codelineno-58-11"></a><span class="w">    </span><span class="n">siftDown</span><span class="p">(</span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-58-12" name="__codelineno-58-12" href="#__codelineno-58-12"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-58-13" name="__codelineno-58-13" href="#__codelineno-58-13"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-58-14" name="__codelineno-58-14" href="#__codelineno-58-14"></a><span class="p">}</span>
<a id="__codelineno-58-15" name="__codelineno-58-15" href="#__codelineno-58-15"></a>
<a id="__codelineno-58-16" name="__codelineno-58-16" href="#__codelineno-58-16"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-58-17" name="__codelineno-58-17" href="#__codelineno-58-17"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftDown</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-58-18" name="__codelineno-58-18" href="#__codelineno-58-18"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-58-19" name="__codelineno-58-19" href="#__codelineno-58-19"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-58-20" name="__codelineno-58-20" href="#__codelineno-58-20"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-58-21" name="__codelineno-58-21" href="#__codelineno-58-21"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">l</span><span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">ma</span><span class="p">))</span>
<a id="__codelineno-58-22" name="__codelineno-58-22" href="#__codelineno-58-22"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-58-23" name="__codelineno-58-23" href="#__codelineno-58-23"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">r</span><span class="p">)</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">ma</span><span class="p">))</span>
<a id="__codelineno-58-24" name="__codelineno-58-24" href="#__codelineno-58-24"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-58-25" name="__codelineno-58-25" href="#__codelineno-58-25"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-58-26" name="__codelineno-58-26" href="#__codelineno-58-26"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-58-27" name="__codelineno-58-27" href="#__codelineno-58-27"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-58-28" name="__codelineno-58-28" href="#__codelineno-58-28"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-58-29" name="__codelineno-58-29" href="#__codelineno-58-29"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">);</span>
<a id="__codelineno-58-30" name="__codelineno-58-30" href="#__codelineno-58-30"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-58-31" name="__codelineno-58-31" href="#__codelineno-58-31"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-58-32" name="__codelineno-58-32" href="#__codelineno-58-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-58-33" name="__codelineno-58-33" href="#__codelineno-58-33"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.cs</span><pre id="__code_59"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_59 > code"></button><code><a id="__codelineno-59-1" name="__codelineno-59-1" href="#__codelineno-59-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-59-2" name="__codelineno-59-2" href="#__codelineno-59-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">Pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-59-3" name="__codelineno-59-3" href="#__codelineno-59-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-59-4" name="__codelineno-59-4" href="#__codelineno-59-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">IsEmpty</span><span class="p">())</span>
<a id="__codelineno-59-5" name="__codelineno-59-5" href="#__codelineno-59-5"></a><span class="w">        </span><span class="k">throw</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="nf">IndexOutOfRangeException</span><span class="p">();</span>
<a id="__codelineno-59-6" name="__codelineno-59-6" href="#__codelineno-59-6"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-59-7" name="__codelineno-59-7" href="#__codelineno-59-7"></a><span class="w">    </span><span class="n">Swap</span><span class="p">(</span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-59-8" name="__codelineno-59-8" href="#__codelineno-59-8"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-59-9" name="__codelineno-59-9" href="#__codelineno-59-9"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="n">Last</span><span class="p">();</span>
<a id="__codelineno-59-10" name="__codelineno-59-10" href="#__codelineno-59-10"></a><span class="w">    </span><span class="n">maxHeap</span><span class="p">.</span><span class="n">RemoveAt</span><span class="p">(</span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-59-11" name="__codelineno-59-11" href="#__codelineno-59-11"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-59-12" name="__codelineno-59-12" href="#__codelineno-59-12"></a><span class="w">    </span><span class="n">SiftDown</span><span class="p">(</span><span class="m">0</span><span class="p">);</span>
<a id="__codelineno-59-13" name="__codelineno-59-13" href="#__codelineno-59-13"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-59-14" name="__codelineno-59-14" href="#__codelineno-59-14"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-59-15" name="__codelineno-59-15" href="#__codelineno-59-15"></a><span class="p">}</span>
<a id="__codelineno-59-16" name="__codelineno-59-16" href="#__codelineno-59-16"></a>
<a id="__codelineno-59-17" name="__codelineno-59-17" href="#__codelineno-59-17"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-59-18" name="__codelineno-59-18" href="#__codelineno-59-18"></a><span class="k">void</span><span class="w"> </span><span class="nf">SiftDown</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-59-19" name="__codelineno-59-19" href="#__codelineno-59-19"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="k">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-59-20" name="__codelineno-59-20" href="#__codelineno-59-20"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-59-21" name="__codelineno-59-21" href="#__codelineno-59-21"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-59-22" name="__codelineno-59-22" href="#__codelineno-59-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span>
<a id="__codelineno-59-23" name="__codelineno-59-23" href="#__codelineno-59-23"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-59-24" name="__codelineno-59-24" href="#__codelineno-59-24"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">Size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span>
<a id="__codelineno-59-25" name="__codelineno-59-25" href="#__codelineno-59-25"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-59-26" name="__codelineno-59-26" href="#__codelineno-59-26"></a><span class="w">        </span><span class="c1">// 若“节点 i 最大”或“越过叶节点”，则结束堆化</span>
<a id="__codelineno-59-27" name="__codelineno-59-27" href="#__codelineno-59-27"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-59-28" name="__codelineno-59-28" href="#__codelineno-59-28"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-59-29" name="__codelineno-59-29" href="#__codelineno-59-29"></a><span class="w">        </span><span class="n">Swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">);</span>
<a id="__codelineno-59-30" name="__codelineno-59-30" href="#__codelineno-59-30"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-59-31" name="__codelineno-59-31" href="#__codelineno-59-31"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-59-32" name="__codelineno-59-32" href="#__codelineno-59-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-59-33" name="__codelineno-59-33" href="#__codelineno-59-33"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.go</span><pre id="__code_60"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_60 > code"></button><code><a id="__codelineno-60-1" name="__codelineno-60-1" href="#__codelineno-60-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-60-2" name="__codelineno-60-2" href="#__codelineno-60-2"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="kt">any</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-3" name="__codelineno-60-3" href="#__codelineno-60-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-60-4" name="__codelineno-60-4" href="#__codelineno-60-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-5" name="__codelineno-60-5" href="#__codelineno-60-5"></a><span class="w">        </span><span class="nx">fmt</span><span class="p">.</span><span class="nx">Println</span><span class="p">(</span><span class="s">"error"</span><span class="p">)</span>
<a id="__codelineno-60-6" name="__codelineno-60-6" href="#__codelineno-60-6"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="kc">nil</span>
<a id="__codelineno-60-7" name="__codelineno-60-7" href="#__codelineno-60-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-60-8" name="__codelineno-60-8" href="#__codelineno-60-8"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-60-9" name="__codelineno-60-9" href="#__codelineno-60-9"></a><span class="w">    </span><span class="nx">h</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="o">-</span><span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-60-10" name="__codelineno-60-10" href="#__codelineno-60-10"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-60-11" name="__codelineno-60-11" href="#__codelineno-60-11"></a><span class="w">    </span><span class="nx">val</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nb">len</span><span class="p">(</span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<a id="__codelineno-60-12" name="__codelineno-60-12" href="#__codelineno-60-12"></a><span class="w">    </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[:</span><span class="nb">len</span><span class="p">(</span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<a id="__codelineno-60-13" name="__codelineno-60-13" href="#__codelineno-60-13"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-60-14" name="__codelineno-60-14" href="#__codelineno-60-14"></a><span class="w">    </span><span class="nx">h</span><span class="p">.</span><span class="nx">siftDown</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<a id="__codelineno-60-15" name="__codelineno-60-15" href="#__codelineno-60-15"></a>
<a id="__codelineno-60-16" name="__codelineno-60-16" href="#__codelineno-60-16"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-60-17" name="__codelineno-60-17" href="#__codelineno-60-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">val</span>
<a id="__codelineno-60-18" name="__codelineno-60-18" href="#__codelineno-60-18"></a><span class="p">}</span>
<a id="__codelineno-60-19" name="__codelineno-60-19" href="#__codelineno-60-19"></a>
<a id="__codelineno-60-20" name="__codelineno-60-20" href="#__codelineno-60-20"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-60-21" name="__codelineno-60-21" href="#__codelineno-60-21"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">h</span><span class="w"> </span><span class="o">*</span><span class="nx">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="nx">siftDown</span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-22" name="__codelineno-60-22" href="#__codelineno-60-22"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="kc">true</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-23" name="__codelineno-60-23" href="#__codelineno-60-23"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 max</span>
<a id="__codelineno-60-24" name="__codelineno-60-24" href="#__codelineno-60-24"></a><span class="w">        </span><span class="nx">l</span><span class="p">,</span><span class="w"> </span><span class="nx">r</span><span class="p">,</span><span class="w"> </span><span class="nx">max</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="p">),</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="p">),</span><span class="w"> </span><span class="nx">i</span>
<a id="__codelineno-60-25" name="__codelineno-60-25" href="#__codelineno-60-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">l</span><span class="w"> </span><span class="p">&lt;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">l</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">&gt;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">max</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-26" name="__codelineno-60-26" href="#__codelineno-60-26"></a><span class="w">            </span><span class="nx">max</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">l</span>
<a id="__codelineno-60-27" name="__codelineno-60-27" href="#__codelineno-60-27"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-60-28" name="__codelineno-60-28" href="#__codelineno-60-28"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">r</span><span class="w"> </span><span class="p">&lt;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">r</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">&gt;</span><span class="w"> </span><span class="nx">h</span><span class="p">.</span><span class="nx">data</span><span class="p">[</span><span class="nx">max</span><span class="p">].(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-29" name="__codelineno-60-29" href="#__codelineno-60-29"></a><span class="w">            </span><span class="nx">max</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">r</span>
<a id="__codelineno-60-30" name="__codelineno-60-30" href="#__codelineno-60-30"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-60-31" name="__codelineno-60-31" href="#__codelineno-60-31"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-60-32" name="__codelineno-60-32" href="#__codelineno-60-32"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">max</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-60-33" name="__codelineno-60-33" href="#__codelineno-60-33"></a><span class="w">            </span><span class="k">break</span>
<a id="__codelineno-60-34" name="__codelineno-60-34" href="#__codelineno-60-34"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-60-35" name="__codelineno-60-35" href="#__codelineno-60-35"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-60-36" name="__codelineno-60-36" href="#__codelineno-60-36"></a><span class="w">        </span><span class="nx">h</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">max</span><span class="p">)</span>
<a id="__codelineno-60-37" name="__codelineno-60-37" href="#__codelineno-60-37"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-60-38" name="__codelineno-60-38" href="#__codelineno-60-38"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">max</span>
<a id="__codelineno-60-39" name="__codelineno-60-39" href="#__codelineno-60-39"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-60-40" name="__codelineno-60-40" href="#__codelineno-60-40"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.swift</span><pre id="__code_61"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_61 > code"></button><code><a id="__codelineno-61-1" name="__codelineno-61-1" href="#__codelineno-61-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-61-2" name="__codelineno-61-2" href="#__codelineno-61-2"></a><span class="kd">func</span> <span class="nf">pop</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-61-3" name="__codelineno-61-3" href="#__codelineno-61-3"></a>    <span class="c1">// 判空处理</span>
<a id="__codelineno-61-4" name="__codelineno-61-4" href="#__codelineno-61-4"></a>    <span class="k">if</span> <span class="bp">isEmpty</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-61-5" name="__codelineno-61-5" href="#__codelineno-61-5"></a>        <span class="bp">fatalError</span><span class="p">(</span><span class="s">"堆为空"</span><span class="p">)</span>
<a id="__codelineno-61-6" name="__codelineno-61-6" href="#__codelineno-61-6"></a>    <span class="p">}</span>
<a id="__codelineno-61-7" name="__codelineno-61-7" href="#__codelineno-61-7"></a>    <span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-61-8" name="__codelineno-61-8" href="#__codelineno-61-8"></a>    <span class="bp">swap</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="mi">0</span><span class="p">,</span> <span class="n">j</span><span class="p">:</span> <span class="n">size</span><span class="p">()</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-61-9" name="__codelineno-61-9" href="#__codelineno-61-9"></a>    <span class="c1">// 删除节点</span>
<a id="__codelineno-61-10" name="__codelineno-61-10" href="#__codelineno-61-10"></a>    <span class="kd">let</span> <span class="nv">val</span> <span class="p">=</span> <span class="n">maxHeap</span><span class="p">.</span><span class="n">remove</span><span class="p">(</span><span class="n">at</span><span class="p">:</span> <span class="n">size</span><span class="p">()</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-61-11" name="__codelineno-61-11" href="#__codelineno-61-11"></a>    <span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-61-12" name="__codelineno-61-12" href="#__codelineno-61-12"></a>    <span class="n">siftDown</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="mi">0</span><span class="p">)</span>
<a id="__codelineno-61-13" name="__codelineno-61-13" href="#__codelineno-61-13"></a>    <span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-61-14" name="__codelineno-61-14" href="#__codelineno-61-14"></a>    <span class="k">return</span> <span class="n">val</span>
<a id="__codelineno-61-15" name="__codelineno-61-15" href="#__codelineno-61-15"></a><span class="p">}</span>
<a id="__codelineno-61-16" name="__codelineno-61-16" href="#__codelineno-61-16"></a>
<a id="__codelineno-61-17" name="__codelineno-61-17" href="#__codelineno-61-17"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-61-18" name="__codelineno-61-18" href="#__codelineno-61-18"></a><span class="kd">func</span> <span class="nf">siftDown</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-61-19" name="__codelineno-61-19" href="#__codelineno-61-19"></a>    <span class="kd">var</span> <span class="nv">i</span> <span class="p">=</span> <span class="n">i</span>
<a id="__codelineno-61-20" name="__codelineno-61-20" href="#__codelineno-61-20"></a>    <span class="k">while</span> <span class="kc">true</span> <span class="p">{</span>
<a id="__codelineno-61-21" name="__codelineno-61-21" href="#__codelineno-61-21"></a>        <span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-61-22" name="__codelineno-61-22" href="#__codelineno-61-22"></a>        <span class="kd">let</span> <span class="nv">l</span> <span class="p">=</span> <span class="kr">left</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">i</span><span class="p">)</span>
<a id="__codelineno-61-23" name="__codelineno-61-23" href="#__codelineno-61-23"></a>        <span class="kd">let</span> <span class="nv">r</span> <span class="p">=</span> <span class="kr">right</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">i</span><span class="p">)</span>
<a id="__codelineno-61-24" name="__codelineno-61-24" href="#__codelineno-61-24"></a>        <span class="kd">var</span> <span class="nv">ma</span> <span class="p">=</span> <span class="n">i</span>
<a id="__codelineno-61-25" name="__codelineno-61-25" href="#__codelineno-61-25"></a>        <span class="k">if</span> <span class="n">l</span> <span class="o">&lt;</span> <span class="n">size</span><span class="p">(),</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span> <span class="o">&gt;</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-61-26" name="__codelineno-61-26" href="#__codelineno-61-26"></a>            <span class="n">ma</span> <span class="p">=</span> <span class="n">l</span>
<a id="__codelineno-61-27" name="__codelineno-61-27" href="#__codelineno-61-27"></a>        <span class="p">}</span>
<a id="__codelineno-61-28" name="__codelineno-61-28" href="#__codelineno-61-28"></a>        <span class="k">if</span> <span class="n">r</span> <span class="o">&lt;</span> <span class="n">size</span><span class="p">(),</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span> <span class="o">&gt;</span> <span class="n">maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-61-29" name="__codelineno-61-29" href="#__codelineno-61-29"></a>            <span class="n">ma</span> <span class="p">=</span> <span class="n">r</span>
<a id="__codelineno-61-30" name="__codelineno-61-30" href="#__codelineno-61-30"></a>        <span class="p">}</span>
<a id="__codelineno-61-31" name="__codelineno-61-31" href="#__codelineno-61-31"></a>        <span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-61-32" name="__codelineno-61-32" href="#__codelineno-61-32"></a>        <span class="k">if</span> <span class="n">ma</span> <span class="p">==</span> <span class="n">i</span> <span class="p">{</span>
<a id="__codelineno-61-33" name="__codelineno-61-33" href="#__codelineno-61-33"></a>            <span class="k">break</span>
<a id="__codelineno-61-34" name="__codelineno-61-34" href="#__codelineno-61-34"></a>        <span class="p">}</span>
<a id="__codelineno-61-35" name="__codelineno-61-35" href="#__codelineno-61-35"></a>        <span class="c1">// 交换两节点</span>
<a id="__codelineno-61-36" name="__codelineno-61-36" href="#__codelineno-61-36"></a>        <span class="bp">swap</span><span class="p">(</span><span class="n">i</span><span class="p">:</span> <span class="n">i</span><span class="p">,</span> <span class="n">j</span><span class="p">:</span> <span class="n">ma</span><span class="p">)</span>
<a id="__codelineno-61-37" name="__codelineno-61-37" href="#__codelineno-61-37"></a>        <span class="c1">// 循环向下堆化</span>
<a id="__codelineno-61-38" name="__codelineno-61-38" href="#__codelineno-61-38"></a>        <span class="n">i</span> <span class="p">=</span> <span class="n">ma</span>
<a id="__codelineno-61-39" name="__codelineno-61-39" href="#__codelineno-61-39"></a>    <span class="p">}</span>
<a id="__codelineno-61-40" name="__codelineno-61-40" href="#__codelineno-61-40"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.js</span><pre id="__code_62"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_62 > code"></button><code><a id="__codelineno-62-1" name="__codelineno-62-1" href="#__codelineno-62-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-62-2" name="__codelineno-62-2" href="#__codelineno-62-2"></a><span class="nx">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-62-3" name="__codelineno-62-3" href="#__codelineno-62-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-62-4" name="__codelineno-62-4" href="#__codelineno-62-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">Error</span><span class="p">(</span><span class="s1">'堆为空'</span><span class="p">);</span>
<a id="__codelineno-62-5" name="__codelineno-62-5" href="#__codelineno-62-5"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-62-6" name="__codelineno-62-6" href="#__codelineno-62-6"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">swap</span><span class="p">(</span><span class="mf">0</span><span class="p">,</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">);</span>
<a id="__codelineno-62-7" name="__codelineno-62-7" href="#__codelineno-62-7"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-62-8" name="__codelineno-62-8" href="#__codelineno-62-8"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">.</span><span class="nx">pop</span><span class="p">();</span>
<a id="__codelineno-62-9" name="__codelineno-62-9" href="#__codelineno-62-9"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-62-10" name="__codelineno-62-10" href="#__codelineno-62-10"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">siftDown</span><span class="p">(</span><span class="mf">0</span><span class="p">);</span>
<a id="__codelineno-62-11" name="__codelineno-62-11" href="#__codelineno-62-11"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-62-12" name="__codelineno-62-12" href="#__codelineno-62-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-62-13" name="__codelineno-62-13" href="#__codelineno-62-13"></a><span class="p">}</span>
<a id="__codelineno-62-14" name="__codelineno-62-14" href="#__codelineno-62-14"></a>
<a id="__codelineno-62-15" name="__codelineno-62-15" href="#__codelineno-62-15"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-62-16" name="__codelineno-62-16" href="#__codelineno-62-16"></a><span class="err">#</span><span class="nx">siftDown</span><span class="p">(</span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-62-17" name="__codelineno-62-17" href="#__codelineno-62-17"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-62-18" name="__codelineno-62-18" href="#__codelineno-62-18"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-62-19" name="__codelineno-62-19" href="#__codelineno-62-19"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="p">),</span>
<a id="__codelineno-62-20" name="__codelineno-62-20" href="#__codelineno-62-20"></a><span class="w">            </span><span class="nx">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-62-21" name="__codelineno-62-21" href="#__codelineno-62-21"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">i</span><span class="p">;</span>
<a id="__codelineno-62-22" name="__codelineno-62-22" href="#__codelineno-62-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">ma</span><span class="p">])</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">l</span><span class="p">;</span>
<a id="__codelineno-62-23" name="__codelineno-62-23" href="#__codelineno-62-23"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">ma</span><span class="p">])</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">r</span><span class="p">;</span>
<a id="__codelineno-62-24" name="__codelineno-62-24" href="#__codelineno-62-24"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-62-25" name="__codelineno-62-25" href="#__codelineno-62-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">ma</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-62-26" name="__codelineno-62-26" href="#__codelineno-62-26"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-62-27" name="__codelineno-62-27" href="#__codelineno-62-27"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">ma</span><span class="p">);</span>
<a id="__codelineno-62-28" name="__codelineno-62-28" href="#__codelineno-62-28"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-62-29" name="__codelineno-62-29" href="#__codelineno-62-29"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">ma</span><span class="p">;</span>
<a id="__codelineno-62-30" name="__codelineno-62-30" href="#__codelineno-62-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-62-31" name="__codelineno-62-31" href="#__codelineno-62-31"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.ts</span><pre id="__code_63"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_63 > code"></button><code><a id="__codelineno-63-1" name="__codelineno-63-1" href="#__codelineno-63-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-63-2" name="__codelineno-63-2" href="#__codelineno-63-2"></a><span class="nx">pop</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-63-3" name="__codelineno-63-3" href="#__codelineno-63-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-63-4" name="__codelineno-63-4" href="#__codelineno-63-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="ne">RangeError</span><span class="p">(</span><span class="s1">'Heap is empty.'</span><span class="p">);</span>
<a id="__codelineno-63-5" name="__codelineno-63-5" href="#__codelineno-63-5"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-63-6" name="__codelineno-63-6" href="#__codelineno-63-6"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="mf">0</span><span class="p">,</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">);</span>
<a id="__codelineno-63-7" name="__codelineno-63-7" href="#__codelineno-63-7"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-63-8" name="__codelineno-63-8" href="#__codelineno-63-8"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">.</span><span class="nx">pop</span><span class="p">();</span>
<a id="__codelineno-63-9" name="__codelineno-63-9" href="#__codelineno-63-9"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-63-10" name="__codelineno-63-10" href="#__codelineno-63-10"></a><span class="w">    </span><span class="k">this</span><span class="p">.</span><span class="nx">siftDown</span><span class="p">(</span><span class="mf">0</span><span class="p">);</span>
<a id="__codelineno-63-11" name="__codelineno-63-11" href="#__codelineno-63-11"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-63-12" name="__codelineno-63-12" href="#__codelineno-63-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-63-13" name="__codelineno-63-13" href="#__codelineno-63-13"></a><span class="p">}</span>
<a id="__codelineno-63-14" name="__codelineno-63-14" href="#__codelineno-63-14"></a>
<a id="__codelineno-63-15" name="__codelineno-63-15" href="#__codelineno-63-15"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-63-16" name="__codelineno-63-16" href="#__codelineno-63-16"></a><span class="nx">siftDown</span><span class="p">(</span><span class="nx">i</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="ow">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-63-17" name="__codelineno-63-17" href="#__codelineno-63-17"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-63-18" name="__codelineno-63-18" href="#__codelineno-63-18"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-63-19" name="__codelineno-63-19" href="#__codelineno-63-19"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">left</span><span class="p">(</span><span class="nx">i</span><span class="p">),</span>
<a id="__codelineno-63-20" name="__codelineno-63-20" href="#__codelineno-63-20"></a><span class="w">            </span><span class="nx">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">right</span><span class="p">(</span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-63-21" name="__codelineno-63-21" href="#__codelineno-63-21"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">i</span><span class="p">;</span>
<a id="__codelineno-63-22" name="__codelineno-63-22" href="#__codelineno-63-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">ma</span><span class="p">])</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">l</span><span class="p">;</span>
<a id="__codelineno-63-23" name="__codelineno-63-23" href="#__codelineno-63-23"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">maxHeap</span><span class="p">[</span><span class="nx">ma</span><span class="p">])</span><span class="w"> </span><span class="nx">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">r</span><span class="p">;</span>
<a id="__codelineno-63-24" name="__codelineno-63-24" href="#__codelineno-63-24"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-63-25" name="__codelineno-63-25" href="#__codelineno-63-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">ma</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="nx">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-63-26" name="__codelineno-63-26" href="#__codelineno-63-26"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-63-27" name="__codelineno-63-27" href="#__codelineno-63-27"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">swap</span><span class="p">(</span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">ma</span><span class="p">);</span>
<a id="__codelineno-63-28" name="__codelineno-63-28" href="#__codelineno-63-28"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-63-29" name="__codelineno-63-29" href="#__codelineno-63-29"></a><span class="w">        </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">ma</span><span class="p">;</span>
<a id="__codelineno-63-30" name="__codelineno-63-30" href="#__codelineno-63-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-63-31" name="__codelineno-63-31" href="#__codelineno-63-31"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.dart</span><pre id="__code_64"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_64 > code"></button><code><a id="__codelineno-64-1" name="__codelineno-64-1" href="#__codelineno-64-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-64-2" name="__codelineno-64-2" href="#__codelineno-64-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">pop</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-64-3" name="__codelineno-64-3" href="#__codelineno-64-3"></a><span class="w">  </span><span class="c1">// 判空处理</span>
<a id="__codelineno-64-4" name="__codelineno-64-4" href="#__codelineno-64-4"></a><span class="w">  </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="n">Exception</span><span class="p">(</span><span class="s1">'堆为空'</span><span class="p">);</span>
<a id="__codelineno-64-5" name="__codelineno-64-5" href="#__codelineno-64-5"></a><span class="w">  </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-64-6" name="__codelineno-64-6" href="#__codelineno-64-6"></a><span class="w">  </span><span class="n">_swap</span><span class="p">(</span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">);</span>
<a id="__codelineno-64-7" name="__codelineno-64-7" href="#__codelineno-64-7"></a><span class="w">  </span><span class="c1">// 删除节点</span>
<a id="__codelineno-64-8" name="__codelineno-64-8" href="#__codelineno-64-8"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">.</span><span class="n">removeLast</span><span class="p">();</span>
<a id="__codelineno-64-9" name="__codelineno-64-9" href="#__codelineno-64-9"></a><span class="w">  </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-64-10" name="__codelineno-64-10" href="#__codelineno-64-10"></a><span class="w">  </span><span class="n">siftDown</span><span class="p">(</span><span class="m">0</span><span class="p">);</span>
<a id="__codelineno-64-11" name="__codelineno-64-11" href="#__codelineno-64-11"></a><span class="w">  </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-64-12" name="__codelineno-64-12" href="#__codelineno-64-12"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-64-13" name="__codelineno-64-13" href="#__codelineno-64-13"></a><span class="p">}</span>
<a id="__codelineno-64-14" name="__codelineno-64-14" href="#__codelineno-64-14"></a>
<a id="__codelineno-64-15" name="__codelineno-64-15" href="#__codelineno-64-15"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-64-16" name="__codelineno-64-16" href="#__codelineno-64-16"></a><span class="kt">void</span><span class="w"> </span><span class="n">siftDown</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-64-17" name="__codelineno-64-17" href="#__codelineno-64-17"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-64-18" name="__codelineno-64-18" href="#__codelineno-64-18"></a><span class="w">    </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-64-19" name="__codelineno-64-19" href="#__codelineno-64-19"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_left</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-64-20" name="__codelineno-64-20" href="#__codelineno-64-20"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_right</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-64-21" name="__codelineno-64-21" href="#__codelineno-64-21"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-64-22" name="__codelineno-64-22" href="#__codelineno-64-22"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-64-23" name="__codelineno-64-23" href="#__codelineno-64-23"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">_maxHeap</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-64-24" name="__codelineno-64-24" href="#__codelineno-64-24"></a><span class="w">    </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-64-25" name="__codelineno-64-25" href="#__codelineno-64-25"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-64-26" name="__codelineno-64-26" href="#__codelineno-64-26"></a><span class="w">    </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-64-27" name="__codelineno-64-27" href="#__codelineno-64-27"></a><span class="w">    </span><span class="n">_swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">);</span>
<a id="__codelineno-64-28" name="__codelineno-64-28" href="#__codelineno-64-28"></a><span class="w">    </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-64-29" name="__codelineno-64-29" href="#__codelineno-64-29"></a><span class="w">    </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-64-30" name="__codelineno-64-30" href="#__codelineno-64-30"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-64-31" name="__codelineno-64-31" href="#__codelineno-64-31"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rs</span><pre id="__code_65"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_65 > code"></button><code><a id="__codelineno-65-1" name="__codelineno-65-1" href="#__codelineno-65-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-65-2" name="__codelineno-65-2" href="#__codelineno-65-2"></a><span class="k">fn</span> <span class="nf">pop</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-65-3" name="__codelineno-65-3" href="#__codelineno-65-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-65-4" name="__codelineno-65-4" href="#__codelineno-65-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">is_empty</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-5" name="__codelineno-65-5" href="#__codelineno-65-5"></a><span class="w">        </span><span class="fm">panic!</span><span class="p">(</span><span class="s">"index out of bounds"</span><span class="p">);</span>
<a id="__codelineno-65-6" name="__codelineno-65-6" href="#__codelineno-65-6"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-65-7" name="__codelineno-65-7" href="#__codelineno-65-7"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-65-8" name="__codelineno-65-8" href="#__codelineno-65-8"></a><span class="w">    </span><span class="bp">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-65-9" name="__codelineno-65-9" href="#__codelineno-65-9"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-65-10" name="__codelineno-65-10" href="#__codelineno-65-10"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="n">pop</span><span class="p">().</span><span class="n">unwrap</span><span class="p">();</span>
<a id="__codelineno-65-11" name="__codelineno-65-11" href="#__codelineno-65-11"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-65-12" name="__codelineno-65-12" href="#__codelineno-65-12"></a><span class="w">    </span><span class="bp">self</span><span class="p">.</span><span class="n">sift_down</span><span class="p">(</span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-65-13" name="__codelineno-65-13" href="#__codelineno-65-13"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-65-14" name="__codelineno-65-14" href="#__codelineno-65-14"></a><span class="w">    </span><span class="n">val</span>
<a id="__codelineno-65-15" name="__codelineno-65-15" href="#__codelineno-65-15"></a><span class="p">}</span>
<a id="__codelineno-65-16" name="__codelineno-65-16" href="#__codelineno-65-16"></a>
<a id="__codelineno-65-17" name="__codelineno-65-17" href="#__codelineno-65-17"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-65-18" name="__codelineno-65-18" href="#__codelineno-65-18"></a><span class="k">fn</span> <span class="nf">sift_down</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">i</span>: <span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-19" name="__codelineno-65-19" href="#__codelineno-65-19"></a><span class="w">    </span><span class="k">loop</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-20" name="__codelineno-65-20" href="#__codelineno-65-20"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-65-21" name="__codelineno-65-21" href="#__codelineno-65-21"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="p">,</span><span class="w"> </span><span class="n">r</span><span class="p">,</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">ma</span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="bp">Self</span>::<span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="bp">Self</span>::<span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-65-22" name="__codelineno-65-22" href="#__codelineno-65-22"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">ma</span><span class="p">]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-23" name="__codelineno-65-23" href="#__codelineno-65-23"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-65-24" name="__codelineno-65-24" href="#__codelineno-65-24"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-65-25" name="__codelineno-65-25" href="#__codelineno-65-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">[</span><span class="n">ma</span><span class="p">]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-26" name="__codelineno-65-26" href="#__codelineno-65-26"></a><span class="w">            </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-65-27" name="__codelineno-65-27" href="#__codelineno-65-27"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-65-28" name="__codelineno-65-28" href="#__codelineno-65-28"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-65-29" name="__codelineno-65-29" href="#__codelineno-65-29"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-65-30" name="__codelineno-65-30" href="#__codelineno-65-30"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-65-31" name="__codelineno-65-31" href="#__codelineno-65-31"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-65-32" name="__codelineno-65-32" href="#__codelineno-65-32"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-65-33" name="__codelineno-65-33" href="#__codelineno-65-33"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">);</span>
<a id="__codelineno-65-34" name="__codelineno-65-34" href="#__codelineno-65-34"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-65-35" name="__codelineno-65-35" href="#__codelineno-65-35"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-65-36" name="__codelineno-65-36" href="#__codelineno-65-36"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-65-37" name="__codelineno-65-37" href="#__codelineno-65-37"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.c</span><pre id="__code_66"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_66 > code"></button><code><a id="__codelineno-66-1" name="__codelineno-66-1" href="#__codelineno-66-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-66-2" name="__codelineno-66-2" href="#__codelineno-66-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">pop</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-3" name="__codelineno-66-3" href="#__codelineno-66-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-66-4" name="__codelineno-66-4" href="#__codelineno-66-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">))</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-5" name="__codelineno-66-5" href="#__codelineno-66-5"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"heap is empty!"</span><span class="p">);</span>
<a id="__codelineno-66-6" name="__codelineno-66-6" href="#__codelineno-66-6"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">INT_MAX</span><span class="p">;</span>
<a id="__codelineno-66-7" name="__codelineno-66-7" href="#__codelineno-66-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-66-8" name="__codelineno-66-8" href="#__codelineno-66-8"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-66-9" name="__codelineno-66-9" href="#__codelineno-66-9"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-66-10" name="__codelineno-66-10" href="#__codelineno-66-10"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-66-11" name="__codelineno-66-11" href="#__codelineno-66-11"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">];</span>
<a id="__codelineno-66-12" name="__codelineno-66-12" href="#__codelineno-66-12"></a><span class="w">    </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">size</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-66-13" name="__codelineno-66-13" href="#__codelineno-66-13"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-66-14" name="__codelineno-66-14" href="#__codelineno-66-14"></a><span class="w">    </span><span class="n">siftDown</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-66-15" name="__codelineno-66-15" href="#__codelineno-66-15"></a>
<a id="__codelineno-66-16" name="__codelineno-66-16" href="#__codelineno-66-16"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-66-17" name="__codelineno-66-17" href="#__codelineno-66-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-66-18" name="__codelineno-66-18" href="#__codelineno-66-18"></a><span class="p">}</span>
<a id="__codelineno-66-19" name="__codelineno-66-19" href="#__codelineno-66-19"></a>
<a id="__codelineno-66-20" name="__codelineno-66-20" href="#__codelineno-66-20"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-66-21" name="__codelineno-66-21" href="#__codelineno-66-21"></a><span class="kt">void</span><span class="w"> </span><span class="nf">siftDown</span><span class="p">(</span><span class="n">MaxHeap</span><span class="w"> </span><span class="o">*</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-22" name="__codelineno-66-22" href="#__codelineno-66-22"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nb">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-23" name="__codelineno-66-23" href="#__codelineno-66-23"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 max</span>
<a id="__codelineno-66-24" name="__codelineno-66-24" href="#__codelineno-66-24"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-66-25" name="__codelineno-66-25" href="#__codelineno-66-25"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-66-26" name="__codelineno-66-26" href="#__codelineno-66-26"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">max</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-66-27" name="__codelineno-66-27" href="#__codelineno-66-27"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">max</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-28" name="__codelineno-66-28" href="#__codelineno-66-28"></a><span class="w">            </span><span class="n">max</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-66-29" name="__codelineno-66-29" href="#__codelineno-66-29"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-66-30" name="__codelineno-66-30" href="#__codelineno-66-30"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">)</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">-&gt;</span><span class="n">data</span><span class="p">[</span><span class="n">max</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-31" name="__codelineno-66-31" href="#__codelineno-66-31"></a><span class="w">            </span><span class="n">max</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-66-32" name="__codelineno-66-32" href="#__codelineno-66-32"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-66-33" name="__codelineno-66-33" href="#__codelineno-66-33"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-66-34" name="__codelineno-66-34" href="#__codelineno-66-34"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">max</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-66-35" name="__codelineno-66-35" href="#__codelineno-66-35"></a><span class="w">            </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-66-36" name="__codelineno-66-36" href="#__codelineno-66-36"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-66-37" name="__codelineno-66-37" href="#__codelineno-66-37"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-66-38" name="__codelineno-66-38" href="#__codelineno-66-38"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">maxHeap</span><span class="p">,</span><span class="w"> </span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">max</span><span class="p">);</span>
<a id="__codelineno-66-39" name="__codelineno-66-39" href="#__codelineno-66-39"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-66-40" name="__codelineno-66-40" href="#__codelineno-66-40"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">max</span><span class="p">;</span>
<a id="__codelineno-66-41" name="__codelineno-66-41" href="#__codelineno-66-41"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-66-42" name="__codelineno-66-42" href="#__codelineno-66-42"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.kt</span><pre id="__code_67"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_67 > code"></button><code><a id="__codelineno-67-1" name="__codelineno-67-1" href="#__codelineno-67-1"></a><span class="cm">/* 元素出堆 */</span>
<a id="__codelineno-67-2" name="__codelineno-67-2" href="#__codelineno-67-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">pop</span><span class="p">():</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-67-3" name="__codelineno-67-3" href="#__codelineno-67-3"></a><span class="w">    </span><span class="c1">// 判空处理</span>
<a id="__codelineno-67-4" name="__codelineno-67-4" href="#__codelineno-67-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">throw</span><span class="w"> </span><span class="n">IndexOutOfBoundsException</span><span class="p">()</span>
<a id="__codelineno-67-5" name="__codelineno-67-5" href="#__codelineno-67-5"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-67-6" name="__codelineno-67-6" href="#__codelineno-67-6"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span>
<a id="__codelineno-67-7" name="__codelineno-67-7" href="#__codelineno-67-7"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-67-8" name="__codelineno-67-8" href="#__codelineno-67-8"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">_val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">maxHeap</span><span class="p">.</span><span class="na">removeAt</span><span class="p">(</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">)</span>
<a id="__codelineno-67-9" name="__codelineno-67-9" href="#__codelineno-67-9"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-67-10" name="__codelineno-67-10" href="#__codelineno-67-10"></a><span class="w">    </span><span class="n">siftDown</span><span class="p">(</span><span class="m">0</span><span class="p">)</span>
<a id="__codelineno-67-11" name="__codelineno-67-11" href="#__codelineno-67-11"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-67-12" name="__codelineno-67-12" href="#__codelineno-67-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">_val</span>
<a id="__codelineno-67-13" name="__codelineno-67-13" href="#__codelineno-67-13"></a><span class="p">}</span>
<a id="__codelineno-67-14" name="__codelineno-67-14" href="#__codelineno-67-14"></a>
<a id="__codelineno-67-15" name="__codelineno-67-15" href="#__codelineno-67-15"></a><span class="cm">/* 从节点 i 开始，从顶至底堆化 */</span>
<a id="__codelineno-67-16" name="__codelineno-67-16" href="#__codelineno-67-16"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">siftDown</span><span class="p">(</span><span class="nb">it</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-67-17" name="__codelineno-67-17" href="#__codelineno-67-17"></a><span class="w">    </span><span class="c1">// Kotlin的函数参数不可变，因此创建临时变量</span>
<a id="__codelineno-67-18" name="__codelineno-67-18" href="#__codelineno-67-18"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">it</span>
<a id="__codelineno-67-19" name="__codelineno-67-19" href="#__codelineno-67-19"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-67-20" name="__codelineno-67-20" href="#__codelineno-67-20"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-67-21" name="__codelineno-67-21" href="#__codelineno-67-21"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-67-22" name="__codelineno-67-22" href="#__codelineno-67-22"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-67-23" name="__codelineno-67-23" href="#__codelineno-67-23"></a><span class="w">        </span><span class="kd">var</span><span class="w"> </span><span class="nv">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span>
<a id="__codelineno-67-24" name="__codelineno-67-24" href="#__codelineno-67-24"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">l</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">ma</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span>
<a id="__codelineno-67-25" name="__codelineno-67-25" href="#__codelineno-67-25"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">r</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">maxHeap</span><span class="o">[</span><span class="n">ma</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span>
<a id="__codelineno-67-26" name="__codelineno-67-26" href="#__codelineno-67-26"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-67-27" name="__codelineno-67-27" href="#__codelineno-67-27"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span>
<a id="__codelineno-67-28" name="__codelineno-67-28" href="#__codelineno-67-28"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-67-29" name="__codelineno-67-29" href="#__codelineno-67-29"></a><span class="w">        </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">)</span>
<a id="__codelineno-67-30" name="__codelineno-67-30" href="#__codelineno-67-30"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-67-31" name="__codelineno-67-31" href="#__codelineno-67-31"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span>
<a id="__codelineno-67-32" name="__codelineno-67-32" href="#__codelineno-67-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-67-33" name="__codelineno-67-33" href="#__codelineno-67-33"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.rb</span><pre id="__code_68"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_68 > code"></button><code><a id="__codelineno-68-1" name="__codelineno-68-1" href="#__codelineno-68-1"></a><span class="c1">### 元素出堆 ###</span>
<a id="__codelineno-68-2" name="__codelineno-68-2" href="#__codelineno-68-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">pop</span>
<a id="__codelineno-68-3" name="__codelineno-68-3" href="#__codelineno-68-3"></a><span class="w">  </span><span class="c1"># 判空处理</span>
<a id="__codelineno-68-4" name="__codelineno-68-4" href="#__codelineno-68-4"></a><span class="w">  </span><span class="k">raise</span><span class="w"> </span><span class="no">IndexError</span><span class="p">,</span><span class="w"> </span><span class="s2">"堆为空"</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">is_empty?</span>
<a id="__codelineno-68-5" name="__codelineno-68-5" href="#__codelineno-68-5"></a><span class="w">  </span><span class="c1"># 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-68-6" name="__codelineno-68-6" href="#__codelineno-68-6"></a><span class="w">  </span><span class="n">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-68-7" name="__codelineno-68-7" href="#__codelineno-68-7"></a><span class="w">  </span><span class="c1"># 删除节点</span>
<a id="__codelineno-68-8" name="__codelineno-68-8" href="#__codelineno-68-8"></a><span class="w">  </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">.</span><span class="n">pop</span>
<a id="__codelineno-68-9" name="__codelineno-68-9" href="#__codelineno-68-9"></a><span class="w">  </span><span class="c1"># 从顶至底堆化</span>
<a id="__codelineno-68-10" name="__codelineno-68-10" href="#__codelineno-68-10"></a><span class="w">  </span><span class="n">sift_down</span><span class="p">(</span><span class="mi">0</span><span class="p">)</span>
<a id="__codelineno-68-11" name="__codelineno-68-11" href="#__codelineno-68-11"></a><span class="w">  </span><span class="c1"># 返回堆顶元素</span>
<a id="__codelineno-68-12" name="__codelineno-68-12" href="#__codelineno-68-12"></a><span class="w">  </span><span class="n">val</span>
<a id="__codelineno-68-13" name="__codelineno-68-13" href="#__codelineno-68-13"></a><span class="k">end</span>
<a id="__codelineno-68-14" name="__codelineno-68-14" href="#__codelineno-68-14"></a>
<a id="__codelineno-68-15" name="__codelineno-68-15" href="#__codelineno-68-15"></a><span class="c1">### 从节点 i 开始，从顶至底堆化 ###</span>
<a id="__codelineno-68-16" name="__codelineno-68-16" href="#__codelineno-68-16"></a><span class="k">def</span><span class="w"> </span><span class="nf">sift_down</span><span class="p">(</span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-68-17" name="__codelineno-68-17" href="#__codelineno-68-17"></a><span class="w">  </span><span class="kp">loop</span><span class="w"> </span><span class="k">do</span>
<a id="__codelineno-68-18" name="__codelineno-68-18" href="#__codelineno-68-18"></a><span class="w">    </span><span class="c1"># 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-68-19" name="__codelineno-68-19" href="#__codelineno-68-19"></a><span class="w">    </span><span class="n">l</span><span class="p">,</span><span class="w"> </span><span class="n">r</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">),</span><span class="w"> </span><span class="n">i</span>
<a id="__codelineno-68-20" name="__codelineno-68-20" href="#__codelineno-68-20"></a><span class="w">    </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="n">l</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="n">ma</span><span class="o">]</span>
<a id="__codelineno-68-21" name="__codelineno-68-21" href="#__codelineno-68-21"></a><span class="w">    </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">size</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="n">r</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="vi">@max_heap</span><span class="o">[</span><span class="n">ma</span><span class="o">]</span>
<a id="__codelineno-68-22" name="__codelineno-68-22" href="#__codelineno-68-22"></a>
<a id="__codelineno-68-23" name="__codelineno-68-23" href="#__codelineno-68-23"></a><span class="w">    </span><span class="c1"># 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-68-24" name="__codelineno-68-24" href="#__codelineno-68-24"></a><span class="w">    </span><span class="k">break</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span>
<a id="__codelineno-68-25" name="__codelineno-68-25" href="#__codelineno-68-25"></a>
<a id="__codelineno-68-26" name="__codelineno-68-26" href="#__codelineno-68-26"></a><span class="w">    </span><span class="c1"># 交换两节点</span>
<a id="__codelineno-68-27" name="__codelineno-68-27" href="#__codelineno-68-27"></a><span class="w">    </span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">)</span>
<a id="__codelineno-68-28" name="__codelineno-68-28" href="#__codelineno-68-28"></a><span class="w">    </span><span class="c1"># 循环向下堆化</span>
<a id="__codelineno-68-29" name="__codelineno-68-29" href="#__codelineno-68-29"></a><span class="w">    </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span>
<a id="__codelineno-68-30" name="__codelineno-68-30" href="#__codelineno-68-30"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-68-31" name="__codelineno-68-31" href="#__codelineno-68-31"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">my_heap.zig</span><pre id="__code_69"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_69 > code"></button><code><a id="__codelineno-69-1" name="__codelineno-69-1" href="#__codelineno-69-1"></a><span class="c1">// 元素出堆</span>
<a id="__codelineno-69-2" name="__codelineno-69-2" href="#__codelineno-69-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">pop</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="n">T</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-69-3" name="__codelineno-69-3" href="#__codelineno-69-3"></a><span class="w">    </span><span class="c1">// 判断处理</span>
<a id="__codelineno-69-4" name="__codelineno-69-4" href="#__codelineno-69-4"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">isEmpty</span><span class="p">())</span><span class="w"> </span><span class="k">unreachable</span><span class="p">;</span>
<a id="__codelineno-69-5" name="__codelineno-69-5" href="#__codelineno-69-5"></a><span class="w">    </span><span class="c1">// 交换根节点与最右叶节点（交换首元素与尾元素）</span>
<a id="__codelineno-69-6" name="__codelineno-69-6" href="#__codelineno-69-6"></a><span class="w">    </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-69-7" name="__codelineno-69-7" href="#__codelineno-69-7"></a><span class="w">    </span><span class="c1">// 删除节点</span>
<a id="__codelineno-69-8" name="__codelineno-69-8" href="#__codelineno-69-8"></a><span class="w">    </span><span class="kr">var</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">pop</span><span class="p">();</span>
<a id="__codelineno-69-9" name="__codelineno-69-9" href="#__codelineno-69-9"></a><span class="w">    </span><span class="c1">// 从顶至底堆化</span>
<a id="__codelineno-69-10" name="__codelineno-69-10" href="#__codelineno-69-10"></a><span class="w">    </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">siftDown</span><span class="p">(</span><span class="mi">0</span><span class="p">);</span>
<a id="__codelineno-69-11" name="__codelineno-69-11" href="#__codelineno-69-11"></a><span class="w">    </span><span class="c1">// 返回堆顶元素</span>
<a id="__codelineno-69-12" name="__codelineno-69-12" href="#__codelineno-69-12"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-69-13" name="__codelineno-69-13" href="#__codelineno-69-13"></a><span class="p">}</span><span class="w"> </span>
<a id="__codelineno-69-14" name="__codelineno-69-14" href="#__codelineno-69-14"></a>
<a id="__codelineno-69-15" name="__codelineno-69-15" href="#__codelineno-69-15"></a><span class="c1">// 从节点 i 开始，从顶至底堆化</span>
<a id="__codelineno-69-16" name="__codelineno-69-16" href="#__codelineno-69-16"></a><span class="k">fn</span><span class="w"> </span><span class="n">siftDown</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">i_</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-69-17" name="__codelineno-69-17" href="#__codelineno-69-17"></a><span class="w">    </span><span class="kr">var</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i_</span><span class="p">;</span>
<a id="__codelineno-69-18" name="__codelineno-69-18" href="#__codelineno-69-18"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="kc">true</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-69-19" name="__codelineno-69-19" href="#__codelineno-69-19"></a><span class="w">        </span><span class="c1">// 判断节点 i, l, r 中值最大的节点，记为 ma</span>
<a id="__codelineno-69-20" name="__codelineno-69-20" href="#__codelineno-69-20"></a><span class="w">        </span><span class="kr">var</span><span class="w"> </span><span class="n">l</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">left</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-69-21" name="__codelineno-69-21" href="#__codelineno-69-21"></a><span class="w">        </span><span class="kr">var</span><span class="w"> </span><span class="n">r</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">right</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-69-22" name="__codelineno-69-22" href="#__codelineno-69-22"></a><span class="w">        </span><span class="kr">var</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-69-23" name="__codelineno-69-23" href="#__codelineno-69-23"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">l</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="k">and</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">l</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">l</span><span class="p">;</span>
<a id="__codelineno-69-24" name="__codelineno-69-24" href="#__codelineno-69-24"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">r</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="k">and</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">r</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">max_heap</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">ma</span><span class="p">])</span><span class="w"> </span><span class="n">ma</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">r</span><span class="p">;</span>
<a id="__codelineno-69-25" name="__codelineno-69-25" href="#__codelineno-69-25"></a><span class="w">        </span><span class="c1">// 若节点 i 最大或索引 l, r 越界，则无须继续堆化，跳出</span>
<a id="__codelineno-69-26" name="__codelineno-69-26" href="#__codelineno-69-26"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ma</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="k">break</span><span class="p">;</span>
<a id="__codelineno-69-27" name="__codelineno-69-27" href="#__codelineno-69-27"></a><span class="w">        </span><span class="c1">// 交换两节点</span>
<a id="__codelineno-69-28" name="__codelineno-69-28" href="#__codelineno-69-28"></a><span class="w">        </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">swap</span><span class="p">(</span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">ma</span><span class="p">);</span>
<a id="__codelineno-69-29" name="__codelineno-69-29" href="#__codelineno-69-29"></a><span class="w">        </span><span class="c1">// 循环向下堆化</span>
<a id="__codelineno-69-30" name="__codelineno-69-30" href="#__codelineno-69-30"></a><span class="w">        </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ma</span><span class="p">;</span>
<a id="__codelineno-69-31" name="__codelineno-69-31" href="#__codelineno-69-31"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-69-32" name="__codelineno-69-32" href="#__codelineno-69-32"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
## 堆常见应用

- **优先队列**：堆通常作为实现优先队列的首选数据结构，其入队和出队操作的时间复杂度均为 $O(\log n)$ ，而建队操作为 $O(n)$ ，这些操作都非常高效。
- **堆排序**：给定一组数据，我们可以用它们建立一个堆，然后不断地执行元素出堆操作，从而得到有序数据。然而，我们通常会使用一种更优雅的方式实现堆排序，详见后续的堆排序章节。
- **获取最大的 $k$ 个元素**：这是一个经典的算法问题，同时也是一种典型应用，例如选择热度前 10 的新闻作为微博热搜，选取销量前 10 的商品等。
