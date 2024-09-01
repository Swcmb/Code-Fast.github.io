# 最大容量问题

!!! question

    输入一个数组 $ht$ ，数组中的每个元素代表一个垂直隔板的高度。数组中的任意两个隔板，以及它们之间的空间可以组成一个容器。
    
    容器的容量等于高度和宽度的乘积（即面积），其中高度由较短的隔板决定，宽度是两个隔板的数组索引之差。
    
    请在数组中选择两个隔板，使得组成的容器的容量最大，返回最大容量。

![最大容量问题的示例数据](max_capacity_problem.assets/max_capacity_example.png)

容器由任意两个隔板围成，**因此本题的状态为两个隔板的索引，记为 $[i, j]$** 。

根据题意，容量等于高度乘以宽度，其中高度由短板决定，宽度是两隔板的索引之差。设容量为 $cap[i, j]$ ，则可得计算公式：

$$
cap[i, j] = \min(ht[i], ht[j]) \times (j - i)
$$

设数组长度为 $n$ ，两个隔板的组合数量（即状态总数）为 $C_n^2 = \frac{n(n - 1)}{2}$ 个。最直接地，**我们可以穷举所有状态**，从而求得最大容量，时间复杂度为 $O(n^2)$ 。

### 贪心策略确定

这道题还有更高效率的解法。如下图所示，现选取一个状态 $[i, j]$ ，其满足索引 $i < j$ 且高度 $ht[i] < ht[j]$ ，即 $i$ 为短板、$j$ 为长板。

![初始状态](max_capacity_problem.assets/max_capacity_initial_state.png)

如下图所示，**若此时将长板 $j$ 向短板 $i$ 靠近，则容量一定变小**。

这是因为在移动长板 $j$ 后，宽度 $j-i$ 肯定变小；而高度由短板决定，因此高度只可能不变（ $i$ 仍为短板）或变小（移动后的 $j$ 成为短板）。

![向内移动长板后的状态](max_capacity_problem.assets/max_capacity_moving_long_board.png)

反向思考，**我们只有向内收缩短板 $i$ ，才有可能使容量变大**。因为虽然宽度一定变小，**但高度可能会变大**（移动后的短板 $i$ 可能会变长）。例如在下图中，移动短板后面积变大。

![向内移动短板后的状态](max_capacity_problem.assets/max_capacity_moving_short_board.png)

由此便可推出本题的贪心策略：初始化两指针分裂容器两端，每轮向内收缩短板对应的指针，直至两指针相遇。

下图展示了贪心策略的执行过程。

1. 初始状态下，指针 $i$ 和 $j$ 分列与数组两端。
2. 计算当前状态的容量 $cap[i, j]$ ，并更新最大容量。
3. 比较板 $i$ 和 板 $j$ 的高度，并将短板向内移动一格。
4. 循环执行第 `2.` 和 `3.` 步，直至 $i$ 和 $j$ 相遇时结束。

=== "<1>"
    ![最大容量问题的贪心过程](max_capacity_problem.assets/max_capacity_greedy_step1.png)

=== "<2>"
    ![max_capacity_greedy_step2](max_capacity_problem.assets/max_capacity_greedy_step2.png)

=== "<3>"
    ![max_capacity_greedy_step3](max_capacity_problem.assets/max_capacity_greedy_step3.png)

=== "<4>"
    ![max_capacity_greedy_step4](max_capacity_problem.assets/max_capacity_greedy_step4.png)

=== "<5>"
    ![max_capacity_greedy_step5](max_capacity_problem.assets/max_capacity_greedy_step5.png)

=== "<6>"
    ![max_capacity_greedy_step6](max_capacity_problem.assets/max_capacity_greedy_step6.png)

=== "<7>"
    ![max_capacity_greedy_step7](max_capacity_problem.assets/max_capacity_greedy_step7.png)

=== "<8>"
    ![max_capacity_greedy_step8](max_capacity_problem.assets/max_capacity_greedy_step8.png)

=== "<9>"
    ![max_capacity_greedy_step9](max_capacity_problem.assets/max_capacity_greedy_step9.png)

### 代码实现

代码循环最多 $n$ 轮，**因此时间复杂度为 $O(n)$** 。

变量 $i$、$j$、$res$ 使用常数大小额外空间，**因此空间复杂度为 $O(1)$** 。

<div class="tabbed-set tabbed-alternate" data-tabs="2:14" style="--md-indicator-x: 0px; --md-indicator-width: 68px;"><input checked="checked" id="__tabbed_2_1" name="__tabbed_2" type="radio"><input id="__tabbed_2_2" name="__tabbed_2" type="radio"><input id="__tabbed_2_3" name="__tabbed_2" type="radio"><input id="__tabbed_2_4" name="__tabbed_2" type="radio"><input id="__tabbed_2_5" name="__tabbed_2" type="radio"><input id="__tabbed_2_6" name="__tabbed_2" type="radio"><input id="__tabbed_2_7" name="__tabbed_2" type="radio"><input id="__tabbed_2_8" name="__tabbed_2" type="radio"><input id="__tabbed_2_9" name="__tabbed_2" type="radio"><input id="__tabbed_2_10" name="__tabbed_2" type="radio"><input id="__tabbed_2_11" name="__tabbed_2" type="radio"><input id="__tabbed_2_12" name="__tabbed_2" type="radio"><input id="__tabbed_2_13" name="__tabbed_2" type="radio"><input id="__tabbed_2_14" name="__tabbed_2" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_2_1"><a href="#__tabbed_2_1" tabindex="-1">Python</a></label><label for="__tabbed_2_2"><a href="#__tabbed_2_2" tabindex="-1">C++</a></label><label for="__tabbed_2_3"><a href="#__tabbed_2_3" tabindex="-1">Java</a></label><label for="__tabbed_2_4"><a href="#__tabbed_2_4" tabindex="-1">C#</a></label><label for="__tabbed_2_5"><a href="#__tabbed_2_5" tabindex="-1">Go</a></label><label for="__tabbed_2_6"><a href="#__tabbed_2_6" tabindex="-1">Swift</a></label><label for="__tabbed_2_7"><a href="#__tabbed_2_7" tabindex="-1">JS</a></label><label for="__tabbed_2_8"><a href="#__tabbed_2_8" tabindex="-1">TS</a></label><label for="__tabbed_2_9"><a href="#__tabbed_2_9" tabindex="-1">Dart</a></label><label for="__tabbed_2_10"><a href="#__tabbed_2_10" tabindex="-1">Rust</a></label><label for="__tabbed_2_11"><a href="#__tabbed_2_11" tabindex="-1">C</a></label><label for="__tabbed_2_12"><a href="#__tabbed_2_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_2_13"><a href="#__tabbed_2_13" tabindex="-1">Ruby</a></label><label for="__tabbed_2_14"><a href="#__tabbed_2_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.py</span><pre id="__code_0"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_0 > code"></button><code><a id="__codelineno-0-1" name="__codelineno-0-1" href="#__codelineno-0-1"></a><span class="k">def</span> <span class="nf">max_capacity</span><span class="p">(</span><span class="n">ht</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">])</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-0-2" name="__codelineno-0-2" href="#__codelineno-0-2"></a><span class="w">    </span><span class="sd">"""最大容量：贪心"""</span>
<a id="__codelineno-0-3" name="__codelineno-0-3" href="#__codelineno-0-3"></a>    <span class="c1"># 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-0-4" name="__codelineno-0-4" href="#__codelineno-0-4"></a>    <span class="n">i</span><span class="p">,</span> <span class="n">j</span> <span class="o">=</span> <span class="mi">0</span><span class="p">,</span> <span class="nb">len</span><span class="p">(</span><span class="n">ht</span><span class="p">)</span> <span class="o">-</span> <span class="mi">1</span>
<a id="__codelineno-0-5" name="__codelineno-0-5" href="#__codelineno-0-5"></a>    <span class="c1"># 初始最大容量为 0</span>
<a id="__codelineno-0-6" name="__codelineno-0-6" href="#__codelineno-0-6"></a>    <span class="n">res</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-0-7" name="__codelineno-0-7" href="#__codelineno-0-7"></a>    <span class="c1"># 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-0-8" name="__codelineno-0-8" href="#__codelineno-0-8"></a>    <span class="k">while</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="n">j</span><span class="p">:</span>
<a id="__codelineno-0-9" name="__codelineno-0-9" href="#__codelineno-0-9"></a>        <span class="c1"># 更新最大容量</span>
<a id="__codelineno-0-10" name="__codelineno-0-10" href="#__codelineno-0-10"></a>        <span class="n">cap</span> <span class="o">=</span> <span class="nb">min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span> <span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span> <span class="o">*</span> <span class="p">(</span><span class="n">j</span> <span class="o">-</span> <span class="n">i</span><span class="p">)</span>
<a id="__codelineno-0-11" name="__codelineno-0-11" href="#__codelineno-0-11"></a>        <span class="n">res</span> <span class="o">=</span> <span class="nb">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span> <span class="n">cap</span><span class="p">)</span>
<a id="__codelineno-0-12" name="__codelineno-0-12" href="#__codelineno-0-12"></a>        <span class="c1"># 向内移动短板</span>
<a id="__codelineno-0-13" name="__codelineno-0-13" href="#__codelineno-0-13"></a>        <span class="k">if</span> <span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&lt;</span> <span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">]:</span>
<a id="__codelineno-0-14" name="__codelineno-0-14" href="#__codelineno-0-14"></a>            <span class="n">i</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-0-15" name="__codelineno-0-15" href="#__codelineno-0-15"></a>        <span class="k">else</span><span class="p">:</span>
<a id="__codelineno-0-16" name="__codelineno-0-16" href="#__codelineno-0-16"></a>            <span class="n">j</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-0-17" name="__codelineno-0-17" href="#__codelineno-0-17"></a>    <span class="k">return</span> <span class="n">res</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.cpp</span><pre id="__code_1"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_1 > code"></button><code><a id="__codelineno-1-1" name="__codelineno-1-1" href="#__codelineno-1-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-1-2" name="__codelineno-1-2" href="#__codelineno-1-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">maxCapacity</span><span class="p">(</span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="o">&amp;</span><span class="n">ht</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-3" name="__codelineno-1-3" href="#__codelineno-1-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-1-4" name="__codelineno-1-4" href="#__codelineno-1-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-1-5" name="__codelineno-1-5" href="#__codelineno-1-5"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-1-6" name="__codelineno-1-6" href="#__codelineno-1-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-1-7" name="__codelineno-1-7" href="#__codelineno-1-7"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-1-8" name="__codelineno-1-8" href="#__codelineno-1-8"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-9" name="__codelineno-1-9" href="#__codelineno-1-9"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-1-10" name="__codelineno-1-10" href="#__codelineno-1-10"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-1-11" name="__codelineno-1-11" href="#__codelineno-1-11"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">);</span>
<a id="__codelineno-1-12" name="__codelineno-1-12" href="#__codelineno-1-12"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-1-13" name="__codelineno-1-13" href="#__codelineno-1-13"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-14" name="__codelineno-1-14" href="#__codelineno-1-14"></a><span class="w">            </span><span class="n">i</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-1-15" name="__codelineno-1-15" href="#__codelineno-1-15"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-16" name="__codelineno-1-16" href="#__codelineno-1-16"></a><span class="w">            </span><span class="n">j</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-1-17" name="__codelineno-1-17" href="#__codelineno-1-17"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-1-18" name="__codelineno-1-18" href="#__codelineno-1-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-1-19" name="__codelineno-1-19" href="#__codelineno-1-19"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-1-20" name="__codelineno-1-20" href="#__codelineno-1-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.java</span><pre id="__code_2"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_2 > code"></button><code><a id="__codelineno-2-1" name="__codelineno-2-1" href="#__codelineno-2-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-2-2" name="__codelineno-2-2" href="#__codelineno-2-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">maxCapacity</span><span class="p">(</span><span class="kt">int</span><span class="o">[]</span><span class="w"> </span><span class="n">ht</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-3" name="__codelineno-2-3" href="#__codelineno-2-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-2-4" name="__codelineno-2-4" href="#__codelineno-2-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="na">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-2-5" name="__codelineno-2-5" href="#__codelineno-2-5"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-2-6" name="__codelineno-2-6" href="#__codelineno-2-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-7" name="__codelineno-2-7" href="#__codelineno-2-7"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-2-8" name="__codelineno-2-8" href="#__codelineno-2-8"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-9" name="__codelineno-2-9" href="#__codelineno-2-9"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-2-10" name="__codelineno-2-10" href="#__codelineno-2-10"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Math</span><span class="p">.</span><span class="na">min</span><span class="p">(</span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="p">,</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-2-11" name="__codelineno-2-11" href="#__codelineno-2-11"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Math</span><span class="p">.</span><span class="na">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">);</span>
<a id="__codelineno-2-12" name="__codelineno-2-12" href="#__codelineno-2-12"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-2-13" name="__codelineno-2-13" href="#__codelineno-2-13"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-14" name="__codelineno-2-14" href="#__codelineno-2-14"></a><span class="w">            </span><span class="n">i</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-2-15" name="__codelineno-2-15" href="#__codelineno-2-15"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-16" name="__codelineno-2-16" href="#__codelineno-2-16"></a><span class="w">            </span><span class="n">j</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-2-17" name="__codelineno-2-17" href="#__codelineno-2-17"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-2-18" name="__codelineno-2-18" href="#__codelineno-2-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-19" name="__codelineno-2-19" href="#__codelineno-2-19"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-2-20" name="__codelineno-2-20" href="#__codelineno-2-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.cs</span><pre id="__code_3"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_3 > code"></button><code><a id="__codelineno-3-1" name="__codelineno-3-1" href="#__codelineno-3-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-3-2" name="__codelineno-3-2" href="#__codelineno-3-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">MaxCapacity</span><span class="p">(</span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="n">ht</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-3" name="__codelineno-3-3" href="#__codelineno-3-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-3-4" name="__codelineno-3-4" href="#__codelineno-3-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="n">Length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-3-5" name="__codelineno-3-5" href="#__codelineno-3-5"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-3-6" name="__codelineno-3-6" href="#__codelineno-3-6"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-3-7" name="__codelineno-3-7" href="#__codelineno-3-7"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-3-8" name="__codelineno-3-8" href="#__codelineno-3-8"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-9" name="__codelineno-3-9" href="#__codelineno-3-9"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-3-10" name="__codelineno-3-10" href="#__codelineno-3-10"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Math</span><span class="p">.</span><span class="n">Min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-3-11" name="__codelineno-3-11" href="#__codelineno-3-11"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Math</span><span class="p">.</span><span class="n">Max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">);</span>
<a id="__codelineno-3-12" name="__codelineno-3-12" href="#__codelineno-3-12"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-3-13" name="__codelineno-3-13" href="#__codelineno-3-13"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-14" name="__codelineno-3-14" href="#__codelineno-3-14"></a><span class="w">            </span><span class="n">i</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-3-15" name="__codelineno-3-15" href="#__codelineno-3-15"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-16" name="__codelineno-3-16" href="#__codelineno-3-16"></a><span class="w">            </span><span class="n">j</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-3-17" name="__codelineno-3-17" href="#__codelineno-3-17"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-3-18" name="__codelineno-3-18" href="#__codelineno-3-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-19" name="__codelineno-3-19" href="#__codelineno-3-19"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-3-20" name="__codelineno-3-20" href="#__codelineno-3-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.go</span><pre id="__code_4"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_4 > code"></button><code><a id="__codelineno-4-1" name="__codelineno-4-1" href="#__codelineno-4-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-4-2" name="__codelineno-4-2" href="#__codelineno-4-2"></a><span class="kd">func</span><span class="w"> </span><span class="nx">maxCapacity</span><span class="p">(</span><span class="nx">ht</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-3" name="__codelineno-4-3" href="#__codelineno-4-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-4-4" name="__codelineno-4-4" href="#__codelineno-4-4"></a><span class="w">    </span><span class="nx">i</span><span class="p">,</span><span class="w"> </span><span class="nx">j</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="nb">len</span><span class="p">(</span><span class="nx">ht</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span>
<a id="__codelineno-4-5" name="__codelineno-4-5" href="#__codelineno-4-5"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-4-6" name="__codelineno-4-6" href="#__codelineno-4-6"></a><span class="w">    </span><span class="nx">res</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-4-7" name="__codelineno-4-7" href="#__codelineno-4-7"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-4-8" name="__codelineno-4-8" href="#__codelineno-4-8"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="p">&lt;</span><span class="w"> </span><span class="nx">j</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-9" name="__codelineno-4-9" href="#__codelineno-4-9"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-4-10" name="__codelineno-4-10" href="#__codelineno-4-10"></a><span class="w">        </span><span class="nx">capacity</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">math</span><span class="p">.</span><span class="nx">Min</span><span class="p">(</span><span class="nb">float64</span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">]),</span><span class="w"> </span><span class="nb">float64</span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">])))</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="nx">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="nx">i</span><span class="p">)</span>
<a id="__codelineno-4-11" name="__codelineno-4-11" href="#__codelineno-4-11"></a><span class="w">        </span><span class="nx">res</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">int</span><span class="p">(</span><span class="nx">math</span><span class="p">.</span><span class="nx">Max</span><span class="p">(</span><span class="nb">float64</span><span class="p">(</span><span class="nx">res</span><span class="p">),</span><span class="w"> </span><span class="nb">float64</span><span class="p">(</span><span class="nx">capacity</span><span class="p">)))</span>
<a id="__codelineno-4-12" name="__codelineno-4-12" href="#__codelineno-4-12"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-4-13" name="__codelineno-4-13" href="#__codelineno-4-13"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="p">&lt;</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-14" name="__codelineno-4-14" href="#__codelineno-4-14"></a><span class="w">            </span><span class="nx">i</span><span class="o">++</span>
<a id="__codelineno-4-15" name="__codelineno-4-15" href="#__codelineno-4-15"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-16" name="__codelineno-4-16" href="#__codelineno-4-16"></a><span class="w">            </span><span class="nx">j</span><span class="o">--</span>
<a id="__codelineno-4-17" name="__codelineno-4-17" href="#__codelineno-4-17"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-4-18" name="__codelineno-4-18" href="#__codelineno-4-18"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-19" name="__codelineno-4-19" href="#__codelineno-4-19"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">res</span>
<a id="__codelineno-4-20" name="__codelineno-4-20" href="#__codelineno-4-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.swift</span><pre id="__code_5"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_5 > code"></button><code><a id="__codelineno-5-1" name="__codelineno-5-1" href="#__codelineno-5-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-5-2" name="__codelineno-5-2" href="#__codelineno-5-2"></a><span class="kd">func</span> <span class="nf">maxCapacity</span><span class="p">(</span><span class="n">ht</span><span class="p">:</span> <span class="p">[</span><span class="nb">Int</span><span class="p">])</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-5-3" name="__codelineno-5-3" href="#__codelineno-5-3"></a>    <span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-5-4" name="__codelineno-5-4" href="#__codelineno-5-4"></a>    <span class="kd">var</span> <span class="nv">i</span> <span class="p">=</span> <span class="n">ht</span><span class="p">.</span><span class="n">startIndex</span><span class="p">,</span> <span class="n">j</span> <span class="p">=</span> <span class="n">ht</span><span class="p">.</span><span class="n">endIndex</span> <span class="o">-</span> <span class="mi">1</span>
<a id="__codelineno-5-5" name="__codelineno-5-5" href="#__codelineno-5-5"></a>    <span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-5-6" name="__codelineno-5-6" href="#__codelineno-5-6"></a>    <span class="kd">var</span> <span class="nv">res</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-5-7" name="__codelineno-5-7" href="#__codelineno-5-7"></a>    <span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-5-8" name="__codelineno-5-8" href="#__codelineno-5-8"></a>    <span class="k">while</span> <span class="n">i</span> <span class="o">&lt;</span> <span class="n">j</span> <span class="p">{</span>
<a id="__codelineno-5-9" name="__codelineno-5-9" href="#__codelineno-5-9"></a>        <span class="c1">// 更新最大容量</span>
<a id="__codelineno-5-10" name="__codelineno-5-10" href="#__codelineno-5-10"></a>        <span class="kd">let</span> <span class="nv">cap</span> <span class="p">=</span> <span class="bp">min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span> <span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span> <span class="o">*</span> <span class="p">(</span><span class="n">j</span> <span class="o">-</span> <span class="n">i</span><span class="p">)</span>
<a id="__codelineno-5-11" name="__codelineno-5-11" href="#__codelineno-5-11"></a>        <span class="n">res</span> <span class="p">=</span> <span class="bp">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span> <span class="n">cap</span><span class="p">)</span>
<a id="__codelineno-5-12" name="__codelineno-5-12" href="#__codelineno-5-12"></a>        <span class="c1">// 向内移动短板</span>
<a id="__codelineno-5-13" name="__codelineno-5-13" href="#__codelineno-5-13"></a>        <span class="k">if</span> <span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&lt;</span> <span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-5-14" name="__codelineno-5-14" href="#__codelineno-5-14"></a>            <span class="n">i</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-5-15" name="__codelineno-5-15" href="#__codelineno-5-15"></a>        <span class="p">}</span> <span class="k">else</span> <span class="p">{</span>
<a id="__codelineno-5-16" name="__codelineno-5-16" href="#__codelineno-5-16"></a>            <span class="n">j</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-5-17" name="__codelineno-5-17" href="#__codelineno-5-17"></a>        <span class="p">}</span>
<a id="__codelineno-5-18" name="__codelineno-5-18" href="#__codelineno-5-18"></a>    <span class="p">}</span>
<a id="__codelineno-5-19" name="__codelineno-5-19" href="#__codelineno-5-19"></a>    <span class="k">return</span> <span class="n">res</span>
<a id="__codelineno-5-20" name="__codelineno-5-20" href="#__codelineno-5-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.js</span><pre id="__code_6"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_6 > code"></button><code><a id="__codelineno-6-1" name="__codelineno-6-1" href="#__codelineno-6-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-6-2" name="__codelineno-6-2" href="#__codelineno-6-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">maxCapacity</span><span class="p">(</span><span class="nx">ht</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-3" name="__codelineno-6-3" href="#__codelineno-6-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-6-4" name="__codelineno-6-4" href="#__codelineno-6-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">,</span>
<a id="__codelineno-6-5" name="__codelineno-6-5" href="#__codelineno-6-5"></a><span class="w">        </span><span class="nx">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">ht</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-6-6" name="__codelineno-6-6" href="#__codelineno-6-6"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-6-7" name="__codelineno-6-7" href="#__codelineno-6-7"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-6-8" name="__codelineno-6-8" href="#__codelineno-6-8"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-6-9" name="__codelineno-6-9" href="#__codelineno-6-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="nx">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-10" name="__codelineno-6-10" href="#__codelineno-6-10"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-6-11" name="__codelineno-6-11" href="#__codelineno-6-11"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">min</span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">],</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="nx">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-6-12" name="__codelineno-6-12" href="#__codelineno-6-12"></a><span class="w">        </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">max</span><span class="p">(</span><span class="nx">res</span><span class="p">,</span><span class="w"> </span><span class="nx">cap</span><span class="p">);</span>
<a id="__codelineno-6-13" name="__codelineno-6-13" href="#__codelineno-6-13"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-6-14" name="__codelineno-6-14" href="#__codelineno-6-14"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-15" name="__codelineno-6-15" href="#__codelineno-6-15"></a><span class="w">            </span><span class="nx">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-6-16" name="__codelineno-6-16" href="#__codelineno-6-16"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-17" name="__codelineno-6-17" href="#__codelineno-6-17"></a><span class="w">            </span><span class="nx">j</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-6-18" name="__codelineno-6-18" href="#__codelineno-6-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-6-19" name="__codelineno-6-19" href="#__codelineno-6-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-6-20" name="__codelineno-6-20" href="#__codelineno-6-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">res</span><span class="p">;</span>
<a id="__codelineno-6-21" name="__codelineno-6-21" href="#__codelineno-6-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.ts</span><pre id="__code_7"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_7 > code"></button><code><a id="__codelineno-7-1" name="__codelineno-7-1" href="#__codelineno-7-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-7-2" name="__codelineno-7-2" href="#__codelineno-7-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">maxCapacity</span><span class="p">(</span><span class="nx">ht</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">[])</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-3" name="__codelineno-7-3" href="#__codelineno-7-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-7-4" name="__codelineno-7-4" href="#__codelineno-7-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">,</span>
<a id="__codelineno-7-5" name="__codelineno-7-5" href="#__codelineno-7-5"></a><span class="w">        </span><span class="nx">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">ht</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-7-6" name="__codelineno-7-6" href="#__codelineno-7-6"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-7-7" name="__codelineno-7-7" href="#__codelineno-7-7"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-8" name="__codelineno-7-8" href="#__codelineno-7-8"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-7-9" name="__codelineno-7-9" href="#__codelineno-7-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="nx">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-10" name="__codelineno-7-10" href="#__codelineno-7-10"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-7-11" name="__codelineno-7-11" href="#__codelineno-7-11"></a><span class="w">        </span><span class="kd">const</span><span class="w"> </span><span class="nx">cap</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">min</span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">],</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="nx">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="nx">i</span><span class="p">);</span>
<a id="__codelineno-7-12" name="__codelineno-7-12" href="#__codelineno-7-12"></a><span class="w">        </span><span class="nx">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Math</span><span class="p">.</span><span class="nx">max</span><span class="p">(</span><span class="nx">res</span><span class="p">,</span><span class="w"> </span><span class="nx">cap</span><span class="p">);</span>
<a id="__codelineno-7-13" name="__codelineno-7-13" href="#__codelineno-7-13"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-7-14" name="__codelineno-7-14" href="#__codelineno-7-14"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">ht</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="nx">ht</span><span class="p">[</span><span class="nx">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-15" name="__codelineno-7-15" href="#__codelineno-7-15"></a><span class="w">            </span><span class="nx">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-7-16" name="__codelineno-7-16" href="#__codelineno-7-16"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-17" name="__codelineno-7-17" href="#__codelineno-7-17"></a><span class="w">            </span><span class="nx">j</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-7-18" name="__codelineno-7-18" href="#__codelineno-7-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-7-19" name="__codelineno-7-19" href="#__codelineno-7-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-20" name="__codelineno-7-20" href="#__codelineno-7-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">res</span><span class="p">;</span>
<a id="__codelineno-7-21" name="__codelineno-7-21" href="#__codelineno-7-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.dart</span><pre id="__code_8"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_8 > code"></button><code><a id="__codelineno-8-1" name="__codelineno-8-1" href="#__codelineno-8-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-8-2" name="__codelineno-8-2" href="#__codelineno-8-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">maxCapacity</span><span class="p">(</span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">ht</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-3" name="__codelineno-8-3" href="#__codelineno-8-3"></a><span class="w">  </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-8-4" name="__codelineno-8-4" href="#__codelineno-8-4"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">,</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="n">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-8-5" name="__codelineno-8-5" href="#__codelineno-8-5"></a><span class="w">  </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-8-6" name="__codelineno-8-6" href="#__codelineno-8-6"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-8-7" name="__codelineno-8-7" href="#__codelineno-8-7"></a><span class="w">  </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-8-8" name="__codelineno-8-8" href="#__codelineno-8-8"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-9" name="__codelineno-8-9" href="#__codelineno-8-9"></a><span class="w">    </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-8-10" name="__codelineno-8-10" href="#__codelineno-8-10"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-8-11" name="__codelineno-8-11" href="#__codelineno-8-11"></a><span class="w">    </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">);</span>
<a id="__codelineno-8-12" name="__codelineno-8-12" href="#__codelineno-8-12"></a><span class="w">    </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-8-13" name="__codelineno-8-13" href="#__codelineno-8-13"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-14" name="__codelineno-8-14" href="#__codelineno-8-14"></a><span class="w">      </span><span class="n">i</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-8-15" name="__codelineno-8-15" href="#__codelineno-8-15"></a><span class="w">    </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-16" name="__codelineno-8-16" href="#__codelineno-8-16"></a><span class="w">      </span><span class="n">j</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-8-17" name="__codelineno-8-17" href="#__codelineno-8-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-18" name="__codelineno-8-18" href="#__codelineno-8-18"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-8-19" name="__codelineno-8-19" href="#__codelineno-8-19"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-8-20" name="__codelineno-8-20" href="#__codelineno-8-20"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.rs</span><pre id="__code_9"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_9 > code"></button><code><a id="__codelineno-9-1" name="__codelineno-9-1" href="#__codelineno-9-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-9-2" name="__codelineno-9-2" href="#__codelineno-9-2"></a><span class="k">fn</span> <span class="nf">max_capacity</span><span class="p">(</span><span class="n">ht</span>: <span class="kp">&amp;</span><span class="p">[</span><span class="kt">i32</span><span class="p">])</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-9-3" name="__codelineno-9-3" href="#__codelineno-9-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-9-4" name="__codelineno-9-4" href="#__codelineno-9-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-9-5" name="__codelineno-9-5" href="#__codelineno-9-5"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="n">len</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-6" name="__codelineno-9-6" href="#__codelineno-9-6"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-9-7" name="__codelineno-9-7" href="#__codelineno-9-7"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-9-8" name="__codelineno-9-8" href="#__codelineno-9-8"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-9-9" name="__codelineno-9-9" href="#__codelineno-9-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-10" name="__codelineno-9-10" href="#__codelineno-9-10"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-9-11" name="__codelineno-9-11" href="#__codelineno-9-11"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span>::<span class="n">cmp</span>::<span class="n">min</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">)</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">i32</span><span class="p">;</span>
<a id="__codelineno-9-12" name="__codelineno-9-12" href="#__codelineno-9-12"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span>::<span class="n">cmp</span>::<span class="n">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">);</span>
<a id="__codelineno-9-13" name="__codelineno-9-13" href="#__codelineno-9-13"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-9-14" name="__codelineno-9-14" href="#__codelineno-9-14"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-15" name="__codelineno-9-15" href="#__codelineno-9-15"></a><span class="w">            </span><span class="n">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-16" name="__codelineno-9-16" href="#__codelineno-9-16"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-17" name="__codelineno-9-17" href="#__codelineno-9-17"></a><span class="w">            </span><span class="n">j</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-18" name="__codelineno-9-18" href="#__codelineno-9-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-9-19" name="__codelineno-9-19" href="#__codelineno-9-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-9-20" name="__codelineno-9-20" href="#__codelineno-9-20"></a><span class="w">    </span><span class="n">res</span>
<a id="__codelineno-9-21" name="__codelineno-9-21" href="#__codelineno-9-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.c</span><pre id="__code_10"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_10 > code"></button><code><a id="__codelineno-10-1" name="__codelineno-10-1" href="#__codelineno-10-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-10-2" name="__codelineno-10-2" href="#__codelineno-10-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">maxCapacity</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">ht</span><span class="p">[],</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">htLength</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-3" name="__codelineno-10-3" href="#__codelineno-10-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-10-4" name="__codelineno-10-4" href="#__codelineno-10-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-10-5" name="__codelineno-10-5" href="#__codelineno-10-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">htLength</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-10-6" name="__codelineno-10-6" href="#__codelineno-10-6"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-10-7" name="__codelineno-10-7" href="#__codelineno-10-7"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-10-8" name="__codelineno-10-8" href="#__codelineno-10-8"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-10-9" name="__codelineno-10-9" href="#__codelineno-10-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-10" name="__codelineno-10-10" href="#__codelineno-10-10"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-10-11" name="__codelineno-10-11" href="#__codelineno-10-11"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">capacity</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">myMin</span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">],</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">);</span>
<a id="__codelineno-10-12" name="__codelineno-10-12" href="#__codelineno-10-12"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">myMax</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">capacity</span><span class="p">);</span>
<a id="__codelineno-10-13" name="__codelineno-10-13" href="#__codelineno-10-13"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-10-14" name="__codelineno-10-14" href="#__codelineno-10-14"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="p">[</span><span class="n">j</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-15" name="__codelineno-10-15" href="#__codelineno-10-15"></a><span class="w">            </span><span class="n">i</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-10-16" name="__codelineno-10-16" href="#__codelineno-10-16"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-17" name="__codelineno-10-17" href="#__codelineno-10-17"></a><span class="w">            </span><span class="n">j</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-10-18" name="__codelineno-10-18" href="#__codelineno-10-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-10-19" name="__codelineno-10-19" href="#__codelineno-10-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-20" name="__codelineno-10-20" href="#__codelineno-10-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">res</span><span class="p">;</span>
<a id="__codelineno-10-21" name="__codelineno-10-21" href="#__codelineno-10-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.kt</span><pre id="__code_11"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_11 > code"></button><code><a id="__codelineno-11-1" name="__codelineno-11-1" href="#__codelineno-11-1"></a><span class="cm">/* 最大容量：贪心 */</span>
<a id="__codelineno-11-2" name="__codelineno-11-2" href="#__codelineno-11-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">maxCapacity</span><span class="p">(</span><span class="n">ht</span><span class="p">:</span><span class="w"> </span><span class="n">IntArray</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-3" name="__codelineno-11-3" href="#__codelineno-11-3"></a><span class="w">    </span><span class="c1">// 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-11-4" name="__codelineno-11-4" href="#__codelineno-11-4"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-11-5" name="__codelineno-11-5" href="#__codelineno-11-5"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">ht</span><span class="p">.</span><span class="na">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span>
<a id="__codelineno-11-6" name="__codelineno-11-6" href="#__codelineno-11-6"></a><span class="w">    </span><span class="c1">// 初始最大容量为 0</span>
<a id="__codelineno-11-7" name="__codelineno-11-7" href="#__codelineno-11-7"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-11-8" name="__codelineno-11-8" href="#__codelineno-11-8"></a><span class="w">    </span><span class="c1">// 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-11-9" name="__codelineno-11-9" href="#__codelineno-11-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-10" name="__codelineno-11-10" href="#__codelineno-11-10"></a><span class="w">        </span><span class="c1">// 更新最大容量</span>
<a id="__codelineno-11-11" name="__codelineno-11-11" href="#__codelineno-11-11"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">min</span><span class="p">(</span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="p">,</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-11-12" name="__codelineno-11-12" href="#__codelineno-11-12"></a><span class="w">        </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">max</span><span class="p">(</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="p">)</span>
<a id="__codelineno-11-13" name="__codelineno-11-13" href="#__codelineno-11-13"></a><span class="w">        </span><span class="c1">// 向内移动短板</span>
<a id="__codelineno-11-14" name="__codelineno-11-14" href="#__codelineno-11-14"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-15" name="__codelineno-11-15" href="#__codelineno-11-15"></a><span class="w">            </span><span class="n">i</span><span class="o">++</span>
<a id="__codelineno-11-16" name="__codelineno-11-16" href="#__codelineno-11-16"></a><span class="w">        </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-17" name="__codelineno-11-17" href="#__codelineno-11-17"></a><span class="w">            </span><span class="n">j</span><span class="o">--</span>
<a id="__codelineno-11-18" name="__codelineno-11-18" href="#__codelineno-11-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-11-19" name="__codelineno-11-19" href="#__codelineno-11-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-20" name="__codelineno-11-20" href="#__codelineno-11-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">res</span>
<a id="__codelineno-11-21" name="__codelineno-11-21" href="#__codelineno-11-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.rb</span><pre id="__code_12"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_12 > code"></button><code><a id="__codelineno-12-1" name="__codelineno-12-1" href="#__codelineno-12-1"></a><span class="c1">### 最大容量：贪心 ###</span>
<a id="__codelineno-12-2" name="__codelineno-12-2" href="#__codelineno-12-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">max_capacity</span><span class="p">(</span><span class="n">ht</span><span class="p">)</span>
<a id="__codelineno-12-3" name="__codelineno-12-3" href="#__codelineno-12-3"></a><span class="w">  </span><span class="c1"># 初始化 i, j，使其分列数组两端</span>
<a id="__codelineno-12-4" name="__codelineno-12-4" href="#__codelineno-12-4"></a><span class="w">  </span><span class="n">i</span><span class="p">,</span><span class="w"> </span><span class="n">j</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">ht</span><span class="o">.</span><span class="n">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-5" name="__codelineno-12-5" href="#__codelineno-12-5"></a><span class="w">  </span><span class="c1"># 初始最大容量为 0</span>
<a id="__codelineno-12-6" name="__codelineno-12-6" href="#__codelineno-12-6"></a><span class="w">  </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-12-7" name="__codelineno-12-7" href="#__codelineno-12-7"></a>
<a id="__codelineno-12-8" name="__codelineno-12-8" href="#__codelineno-12-8"></a><span class="w">  </span><span class="c1"># 循环贪心选择，直至两板相遇</span>
<a id="__codelineno-12-9" name="__codelineno-12-9" href="#__codelineno-12-9"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">j</span>
<a id="__codelineno-12-10" name="__codelineno-12-10" href="#__codelineno-12-10"></a><span class="w">    </span><span class="c1"># 更新最大容量</span>
<a id="__codelineno-12-11" name="__codelineno-12-11" href="#__codelineno-12-11"></a><span class="w">    </span><span class="n">cap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[</span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="p">,</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]].</span><span class="n">min</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="p">(</span><span class="n">j</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="n">i</span><span class="p">)</span>
<a id="__codelineno-12-12" name="__codelineno-12-12" href="#__codelineno-12-12"></a><span class="w">    </span><span class="n">res</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[</span><span class="n">res</span><span class="p">,</span><span class="w"> </span><span class="n">cap</span><span class="o">].</span><span class="n">max</span>
<a id="__codelineno-12-13" name="__codelineno-12-13" href="#__codelineno-12-13"></a><span class="w">    </span><span class="c1"># 向内移动短板</span>
<a id="__codelineno-12-14" name="__codelineno-12-14" href="#__codelineno-12-14"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">ht</span><span class="o">[</span><span class="n">j</span><span class="o">]</span>
<a id="__codelineno-12-15" name="__codelineno-12-15" href="#__codelineno-12-15"></a><span class="w">      </span><span class="n">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-16" name="__codelineno-12-16" href="#__codelineno-12-16"></a><span class="w">    </span><span class="k">else</span>
<a id="__codelineno-12-17" name="__codelineno-12-17" href="#__codelineno-12-17"></a><span class="w">      </span><span class="n">j</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-18" name="__codelineno-12-18" href="#__codelineno-12-18"></a><span class="w">    </span><span class="k">end</span>
<a id="__codelineno-12-19" name="__codelineno-12-19" href="#__codelineno-12-19"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-12-20" name="__codelineno-12-20" href="#__codelineno-12-20"></a>
<a id="__codelineno-12-21" name="__codelineno-12-21" href="#__codelineno-12-21"></a><span class="w">  </span><span class="n">res</span>
<a id="__codelineno-12-22" name="__codelineno-12-22" href="#__codelineno-12-22"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">max_capacity.zig</span><pre id="__code_13"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_13 > code"></button><code><a id="__codelineno-13-1" name="__codelineno-13-1" href="#__codelineno-13-1"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">maxCapacity</span><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>

### 正确性证明

之所以贪心比穷举更快，是因为每轮的贪心选择都会“跳过”一些状态。

比如在状态 $cap[i, j]$ 下，$i$ 为短板、$j$ 为长板。若贪心地将短板 $i$ 向内移动一格，会导致下图所示的状态被“跳过”。**这意味着之后无法验证这些状态的容量大小**。

$$
cap[i, i+1], cap[i, i+2], \dots, cap[i, j-2], cap[i, j-1]
$$

![移动短板导致被跳过的状态](max_capacity_problem.assets/max_capacity_skipped_states.png)

观察发现，**这些被跳过的状态实际上就是将长板 $j$ 向内移动的所有状态**。而在第二步中，我们已经证明内移长板一定会导致容量变小。也就是说，被跳过的状态都不可能是最优解，**跳过它们不会导致错过最优解**。

以上的分析说明，**移动短板的操作是“安全”的**，贪心策略是有效的。
