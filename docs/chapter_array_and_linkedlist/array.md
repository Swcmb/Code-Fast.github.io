# 数组

「数组 array」是一种线性数据结构，其将相同类型元素存储在连续的内存空间中。我们将元素在数组中的位置称为该元素的「索引 index」。下图展示了数组的主要术语和概念。

![数组定义与存储方式](array.assets/array_definition.png)

## 数组常用操作

### 初始化数组

我们可以根据需求选用数组的两种初始化方式：无初始值、给定初始值。在未指定初始值的情况下，大多数编程语言会将数组元素初始化为 $0$ 。

=== "Python"

    ```python title="array.py"
    # 初始化数组
    arr: list[int] = [0] * 5  # [ 0, 0, 0, 0, 0 ]
    nums: list[int] = [1, 3, 2, 5, 4]  
    ```

=== "C++"

    ```cpp title="array.cpp"
    /* 初始化数组 */
    // 存储在栈上
    int arr[5];
    int nums[5] = { 1, 3, 2, 5, 4 };
    // 存储在堆上（需要手动释放空间）
    int* arr1 = new int[5];
    int* nums1 = new int[5] { 1, 3, 2, 5, 4 };
    ```

=== "Java"

    ```java title="array.java"
    /* 初始化数组 */
    int[] arr = new int[5]; // { 0, 0, 0, 0, 0 }
    int[] nums = { 1, 3, 2, 5, 4 };
    ```

=== "C#"

    ```csharp title="array.cs"
    /* 初始化数组 */
    int[] arr = new int[5]; // { 0, 0, 0, 0, 0 }
    int[] nums = { 1, 3, 2, 5, 4 };
    ```

=== "Go"

    ```go title="array.go"
    /* 初始化数组 */
    var arr [5]int
    // 在 Go 中，指定长度时（[5]int）为数组，不指定长度时（[]int）为切片
    // 由于 Go 的数组被设计为在编译期确定长度，因此只能使用常量来指定长度
    // 为了方便实现扩容 extend() 方法，以下将切片（Slice）看作数组（Array）
    nums := []int{1, 3, 2, 5, 4}
    ```

=== "Swift"

    ```swift title="array.swift"
    /* 初始化数组 */
    let arr = Array(repeating: 0, count: 5) // [0, 0, 0, 0, 0]
    let nums = [1, 3, 2, 5, 4]
    ```

=== "JS"

    ```javascript title="array.js"
    /* 初始化数组 */
    var arr = new Array(5).fill(0);
    var nums = [1, 3, 2, 5, 4];
    ```

=== "TS"

    ```typescript title="array.ts"
    /* 初始化数组 */
    let arr: number[] = new Array(5).fill(0);
    let nums: number[] = [1, 3, 2, 5, 4];
    ```

=== "Dart"

    ```dart title="array.dart"
    /* 初始化数组 */
    List<int> arr = List.filled(5, 0); // [0, 0, 0, 0, 0]
    List<int> nums = [1, 3, 2, 5, 4];
    ```

=== "Rust"

    ```rust title="array.rs"
    /* 初始化数组 */
    let arr: Vec<i32> = vec![0; 5]; // [0, 0, 0, 0, 0]
    let nums: Vec<i32> = vec![1, 3, 2, 5, 4];
    ```

=== "C"

    ```c title="array.c"
    /* 初始化数组 */
    int arr[5] = { 0 }; // { 0, 0, 0, 0, 0 }
    int nums[5] = { 1, 3, 2, 5, 4 };
    ```

=== "Zig"

    ```zig title="array.zig"
    // 初始化数组
    var arr = [_]i32{0} ** 5; // { 0, 0, 0, 0, 0 }
    var nums = [_]i32{ 1, 3, 2, 5, 4 };
    ```

### 访问元素

数组元素被存储在连续的内存空间中，这意味着计算数组元素的内存地址非常容易。给定数组内存地址（即首元素内存地址）和某个元素的索引，我们可以使用下图所示的公式计算得到该元素的内存地址，从而直接访问此元素。

![数组元素的内存地址计算](array.assets/array_memory_location_calculation.png)

观察上图，我们发现数组首个元素的索引为 $0$ ，这似乎有些反直觉，因为从 $1$ 开始计数会更自然。但从地址计算公式的角度看，**索引的含义本质上是内存地址的偏移量**。首个元素的地址偏移量是 $0$ ，因此它的索引为 $0$ 也是合理的。

在数组中访问元素是非常高效的，我们可以在 $O(1)$ 时间内随机访问数组中的任意一个元素。

<div class="tabbed-set tabbed-alternate" data-tabs="2:14" style="--md-indicator-x: 167px; --md-indicator-width: 40px;"><input checked="checked" id="__tabbed_2_1" name="__tabbed_2" type="radio"><input id="__tabbed_2_2" name="__tabbed_2" type="radio"><input id="__tabbed_2_3" name="__tabbed_2" type="radio"><input id="__tabbed_2_4" name="__tabbed_2" type="radio"><input id="__tabbed_2_5" name="__tabbed_2" type="radio"><input id="__tabbed_2_6" name="__tabbed_2" type="radio"><input id="__tabbed_2_7" name="__tabbed_2" type="radio"><input id="__tabbed_2_8" name="__tabbed_2" type="radio"><input id="__tabbed_2_9" name="__tabbed_2" type="radio"><input id="__tabbed_2_10" name="__tabbed_2" type="radio"><input id="__tabbed_2_11" name="__tabbed_2" type="radio"><input id="__tabbed_2_12" name="__tabbed_2" type="radio"><input id="__tabbed_2_13" name="__tabbed_2" type="radio"><input id="__tabbed_2_14" name="__tabbed_2" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_2_1"><a href="#__tabbed_2_1" tabindex="-1">Python</a></label><label for="__tabbed_2_2"><a href="#__tabbed_2_2" tabindex="-1">C++</a></label><label for="__tabbed_2_3"><a href="#__tabbed_2_3" tabindex="-1">Java</a></label><label for="__tabbed_2_4"><a href="#__tabbed_2_4" tabindex="-1">C#</a></label><label for="__tabbed_2_5"><a href="#__tabbed_2_5" tabindex="-1">Go</a></label><label for="__tabbed_2_6"><a href="#__tabbed_2_6" tabindex="-1">Swift</a></label><label for="__tabbed_2_7"><a href="#__tabbed_2_7" tabindex="-1">JS</a></label><label for="__tabbed_2_8"><a href="#__tabbed_2_8" tabindex="-1">TS</a></label><label for="__tabbed_2_9"><a href="#__tabbed_2_9" tabindex="-1">Dart</a></label><label for="__tabbed_2_10"><a href="#__tabbed_2_10" tabindex="-1">Rust</a></label><label for="__tabbed_2_11"><a href="#__tabbed_2_11" tabindex="-1">C</a></label><label for="__tabbed_2_12"><a href="#__tabbed_2_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_2_13"><a href="#__tabbed_2_13" tabindex="-1">Ruby</a></label><label for="__tabbed_2_14"><a href="#__tabbed_2_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.py</span><pre id="__code_14"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_14 > code"></button><code><a id="__codelineno-14-1" name="__codelineno-14-1" href="#__codelineno-14-1"></a><span class="k">def</span> <span class="nf">random_access</span><span class="p">(</span><span class="n">nums</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">])</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-14-2" name="__codelineno-14-2" href="#__codelineno-14-2"></a><span class="w">    </span><span class="sd">"""随机访问元素"""</span>
<a id="__codelineno-14-3" name="__codelineno-14-3" href="#__codelineno-14-3"></a>    <span class="c1"># 在区间 [0, len(nums)-1] 中随机抽取一个数字</span>
<a id="__codelineno-14-4" name="__codelineno-14-4" href="#__codelineno-14-4"></a>    <span class="n">random_index</span> <span class="o">=</span> <span class="n">random</span><span class="o">.</span><span class="n">randint</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">nums</span><span class="p">)</span> <span class="o">-</span> <span class="mi">1</span><span class="p">)</span>
<a id="__codelineno-14-5" name="__codelineno-14-5" href="#__codelineno-14-5"></a>    <span class="c1"># 获取并返回随机元素</span>
<a id="__codelineno-14-6" name="__codelineno-14-6" href="#__codelineno-14-6"></a>    <span class="n">random_num</span> <span class="o">=</span> <span class="n">nums</span><span class="p">[</span><span class="n">random_index</span><span class="p">]</span>
<a id="__codelineno-14-7" name="__codelineno-14-7" href="#__codelineno-14-7"></a>    <span class="k">return</span> <span class="n">random_num</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.cpp</span><pre id="__code_15"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_15 > code"></button><code><a id="__codelineno-15-1" name="__codelineno-15-1" href="#__codelineno-15-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-15-2" name="__codelineno-15-2" href="#__codelineno-15-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">randomAccess</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="o">*</span><span class="n">nums</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-15-3" name="__codelineno-15-3" href="#__codelineno-15-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, size) 中随机抽取一个数字</span>
<a id="__codelineno-15-4" name="__codelineno-15-4" href="#__codelineno-15-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">rand</span><span class="p">()</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">size</span><span class="p">;</span>
<a id="__codelineno-15-5" name="__codelineno-15-5" href="#__codelineno-15-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-15-6" name="__codelineno-15-6" href="#__codelineno-15-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">];</span>
<a id="__codelineno-15-7" name="__codelineno-15-7" href="#__codelineno-15-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-15-8" name="__codelineno-15-8" href="#__codelineno-15-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.java</span><pre id="__code_16"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_16 > code"></button><code><a id="__codelineno-16-1" name="__codelineno-16-1" href="#__codelineno-16-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-16-2" name="__codelineno-16-2" href="#__codelineno-16-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">randomAccess</span><span class="p">(</span><span class="kt">int</span><span class="o">[]</span><span class="w"> </span><span class="n">nums</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-16-3" name="__codelineno-16-3" href="#__codelineno-16-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-16-4" name="__codelineno-16-4" href="#__codelineno-16-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ThreadLocalRandom</span><span class="p">.</span><span class="na">current</span><span class="p">().</span><span class="na">nextInt</span><span class="p">(</span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">nums</span><span class="p">.</span><span class="na">length</span><span class="p">);</span>
<a id="__codelineno-16-5" name="__codelineno-16-5" href="#__codelineno-16-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-16-6" name="__codelineno-16-6" href="#__codelineno-16-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="o">[</span><span class="n">randomIndex</span><span class="o">]</span><span class="p">;</span>
<a id="__codelineno-16-7" name="__codelineno-16-7" href="#__codelineno-16-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-16-8" name="__codelineno-16-8" href="#__codelineno-16-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.cs</span><pre id="__code_17"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_17 > code"></button><code><a id="__codelineno-17-1" name="__codelineno-17-1" href="#__codelineno-17-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-17-2" name="__codelineno-17-2" href="#__codelineno-17-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">RandomAccess</span><span class="p">(</span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="n">nums</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-17-3" name="__codelineno-17-3" href="#__codelineno-17-3"></a><span class="w">    </span><span class="n">Random</span><span class="w"> </span><span class="n">random</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="p">();</span>
<a id="__codelineno-17-4" name="__codelineno-17-4" href="#__codelineno-17-4"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.Length) 中随机抽取一个数字</span>
<a id="__codelineno-17-5" name="__codelineno-17-5" href="#__codelineno-17-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">random</span><span class="p">.</span><span class="n">Next</span><span class="p">(</span><span class="n">nums</span><span class="p">.</span><span class="n">Length</span><span class="p">);</span>
<a id="__codelineno-17-6" name="__codelineno-17-6" href="#__codelineno-17-6"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-17-7" name="__codelineno-17-7" href="#__codelineno-17-7"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">];</span>
<a id="__codelineno-17-8" name="__codelineno-17-8" href="#__codelineno-17-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-17-9" name="__codelineno-17-9" href="#__codelineno-17-9"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.go</span><pre id="__code_18"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_18 > code"></button><code><a id="__codelineno-18-1" name="__codelineno-18-1" href="#__codelineno-18-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-18-2" name="__codelineno-18-2" href="#__codelineno-18-2"></a><span class="kd">func</span><span class="w"> </span><span class="nx">randomAccess</span><span class="p">(</span><span class="nx">nums</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">(</span><span class="nx">randomNum</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-18-3" name="__codelineno-18-3" href="#__codelineno-18-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-18-4" name="__codelineno-18-4" href="#__codelineno-18-4"></a><span class="w">    </span><span class="nx">randomIndex</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">rand</span><span class="p">.</span><span class="nx">Intn</span><span class="p">(</span><span class="nb">len</span><span class="p">(</span><span class="nx">nums</span><span class="p">))</span>
<a id="__codelineno-18-5" name="__codelineno-18-5" href="#__codelineno-18-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-18-6" name="__codelineno-18-6" href="#__codelineno-18-6"></a><span class="w">    </span><span class="nx">randomNum</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">nums</span><span class="p">[</span><span class="nx">randomIndex</span><span class="p">]</span>
<a id="__codelineno-18-7" name="__codelineno-18-7" href="#__codelineno-18-7"></a><span class="w">    </span><span class="k">return</span>
<a id="__codelineno-18-8" name="__codelineno-18-8" href="#__codelineno-18-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.swift</span><pre id="__code_19"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_19 > code"></button><code><a id="__codelineno-19-1" name="__codelineno-19-1" href="#__codelineno-19-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-19-2" name="__codelineno-19-2" href="#__codelineno-19-2"></a><span class="kd">func</span> <span class="nf">randomAccess</span><span class="p">(</span><span class="n">nums</span><span class="p">:</span> <span class="p">[</span><span class="nb">Int</span><span class="p">])</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-19-3" name="__codelineno-19-3" href="#__codelineno-19-3"></a>    <span class="c1">// 在区间 [0, nums.count) 中随机抽取一个数字</span>
<a id="__codelineno-19-4" name="__codelineno-19-4" href="#__codelineno-19-4"></a>    <span class="kd">let</span> <span class="nv">randomIndex</span> <span class="p">=</span> <span class="n">nums</span><span class="p">.</span><span class="bp">indices</span><span class="p">.</span><span class="n">randomElement</span><span class="p">()</span><span class="o">!</span>
<a id="__codelineno-19-5" name="__codelineno-19-5" href="#__codelineno-19-5"></a>    <span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-19-6" name="__codelineno-19-6" href="#__codelineno-19-6"></a>    <span class="kd">let</span> <span class="nv">randomNum</span> <span class="p">=</span> <span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">]</span>
<a id="__codelineno-19-7" name="__codelineno-19-7" href="#__codelineno-19-7"></a>    <span class="k">return</span> <span class="n">randomNum</span>
<a id="__codelineno-19-8" name="__codelineno-19-8" href="#__codelineno-19-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.js</span><pre id="__code_20"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_20 > code"></button><code><a id="__codelineno-20-1" name="__codelineno-20-1" href="#__codelineno-20-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-20-2" name="__codelineno-20-2" href="#__codelineno-20-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">randomAccess</span><span class="p">(</span><span class="nx">nums</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-20-3" name="__codelineno-20-3" href="#__codelineno-20-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-20-4" name="__codelineno-20-4" href="#__codelineno-20-4"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">random_index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">floor</span><span class="p">(</span><span class="nb">Math</span><span class="p">.</span><span class="nx">random</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">nums</span><span class="p">.</span><span class="nx">length</span><span class="p">);</span>
<a id="__codelineno-20-5" name="__codelineno-20-5" href="#__codelineno-20-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-20-6" name="__codelineno-20-6" href="#__codelineno-20-6"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">random_num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">nums</span><span class="p">[</span><span class="nx">random_index</span><span class="p">];</span>
<a id="__codelineno-20-7" name="__codelineno-20-7" href="#__codelineno-20-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">random_num</span><span class="p">;</span>
<a id="__codelineno-20-8" name="__codelineno-20-8" href="#__codelineno-20-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.ts</span><pre id="__code_21"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_21 > code"></button><code><a id="__codelineno-21-1" name="__codelineno-21-1" href="#__codelineno-21-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-21-2" name="__codelineno-21-2" href="#__codelineno-21-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">randomAccess</span><span class="p">(</span><span class="nx">nums</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">[])</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-21-3" name="__codelineno-21-3" href="#__codelineno-21-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-21-4" name="__codelineno-21-4" href="#__codelineno-21-4"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">random_index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">floor</span><span class="p">(</span><span class="nb">Math</span><span class="p">.</span><span class="nx">random</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">nums</span><span class="p">.</span><span class="nx">length</span><span class="p">);</span>
<a id="__codelineno-21-5" name="__codelineno-21-5" href="#__codelineno-21-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-21-6" name="__codelineno-21-6" href="#__codelineno-21-6"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">random_num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">nums</span><span class="p">[</span><span class="nx">random_index</span><span class="p">];</span>
<a id="__codelineno-21-7" name="__codelineno-21-7" href="#__codelineno-21-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">random_num</span><span class="p">;</span>
<a id="__codelineno-21-8" name="__codelineno-21-8" href="#__codelineno-21-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.dart</span><pre id="__code_22"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_22 > code"></button><code><a id="__codelineno-22-1" name="__codelineno-22-1" href="#__codelineno-22-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-22-2" name="__codelineno-22-2" href="#__codelineno-22-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">randomAccess</span><span class="p">(</span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">nums</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-22-3" name="__codelineno-22-3" href="#__codelineno-22-3"></a><span class="w">  </span><span class="c1">// 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-22-4" name="__codelineno-22-4" href="#__codelineno-22-4"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Random</span><span class="p">().</span><span class="n">nextInt</span><span class="p">(</span><span class="n">nums</span><span class="p">.</span><span class="n">length</span><span class="p">);</span>
<a id="__codelineno-22-5" name="__codelineno-22-5" href="#__codelineno-22-5"></a><span class="w">  </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-22-6" name="__codelineno-22-6" href="#__codelineno-22-6"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">];</span>
<a id="__codelineno-22-7" name="__codelineno-22-7" href="#__codelineno-22-7"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-22-8" name="__codelineno-22-8" href="#__codelineno-22-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.rs</span><pre id="__code_23"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_23 > code"></button><code><a id="__codelineno-23-1" name="__codelineno-23-1" href="#__codelineno-23-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-23-2" name="__codelineno-23-2" href="#__codelineno-23-2"></a><span class="k">fn</span> <span class="nf">random_access</span><span class="p">(</span><span class="n">nums</span>: <span class="kp">&amp;</span><span class="p">[</span><span class="kt">i32</span><span class="p">])</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-23-3" name="__codelineno-23-3" href="#__codelineno-23-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.len()) 中随机抽取一个数字</span>
<a id="__codelineno-23-4" name="__codelineno-23-4" href="#__codelineno-23-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">random_index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">rand</span>::<span class="n">thread_rng</span><span class="p">().</span><span class="n">gen_range</span><span class="p">(</span><span class="mi">0</span><span class="o">..</span><span class="n">nums</span><span class="p">.</span><span class="n">len</span><span class="p">());</span>
<a id="__codelineno-23-5" name="__codelineno-23-5" href="#__codelineno-23-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-23-6" name="__codelineno-23-6" href="#__codelineno-23-6"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="n">random_num</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">random_index</span><span class="p">];</span>
<a id="__codelineno-23-7" name="__codelineno-23-7" href="#__codelineno-23-7"></a><span class="w">    </span><span class="n">random_num</span>
<a id="__codelineno-23-8" name="__codelineno-23-8" href="#__codelineno-23-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.c</span><pre id="__code_24"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_24 > code"></button><code><a id="__codelineno-24-1" name="__codelineno-24-1" href="#__codelineno-24-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-24-2" name="__codelineno-24-2" href="#__codelineno-24-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">randomAccess</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="o">*</span><span class="n">nums</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-24-3" name="__codelineno-24-3" href="#__codelineno-24-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, size) 中随机抽取一个数字</span>
<a id="__codelineno-24-4" name="__codelineno-24-4" href="#__codelineno-24-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">rand</span><span class="p">()</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">size</span><span class="p">;</span>
<a id="__codelineno-24-5" name="__codelineno-24-5" href="#__codelineno-24-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-24-6" name="__codelineno-24-6" href="#__codelineno-24-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">];</span>
<a id="__codelineno-24-7" name="__codelineno-24-7" href="#__codelineno-24-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-24-8" name="__codelineno-24-8" href="#__codelineno-24-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.kt</span><pre id="__code_25"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_25 > code"></button><code><a id="__codelineno-25-1" name="__codelineno-25-1" href="#__codelineno-25-1"></a><span class="cm">/* 随机访问元素 */</span>
<a id="__codelineno-25-2" name="__codelineno-25-2" href="#__codelineno-25-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">randomAccess</span><span class="p">(</span><span class="n">nums</span><span class="p">:</span><span class="w"> </span><span class="n">IntArray</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-25-3" name="__codelineno-25-3" href="#__codelineno-25-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.size) 中随机抽取一个数字</span>
<a id="__codelineno-25-4" name="__codelineno-25-4" href="#__codelineno-25-4"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ThreadLocalRandom</span><span class="p">.</span><span class="na">current</span><span class="p">().</span><span class="na">nextInt</span><span class="p">(</span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">nums</span><span class="p">.</span><span class="na">size</span><span class="p">)</span>
<a id="__codelineno-25-5" name="__codelineno-25-5" href="#__codelineno-25-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-25-6" name="__codelineno-25-6" href="#__codelineno-25-6"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="o">[</span><span class="n">randomIndex</span><span class="o">]</span>
<a id="__codelineno-25-7" name="__codelineno-25-7" href="#__codelineno-25-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span>
<a id="__codelineno-25-8" name="__codelineno-25-8" href="#__codelineno-25-8"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.rb</span><pre id="__code_26"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_26 > code"></button><code><a id="__codelineno-26-1" name="__codelineno-26-1" href="#__codelineno-26-1"></a><span class="c1">### 随机访问元素 ###</span>
<a id="__codelineno-26-2" name="__codelineno-26-2" href="#__codelineno-26-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">random_access</span><span class="p">(</span><span class="n">nums</span><span class="p">)</span>
<a id="__codelineno-26-3" name="__codelineno-26-3" href="#__codelineno-26-3"></a><span class="w">  </span><span class="c1"># 在区间 [0, nums.length) 中随机抽取一个数字</span>
<a id="__codelineno-26-4" name="__codelineno-26-4" href="#__codelineno-26-4"></a><span class="w">  </span><span class="n">random_index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="no">Random</span><span class="o">.</span><span class="n">rand</span><span class="p">(</span><span class="mi">0</span><span class="o">...</span><span class="n">nums</span><span class="o">.</span><span class="n">length</span><span class="p">)</span>
<a id="__codelineno-26-5" name="__codelineno-26-5" href="#__codelineno-26-5"></a>
<a id="__codelineno-26-6" name="__codelineno-26-6" href="#__codelineno-26-6"></a><span class="w">  </span><span class="c1"># 获取并返回随机元素</span>
<a id="__codelineno-26-7" name="__codelineno-26-7" href="#__codelineno-26-7"></a><span class="w">  </span><span class="n">nums</span><span class="o">[</span><span class="n">random_index</span><span class="o">]</span>
<a id="__codelineno-26-8" name="__codelineno-26-8" href="#__codelineno-26-8"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array.zig</span><pre id="__code_27"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_27 > code"></button><code><a id="__codelineno-27-1" name="__codelineno-27-1" href="#__codelineno-27-1"></a><span class="c1">// 随机访问元素</span>
<a id="__codelineno-27-2" name="__codelineno-27-2" href="#__codelineno-27-2"></a><span class="k">fn</span><span class="w"> </span><span class="n">randomAccess</span><span class="p">(</span><span class="n">nums</span><span class="o">:</span><span class="w"> </span><span class="p">[]</span><span class="kt">i32</span><span class="p">)</span><span class="w"> </span><span class="kt">i32</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-27-3" name="__codelineno-27-3" href="#__codelineno-27-3"></a><span class="w">    </span><span class="c1">// 在区间 [0, nums.len) 中随机抽取一个整数</span>
<a id="__codelineno-27-4" name="__codelineno-27-4" href="#__codelineno-27-4"></a><span class="w">    </span><span class="kr">var</span><span class="w"> </span><span class="n">randomIndex</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">crypto</span><span class="p">.</span><span class="n">random</span><span class="p">.</span><span class="n">intRangeLessThan</span><span class="p">(</span><span class="kt">usize</span><span class="p">,</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">nums</span><span class="p">.</span><span class="n">len</span><span class="p">);</span>
<a id="__codelineno-27-5" name="__codelineno-27-5" href="#__codelineno-27-5"></a><span class="w">    </span><span class="c1">// 获取并返回随机元素</span>
<a id="__codelineno-27-6" name="__codelineno-27-6" href="#__codelineno-27-6"></a><span class="w">    </span><span class="kr">var</span><span class="w"> </span><span class="n">randomNum</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">nums</span><span class="p">[</span><span class="n">randomIndex</span><span class="p">];</span>
<a id="__codelineno-27-7" name="__codelineno-27-7" href="#__codelineno-27-7"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">randomNum</span><span class="p">;</span>
<a id="__codelineno-27-8" name="__codelineno-27-8" href="#__codelineno-27-8"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>

### 插入元素

数组元素在内存中是“紧挨着的”，它们之间没有空间再存放任何数据。如下图所示，如果想要在数组中间插入一个元素，则需要将该元素之后的所有元素都向后移动一位，之后再把元素赋值给该索引。

![数组插入元素示例](array.assets/array_insert_element.png)

值得注意的是，由于数组的长度是固定的，因此插入一个元素必定会导致数组尾部元素的“丢失”。我们将这个问题的解决方案留在列表章节中讨论。

```src
[file]{array}-[class]{}-[func]{insert}
```

### 删除元素

同理，如下图所示，若想要删除索引 $i$ 处的元素，则需要把索引 $i$ 之后的元素都向前移动一位。

![数组删除元素示例](array.assets/array_remove_element.png)

请注意，删除元素完成后，原先末尾的元素变得“无意义”了，所以我们无须特意去修改它。

```src
[file]{array}-[class]{}-[func]{remove}
```

总的来看，数组的插入与删除操作有以下缺点。

- **时间复杂度高**：数组的插入和删除的平均时间复杂度均为 $O(n)$ ，其中 $n$ 为数组长度。
- **丢失元素**：由于数组的长度不可变，因此在插入元素后，超出数组长度范围的元素会丢失。
- **内存浪费**：我们可以初始化一个比较长的数组，只用前面一部分，这样在插入数据时，丢失的末尾元素都是“无意义”的，但这样做也会造成部分内存空间的浪费。

### 遍历数组

在大多数编程语言中，我们既可以通过索引遍历数组，也可以直接遍历获取数组中的每个元素。

```src
[file]{array}-[class]{}-[func]{traverse}
```

### 查找元素

在数组中查找指定元素需要遍历数组，每轮判断元素值是否匹配，若匹配则输出对应索引。

因为数组是线性数据结构，所以上述查找操作被称为“线性查找”。

```src
[file]{array}-[class]{}-[func]{find}
```

### 扩容数组

在复杂的系统环境中，程序难以保证数组之后的内存空间是可用的，从而无法安全地扩展数组容量。因此在大多数编程语言中，**数组的长度是不可变的**。

如果我们希望扩容数组，则需重新建立一个更大的数组，然后把原数组元素依次拷贝到新数组。这是一个 $O(n)$ 的操作，在数组很大的情况下是非常耗时的。

```src
[file]{array}-[class]{}-[func]{extend}
```

## 数组优点与局限性

数组存储在连续的内存空间内，且元素类型相同。这种做法包含丰富的先验信息，系统可以利用这些信息来优化数据结构的操作效率。

- **空间效率高**: 数组为数据分配了连续的内存块，无须额外的结构开销。
- **支持随机访问**: 数组允许在 $O(1)$ 时间内访问任何元素。
- **缓存局部性**: 当访问数组元素时，计算机不仅会加载它，还会缓存其周围的其他数据，从而借助高速缓存来提升后续操作的执行速度。

连续空间存储是一把双刃剑，其存在以下缺点。

- **插入与删除效率低**:当数组中元素较多时，插入与删除操作需要移动大量的元素。
- **长度不可变**: 数组在初始化后长度就固定了，扩容数组需要将所有数据复制到新数组，开销很大。
- **空间浪费**: 如果数组分配的大小超过了实际所需，那么多余的空间就被浪费了。

## 数组典型应用

数组是一种基础且常见的数据结构，既频繁应用在各类算法之中，也可用于实现各种复杂数据结构。

- **随机访问**：如果我们想要随机抽取一些样本，那么可以用数组存储，并生成一个随机序列，根据索引实现样本的随机抽取。
- **排序和搜索**：数组是排序和搜索算法最常用的数据结构。快速排序、归并排序、二分查找等都主要在数组上进行。
- **查找表**：当我们需要快速查找一个元素或者需要查找一个元素的对应关系时，可以使用数组作为查找表。假如我们想要实现字符到 ASCII 码的映射，则可以将字符的 ASCII 码值作为索引，对应的元素存放在数组中的对应位置。
- **机器学习**：神经网络中大量使用了向量、矩阵、张量之间的线性代数运算，这些数据都是以数组的形式构建的。数组是神经网络编程中最常使用的数据结构。
- **数据结构实现**：数组可以用于实现栈、队列、哈希表、堆、图等数据结构。例如，图的邻接矩阵表示实际上是一个二维数组。
