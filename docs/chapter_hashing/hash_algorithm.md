# 哈希算法

在上两节中，我们了解了哈希表的工作原理和哈希冲突的处理方法。然而无论是开放寻址还是链地址法，**它们只能保证哈希表可以在发生冲突时正常工作，但无法减少哈希冲突的发生**。

如果哈希冲突过于频繁，哈希表的性能则会急剧劣化。如下图所示，对于链地址哈希表，理想情况下键值对平均分布在各个桶中，达到最佳查询效率；最差情况下所有键值对都被存储到同一个桶中，时间复杂度退化至 $O(n)$ 。

![哈希冲突的最佳与最差情况](hash_algorithm.assets/hash_collision_best_worst_condition.png)

**键值对的分布情况由哈希函数决定**。回忆哈希函数的计算步骤，先计算哈希值，再对数组长度取模：

```shell
index = hash(key) % capacity
```

观察以上公式，当哈希表容量 `capacity` 固定时，**哈希算法 `hash()` 决定了输出值**，进而决定了键值对在哈希表中的分布情况。

这意味着，为了减小哈希冲突的发生概率，我们应当将注意力集中在哈希算法 `hash()` 的设计上。

## 哈希算法的目标

为了实现“既快又稳”的哈希表数据结构，哈希算法应包含以下特点。

- **确定性**：对于相同的输入，哈希算法应始终产生相同的输出。这样才能确保哈希表是可靠的。
- **效率高**：计算哈希值的过程应该足够快。计算开销越小，哈希表的实用性越高。
- **均匀分布**：哈希算法应使得键值对平均分布在哈希表中。分布越平均，哈希冲突的概率就越低。

实际上，哈希算法除了可以用于实现哈希表，还广泛应用于其他领域中。

- **密码存储**：为了保护用户密码的安全，系统通常不会直接存储用户的明文密码，而是存储密码的哈希值。当用户输入密码时，系统会对输入的密码计算哈希值，然后与存储的哈希值进行比较。如果两者匹配，那么密码就被视为正确。
- **数据完整性检查**：数据发送方可以计算数据的哈希值并将其一同发送；接收方可以重新计算接收到的数据的哈希值，并与接收到的哈希值进行比较。如果两者匹配，那么数据就被视为完整的。

对于密码学的相关应用，为了防止从哈希值推导出原始密码等逆向工程，哈希算法需要具备更高等级的安全特性。

- **单向性**：无法通过哈希值反推出关于输入数据的任何信息。
- **抗碰撞性**：应当极其困难找到两个不同的输入，使得它们的哈希值相同。
- **雪崩效应**：输入的微小变化应当导致输出的显著且不可预测的变化。

请注意，**“均匀分布”与“抗碰撞性”是两个独立的概念**，满足均匀分布不一定满足抗碰撞性。例如，在随机输入 `key` 下，哈希函数 `key % 100` 可以产生均匀分布的输出。然而该哈希算法过于简单，所有后两位相等的 `key` 的输出都相同，因此我们可以很容易地从哈希值反推出可用的 `key` ，从而破解密码。

## 哈希算法的设计

哈希算法的设计是一个需要考虑许多因素的复杂问题。然而对于某些要求不高的场景，我们也能设计一些简单的哈希算法。

- **加法哈希**：对输入的每个字符的 ASCII 码进行相加，将得到的总和作为哈希值。
- **乘法哈希**：利用了乘法的不相关性，每轮乘以一个常数，将各个字符的 ASCII 码累积到哈希值中。
- **异或哈希**：将输入数据的每个元素通过异或操作累积到一个哈希值中。
- **旋转哈希**：将每个字符的 ASCII 码累积到一个哈希值中，每次累积之前都会对哈希值进行旋转操作。

<div class="tabbed-set tabbed-alternate" data-tabs="1:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_1_1" name="__tabbed_1" type="radio"><input id="__tabbed_1_2" name="__tabbed_1" type="radio"><input id="__tabbed_1_3" name="__tabbed_1" type="radio"><input id="__tabbed_1_4" name="__tabbed_1" type="radio"><input id="__tabbed_1_5" name="__tabbed_1" type="radio"><input id="__tabbed_1_6" name="__tabbed_1" type="radio"><input id="__tabbed_1_7" name="__tabbed_1" type="radio"><input id="__tabbed_1_8" name="__tabbed_1" type="radio"><input id="__tabbed_1_9" name="__tabbed_1" type="radio"><input id="__tabbed_1_10" name="__tabbed_1" type="radio"><input id="__tabbed_1_11" name="__tabbed_1" type="radio"><input id="__tabbed_1_12" name="__tabbed_1" type="radio"><input id="__tabbed_1_13" name="__tabbed_1" type="radio"><input id="__tabbed_1_14" name="__tabbed_1" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_1_1"><a href="#__tabbed_1_1" tabindex="-1">Python</a></label><label for="__tabbed_1_2"><a href="#__tabbed_1_2" tabindex="-1">C++</a></label><label for="__tabbed_1_3"><a href="#__tabbed_1_3" tabindex="-1">Java</a></label><label for="__tabbed_1_4"><a href="#__tabbed_1_4" tabindex="-1">C#</a></label><label for="__tabbed_1_5"><a href="#__tabbed_1_5" tabindex="-1">Go</a></label><label for="__tabbed_1_6"><a href="#__tabbed_1_6" tabindex="-1">Swift</a></label><label for="__tabbed_1_7"><a href="#__tabbed_1_7" tabindex="-1">JS</a></label><label for="__tabbed_1_8"><a href="#__tabbed_1_8" tabindex="-1">TS</a></label><label for="__tabbed_1_9"><a href="#__tabbed_1_9" tabindex="-1">Dart</a></label><label for="__tabbed_1_10"><a href="#__tabbed_1_10" tabindex="-1">Rust</a></label><label for="__tabbed_1_11"><a href="#__tabbed_1_11" tabindex="-1">C</a></label><label for="__tabbed_1_12"><a href="#__tabbed_1_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_1_13"><a href="#__tabbed_1_13" tabindex="-1">Ruby</a></label><label for="__tabbed_1_14"><a href="#__tabbed_1_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.py</span><pre id="__code_1"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_1 > code"></button><code><a id="__codelineno-1-1" name="__codelineno-1-1" href="#__codelineno-1-1"></a><span class="k">def</span> <span class="nf">add_hash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">str</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-1-2" name="__codelineno-1-2" href="#__codelineno-1-2"></a><span class="w">    </span><span class="sd">"""加法哈希"""</span>
<a id="__codelineno-1-3" name="__codelineno-1-3" href="#__codelineno-1-3"></a>    <span class="nb">hash</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-1-4" name="__codelineno-1-4" href="#__codelineno-1-4"></a>    <span class="n">modulus</span> <span class="o">=</span> <span class="mi">1000000007</span>
<a id="__codelineno-1-5" name="__codelineno-1-5" href="#__codelineno-1-5"></a>    <span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">key</span><span class="p">:</span>
<a id="__codelineno-1-6" name="__codelineno-1-6" href="#__codelineno-1-6"></a>        <span class="nb">hash</span> <span class="o">+=</span> <span class="nb">ord</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<a id="__codelineno-1-7" name="__codelineno-1-7" href="#__codelineno-1-7"></a>    <span class="k">return</span> <span class="nb">hash</span> <span class="o">%</span> <span class="n">modulus</span>
<a id="__codelineno-1-8" name="__codelineno-1-8" href="#__codelineno-1-8"></a>
<a id="__codelineno-1-9" name="__codelineno-1-9" href="#__codelineno-1-9"></a><span class="k">def</span> <span class="nf">mul_hash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">str</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-1-10" name="__codelineno-1-10" href="#__codelineno-1-10"></a><span class="w">    </span><span class="sd">"""乘法哈希"""</span>
<a id="__codelineno-1-11" name="__codelineno-1-11" href="#__codelineno-1-11"></a>    <span class="nb">hash</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-1-12" name="__codelineno-1-12" href="#__codelineno-1-12"></a>    <span class="n">modulus</span> <span class="o">=</span> <span class="mi">1000000007</span>
<a id="__codelineno-1-13" name="__codelineno-1-13" href="#__codelineno-1-13"></a>    <span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">key</span><span class="p">:</span>
<a id="__codelineno-1-14" name="__codelineno-1-14" href="#__codelineno-1-14"></a>        <span class="nb">hash</span> <span class="o">=</span> <span class="mi">31</span> <span class="o">*</span> <span class="nb">hash</span> <span class="o">+</span> <span class="nb">ord</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<a id="__codelineno-1-15" name="__codelineno-1-15" href="#__codelineno-1-15"></a>    <span class="k">return</span> <span class="nb">hash</span> <span class="o">%</span> <span class="n">modulus</span>
<a id="__codelineno-1-16" name="__codelineno-1-16" href="#__codelineno-1-16"></a>
<a id="__codelineno-1-17" name="__codelineno-1-17" href="#__codelineno-1-17"></a><span class="k">def</span> <span class="nf">xor_hash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">str</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-1-18" name="__codelineno-1-18" href="#__codelineno-1-18"></a><span class="w">    </span><span class="sd">"""异或哈希"""</span>
<a id="__codelineno-1-19" name="__codelineno-1-19" href="#__codelineno-1-19"></a>    <span class="nb">hash</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-1-20" name="__codelineno-1-20" href="#__codelineno-1-20"></a>    <span class="n">modulus</span> <span class="o">=</span> <span class="mi">1000000007</span>
<a id="__codelineno-1-21" name="__codelineno-1-21" href="#__codelineno-1-21"></a>    <span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">key</span><span class="p">:</span>
<a id="__codelineno-1-22" name="__codelineno-1-22" href="#__codelineno-1-22"></a>        <span class="nb">hash</span> <span class="o">^=</span> <span class="nb">ord</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<a id="__codelineno-1-23" name="__codelineno-1-23" href="#__codelineno-1-23"></a>    <span class="k">return</span> <span class="nb">hash</span> <span class="o">%</span> <span class="n">modulus</span>
<a id="__codelineno-1-24" name="__codelineno-1-24" href="#__codelineno-1-24"></a>
<a id="__codelineno-1-25" name="__codelineno-1-25" href="#__codelineno-1-25"></a><span class="k">def</span> <span class="nf">rot_hash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">str</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-1-26" name="__codelineno-1-26" href="#__codelineno-1-26"></a><span class="w">    </span><span class="sd">"""旋转哈希"""</span>
<a id="__codelineno-1-27" name="__codelineno-1-27" href="#__codelineno-1-27"></a>    <span class="nb">hash</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-1-28" name="__codelineno-1-28" href="#__codelineno-1-28"></a>    <span class="n">modulus</span> <span class="o">=</span> <span class="mi">1000000007</span>
<a id="__codelineno-1-29" name="__codelineno-1-29" href="#__codelineno-1-29"></a>    <span class="k">for</span> <span class="n">c</span> <span class="ow">in</span> <span class="n">key</span><span class="p">:</span>
<a id="__codelineno-1-30" name="__codelineno-1-30" href="#__codelineno-1-30"></a>        <span class="nb">hash</span> <span class="o">=</span> <span class="p">(</span><span class="nb">hash</span> <span class="o">&lt;&lt;</span> <span class="mi">4</span><span class="p">)</span> <span class="o">^</span> <span class="p">(</span><span class="nb">hash</span> <span class="o">&gt;&gt;</span> <span class="mi">28</span><span class="p">)</span> <span class="o">^</span> <span class="nb">ord</span><span class="p">(</span><span class="n">c</span><span class="p">)</span>
<a id="__codelineno-1-31" name="__codelineno-1-31" href="#__codelineno-1-31"></a>    <span class="k">return</span> <span class="nb">hash</span> <span class="o">%</span> <span class="n">modulus</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.cpp</span><pre id="__code_2"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_2 > code"></button><code><a id="__codelineno-2-1" name="__codelineno-2-1" href="#__codelineno-2-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-2-2" name="__codelineno-2-2" href="#__codelineno-2-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">addHash</span><span class="p">(</span><span class="n">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-3" name="__codelineno-2-3" href="#__codelineno-2-3"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-4" name="__codelineno-2-4" href="#__codelineno-2-4"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-2-5" name="__codelineno-2-5" href="#__codelineno-2-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-6" name="__codelineno-2-6" href="#__codelineno-2-6"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-2-7" name="__codelineno-2-7" href="#__codelineno-2-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-8" name="__codelineno-2-8" href="#__codelineno-2-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-2-9" name="__codelineno-2-9" href="#__codelineno-2-9"></a><span class="p">}</span>
<a id="__codelineno-2-10" name="__codelineno-2-10" href="#__codelineno-2-10"></a>
<a id="__codelineno-2-11" name="__codelineno-2-11" href="#__codelineno-2-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-2-12" name="__codelineno-2-12" href="#__codelineno-2-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">mulHash</span><span class="p">(</span><span class="n">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-13" name="__codelineno-2-13" href="#__codelineno-2-13"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-14" name="__codelineno-2-14" href="#__codelineno-2-14"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-2-15" name="__codelineno-2-15" href="#__codelineno-2-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-16" name="__codelineno-2-16" href="#__codelineno-2-16"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-2-17" name="__codelineno-2-17" href="#__codelineno-2-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-18" name="__codelineno-2-18" href="#__codelineno-2-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-2-19" name="__codelineno-2-19" href="#__codelineno-2-19"></a><span class="p">}</span>
<a id="__codelineno-2-20" name="__codelineno-2-20" href="#__codelineno-2-20"></a>
<a id="__codelineno-2-21" name="__codelineno-2-21" href="#__codelineno-2-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-2-22" name="__codelineno-2-22" href="#__codelineno-2-22"></a><span class="kt">int</span><span class="w"> </span><span class="nf">xorHash</span><span class="p">(</span><span class="n">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-23" name="__codelineno-2-23" href="#__codelineno-2-23"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-24" name="__codelineno-2-24" href="#__codelineno-2-24"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-2-25" name="__codelineno-2-25" href="#__codelineno-2-25"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-26" name="__codelineno-2-26" href="#__codelineno-2-26"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">c</span><span class="p">;</span>
<a id="__codelineno-2-27" name="__codelineno-2-27" href="#__codelineno-2-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-28" name="__codelineno-2-28" href="#__codelineno-2-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-2-29" name="__codelineno-2-29" href="#__codelineno-2-29"></a><span class="p">}</span>
<a id="__codelineno-2-30" name="__codelineno-2-30" href="#__codelineno-2-30"></a>
<a id="__codelineno-2-31" name="__codelineno-2-31" href="#__codelineno-2-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-2-32" name="__codelineno-2-32" href="#__codelineno-2-32"></a><span class="kt">int</span><span class="w"> </span><span class="nf">rotHash</span><span class="p">(</span><span class="n">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-33" name="__codelineno-2-33" href="#__codelineno-2-33"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-34" name="__codelineno-2-34" href="#__codelineno-2-34"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-2-35" name="__codelineno-2-35" href="#__codelineno-2-35"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-36" name="__codelineno-2-36" href="#__codelineno-2-36"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-2-37" name="__codelineno-2-37" href="#__codelineno-2-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-38" name="__codelineno-2-38" href="#__codelineno-2-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-2-39" name="__codelineno-2-39" href="#__codelineno-2-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.java</span><pre id="__code_3"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_3 > code"></button><code><a id="__codelineno-3-1" name="__codelineno-3-1" href="#__codelineno-3-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-3-2" name="__codelineno-3-2" href="#__codelineno-3-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">addHash</span><span class="p">(</span><span class="n">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-3" name="__codelineno-3-3" href="#__codelineno-3-3"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-3-4" name="__codelineno-3-4" href="#__codelineno-3-4"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-3-5" name="__codelineno-3-5" href="#__codelineno-3-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-6" name="__codelineno-3-6" href="#__codelineno-3-6"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-3-7" name="__codelineno-3-7" href="#__codelineno-3-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-8" name="__codelineno-3-8" href="#__codelineno-3-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-3-9" name="__codelineno-3-9" href="#__codelineno-3-9"></a><span class="p">}</span>
<a id="__codelineno-3-10" name="__codelineno-3-10" href="#__codelineno-3-10"></a>
<a id="__codelineno-3-11" name="__codelineno-3-11" href="#__codelineno-3-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-3-12" name="__codelineno-3-12" href="#__codelineno-3-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">mulHash</span><span class="p">(</span><span class="n">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-13" name="__codelineno-3-13" href="#__codelineno-3-13"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-3-14" name="__codelineno-3-14" href="#__codelineno-3-14"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-3-15" name="__codelineno-3-15" href="#__codelineno-3-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-16" name="__codelineno-3-16" href="#__codelineno-3-16"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-3-17" name="__codelineno-3-17" href="#__codelineno-3-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-18" name="__codelineno-3-18" href="#__codelineno-3-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-3-19" name="__codelineno-3-19" href="#__codelineno-3-19"></a><span class="p">}</span>
<a id="__codelineno-3-20" name="__codelineno-3-20" href="#__codelineno-3-20"></a>
<a id="__codelineno-3-21" name="__codelineno-3-21" href="#__codelineno-3-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-3-22" name="__codelineno-3-22" href="#__codelineno-3-22"></a><span class="kt">int</span><span class="w"> </span><span class="nf">xorHash</span><span class="p">(</span><span class="n">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-23" name="__codelineno-3-23" href="#__codelineno-3-23"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-3-24" name="__codelineno-3-24" href="#__codelineno-3-24"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-3-25" name="__codelineno-3-25" href="#__codelineno-3-25"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-26" name="__codelineno-3-26" href="#__codelineno-3-26"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">c</span><span class="p">;</span>
<a id="__codelineno-3-27" name="__codelineno-3-27" href="#__codelineno-3-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-28" name="__codelineno-3-28" href="#__codelineno-3-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-3-29" name="__codelineno-3-29" href="#__codelineno-3-29"></a><span class="p">}</span>
<a id="__codelineno-3-30" name="__codelineno-3-30" href="#__codelineno-3-30"></a>
<a id="__codelineno-3-31" name="__codelineno-3-31" href="#__codelineno-3-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-3-32" name="__codelineno-3-32" href="#__codelineno-3-32"></a><span class="kt">int</span><span class="w"> </span><span class="nf">rotHash</span><span class="p">(</span><span class="n">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-33" name="__codelineno-3-33" href="#__codelineno-3-33"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-3-34" name="__codelineno-3-34" href="#__codelineno-3-34"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-3-35" name="__codelineno-3-35" href="#__codelineno-3-35"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-36" name="__codelineno-3-36" href="#__codelineno-3-36"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-3-37" name="__codelineno-3-37" href="#__codelineno-3-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-38" name="__codelineno-3-38" href="#__codelineno-3-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-3-39" name="__codelineno-3-39" href="#__codelineno-3-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.cs</span><pre id="__code_4"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_4 > code"></button><code><a id="__codelineno-4-1" name="__codelineno-4-1" href="#__codelineno-4-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-4-2" name="__codelineno-4-2" href="#__codelineno-4-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">AddHash</span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-3" name="__codelineno-4-3" href="#__codelineno-4-3"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-4-4" name="__codelineno-4-4" href="#__codelineno-4-4"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-4-5" name="__codelineno-4-5" href="#__codelineno-4-5"></a><span class="w">    </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-6" name="__codelineno-4-6" href="#__codelineno-4-6"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-4-7" name="__codelineno-4-7" href="#__codelineno-4-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-8" name="__codelineno-4-8" href="#__codelineno-4-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-4-9" name="__codelineno-4-9" href="#__codelineno-4-9"></a><span class="p">}</span>
<a id="__codelineno-4-10" name="__codelineno-4-10" href="#__codelineno-4-10"></a>
<a id="__codelineno-4-11" name="__codelineno-4-11" href="#__codelineno-4-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-4-12" name="__codelineno-4-12" href="#__codelineno-4-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">MulHash</span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-13" name="__codelineno-4-13" href="#__codelineno-4-13"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-4-14" name="__codelineno-4-14" href="#__codelineno-4-14"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-4-15" name="__codelineno-4-15" href="#__codelineno-4-15"></a><span class="w">    </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-16" name="__codelineno-4-16" href="#__codelineno-4-16"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="m">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-4-17" name="__codelineno-4-17" href="#__codelineno-4-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-18" name="__codelineno-4-18" href="#__codelineno-4-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-4-19" name="__codelineno-4-19" href="#__codelineno-4-19"></a><span class="p">}</span>
<a id="__codelineno-4-20" name="__codelineno-4-20" href="#__codelineno-4-20"></a>
<a id="__codelineno-4-21" name="__codelineno-4-21" href="#__codelineno-4-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-4-22" name="__codelineno-4-22" href="#__codelineno-4-22"></a><span class="kt">int</span><span class="w"> </span><span class="nf">XorHash</span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-23" name="__codelineno-4-23" href="#__codelineno-4-23"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-4-24" name="__codelineno-4-24" href="#__codelineno-4-24"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-4-25" name="__codelineno-4-25" href="#__codelineno-4-25"></a><span class="w">    </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-26" name="__codelineno-4-26" href="#__codelineno-4-26"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="n">c</span><span class="p">;</span>
<a id="__codelineno-4-27" name="__codelineno-4-27" href="#__codelineno-4-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-28" name="__codelineno-4-28" href="#__codelineno-4-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-4-29" name="__codelineno-4-29" href="#__codelineno-4-29"></a><span class="p">}</span>
<a id="__codelineno-4-30" name="__codelineno-4-30" href="#__codelineno-4-30"></a>
<a id="__codelineno-4-31" name="__codelineno-4-31" href="#__codelineno-4-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-4-32" name="__codelineno-4-32" href="#__codelineno-4-32"></a><span class="kt">int</span><span class="w"> </span><span class="nf">RotHash</span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-33" name="__codelineno-4-33" href="#__codelineno-4-33"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-4-34" name="__codelineno-4-34" href="#__codelineno-4-34"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-4-35" name="__codelineno-4-35" href="#__codelineno-4-35"></a><span class="w">    </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-36" name="__codelineno-4-36" href="#__codelineno-4-36"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="m">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="m">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="n">c</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-4-37" name="__codelineno-4-37" href="#__codelineno-4-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-38" name="__codelineno-4-38" href="#__codelineno-4-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-4-39" name="__codelineno-4-39" href="#__codelineno-4-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.go</span><pre id="__code_5"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_5 > code"></button><code><a id="__codelineno-5-1" name="__codelineno-5-1" href="#__codelineno-5-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-5-2" name="__codelineno-5-2" href="#__codelineno-5-2"></a><span class="kd">func</span><span class="w"> </span><span class="nx">addHash</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-3" name="__codelineno-5-3" href="#__codelineno-5-3"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-4" name="__codelineno-5-4" href="#__codelineno-5-4"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">modulus</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-5" name="__codelineno-5-5" href="#__codelineno-5-5"></a>
<a id="__codelineno-5-6" name="__codelineno-5-6" href="#__codelineno-5-6"></a><span class="w">    </span><span class="nx">modulus</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="mi">1000000007</span>
<a id="__codelineno-5-7" name="__codelineno-5-7" href="#__codelineno-5-7"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">b</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="p">[]</span><span class="nb">byte</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-8" name="__codelineno-5-8" href="#__codelineno-5-8"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nb">int64</span><span class="p">(</span><span class="nx">b</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">modulus</span>
<a id="__codelineno-5-9" name="__codelineno-5-9" href="#__codelineno-5-9"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-5-10" name="__codelineno-5-10" href="#__codelineno-5-10"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">hash</span><span class="p">)</span>
<a id="__codelineno-5-11" name="__codelineno-5-11" href="#__codelineno-5-11"></a><span class="p">}</span>
<a id="__codelineno-5-12" name="__codelineno-5-12" href="#__codelineno-5-12"></a>
<a id="__codelineno-5-13" name="__codelineno-5-13" href="#__codelineno-5-13"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-5-14" name="__codelineno-5-14" href="#__codelineno-5-14"></a><span class="kd">func</span><span class="w"> </span><span class="nx">mulHash</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-15" name="__codelineno-5-15" href="#__codelineno-5-15"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-16" name="__codelineno-5-16" href="#__codelineno-5-16"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">modulus</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-17" name="__codelineno-5-17" href="#__codelineno-5-17"></a>
<a id="__codelineno-5-18" name="__codelineno-5-18" href="#__codelineno-5-18"></a><span class="w">    </span><span class="nx">modulus</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="mi">1000000007</span>
<a id="__codelineno-5-19" name="__codelineno-5-19" href="#__codelineno-5-19"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">b</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="p">[]</span><span class="nb">byte</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-20" name="__codelineno-5-20" href="#__codelineno-5-20"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="o">*</span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nb">int64</span><span class="p">(</span><span class="nx">b</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">modulus</span>
<a id="__codelineno-5-21" name="__codelineno-5-21" href="#__codelineno-5-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-5-22" name="__codelineno-5-22" href="#__codelineno-5-22"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">hash</span><span class="p">)</span>
<a id="__codelineno-5-23" name="__codelineno-5-23" href="#__codelineno-5-23"></a><span class="p">}</span>
<a id="__codelineno-5-24" name="__codelineno-5-24" href="#__codelineno-5-24"></a>
<a id="__codelineno-5-25" name="__codelineno-5-25" href="#__codelineno-5-25"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-5-26" name="__codelineno-5-26" href="#__codelineno-5-26"></a><span class="kd">func</span><span class="w"> </span><span class="nx">xorHash</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-27" name="__codelineno-5-27" href="#__codelineno-5-27"></a><span class="w">    </span><span class="nx">hash</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-5-28" name="__codelineno-5-28" href="#__codelineno-5-28"></a><span class="w">    </span><span class="nx">modulus</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="mi">1000000007</span>
<a id="__codelineno-5-29" name="__codelineno-5-29" href="#__codelineno-5-29"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">b</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="p">[]</span><span class="nb">byte</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-30" name="__codelineno-5-30" href="#__codelineno-5-30"></a><span class="w">        </span><span class="nx">fmt</span><span class="p">.</span><span class="nx">Println</span><span class="p">(</span><span class="nb">int</span><span class="p">(</span><span class="nx">b</span><span class="p">))</span>
<a id="__codelineno-5-31" name="__codelineno-5-31" href="#__codelineno-5-31"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="p">^=</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">b</span><span class="p">)</span>
<a id="__codelineno-5-32" name="__codelineno-5-32" href="#__codelineno-5-32"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="o">*</span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">b</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">modulus</span>
<a id="__codelineno-5-33" name="__codelineno-5-33" href="#__codelineno-5-33"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-5-34" name="__codelineno-5-34" href="#__codelineno-5-34"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="nx">modulus</span>
<a id="__codelineno-5-35" name="__codelineno-5-35" href="#__codelineno-5-35"></a><span class="p">}</span>
<a id="__codelineno-5-36" name="__codelineno-5-36" href="#__codelineno-5-36"></a>
<a id="__codelineno-5-37" name="__codelineno-5-37" href="#__codelineno-5-37"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-5-38" name="__codelineno-5-38" href="#__codelineno-5-38"></a><span class="kd">func</span><span class="w"> </span><span class="nx">rotHash</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-39" name="__codelineno-5-39" href="#__codelineno-5-39"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-40" name="__codelineno-5-40" href="#__codelineno-5-40"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">modulus</span><span class="w"> </span><span class="kt">int64</span>
<a id="__codelineno-5-41" name="__codelineno-5-41" href="#__codelineno-5-41"></a>
<a id="__codelineno-5-42" name="__codelineno-5-42" href="#__codelineno-5-42"></a><span class="w">    </span><span class="nx">modulus</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="mi">1000000007</span>
<a id="__codelineno-5-43" name="__codelineno-5-43" href="#__codelineno-5-43"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">b</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="p">[]</span><span class="nb">byte</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-5-44" name="__codelineno-5-44" href="#__codelineno-5-44"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="p">((</span><span class="nx">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="p">^</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="p">^</span><span class="w"> </span><span class="nb">int64</span><span class="p">(</span><span class="nx">b</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">modulus</span>
<a id="__codelineno-5-45" name="__codelineno-5-45" href="#__codelineno-5-45"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-5-46" name="__codelineno-5-46" href="#__codelineno-5-46"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">hash</span><span class="p">)</span>
<a id="__codelineno-5-47" name="__codelineno-5-47" href="#__codelineno-5-47"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.swift</span><pre id="__code_6"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_6 > code"></button><code><a id="__codelineno-6-1" name="__codelineno-6-1" href="#__codelineno-6-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-6-2" name="__codelineno-6-2" href="#__codelineno-6-2"></a><span class="kd">func</span> <span class="nf">addHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-6-3" name="__codelineno-6-3" href="#__codelineno-6-3"></a>    <span class="kd">var</span> <span class="nv">hash</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-6-4" name="__codelineno-6-4" href="#__codelineno-6-4"></a>    <span class="kd">let</span> <span class="nv">MODULUS</span> <span class="p">=</span> <span class="mi">1_000_000_007</span>
<a id="__codelineno-6-5" name="__codelineno-6-5" href="#__codelineno-6-5"></a>    <span class="k">for</span> <span class="n">c</span> <span class="k">in</span> <span class="n">key</span> <span class="p">{</span>
<a id="__codelineno-6-6" name="__codelineno-6-6" href="#__codelineno-6-6"></a>        <span class="k">for</span> <span class="n">scalar</span> <span class="k">in</span> <span class="n">c</span><span class="p">.</span><span class="n">unicodeScalars</span> <span class="p">{</span>
<a id="__codelineno-6-7" name="__codelineno-6-7" href="#__codelineno-6-7"></a>            <span class="n">hash</span> <span class="p">=</span> <span class="p">(</span><span class="n">hash</span> <span class="o">+</span> <span class="nb">Int</span><span class="p">(</span><span class="n">scalar</span><span class="p">.</span><span class="n">value</span><span class="p">))</span> <span class="o">%</span> <span class="n">MODULUS</span>
<a id="__codelineno-6-8" name="__codelineno-6-8" href="#__codelineno-6-8"></a>        <span class="p">}</span>
<a id="__codelineno-6-9" name="__codelineno-6-9" href="#__codelineno-6-9"></a>    <span class="p">}</span>
<a id="__codelineno-6-10" name="__codelineno-6-10" href="#__codelineno-6-10"></a>    <span class="k">return</span> <span class="n">hash</span>
<a id="__codelineno-6-11" name="__codelineno-6-11" href="#__codelineno-6-11"></a><span class="p">}</span>
<a id="__codelineno-6-12" name="__codelineno-6-12" href="#__codelineno-6-12"></a>
<a id="__codelineno-6-13" name="__codelineno-6-13" href="#__codelineno-6-13"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-6-14" name="__codelineno-6-14" href="#__codelineno-6-14"></a><span class="kd">func</span> <span class="nf">mulHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-6-15" name="__codelineno-6-15" href="#__codelineno-6-15"></a>    <span class="kd">var</span> <span class="nv">hash</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-6-16" name="__codelineno-6-16" href="#__codelineno-6-16"></a>    <span class="kd">let</span> <span class="nv">MODULUS</span> <span class="p">=</span> <span class="mi">1_000_000_007</span>
<a id="__codelineno-6-17" name="__codelineno-6-17" href="#__codelineno-6-17"></a>    <span class="k">for</span> <span class="n">c</span> <span class="k">in</span> <span class="n">key</span> <span class="p">{</span>
<a id="__codelineno-6-18" name="__codelineno-6-18" href="#__codelineno-6-18"></a>        <span class="k">for</span> <span class="n">scalar</span> <span class="k">in</span> <span class="n">c</span><span class="p">.</span><span class="n">unicodeScalars</span> <span class="p">{</span>
<a id="__codelineno-6-19" name="__codelineno-6-19" href="#__codelineno-6-19"></a>            <span class="n">hash</span> <span class="p">=</span> <span class="p">(</span><span class="mi">31</span> <span class="o">*</span> <span class="n">hash</span> <span class="o">+</span> <span class="nb">Int</span><span class="p">(</span><span class="n">scalar</span><span class="p">.</span><span class="n">value</span><span class="p">))</span> <span class="o">%</span> <span class="n">MODULUS</span>
<a id="__codelineno-6-20" name="__codelineno-6-20" href="#__codelineno-6-20"></a>        <span class="p">}</span>
<a id="__codelineno-6-21" name="__codelineno-6-21" href="#__codelineno-6-21"></a>    <span class="p">}</span>
<a id="__codelineno-6-22" name="__codelineno-6-22" href="#__codelineno-6-22"></a>    <span class="k">return</span> <span class="n">hash</span>
<a id="__codelineno-6-23" name="__codelineno-6-23" href="#__codelineno-6-23"></a><span class="p">}</span>
<a id="__codelineno-6-24" name="__codelineno-6-24" href="#__codelineno-6-24"></a>
<a id="__codelineno-6-25" name="__codelineno-6-25" href="#__codelineno-6-25"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-6-26" name="__codelineno-6-26" href="#__codelineno-6-26"></a><span class="kd">func</span> <span class="nf">xorHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-6-27" name="__codelineno-6-27" href="#__codelineno-6-27"></a>    <span class="kd">var</span> <span class="nv">hash</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-6-28" name="__codelineno-6-28" href="#__codelineno-6-28"></a>    <span class="kd">let</span> <span class="nv">MODULUS</span> <span class="p">=</span> <span class="mi">1_000_000_007</span>
<a id="__codelineno-6-29" name="__codelineno-6-29" href="#__codelineno-6-29"></a>    <span class="k">for</span> <span class="n">c</span> <span class="k">in</span> <span class="n">key</span> <span class="p">{</span>
<a id="__codelineno-6-30" name="__codelineno-6-30" href="#__codelineno-6-30"></a>        <span class="k">for</span> <span class="n">scalar</span> <span class="k">in</span> <span class="n">c</span><span class="p">.</span><span class="n">unicodeScalars</span> <span class="p">{</span>
<a id="__codelineno-6-31" name="__codelineno-6-31" href="#__codelineno-6-31"></a>            <span class="n">hash</span> <span class="o">^=</span> <span class="nb">Int</span><span class="p">(</span><span class="n">scalar</span><span class="p">.</span><span class="n">value</span><span class="p">)</span>
<a id="__codelineno-6-32" name="__codelineno-6-32" href="#__codelineno-6-32"></a>        <span class="p">}</span>
<a id="__codelineno-6-33" name="__codelineno-6-33" href="#__codelineno-6-33"></a>    <span class="p">}</span>
<a id="__codelineno-6-34" name="__codelineno-6-34" href="#__codelineno-6-34"></a>    <span class="k">return</span> <span class="n">hash</span> <span class="o">&amp;</span> <span class="n">MODULUS</span>
<a id="__codelineno-6-35" name="__codelineno-6-35" href="#__codelineno-6-35"></a><span class="p">}</span>
<a id="__codelineno-6-36" name="__codelineno-6-36" href="#__codelineno-6-36"></a>
<a id="__codelineno-6-37" name="__codelineno-6-37" href="#__codelineno-6-37"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-6-38" name="__codelineno-6-38" href="#__codelineno-6-38"></a><span class="kd">func</span> <span class="nf">rotHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-6-39" name="__codelineno-6-39" href="#__codelineno-6-39"></a>    <span class="kd">var</span> <span class="nv">hash</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-6-40" name="__codelineno-6-40" href="#__codelineno-6-40"></a>    <span class="kd">let</span> <span class="nv">MODULUS</span> <span class="p">=</span> <span class="mi">1_000_000_007</span>
<a id="__codelineno-6-41" name="__codelineno-6-41" href="#__codelineno-6-41"></a>    <span class="k">for</span> <span class="n">c</span> <span class="k">in</span> <span class="n">key</span> <span class="p">{</span>
<a id="__codelineno-6-42" name="__codelineno-6-42" href="#__codelineno-6-42"></a>        <span class="k">for</span> <span class="n">scalar</span> <span class="k">in</span> <span class="n">c</span><span class="p">.</span><span class="n">unicodeScalars</span> <span class="p">{</span>
<a id="__codelineno-6-43" name="__codelineno-6-43" href="#__codelineno-6-43"></a>            <span class="n">hash</span> <span class="p">=</span> <span class="p">((</span><span class="n">hash</span> <span class="o">&lt;&lt;</span> <span class="mi">4</span><span class="p">)</span> <span class="o">^</span> <span class="p">(</span><span class="n">hash</span> <span class="o">&gt;&gt;</span> <span class="mi">28</span><span class="p">)</span> <span class="o">^</span> <span class="nb">Int</span><span class="p">(</span><span class="n">scalar</span><span class="p">.</span><span class="n">value</span><span class="p">))</span> <span class="o">%</span> <span class="n">MODULUS</span>
<a id="__codelineno-6-44" name="__codelineno-6-44" href="#__codelineno-6-44"></a>        <span class="p">}</span>
<a id="__codelineno-6-45" name="__codelineno-6-45" href="#__codelineno-6-45"></a>    <span class="p">}</span>
<a id="__codelineno-6-46" name="__codelineno-6-46" href="#__codelineno-6-46"></a>    <span class="k">return</span> <span class="n">hash</span>
<a id="__codelineno-6-47" name="__codelineno-6-47" href="#__codelineno-6-47"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.js</span><pre id="__code_7"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_7 > code"></button><code><a id="__codelineno-7-1" name="__codelineno-7-1" href="#__codelineno-7-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-7-2" name="__codelineno-7-2" href="#__codelineno-7-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">addHash</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-3" name="__codelineno-7-3" href="#__codelineno-7-3"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-4" name="__codelineno-7-4" href="#__codelineno-7-4"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-7-5" name="__codelineno-7-5" href="#__codelineno-7-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-6" name="__codelineno-7-6" href="#__codelineno-7-6"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-7-7" name="__codelineno-7-7" href="#__codelineno-7-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-8" name="__codelineno-7-8" href="#__codelineno-7-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-7-9" name="__codelineno-7-9" href="#__codelineno-7-9"></a><span class="p">}</span>
<a id="__codelineno-7-10" name="__codelineno-7-10" href="#__codelineno-7-10"></a>
<a id="__codelineno-7-11" name="__codelineno-7-11" href="#__codelineno-7-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-7-12" name="__codelineno-7-12" href="#__codelineno-7-12"></a><span class="kd">function</span><span class="w"> </span><span class="nx">mulHash</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-13" name="__codelineno-7-13" href="#__codelineno-7-13"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-14" name="__codelineno-7-14" href="#__codelineno-7-14"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-7-15" name="__codelineno-7-15" href="#__codelineno-7-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-16" name="__codelineno-7-16" href="#__codelineno-7-16"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mf">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-7-17" name="__codelineno-7-17" href="#__codelineno-7-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-18" name="__codelineno-7-18" href="#__codelineno-7-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-7-19" name="__codelineno-7-19" href="#__codelineno-7-19"></a><span class="p">}</span>
<a id="__codelineno-7-20" name="__codelineno-7-20" href="#__codelineno-7-20"></a>
<a id="__codelineno-7-21" name="__codelineno-7-21" href="#__codelineno-7-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-7-22" name="__codelineno-7-22" href="#__codelineno-7-22"></a><span class="kd">function</span><span class="w"> </span><span class="nx">xorHash</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-23" name="__codelineno-7-23" href="#__codelineno-7-23"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-24" name="__codelineno-7-24" href="#__codelineno-7-24"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-7-25" name="__codelineno-7-25" href="#__codelineno-7-25"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-26" name="__codelineno-7-26" href="#__codelineno-7-26"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">);</span>
<a id="__codelineno-7-27" name="__codelineno-7-27" href="#__codelineno-7-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-28" name="__codelineno-7-28" href="#__codelineno-7-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-7-29" name="__codelineno-7-29" href="#__codelineno-7-29"></a><span class="p">}</span>
<a id="__codelineno-7-30" name="__codelineno-7-30" href="#__codelineno-7-30"></a>
<a id="__codelineno-7-31" name="__codelineno-7-31" href="#__codelineno-7-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-7-32" name="__codelineno-7-32" href="#__codelineno-7-32"></a><span class="kd">function</span><span class="w"> </span><span class="nx">rotHash</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-33" name="__codelineno-7-33" href="#__codelineno-7-33"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-34" name="__codelineno-7-34" href="#__codelineno-7-34"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-7-35" name="__codelineno-7-35" href="#__codelineno-7-35"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-36" name="__codelineno-7-36" href="#__codelineno-7-36"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="nx">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mf">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mf">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-7-37" name="__codelineno-7-37" href="#__codelineno-7-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-38" name="__codelineno-7-38" href="#__codelineno-7-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-7-39" name="__codelineno-7-39" href="#__codelineno-7-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.ts</span><pre id="__code_8"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_8 > code"></button><code><a id="__codelineno-8-1" name="__codelineno-8-1" href="#__codelineno-8-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-8-2" name="__codelineno-8-2" href="#__codelineno-8-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">addHash</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-3" name="__codelineno-8-3" href="#__codelineno-8-3"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-8-4" name="__codelineno-8-4" href="#__codelineno-8-4"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-8-5" name="__codelineno-8-5" href="#__codelineno-8-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-6" name="__codelineno-8-6" href="#__codelineno-8-6"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-8-7" name="__codelineno-8-7" href="#__codelineno-8-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-8" name="__codelineno-8-8" href="#__codelineno-8-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-8-9" name="__codelineno-8-9" href="#__codelineno-8-9"></a><span class="p">}</span>
<a id="__codelineno-8-10" name="__codelineno-8-10" href="#__codelineno-8-10"></a>
<a id="__codelineno-8-11" name="__codelineno-8-11" href="#__codelineno-8-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-8-12" name="__codelineno-8-12" href="#__codelineno-8-12"></a><span class="kd">function</span><span class="w"> </span><span class="nx">mulHash</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-13" name="__codelineno-8-13" href="#__codelineno-8-13"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-8-14" name="__codelineno-8-14" href="#__codelineno-8-14"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-8-15" name="__codelineno-8-15" href="#__codelineno-8-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-16" name="__codelineno-8-16" href="#__codelineno-8-16"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mf">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-8-17" name="__codelineno-8-17" href="#__codelineno-8-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-18" name="__codelineno-8-18" href="#__codelineno-8-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-8-19" name="__codelineno-8-19" href="#__codelineno-8-19"></a><span class="p">}</span>
<a id="__codelineno-8-20" name="__codelineno-8-20" href="#__codelineno-8-20"></a>
<a id="__codelineno-8-21" name="__codelineno-8-21" href="#__codelineno-8-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-8-22" name="__codelineno-8-22" href="#__codelineno-8-22"></a><span class="kd">function</span><span class="w"> </span><span class="nx">xorHash</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-23" name="__codelineno-8-23" href="#__codelineno-8-23"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-8-24" name="__codelineno-8-24" href="#__codelineno-8-24"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-8-25" name="__codelineno-8-25" href="#__codelineno-8-25"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-26" name="__codelineno-8-26" href="#__codelineno-8-26"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">);</span>
<a id="__codelineno-8-27" name="__codelineno-8-27" href="#__codelineno-8-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-28" name="__codelineno-8-28" href="#__codelineno-8-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-8-29" name="__codelineno-8-29" href="#__codelineno-8-29"></a><span class="p">}</span>
<a id="__codelineno-8-30" name="__codelineno-8-30" href="#__codelineno-8-30"></a>
<a id="__codelineno-8-31" name="__codelineno-8-31" href="#__codelineno-8-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-8-32" name="__codelineno-8-32" href="#__codelineno-8-32"></a><span class="kd">function</span><span class="w"> </span><span class="nx">rotHash</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-33" name="__codelineno-8-33" href="#__codelineno-8-33"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-8-34" name="__codelineno-8-34" href="#__codelineno-8-34"></a><span class="w">    </span><span class="kd">const</span><span class="w"> </span><span class="nx">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">1000000007</span><span class="p">;</span>
<a id="__codelineno-8-35" name="__codelineno-8-35" href="#__codelineno-8-35"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">c</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-36" name="__codelineno-8-36" href="#__codelineno-8-36"></a><span class="w">        </span><span class="nx">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="nx">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mf">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="nx">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mf">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="nx">c</span><span class="p">.</span><span class="nx">charCodeAt</span><span class="p">(</span><span class="mf">0</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="nx">MODULUS</span><span class="p">;</span>
<a id="__codelineno-8-37" name="__codelineno-8-37" href="#__codelineno-8-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-38" name="__codelineno-8-38" href="#__codelineno-8-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">hash</span><span class="p">;</span>
<a id="__codelineno-8-39" name="__codelineno-8-39" href="#__codelineno-8-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.dart</span><pre id="__code_9"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_9 > code"></button><code><a id="__codelineno-9-1" name="__codelineno-9-1" href="#__codelineno-9-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-9-2" name="__codelineno-9-2" href="#__codelineno-9-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">addHash</span><span class="p">(</span><span class="kt">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-3" name="__codelineno-9-3" href="#__codelineno-9-3"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-9-4" name="__codelineno-9-4" href="#__codelineno-9-4"></a><span class="w">  </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-9-5" name="__codelineno-9-5" href="#__codelineno-9-5"></a><span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">length</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-6" name="__codelineno-9-6" href="#__codelineno-9-6"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">codeUnitAt</span><span class="p">(</span><span class="n">i</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-9-7" name="__codelineno-9-7" href="#__codelineno-9-7"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-9-8" name="__codelineno-9-8" href="#__codelineno-9-8"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-9-9" name="__codelineno-9-9" href="#__codelineno-9-9"></a><span class="p">}</span>
<a id="__codelineno-9-10" name="__codelineno-9-10" href="#__codelineno-9-10"></a>
<a id="__codelineno-9-11" name="__codelineno-9-11" href="#__codelineno-9-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-9-12" name="__codelineno-9-12" href="#__codelineno-9-12"></a><span class="kt">int</span><span class="w"> </span><span class="n">mulHash</span><span class="p">(</span><span class="kt">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-13" name="__codelineno-9-13" href="#__codelineno-9-13"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-9-14" name="__codelineno-9-14" href="#__codelineno-9-14"></a><span class="w">  </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-9-15" name="__codelineno-9-15" href="#__codelineno-9-15"></a><span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">length</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-16" name="__codelineno-9-16" href="#__codelineno-9-16"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="m">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">codeUnitAt</span><span class="p">(</span><span class="n">i</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-9-17" name="__codelineno-9-17" href="#__codelineno-9-17"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-9-18" name="__codelineno-9-18" href="#__codelineno-9-18"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-9-19" name="__codelineno-9-19" href="#__codelineno-9-19"></a><span class="p">}</span>
<a id="__codelineno-9-20" name="__codelineno-9-20" href="#__codelineno-9-20"></a>
<a id="__codelineno-9-21" name="__codelineno-9-21" href="#__codelineno-9-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-9-22" name="__codelineno-9-22" href="#__codelineno-9-22"></a><span class="kt">int</span><span class="w"> </span><span class="n">xorHash</span><span class="p">(</span><span class="kt">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-23" name="__codelineno-9-23" href="#__codelineno-9-23"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-9-24" name="__codelineno-9-24" href="#__codelineno-9-24"></a><span class="w">  </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-9-25" name="__codelineno-9-25" href="#__codelineno-9-25"></a><span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">length</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-26" name="__codelineno-9-26" href="#__codelineno-9-26"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">codeUnitAt</span><span class="p">(</span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-9-27" name="__codelineno-9-27" href="#__codelineno-9-27"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-9-28" name="__codelineno-9-28" href="#__codelineno-9-28"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-9-29" name="__codelineno-9-29" href="#__codelineno-9-29"></a><span class="p">}</span>
<a id="__codelineno-9-30" name="__codelineno-9-30" href="#__codelineno-9-30"></a>
<a id="__codelineno-9-31" name="__codelineno-9-31" href="#__codelineno-9-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-9-32" name="__codelineno-9-32" href="#__codelineno-9-32"></a><span class="kt">int</span><span class="w"> </span><span class="n">rotHash</span><span class="p">(</span><span class="kt">String</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-33" name="__codelineno-9-33" href="#__codelineno-9-33"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-9-34" name="__codelineno-9-34" href="#__codelineno-9-34"></a><span class="w">  </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span><span class="p">;</span>
<a id="__codelineno-9-35" name="__codelineno-9-35" href="#__codelineno-9-35"></a><span class="w">  </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">length</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-36" name="__codelineno-9-36" href="#__codelineno-9-36"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="m">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="m">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">codeUnitAt</span><span class="p">(</span><span class="n">i</span><span class="p">))</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-9-37" name="__codelineno-9-37" href="#__codelineno-9-37"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-9-38" name="__codelineno-9-38" href="#__codelineno-9-38"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-9-39" name="__codelineno-9-39" href="#__codelineno-9-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.rs</span><pre id="__code_10"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_10 > code"></button><code><a id="__codelineno-10-1" name="__codelineno-10-1" href="#__codelineno-10-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-10-2" name="__codelineno-10-2" href="#__codelineno-10-2"></a><span class="k">fn</span> <span class="nf">add_hash</span><span class="p">(</span><span class="n">key</span>: <span class="kp">&amp;</span><span class="kt">str</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-10-3" name="__codelineno-10-3" href="#__codelineno-10-3"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0_</span><span class="k">i64</span><span class="p">;</span>
<a id="__codelineno-10-4" name="__codelineno-10-4" href="#__codelineno-10-4"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="n">MODULUS</span>: <span class="kt">i64</span> <span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-10-5" name="__codelineno-10-5" href="#__codelineno-10-5"></a>
<a id="__codelineno-10-6" name="__codelineno-10-6" href="#__codelineno-10-6"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">chars</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-7" name="__codelineno-10-7" href="#__codelineno-10-7"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i64</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-10-8" name="__codelineno-10-8" href="#__codelineno-10-8"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-9" name="__codelineno-10-9" href="#__codelineno-10-9"></a>
<a id="__codelineno-10-10" name="__codelineno-10-10" href="#__codelineno-10-10"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i32</span>
<a id="__codelineno-10-11" name="__codelineno-10-11" href="#__codelineno-10-11"></a><span class="p">}</span>
<a id="__codelineno-10-12" name="__codelineno-10-12" href="#__codelineno-10-12"></a>
<a id="__codelineno-10-13" name="__codelineno-10-13" href="#__codelineno-10-13"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-10-14" name="__codelineno-10-14" href="#__codelineno-10-14"></a><span class="k">fn</span> <span class="nf">mul_hash</span><span class="p">(</span><span class="n">key</span>: <span class="kp">&amp;</span><span class="kt">str</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-10-15" name="__codelineno-10-15" href="#__codelineno-10-15"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0_</span><span class="k">i64</span><span class="p">;</span>
<a id="__codelineno-10-16" name="__codelineno-10-16" href="#__codelineno-10-16"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="n">MODULUS</span>: <span class="kt">i64</span> <span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-10-17" name="__codelineno-10-17" href="#__codelineno-10-17"></a>
<a id="__codelineno-10-18" name="__codelineno-10-18" href="#__codelineno-10-18"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">chars</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-19" name="__codelineno-10-19" href="#__codelineno-10-19"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i64</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-10-20" name="__codelineno-10-20" href="#__codelineno-10-20"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-21" name="__codelineno-10-21" href="#__codelineno-10-21"></a>
<a id="__codelineno-10-22" name="__codelineno-10-22" href="#__codelineno-10-22"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i32</span>
<a id="__codelineno-10-23" name="__codelineno-10-23" href="#__codelineno-10-23"></a><span class="p">}</span>
<a id="__codelineno-10-24" name="__codelineno-10-24" href="#__codelineno-10-24"></a>
<a id="__codelineno-10-25" name="__codelineno-10-25" href="#__codelineno-10-25"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-10-26" name="__codelineno-10-26" href="#__codelineno-10-26"></a><span class="k">fn</span> <span class="nf">xor_hash</span><span class="p">(</span><span class="n">key</span>: <span class="kp">&amp;</span><span class="kt">str</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-10-27" name="__codelineno-10-27" href="#__codelineno-10-27"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0_</span><span class="k">i64</span><span class="p">;</span>
<a id="__codelineno-10-28" name="__codelineno-10-28" href="#__codelineno-10-28"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="n">MODULUS</span>: <span class="kt">i64</span> <span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-10-29" name="__codelineno-10-29" href="#__codelineno-10-29"></a>
<a id="__codelineno-10-30" name="__codelineno-10-30" href="#__codelineno-10-30"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">chars</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-31" name="__codelineno-10-31" href="#__codelineno-10-31"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i64</span><span class="p">;</span>
<a id="__codelineno-10-32" name="__codelineno-10-32" href="#__codelineno-10-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-33" name="__codelineno-10-33" href="#__codelineno-10-33"></a>
<a id="__codelineno-10-34" name="__codelineno-10-34" href="#__codelineno-10-34"></a><span class="w">    </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">)</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i32</span>
<a id="__codelineno-10-35" name="__codelineno-10-35" href="#__codelineno-10-35"></a><span class="p">}</span>
<a id="__codelineno-10-36" name="__codelineno-10-36" href="#__codelineno-10-36"></a>
<a id="__codelineno-10-37" name="__codelineno-10-37" href="#__codelineno-10-37"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-10-38" name="__codelineno-10-38" href="#__codelineno-10-38"></a><span class="k">fn</span> <span class="nf">rot_hash</span><span class="p">(</span><span class="n">key</span>: <span class="kp">&amp;</span><span class="kt">str</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-10-39" name="__codelineno-10-39" href="#__codelineno-10-39"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0_</span><span class="k">i64</span><span class="p">;</span>
<a id="__codelineno-10-40" name="__codelineno-10-40" href="#__codelineno-10-40"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="n">MODULUS</span>: <span class="kt">i64</span> <span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-10-41" name="__codelineno-10-41" href="#__codelineno-10-41"></a>
<a id="__codelineno-10-42" name="__codelineno-10-42" href="#__codelineno-10-42"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="n">chars</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-43" name="__codelineno-10-43" href="#__codelineno-10-43"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="n">c</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i64</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-10-44" name="__codelineno-10-44" href="#__codelineno-10-44"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-45" name="__codelineno-10-45" href="#__codelineno-10-45"></a>
<a id="__codelineno-10-46" name="__codelineno-10-46" href="#__codelineno-10-46"></a><span class="w">    </span><span class="n">hash</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i32</span>
<a id="__codelineno-10-47" name="__codelineno-10-47" href="#__codelineno-10-47"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.c</span><pre id="__code_11"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_11 > code"></button><code><a id="__codelineno-11-1" name="__codelineno-11-1" href="#__codelineno-11-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-11-2" name="__codelineno-11-2" href="#__codelineno-11-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">addHash</span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-3" name="__codelineno-11-3" href="#__codelineno-11-3"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-11-4" name="__codelineno-11-4" href="#__codelineno-11-4"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-11-5" name="__codelineno-11-5" href="#__codelineno-11-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">strlen</span><span class="p">(</span><span class="n">key</span><span class="p">);</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-6" name="__codelineno-11-6" href="#__codelineno-11-6"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="p">)</span><span class="n">key</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-11-7" name="__codelineno-11-7" href="#__codelineno-11-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-8" name="__codelineno-11-8" href="#__codelineno-11-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-11-9" name="__codelineno-11-9" href="#__codelineno-11-9"></a><span class="p">}</span>
<a id="__codelineno-11-10" name="__codelineno-11-10" href="#__codelineno-11-10"></a>
<a id="__codelineno-11-11" name="__codelineno-11-11" href="#__codelineno-11-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-11-12" name="__codelineno-11-12" href="#__codelineno-11-12"></a><span class="kt">int</span><span class="w"> </span><span class="nf">mulHash</span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-13" name="__codelineno-11-13" href="#__codelineno-11-13"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-11-14" name="__codelineno-11-14" href="#__codelineno-11-14"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-11-15" name="__codelineno-11-15" href="#__codelineno-11-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">strlen</span><span class="p">(</span><span class="n">key</span><span class="p">);</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-16" name="__codelineno-11-16" href="#__codelineno-11-16"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="mi">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="p">)</span><span class="n">key</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-11-17" name="__codelineno-11-17" href="#__codelineno-11-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-18" name="__codelineno-11-18" href="#__codelineno-11-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-11-19" name="__codelineno-11-19" href="#__codelineno-11-19"></a><span class="p">}</span>
<a id="__codelineno-11-20" name="__codelineno-11-20" href="#__codelineno-11-20"></a>
<a id="__codelineno-11-21" name="__codelineno-11-21" href="#__codelineno-11-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-11-22" name="__codelineno-11-22" href="#__codelineno-11-22"></a><span class="kt">int</span><span class="w"> </span><span class="nf">xorHash</span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-23" name="__codelineno-11-23" href="#__codelineno-11-23"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-11-24" name="__codelineno-11-24" href="#__codelineno-11-24"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-11-25" name="__codelineno-11-25" href="#__codelineno-11-25"></a>
<a id="__codelineno-11-26" name="__codelineno-11-26" href="#__codelineno-11-26"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">strlen</span><span class="p">(</span><span class="n">key</span><span class="p">);</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-27" name="__codelineno-11-27" href="#__codelineno-11-27"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="p">)</span><span class="n">key</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-11-28" name="__codelineno-11-28" href="#__codelineno-11-28"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-29" name="__codelineno-11-29" href="#__codelineno-11-29"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">&amp;</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-11-30" name="__codelineno-11-30" href="#__codelineno-11-30"></a><span class="p">}</span>
<a id="__codelineno-11-31" name="__codelineno-11-31" href="#__codelineno-11-31"></a>
<a id="__codelineno-11-32" name="__codelineno-11-32" href="#__codelineno-11-32"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-11-33" name="__codelineno-11-33" href="#__codelineno-11-33"></a><span class="kt">int</span><span class="w"> </span><span class="nf">rotHash</span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-34" name="__codelineno-11-34" href="#__codelineno-11-34"></a><span class="w">    </span><span class="kt">long</span><span class="w"> </span><span class="kt">long</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-11-35" name="__codelineno-11-35" href="#__codelineno-11-35"></a><span class="w">    </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1000000007</span><span class="p">;</span>
<a id="__codelineno-11-36" name="__codelineno-11-36" href="#__codelineno-11-36"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">strlen</span><span class="p">(</span><span class="n">key</span><span class="p">);</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-37" name="__codelineno-11-37" href="#__codelineno-11-37"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="kt">unsigned</span><span class="w"> </span><span class="kt">char</span><span class="p">)</span><span class="n">key</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span><span class="p">;</span>
<a id="__codelineno-11-38" name="__codelineno-11-38" href="#__codelineno-11-38"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-39" name="__codelineno-11-39" href="#__codelineno-11-39"></a>
<a id="__codelineno-11-40" name="__codelineno-11-40" href="#__codelineno-11-40"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="p">)</span><span class="n">hash</span><span class="p">;</span>
<a id="__codelineno-11-41" name="__codelineno-11-41" href="#__codelineno-11-41"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.kt</span><pre id="__code_12"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_12 > code"></button><code><a id="__codelineno-12-1" name="__codelineno-12-1" href="#__codelineno-12-1"></a><span class="cm">/* 加法哈希 */</span>
<a id="__codelineno-12-2" name="__codelineno-12-2" href="#__codelineno-12-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">addHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-3" name="__codelineno-12-3" href="#__codelineno-12-3"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0L</span>
<a id="__codelineno-12-4" name="__codelineno-12-4" href="#__codelineno-12-4"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span>
<a id="__codelineno-12-5" name="__codelineno-12-5" href="#__codelineno-12-5"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-6" name="__codelineno-12-6" href="#__codelineno-12-6"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="p">.</span><span class="na">code</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span>
<a id="__codelineno-12-7" name="__codelineno-12-7" href="#__codelineno-12-7"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-12-8" name="__codelineno-12-8" href="#__codelineno-12-8"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">.</span><span class="na">toInt</span><span class="p">()</span>
<a id="__codelineno-12-9" name="__codelineno-12-9" href="#__codelineno-12-9"></a><span class="p">}</span>
<a id="__codelineno-12-10" name="__codelineno-12-10" href="#__codelineno-12-10"></a>
<a id="__codelineno-12-11" name="__codelineno-12-11" href="#__codelineno-12-11"></a><span class="cm">/* 乘法哈希 */</span>
<a id="__codelineno-12-12" name="__codelineno-12-12" href="#__codelineno-12-12"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">mulHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-13" name="__codelineno-12-13" href="#__codelineno-12-13"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0L</span>
<a id="__codelineno-12-14" name="__codelineno-12-14" href="#__codelineno-12-14"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span>
<a id="__codelineno-12-15" name="__codelineno-12-15" href="#__codelineno-12-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-16" name="__codelineno-12-16" href="#__codelineno-12-16"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="m">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="p">.</span><span class="na">code</span><span class="p">)</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span>
<a id="__codelineno-12-17" name="__codelineno-12-17" href="#__codelineno-12-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-12-18" name="__codelineno-12-18" href="#__codelineno-12-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">.</span><span class="na">toInt</span><span class="p">()</span>
<a id="__codelineno-12-19" name="__codelineno-12-19" href="#__codelineno-12-19"></a><span class="p">}</span>
<a id="__codelineno-12-20" name="__codelineno-12-20" href="#__codelineno-12-20"></a>
<a id="__codelineno-12-21" name="__codelineno-12-21" href="#__codelineno-12-21"></a><span class="cm">/* 异或哈希 */</span>
<a id="__codelineno-12-22" name="__codelineno-12-22" href="#__codelineno-12-22"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">xorHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-23" name="__codelineno-12-23" href="#__codelineno-12-23"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-12-24" name="__codelineno-12-24" href="#__codelineno-12-24"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span>
<a id="__codelineno-12-25" name="__codelineno-12-25" href="#__codelineno-12-25"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-26" name="__codelineno-12-26" href="#__codelineno-12-26"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="n">xor</span><span class="w"> </span><span class="n">c</span><span class="p">.</span><span class="na">code</span>
<a id="__codelineno-12-27" name="__codelineno-12-27" href="#__codelineno-12-27"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-12-28" name="__codelineno-12-28" href="#__codelineno-12-28"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="w"> </span><span class="n">and</span><span class="w"> </span><span class="n">MODULUS</span>
<a id="__codelineno-12-29" name="__codelineno-12-29" href="#__codelineno-12-29"></a><span class="p">}</span>
<a id="__codelineno-12-30" name="__codelineno-12-30" href="#__codelineno-12-30"></a>
<a id="__codelineno-12-31" name="__codelineno-12-31" href="#__codelineno-12-31"></a><span class="cm">/* 旋转哈希 */</span>
<a id="__codelineno-12-32" name="__codelineno-12-32" href="#__codelineno-12-32"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">rotHash</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-33" name="__codelineno-12-33" href="#__codelineno-12-33"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0L</span>
<a id="__codelineno-12-34" name="__codelineno-12-34" href="#__codelineno-12-34"></a><span class="w">    </span><span class="kd">val</span><span class="w"> </span><span class="nv">MODULUS</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">1000000007</span>
<a id="__codelineno-12-35" name="__codelineno-12-35" href="#__codelineno-12-35"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">c</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">key</span><span class="p">.</span><span class="na">toCharArray</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-12-36" name="__codelineno-12-36" href="#__codelineno-12-36"></a><span class="w">        </span><span class="n">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">((</span><span class="n">hash</span><span class="w"> </span><span class="n">shl</span><span class="w"> </span><span class="m">4</span><span class="p">)</span><span class="w"> </span><span class="n">xor</span><span class="w"> </span><span class="p">(</span><span class="n">hash</span><span class="w"> </span><span class="n">shr</span><span class="w"> </span><span class="m">28</span><span class="p">)</span><span class="w"> </span><span class="n">xor</span><span class="w"> </span><span class="n">c</span><span class="p">.</span><span class="na">code</span><span class="p">.</span><span class="na">toLong</span><span class="p">())</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">MODULUS</span>
<a id="__codelineno-12-37" name="__codelineno-12-37" href="#__codelineno-12-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-12-38" name="__codelineno-12-38" href="#__codelineno-12-38"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hash</span><span class="p">.</span><span class="na">toInt</span><span class="p">()</span>
<a id="__codelineno-12-39" name="__codelineno-12-39" href="#__codelineno-12-39"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.rb</span><pre id="__code_13"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_13 > code"></button><code><a id="__codelineno-13-1" name="__codelineno-13-1" href="#__codelineno-13-1"></a><span class="c1">### 加法哈希 ###</span>
<a id="__codelineno-13-2" name="__codelineno-13-2" href="#__codelineno-13-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">add_hash</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-13-3" name="__codelineno-13-3" href="#__codelineno-13-3"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-13-4" name="__codelineno-13-4" href="#__codelineno-13-4"></a><span class="w">  </span><span class="n">modulus</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1_000_000_007</span>
<a id="__codelineno-13-5" name="__codelineno-13-5" href="#__codelineno-13-5"></a>
<a id="__codelineno-13-6" name="__codelineno-13-6" href="#__codelineno-13-6"></a><span class="w">  </span><span class="n">key</span><span class="o">.</span><span class="n">each_char</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">c</span><span class="o">|</span><span class="w"> </span><span class="nb">hash</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="n">c</span><span class="o">.</span><span class="n">ord</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-13-7" name="__codelineno-13-7" href="#__codelineno-13-7"></a>
<a id="__codelineno-13-8" name="__codelineno-13-8" href="#__codelineno-13-8"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">modulus</span>
<a id="__codelineno-13-9" name="__codelineno-13-9" href="#__codelineno-13-9"></a><span class="k">end</span>
<a id="__codelineno-13-10" name="__codelineno-13-10" href="#__codelineno-13-10"></a>
<a id="__codelineno-13-11" name="__codelineno-13-11" href="#__codelineno-13-11"></a><span class="c1">### 乘法哈希 ###</span>
<a id="__codelineno-13-12" name="__codelineno-13-12" href="#__codelineno-13-12"></a><span class="k">def</span><span class="w"> </span><span class="nf">mul_hash</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-13-13" name="__codelineno-13-13" href="#__codelineno-13-13"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-13-14" name="__codelineno-13-14" href="#__codelineno-13-14"></a><span class="w">  </span><span class="n">modulus</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1_000_000_007</span>
<a id="__codelineno-13-15" name="__codelineno-13-15" href="#__codelineno-13-15"></a>
<a id="__codelineno-13-16" name="__codelineno-13-16" href="#__codelineno-13-16"></a><span class="w">  </span><span class="n">key</span><span class="o">.</span><span class="n">each_char</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">c</span><span class="o">|</span><span class="w"> </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">31</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="nb">hash</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">c</span><span class="o">.</span><span class="n">ord</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-13-17" name="__codelineno-13-17" href="#__codelineno-13-17"></a>
<a id="__codelineno-13-18" name="__codelineno-13-18" href="#__codelineno-13-18"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">modulus</span>
<a id="__codelineno-13-19" name="__codelineno-13-19" href="#__codelineno-13-19"></a><span class="k">end</span>
<a id="__codelineno-13-20" name="__codelineno-13-20" href="#__codelineno-13-20"></a>
<a id="__codelineno-13-21" name="__codelineno-13-21" href="#__codelineno-13-21"></a><span class="c1">### 异或哈希 ###</span>
<a id="__codelineno-13-22" name="__codelineno-13-22" href="#__codelineno-13-22"></a><span class="k">def</span><span class="w"> </span><span class="nf">xor_hash</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-13-23" name="__codelineno-13-23" href="#__codelineno-13-23"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-13-24" name="__codelineno-13-24" href="#__codelineno-13-24"></a><span class="w">  </span><span class="n">modulus</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1_000_000_007</span>
<a id="__codelineno-13-25" name="__codelineno-13-25" href="#__codelineno-13-25"></a>
<a id="__codelineno-13-26" name="__codelineno-13-26" href="#__codelineno-13-26"></a><span class="w">  </span><span class="n">key</span><span class="o">.</span><span class="n">each_char</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">c</span><span class="o">|</span><span class="w"> </span><span class="nb">hash</span><span class="w"> </span><span class="o">^=</span><span class="w"> </span><span class="n">c</span><span class="o">.</span><span class="n">ord</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-13-27" name="__codelineno-13-27" href="#__codelineno-13-27"></a>
<a id="__codelineno-13-28" name="__codelineno-13-28" href="#__codelineno-13-28"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">modulus</span>
<a id="__codelineno-13-29" name="__codelineno-13-29" href="#__codelineno-13-29"></a><span class="k">end</span>
<a id="__codelineno-13-30" name="__codelineno-13-30" href="#__codelineno-13-30"></a>
<a id="__codelineno-13-31" name="__codelineno-13-31" href="#__codelineno-13-31"></a><span class="c1">### 旋转哈希 ###</span>
<a id="__codelineno-13-32" name="__codelineno-13-32" href="#__codelineno-13-32"></a><span class="k">def</span><span class="w"> </span><span class="nf">rot_hash</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-13-33" name="__codelineno-13-33" href="#__codelineno-13-33"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-13-34" name="__codelineno-13-34" href="#__codelineno-13-34"></a><span class="w">  </span><span class="n">modulus</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">1_000_000_007</span>
<a id="__codelineno-13-35" name="__codelineno-13-35" href="#__codelineno-13-35"></a>
<a id="__codelineno-13-36" name="__codelineno-13-36" href="#__codelineno-13-36"></a><span class="w">  </span><span class="n">key</span><span class="o">.</span><span class="n">each_char</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">c</span><span class="o">|</span><span class="w"> </span><span class="nb">hash</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="nb">hash</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="mi">4</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="p">(</span><span class="nb">hash</span><span class="w"> </span><span class="o">&gt;&gt;</span><span class="w"> </span><span class="mi">28</span><span class="p">)</span><span class="w"> </span><span class="o">^</span><span class="w"> </span><span class="n">c</span><span class="o">.</span><span class="n">ord</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-13-37" name="__codelineno-13-37" href="#__codelineno-13-37"></a>
<a id="__codelineno-13-38" name="__codelineno-13-38" href="#__codelineno-13-38"></a><span class="w">  </span><span class="nb">hash</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="n">modulus</span>
<a id="__codelineno-13-39" name="__codelineno-13-39" href="#__codelineno-13-39"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">simple_hash.zig</span><pre id="__code_14"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_14 > code"></button><code><a id="__codelineno-14-1" name="__codelineno-14-1" href="#__codelineno-14-1"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">addHash</span><span class="p">}</span>
<a id="__codelineno-14-2" name="__codelineno-14-2" href="#__codelineno-14-2"></a>
<a id="__codelineno-14-3" name="__codelineno-14-3" href="#__codelineno-14-3"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">mulHash</span><span class="p">}</span>
<a id="__codelineno-14-4" name="__codelineno-14-4" href="#__codelineno-14-4"></a>
<a id="__codelineno-14-5" name="__codelineno-14-5" href="#__codelineno-14-5"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">xorHash</span><span class="p">}</span>
<a id="__codelineno-14-6" name="__codelineno-14-6" href="#__codelineno-14-6"></a>
<a id="__codelineno-14-7" name="__codelineno-14-7" href="#__codelineno-14-7"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">rotHash</span><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
观察发现，每种哈希算法的最后一步都是对大质数 $1000000007$ 取模，以确保哈希值在合适的范围内。值得思考的是，为什么要强调对质数取模，或者说对合数取模的弊端是什么？这是一个有趣的问题。

先抛出结论：**当我们使用大质数作为模数时，可以最大化地保证哈希值的均匀分布**。因为质数不会与其他数字存在公约数，可以减少因取模操作而产生的周期性模式，从而避免哈希冲突。

举个例子，假设我们选择合数 $9$ 作为模数，它可以被 $3$ 整除。那么所有可以被 $3$ 整除的 `key` 都会被映射到 $0$、$3$、$6$ 这三个哈希值。

$$
\begin{aligned}
\text{modulus} & = 9 \newline
\text{key} & = \{ 0, 3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, \dots \} \newline
\text{hash} & = \{ 0, 3, 6, 0, 3, 6, 0, 3, 6, 0, 3, 6,\dots \}
\end{aligned}
$$

如果输入 `key` 恰好满足这种等差数列的数据分布，那么哈希值就会出现聚堆，从而加重哈希冲突。现在，假设将 `modulus` 替换为质数 $13$ ，由于 `key` 和 `modulus` 之间不存在公约数，输出的哈希值的均匀性会明显提升。

$$
\begin{aligned}
\text{modulus} & = 13 \newline
\text{key} & = \{ 0, 3, 6, 9, 12, 15, 18, 21, 24, 27, 30, 33, \dots \} \newline
\text{hash} & = \{ 0, 3, 6, 9, 12, 2, 5, 8, 11, 1, 4, 7, \dots \}
\end{aligned}
$$

值得说明的是，如果能够保证 `key` 是随机均匀分布的，那么选择质数或者合数作为模数都是可以的，它们都能输出均匀分布的哈希值。而当 `key` 的分布存在某种周期性时，对合数取模更容易出现聚集现象。

总而言之，我们通常选取质数作为模数，并且这个质数最好足够大，以尽可能消除周期性模式，提升哈希算法的稳健性。

## 常见哈希算法

不难发现，以上介绍的简单哈希算法都比较“脆弱”，远远没有达到哈希算法的设计目标。例如，由于加法和异或满足交换律，因此加法哈希和异或哈希无法区分内容相同但顺序不同的字符串，这可能会加剧哈希冲突，并引起一些安全问题。

在实际中，我们通常会用一些标准哈希算法，例如 MD5、SHA-1、SHA-2、SHA3 等。它们可以将任意长度的输入数据映射到恒定长度的哈希值。

近一个世纪以来，哈希算法处在不断升级与优化的过程中。一部分研究人员努力提升哈希算法的性能，另一部分研究人员和黑客则致力于寻找哈希算法的安全性问题。下表展示了在实际应用中常见的哈希算法。

- MD5 和 SHA-1 已多次被成功攻击，因此它们被各类安全应用弃用。
- SHA-2 系列中的 SHA-256 是最安全的哈希算法之一，仍未出现成功的攻击案例，因此常被用在各类安全应用与协议中。
- SHA-3 相较 SHA-2 的实现开销更低、计算效率更高，但目前使用覆盖度不如 SHA-2 系列。

<p align="center"> 表 <id> &nbsp; 常见的哈希算法 </p>

|          | MD5                            | SHA-1            | SHA-2                        | SHA-3                |
| -------- | ------------------------------ | ---------------- | ---------------------------- | -------------------- |
| 推出时间 | 1992                           | 1995             | 2002                         | 2008                 |
| 输出长度 | 128 bits                       | 160 bits         | 256 / 512 bits               | 224/256/384/512 bits |
| 哈希冲突 | 较多                           | 较多             | 很少                         | 很少                 |
| 安全等级 | 低，已被成功攻击               | 低，已被成功攻击 | 高                           | 高                   |
| 应用     | 已被弃用，仍用于数据完整性检查 | 已被弃用         | 加密货币交易验证、数字签名等 | 可用于替代 SHA-2     |

## 数据结构的哈希值

我们知道，哈希表的 `key` 可以是整数、小数或字符串等数据类型。编程语言通常会为这些数据类型提供内置的哈希算法，用于计算哈希表中的桶索引。以 Python 为例，我们可以调用 `hash()` 函数来计算各种数据类型的哈希值。

- 整数和布尔量的哈希值就是其本身。
- 浮点数和字符串的哈希值计算较为复杂，有兴趣的同学请自行学习。
- 元组的哈希值是对其中每一个元素进行哈希，然后将这些哈希值组合起来，得到单一的哈希值。
- 对象的哈希值基于其内存地址生成。通过重写对象的哈希方法，可实现基于内容生成哈希值。

!!! tip

    请注意，不同编程语言的内置哈希值计算函数的定义和方法不同。

=== "Python"

    ```python title="built_in_hash.py"
    num = 3
    hash_num = hash(num)
    # 整数 3 的哈希值为 3

    bol = True
    hash_bol = hash(bol)
    # 布尔量 True 的哈希值为 1

    dec = 3.14159
    hash_dec = hash(dec)
    # 小数 3.14159 的哈希值为 326484311674566659

    str = "Hello 算法"
    hash_str = hash(str)
    # 字符串 Hello 算法 的哈希值为 4617003410720528961

    tup = (12836, "小哈")
    hash_tup = hash(tup)
    # 元组 (12836, '小哈') 的哈希值为 1029005403108185979

    obj = ListNode(0)
    hash_obj = hash(obj)
    # 节点对象 <ListNode object at 0x1058fd810> 的哈希值为 274267521
    ```

=== "C++"

    ```cpp title="built_in_hash.cpp"
    int num = 3;
    size_t hashNum = hash<int>()(num);
    // 整数 3 的哈希值为 3

    bool bol = true;
    size_t hashBol = hash<bool>()(bol);
    // 布尔量 1 的哈希值为 1

    double dec = 3.14159;
    size_t hashDec = hash<double>()(dec);
    // 小数 3.14159 的哈希值为 4614256650576692846

    string str = "Hello 算法";
    size_t hashStr = hash<string>()(str);
    // 字符串 Hello 算法 的哈希值为 15466937326284535026

    // 在 C++ 中，内置 std:hash() 仅提供基本数据类型的哈希值计算
    // 数组、对象的哈希值计算需要自行实现
    ```

=== "Java"

    ```java title="built_in_hash.java"
    int num = 3;
    int hashNum = Integer.hashCode(num);
    // 整数 3 的哈希值为 3

    boolean bol = true;
    int hashBol = Boolean.hashCode(bol);
    // 布尔量 true 的哈希值为 1231

    double dec = 3.14159;
    int hashDec = Double.hashCode(dec);
    // 小数 3.14159 的哈希值为 -1340954729

    String str = "Hello 算法";
    int hashStr = str.hashCode();
    // 字符串 Hello 算法 的哈希值为 -727081396

    Object[] arr = { 12836, "小哈" };
    int hashTup = Arrays.hashCode(arr);
    // 数组 [12836, 小哈] 的哈希值为 1151158

    ListNode obj = new ListNode(0);
    int hashObj = obj.hashCode();
    // 节点对象 utils.ListNode@7dc5e7b4 的哈希值为 2110121908
    ```

=== "C#"

    ```csharp title="built_in_hash.cs"
    int num = 3;
    int hashNum = num.GetHashCode();
    // 整数 3 的哈希值为 3;

    bool bol = true;
    int hashBol = bol.GetHashCode();
    // 布尔量 true 的哈希值为 1;

    double dec = 3.14159;
    int hashDec = dec.GetHashCode();
    // 小数 3.14159 的哈希值为 -1340954729;

    string str = "Hello 算法";
    int hashStr = str.GetHashCode();
    // 字符串 Hello 算法 的哈希值为 -586107568;

    object[] arr = { 12836, "小哈" };
    int hashTup = arr.GetHashCode();
    // 数组 [12836, 小哈] 的哈希值为 42931033;

    ListNode obj = new(0);
    int hashObj = obj.GetHashCode();
    // 节点对象 0 的哈希值为 39053774;
    ```

=== "Go"

    ```go title="built_in_hash.go"
    // Go 未提供内置 hash code 函数
    ```

=== "Swift"

    ```swift title="built_in_hash.swift"
    let num = 3
    let hashNum = num.hashValue
    // 整数 3 的哈希值为 9047044699613009734

    let bol = true
    let hashBol = bol.hashValue
    // 布尔量 true 的哈希值为 -4431640247352757451

    let dec = 3.14159
    let hashDec = dec.hashValue
    // 小数 3.14159 的哈希值为 -2465384235396674631

    let str = "Hello 算法"
    let hashStr = str.hashValue
    // 字符串 Hello 算法 的哈希值为 -7850626797806988787

    let arr = [AnyHashable(12836), AnyHashable("小哈")]
    let hashTup = arr.hashValue
    // 数组 [AnyHashable(12836), AnyHashable("小哈")] 的哈希值为 -2308633508154532996

    let obj = ListNode(x: 0)
    let hashObj = obj.hashValue
    // 节点对象 utils.ListNode 的哈希值为 -2434780518035996159
    ```

=== "JS"

    ```javascript title="built_in_hash.js"
    // JavaScript 未提供内置 hash code 函数
    ```

=== "TS"

    ```typescript title="built_in_hash.ts"
    // TypeScript 未提供内置 hash code 函数
    ```

=== "Dart"

    ```dart title="built_in_hash.dart"
    int num = 3;
    int hashNum = num.hashCode;
    // 整数 3 的哈希值为 34803

    bool bol = true;
    int hashBol = bol.hashCode;
    // 布尔值 true 的哈希值为 1231

    double dec = 3.14159;
    int hashDec = dec.hashCode;
    // 小数 3.14159 的哈希值为 2570631074981783

    String str = "Hello 算法";
    int hashStr = str.hashCode;
    // 字符串 Hello 算法 的哈希值为 468167534

    List arr = [12836, "小哈"];
    int hashArr = arr.hashCode;
    // 数组 [12836, 小哈] 的哈希值为 976512528

    ListNode obj = new ListNode(0);
    int hashObj = obj.hashCode;
    // 节点对象 Instance of 'ListNode' 的哈希值为 1033450432
    ```

=== "Rust"

    ```rust title="built_in_hash.rs"
    use std::collections::hash_map::DefaultHasher;
    use std::hash::{Hash, Hasher};
    
    let num = 3;
    let mut num_hasher = DefaultHasher::new();
    num.hash(&mut num_hasher);
    let hash_num = num_hasher.finish();
    // 整数 3 的哈希值为 568126464209439262

    let bol = true;
    let mut bol_hasher = DefaultHasher::new();
    bol.hash(&mut bol_hasher);
    let hash_bol = bol_hasher.finish();
    // 布尔量 true 的哈希值为 4952851536318644461

    let dec: f32 = 3.14159;
    let mut dec_hasher = DefaultHasher::new();
    dec.to_bits().hash(&mut dec_hasher);
    let hash_dec = dec_hasher.finish();
    println!("小数 {} 的哈希值为 {}", dec, hash_dec);
    // 小数 3.14159 的哈希值为 2566941990314602357

    let str = "Hello 算法";
    let mut str_hasher = DefaultHasher::new();
    str.hash(&mut str_hasher);
    let hash_str = str_hasher.finish();
    // 字符串 Hello 算法 的哈希值为 16092673739211250988

    let arr = (&12836, &"小哈");
    let mut tup_hasher = DefaultHasher::new();
    arr.hash(&mut tup_hasher);
    let hash_tup = tup_hasher.finish();
    // 元组 (12836, "小哈") 的哈希值为 1885128010422702749

    let node = ListNode::new(42);
    let mut hasher = DefaultHasher::new();
    node.borrow().val.hash(&mut hasher);
    let hash = hasher.finish();
    // 节点对象 RefCell { value: ListNode { val: 42, next: None } } 的哈希值为15387811073369036852
    ```

=== "C"

    ```c title="built_in_hash.c"
    // C 未提供内置 hash code 函数
    ```

=== "Zig"

    ```zig title="built_in_hash.zig"

    ```

在许多编程语言中，**只有不可变对象才可作为哈希表的 `key`** 。假如我们将列表（动态数组）作为 `key` ，当列表的内容发生变化时，它的哈希值也随之改变，我们就无法在哈希表中查询到原先的 `value` 了。

虽然自定义对象（比如链表节点）的成员变量是可变的，但它是可哈希的。**这是因为对象的哈希值通常是基于内存地址生成的**，即使对象的内容发生了变化，但它的内存地址不变，哈希值仍然是不变的。

细心的你可能发现在不同控制台中运行程序时，输出的哈希值是不同的。**这是因为 Python 解释器在每次启动时，都会为字符串哈希函数加入一个随机的盐（Salt）值**。这种做法可以有效防止 HashDoS 攻击，提升哈希算法的安全性。
