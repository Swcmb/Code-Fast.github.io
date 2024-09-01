# 贪心算法

「贪心算法 greedy algorithm」是一种常见的解决优化问题的算法，其基本思想是在问题的每个决策阶段，都选择当前看起来最优的选择，即贪心地做出局部最优的决策，以期望获得全局最优解。贪心算法简洁且高效，在许多实际问题中都有着广泛的应用。

贪心算法和动态规划都常用于解决优化问题。它们之间存在一些相似之处，比如都依赖最优子结构性质，但工作原理是不同的。

- 动态规划会根据之前阶段的所有决策来考虑当前决策，并使用过去子问题的解来构建当前子问题的解。
- 贪心算法不会重新考虑过去的决策，而是一路向前地进行贪心选择，不断缩小问题范围，直至问题被解决。

我们先通过例题“零钱兑换”了解贪心算法的工作原理。这道题已经在动态规划章节中介绍过，相信你对它并不陌生。

!!! question

    给定 $n$ 种硬币，第 $i$ 种硬币的面值为 $coins[i - 1]$ ，目标金额为 $amt$ ，每种硬币可以重复选取，问能够凑出目标金额的最少硬币个数。如果无法凑出目标金额则返回 $-1$ 。

本题的贪心策略如下图所示。给定目标金额，**我们贪心地选择不大于且最接近它的硬币**，不断循环该步骤，直至凑出目标金额为止。

![零钱兑换的贪心策略](greedy_algorithm.assets/coin_change_greedy_strategy.png)

实现代码如下所示。你可能会不由地发出感叹：So Clean ！贪心算法仅用十行代码就解决了零钱兑换问题。

<div class="tabbed-set tabbed-alternate" data-tabs="1:14" style="--md-indicator-x: 0px; --md-indicator-width: 68px;"><input checked="checked" id="__tabbed_1_1" name="__tabbed_1" type="radio"><input id="__tabbed_1_2" name="__tabbed_1" type="radio"><input id="__tabbed_1_3" name="__tabbed_1" type="radio"><input id="__tabbed_1_4" name="__tabbed_1" type="radio"><input id="__tabbed_1_5" name="__tabbed_1" type="radio"><input id="__tabbed_1_6" name="__tabbed_1" type="radio"><input id="__tabbed_1_7" name="__tabbed_1" type="radio"><input id="__tabbed_1_8" name="__tabbed_1" type="radio"><input id="__tabbed_1_9" name="__tabbed_1" type="radio"><input id="__tabbed_1_10" name="__tabbed_1" type="radio"><input id="__tabbed_1_11" name="__tabbed_1" type="radio"><input id="__tabbed_1_12" name="__tabbed_1" type="radio"><input id="__tabbed_1_13" name="__tabbed_1" type="radio"><input id="__tabbed_1_14" name="__tabbed_1" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_1_1"><a href="#__tabbed_1_1" tabindex="-1">Python</a></label><label for="__tabbed_1_2"><a href="#__tabbed_1_2" tabindex="-1">C++</a></label><label for="__tabbed_1_3"><a href="#__tabbed_1_3" tabindex="-1">Java</a></label><label for="__tabbed_1_4"><a href="#__tabbed_1_4" tabindex="-1">C#</a></label><label for="__tabbed_1_5"><a href="#__tabbed_1_5" tabindex="-1">Go</a></label><label for="__tabbed_1_6"><a href="#__tabbed_1_6" tabindex="-1">Swift</a></label><label for="__tabbed_1_7"><a href="#__tabbed_1_7" tabindex="-1">JS</a></label><label for="__tabbed_1_8"><a href="#__tabbed_1_8" tabindex="-1">TS</a></label><label for="__tabbed_1_9"><a href="#__tabbed_1_9" tabindex="-1">Dart</a></label><label for="__tabbed_1_10"><a href="#__tabbed_1_10" tabindex="-1">Rust</a></label><label for="__tabbed_1_11"><a href="#__tabbed_1_11" tabindex="-1">C</a></label><label for="__tabbed_1_12"><a href="#__tabbed_1_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_1_13"><a href="#__tabbed_1_13" tabindex="-1">Ruby</a></label><label for="__tabbed_1_14"><a href="#__tabbed_1_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.py</span><pre id="__code_0"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_0 > code"></button><code><a id="__codelineno-0-1" name="__codelineno-0-1" href="#__codelineno-0-1"></a><span class="k">def</span> <span class="nf">coin_change_greedy</span><span class="p">(</span><span class="n">coins</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">],</span> <span class="n">amt</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-0-2" name="__codelineno-0-2" href="#__codelineno-0-2"></a><span class="w">    </span><span class="sd">"""零钱兑换：贪心"""</span>
<a id="__codelineno-0-3" name="__codelineno-0-3" href="#__codelineno-0-3"></a>    <span class="c1"># 假设 coins 列表有序</span>
<a id="__codelineno-0-4" name="__codelineno-0-4" href="#__codelineno-0-4"></a>    <span class="n">i</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">coins</span><span class="p">)</span> <span class="o">-</span> <span class="mi">1</span>
<a id="__codelineno-0-5" name="__codelineno-0-5" href="#__codelineno-0-5"></a>    <span class="n">count</span> <span class="o">=</span> <span class="mi">0</span>
<a id="__codelineno-0-6" name="__codelineno-0-6" href="#__codelineno-0-6"></a>    <span class="c1"># 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-0-7" name="__codelineno-0-7" href="#__codelineno-0-7"></a>    <span class="k">while</span> <span class="n">amt</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
<a id="__codelineno-0-8" name="__codelineno-0-8" href="#__codelineno-0-8"></a>        <span class="c1"># 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-0-9" name="__codelineno-0-9" href="#__codelineno-0-9"></a>        <span class="k">while</span> <span class="n">i</span> <span class="o">&gt;</span> <span class="mi">0</span> <span class="ow">and</span> <span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&gt;</span> <span class="n">amt</span><span class="p">:</span>
<a id="__codelineno-0-10" name="__codelineno-0-10" href="#__codelineno-0-10"></a>            <span class="n">i</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-0-11" name="__codelineno-0-11" href="#__codelineno-0-11"></a>        <span class="c1"># 选择 coins[i]</span>
<a id="__codelineno-0-12" name="__codelineno-0-12" href="#__codelineno-0-12"></a>        <span class="n">amt</span> <span class="o">-=</span> <span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span>
<a id="__codelineno-0-13" name="__codelineno-0-13" href="#__codelineno-0-13"></a>        <span class="n">count</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-0-14" name="__codelineno-0-14" href="#__codelineno-0-14"></a>    <span class="c1"># 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-0-15" name="__codelineno-0-15" href="#__codelineno-0-15"></a>    <span class="k">return</span> <span class="n">count</span> <span class="k">if</span> <span class="n">amt</span> <span class="o">==</span> <span class="mi">0</span> <span class="k">else</span> <span class="o">-</span><span class="mi">1</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.cpp</span><pre id="__code_1"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_1 > code"></button><code><a id="__codelineno-1-1" name="__codelineno-1-1" href="#__codelineno-1-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-1-2" name="__codelineno-1-2" href="#__codelineno-1-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">coinChangeGreedy</span><span class="p">(</span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="o">&amp;</span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-3" name="__codelineno-1-3" href="#__codelineno-1-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-1-4" name="__codelineno-1-4" href="#__codelineno-1-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="n">size</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-1-5" name="__codelineno-1-5" href="#__codelineno-1-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-1-6" name="__codelineno-1-6" href="#__codelineno-1-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-1-7" name="__codelineno-1-7" href="#__codelineno-1-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-8" name="__codelineno-1-8" href="#__codelineno-1-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-1-9" name="__codelineno-1-9" href="#__codelineno-1-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-1-10" name="__codelineno-1-10" href="#__codelineno-1-10"></a><span class="w">            </span><span class="n">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-1-11" name="__codelineno-1-11" href="#__codelineno-1-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-1-12" name="__codelineno-1-12" href="#__codelineno-1-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-1-13" name="__codelineno-1-13" href="#__codelineno-1-13"></a><span class="w">        </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-1-14" name="__codelineno-1-14" href="#__codelineno-1-14"></a><span class="w">        </span><span class="n">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-1-15" name="__codelineno-1-15" href="#__codelineno-1-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-1-16" name="__codelineno-1-16" href="#__codelineno-1-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-1-17" name="__codelineno-1-17" href="#__codelineno-1-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="mi">-1</span><span class="p">;</span>
<a id="__codelineno-1-18" name="__codelineno-1-18" href="#__codelineno-1-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.java</span><pre id="__code_2"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_2 > code"></button><code><a id="__codelineno-2-1" name="__codelineno-2-1" href="#__codelineno-2-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-2-2" name="__codelineno-2-2" href="#__codelineno-2-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">coinChangeGreedy</span><span class="p">(</span><span class="kt">int</span><span class="o">[]</span><span class="w"> </span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-3" name="__codelineno-2-3" href="#__codelineno-2-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-2-4" name="__codelineno-2-4" href="#__codelineno-2-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="na">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-2-5" name="__codelineno-2-5" href="#__codelineno-2-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-2-6" name="__codelineno-2-6" href="#__codelineno-2-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-2-7" name="__codelineno-2-7" href="#__codelineno-2-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-8" name="__codelineno-2-8" href="#__codelineno-2-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-2-9" name="__codelineno-2-9" href="#__codelineno-2-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-2-10" name="__codelineno-2-10" href="#__codelineno-2-10"></a><span class="w">            </span><span class="n">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-2-11" name="__codelineno-2-11" href="#__codelineno-2-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-2-12" name="__codelineno-2-12" href="#__codelineno-2-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-2-13" name="__codelineno-2-13" href="#__codelineno-2-13"></a><span class="w">        </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="p">;</span>
<a id="__codelineno-2-14" name="__codelineno-2-14" href="#__codelineno-2-14"></a><span class="w">        </span><span class="n">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-2-15" name="__codelineno-2-15" href="#__codelineno-2-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-2-16" name="__codelineno-2-16" href="#__codelineno-2-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-2-17" name="__codelineno-2-17" href="#__codelineno-2-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="o">-</span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-2-18" name="__codelineno-2-18" href="#__codelineno-2-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.cs</span><pre id="__code_3"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_3 > code"></button><code><a id="__codelineno-3-1" name="__codelineno-3-1" href="#__codelineno-3-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-3-2" name="__codelineno-3-2" href="#__codelineno-3-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">CoinChangeGreedy</span><span class="p">(</span><span class="kt">int</span><span class="p">[]</span><span class="w"> </span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-3" name="__codelineno-3-3" href="#__codelineno-3-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-3-4" name="__codelineno-3-4" href="#__codelineno-3-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="n">Length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-3-5" name="__codelineno-3-5" href="#__codelineno-3-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-3-6" name="__codelineno-3-6" href="#__codelineno-3-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-3-7" name="__codelineno-3-7" href="#__codelineno-3-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-8" name="__codelineno-3-8" href="#__codelineno-3-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-3-9" name="__codelineno-3-9" href="#__codelineno-3-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-3-10" name="__codelineno-3-10" href="#__codelineno-3-10"></a><span class="w">            </span><span class="n">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-3-11" name="__codelineno-3-11" href="#__codelineno-3-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-3-12" name="__codelineno-3-12" href="#__codelineno-3-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-3-13" name="__codelineno-3-13" href="#__codelineno-3-13"></a><span class="w">        </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-3-14" name="__codelineno-3-14" href="#__codelineno-3-14"></a><span class="w">        </span><span class="n">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-3-15" name="__codelineno-3-15" href="#__codelineno-3-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-3-16" name="__codelineno-3-16" href="#__codelineno-3-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-3-17" name="__codelineno-3-17" href="#__codelineno-3-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="o">-</span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-3-18" name="__codelineno-3-18" href="#__codelineno-3-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.go</span><pre id="__code_4"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_4 > code"></button><code><a id="__codelineno-4-1" name="__codelineno-4-1" href="#__codelineno-4-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-4-2" name="__codelineno-4-2" href="#__codelineno-4-2"></a><span class="kd">func</span><span class="w"> </span><span class="nx">coinChangeGreedy</span><span class="p">(</span><span class="nx">coins</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="p">,</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-3" name="__codelineno-4-3" href="#__codelineno-4-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-4-4" name="__codelineno-4-4" href="#__codelineno-4-4"></a><span class="w">    </span><span class="nx">i</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nb">len</span><span class="p">(</span><span class="nx">coins</span><span class="p">)</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-4-5" name="__codelineno-4-5" href="#__codelineno-4-5"></a><span class="w">    </span><span class="nx">count</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-4-6" name="__codelineno-4-6" href="#__codelineno-4-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-4-7" name="__codelineno-4-7" href="#__codelineno-4-7"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="p">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-8" name="__codelineno-4-8" href="#__codelineno-4-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-4-9" name="__codelineno-4-9" href="#__codelineno-4-9"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="p">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="p">&gt;</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-10" name="__codelineno-4-10" href="#__codelineno-4-10"></a><span class="w">            </span><span class="nx">i</span><span class="o">--</span>
<a id="__codelineno-4-11" name="__codelineno-4-11" href="#__codelineno-4-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-4-12" name="__codelineno-4-12" href="#__codelineno-4-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-4-13" name="__codelineno-4-13" href="#__codelineno-4-13"></a><span class="w">        </span><span class="nx">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span>
<a id="__codelineno-4-14" name="__codelineno-4-14" href="#__codelineno-4-14"></a><span class="w">        </span><span class="nx">count</span><span class="o">++</span>
<a id="__codelineno-4-15" name="__codelineno-4-15" href="#__codelineno-4-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-16" name="__codelineno-4-16" href="#__codelineno-4-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-4-17" name="__codelineno-4-17" href="#__codelineno-4-17"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-4-18" name="__codelineno-4-18" href="#__codelineno-4-18"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="o">-</span><span class="mi">1</span>
<a id="__codelineno-4-19" name="__codelineno-4-19" href="#__codelineno-4-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-4-20" name="__codelineno-4-20" href="#__codelineno-4-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">count</span>
<a id="__codelineno-4-21" name="__codelineno-4-21" href="#__codelineno-4-21"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.swift</span><pre id="__code_5"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_5 > code"></button><code><a id="__codelineno-5-1" name="__codelineno-5-1" href="#__codelineno-5-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-5-2" name="__codelineno-5-2" href="#__codelineno-5-2"></a><span class="kd">func</span> <span class="nf">coinChangeGreedy</span><span class="p">(</span><span class="n">coins</span><span class="p">:</span> <span class="p">[</span><span class="nb">Int</span><span class="p">],</span> <span class="n">amt</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-5-3" name="__codelineno-5-3" href="#__codelineno-5-3"></a>    <span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-5-4" name="__codelineno-5-4" href="#__codelineno-5-4"></a>    <span class="kd">var</span> <span class="nv">i</span> <span class="p">=</span> <span class="n">coins</span><span class="p">.</span><span class="bp">count</span> <span class="o">-</span> <span class="mi">1</span>
<a id="__codelineno-5-5" name="__codelineno-5-5" href="#__codelineno-5-5"></a>    <span class="kd">var</span> <span class="nv">count</span> <span class="p">=</span> <span class="mi">0</span>
<a id="__codelineno-5-6" name="__codelineno-5-6" href="#__codelineno-5-6"></a>    <span class="kd">var</span> <span class="nv">amt</span> <span class="p">=</span> <span class="n">amt</span>
<a id="__codelineno-5-7" name="__codelineno-5-7" href="#__codelineno-5-7"></a>    <span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-5-8" name="__codelineno-5-8" href="#__codelineno-5-8"></a>    <span class="k">while</span> <span class="n">amt</span> <span class="o">&gt;</span> <span class="mi">0</span> <span class="p">{</span>
<a id="__codelineno-5-9" name="__codelineno-5-9" href="#__codelineno-5-9"></a>        <span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-5-10" name="__codelineno-5-10" href="#__codelineno-5-10"></a>        <span class="k">while</span> <span class="n">i</span> <span class="o">&gt;</span> <span class="mi">0</span> <span class="o">&amp;&amp;</span> <span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span> <span class="o">&gt;</span> <span class="n">amt</span> <span class="p">{</span>
<a id="__codelineno-5-11" name="__codelineno-5-11" href="#__codelineno-5-11"></a>            <span class="n">i</span> <span class="o">-=</span> <span class="mi">1</span>
<a id="__codelineno-5-12" name="__codelineno-5-12" href="#__codelineno-5-12"></a>        <span class="p">}</span>
<a id="__codelineno-5-13" name="__codelineno-5-13" href="#__codelineno-5-13"></a>        <span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-5-14" name="__codelineno-5-14" href="#__codelineno-5-14"></a>        <span class="n">amt</span> <span class="o">-=</span> <span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span>
<a id="__codelineno-5-15" name="__codelineno-5-15" href="#__codelineno-5-15"></a>        <span class="bp">count</span> <span class="o">+=</span> <span class="mi">1</span>
<a id="__codelineno-5-16" name="__codelineno-5-16" href="#__codelineno-5-16"></a>    <span class="p">}</span>
<a id="__codelineno-5-17" name="__codelineno-5-17" href="#__codelineno-5-17"></a>    <span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-5-18" name="__codelineno-5-18" href="#__codelineno-5-18"></a>    <span class="k">return</span> <span class="n">amt</span> <span class="p">==</span> <span class="mi">0</span> <span class="p">?</span> <span class="bp">count</span> <span class="p">:</span> <span class="o">-</span><span class="mi">1</span>
<a id="__codelineno-5-19" name="__codelineno-5-19" href="#__codelineno-5-19"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.js</span><pre id="__code_6"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_6 > code"></button><code><a id="__codelineno-6-1" name="__codelineno-6-1" href="#__codelineno-6-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-6-2" name="__codelineno-6-2" href="#__codelineno-6-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">coinChangeGreedy</span><span class="p">(</span><span class="nx">coins</span><span class="p">,</span><span class="w"> </span><span class="nx">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-3" name="__codelineno-6-3" href="#__codelineno-6-3"></a><span class="w">    </span><span class="c1">// 假设 coins 数组有序</span>
<a id="__codelineno-6-4" name="__codelineno-6-4" href="#__codelineno-6-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">coins</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-6-5" name="__codelineno-6-5" href="#__codelineno-6-5"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-6-6" name="__codelineno-6-6" href="#__codelineno-6-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-6-7" name="__codelineno-6-7" href="#__codelineno-6-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mf">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-8" name="__codelineno-6-8" href="#__codelineno-6-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-6-9" name="__codelineno-6-9" href="#__codelineno-6-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="nx">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-6-10" name="__codelineno-6-10" href="#__codelineno-6-10"></a><span class="w">            </span><span class="nx">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-6-11" name="__codelineno-6-11" href="#__codelineno-6-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-6-12" name="__codelineno-6-12" href="#__codelineno-6-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-6-13" name="__codelineno-6-13" href="#__codelineno-6-13"></a><span class="w">        </span><span class="nx">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">];</span>
<a id="__codelineno-6-14" name="__codelineno-6-14" href="#__codelineno-6-14"></a><span class="w">        </span><span class="nx">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-6-15" name="__codelineno-6-15" href="#__codelineno-6-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-6-16" name="__codelineno-6-16" href="#__codelineno-6-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-6-17" name="__codelineno-6-17" href="#__codelineno-6-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="nx">count</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="o">-</span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-6-18" name="__codelineno-6-18" href="#__codelineno-6-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.ts</span><pre id="__code_7"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_7 > code"></button><code><a id="__codelineno-7-1" name="__codelineno-7-1" href="#__codelineno-7-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-7-2" name="__codelineno-7-2" href="#__codelineno-7-2"></a><span class="kd">function</span><span class="w"> </span><span class="nx">coinChangeGreedy</span><span class="p">(</span><span class="nx">coins</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">[],</span><span class="w"> </span><span class="nx">amt</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-3" name="__codelineno-7-3" href="#__codelineno-7-3"></a><span class="w">    </span><span class="c1">// 假设 coins 数组有序</span>
<a id="__codelineno-7-4" name="__codelineno-7-4" href="#__codelineno-7-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">coins</span><span class="p">.</span><span class="nx">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-7-5" name="__codelineno-7-5" href="#__codelineno-7-5"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="nx">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span>
<a id="__codelineno-7-6" name="__codelineno-7-6" href="#__codelineno-7-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-7-7" name="__codelineno-7-7" href="#__codelineno-7-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mf">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-8" name="__codelineno-7-8" href="#__codelineno-7-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-7-9" name="__codelineno-7-9" href="#__codelineno-7-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="nx">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="nx">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-7-10" name="__codelineno-7-10" href="#__codelineno-7-10"></a><span class="w">            </span><span class="nx">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-7-11" name="__codelineno-7-11" href="#__codelineno-7-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-7-12" name="__codelineno-7-12" href="#__codelineno-7-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-7-13" name="__codelineno-7-13" href="#__codelineno-7-13"></a><span class="w">        </span><span class="nx">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="nx">coins</span><span class="p">[</span><span class="nx">i</span><span class="p">];</span>
<a id="__codelineno-7-14" name="__codelineno-7-14" href="#__codelineno-7-14"></a><span class="w">        </span><span class="nx">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-7-15" name="__codelineno-7-15" href="#__codelineno-7-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-7-16" name="__codelineno-7-16" href="#__codelineno-7-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-7-17" name="__codelineno-7-17" href="#__codelineno-7-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">amt</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="mf">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="nx">count</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="o">-</span><span class="mf">1</span><span class="p">;</span>
<a id="__codelineno-7-18" name="__codelineno-7-18" href="#__codelineno-7-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.dart</span><pre id="__code_8"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_8 > code"></button><code><a id="__codelineno-8-1" name="__codelineno-8-1" href="#__codelineno-8-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-8-2" name="__codelineno-8-2" href="#__codelineno-8-2"></a><span class="kt">int</span><span class="w"> </span><span class="n">coinChangeGreedy</span><span class="p">(</span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-3" name="__codelineno-8-3" href="#__codelineno-8-3"></a><span class="w">  </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-8-4" name="__codelineno-8-4" href="#__codelineno-8-4"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="n">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-8-5" name="__codelineno-8-5" href="#__codelineno-8-5"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span>
<a id="__codelineno-8-6" name="__codelineno-8-6" href="#__codelineno-8-6"></a><span class="w">  </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-8-7" name="__codelineno-8-7" href="#__codelineno-8-7"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-8" name="__codelineno-8-8" href="#__codelineno-8-8"></a><span class="w">    </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-8-9" name="__codelineno-8-9" href="#__codelineno-8-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-8-10" name="__codelineno-8-10" href="#__codelineno-8-10"></a><span class="w">      </span><span class="n">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-8-11" name="__codelineno-8-11" href="#__codelineno-8-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-8-12" name="__codelineno-8-12" href="#__codelineno-8-12"></a><span class="w">    </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-8-13" name="__codelineno-8-13" href="#__codelineno-8-13"></a><span class="w">    </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-8-14" name="__codelineno-8-14" href="#__codelineno-8-14"></a><span class="w">    </span><span class="n">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-8-15" name="__codelineno-8-15" href="#__codelineno-8-15"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-8-16" name="__codelineno-8-16" href="#__codelineno-8-16"></a><span class="w">  </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-8-17" name="__codelineno-8-17" href="#__codelineno-8-17"></a><span class="w">  </span><span class="k">return</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="o">-</span><span class="m">1</span><span class="p">;</span>
<a id="__codelineno-8-18" name="__codelineno-8-18" href="#__codelineno-8-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.rs</span><pre id="__code_9"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_9 > code"></button><code><a id="__codelineno-9-1" name="__codelineno-9-1" href="#__codelineno-9-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-9-2" name="__codelineno-9-2" href="#__codelineno-9-2"></a><span class="k">fn</span> <span class="nf">coin_change_greedy</span><span class="p">(</span><span class="n">coins</span>: <span class="kp">&amp;</span><span class="p">[</span><span class="kt">i32</span><span class="p">],</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">amt</span>: <span class="kt">i32</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">i32</span> <span class="p">{</span>
<a id="__codelineno-9-3" name="__codelineno-9-3" href="#__codelineno-9-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-9-4" name="__codelineno-9-4" href="#__codelineno-9-4"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="n">len</span><span class="p">()</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-5" name="__codelineno-9-5" href="#__codelineno-9-5"></a><span class="w">    </span><span class="kd">let</span><span class="w"> </span><span class="k">mut</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-9-6" name="__codelineno-9-6" href="#__codelineno-9-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-9-7" name="__codelineno-9-7" href="#__codelineno-9-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-8" name="__codelineno-9-8" href="#__codelineno-9-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-9-9" name="__codelineno-9-9" href="#__codelineno-9-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-10" name="__codelineno-9-10" href="#__codelineno-9-10"></a><span class="w">            </span><span class="n">i</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-11" name="__codelineno-9-11" href="#__codelineno-9-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-9-12" name="__codelineno-9-12" href="#__codelineno-9-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-9-13" name="__codelineno-9-13" href="#__codelineno-9-13"></a><span class="w">        </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-9-14" name="__codelineno-9-14" href="#__codelineno-9-14"></a><span class="w">        </span><span class="n">count</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-9-15" name="__codelineno-9-15" href="#__codelineno-9-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-9-16" name="__codelineno-9-16" href="#__codelineno-9-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-9-17" name="__codelineno-9-17" href="#__codelineno-9-17"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-18" name="__codelineno-9-18" href="#__codelineno-9-18"></a><span class="w">        </span><span class="n">count</span>
<a id="__codelineno-9-19" name="__codelineno-9-19" href="#__codelineno-9-19"></a><span class="w">    </span><span class="p">}</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-9-20" name="__codelineno-9-20" href="#__codelineno-9-20"></a><span class="w">        </span><span class="o">-</span><span class="mi">1</span>
<a id="__codelineno-9-21" name="__codelineno-9-21" href="#__codelineno-9-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-9-22" name="__codelineno-9-22" href="#__codelineno-9-22"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.c</span><pre id="__code_10"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_10 > code"></button><code><a id="__codelineno-10-1" name="__codelineno-10-1" href="#__codelineno-10-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-10-2" name="__codelineno-10-2" href="#__codelineno-10-2"></a><span class="kt">int</span><span class="w"> </span><span class="nf">coinChangeGreedy</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="o">*</span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">size</span><span class="p">,</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-3" name="__codelineno-10-3" href="#__codelineno-10-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-10-4" name="__codelineno-10-4" href="#__codelineno-10-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span><span class="p">;</span>
<a id="__codelineno-10-5" name="__codelineno-10-5" href="#__codelineno-10-5"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-10-6" name="__codelineno-10-6" href="#__codelineno-10-6"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-10-7" name="__codelineno-10-7" href="#__codelineno-10-7"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-8" name="__codelineno-10-8" href="#__codelineno-10-8"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-10-9" name="__codelineno-10-9" href="#__codelineno-10-9"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-10-10" name="__codelineno-10-10" href="#__codelineno-10-10"></a><span class="w">            </span><span class="n">i</span><span class="o">--</span><span class="p">;</span>
<a id="__codelineno-10-11" name="__codelineno-10-11" href="#__codelineno-10-11"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-10-12" name="__codelineno-10-12" href="#__codelineno-10-12"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-10-13" name="__codelineno-10-13" href="#__codelineno-10-13"></a><span class="w">        </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="p">[</span><span class="n">i</span><span class="p">];</span>
<a id="__codelineno-10-14" name="__codelineno-10-14" href="#__codelineno-10-14"></a><span class="w">        </span><span class="n">count</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-10-15" name="__codelineno-10-15" href="#__codelineno-10-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-10-16" name="__codelineno-10-16" href="#__codelineno-10-16"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-10-17" name="__codelineno-10-17" href="#__codelineno-10-17"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="mi">-1</span><span class="p">;</span>
<a id="__codelineno-10-18" name="__codelineno-10-18" href="#__codelineno-10-18"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.kt</span><pre id="__code_11"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_11 > code"></button><code><a id="__codelineno-11-1" name="__codelineno-11-1" href="#__codelineno-11-1"></a><span class="cm">/* 零钱兑换：贪心 */</span>
<a id="__codelineno-11-2" name="__codelineno-11-2" href="#__codelineno-11-2"></a><span class="kd">fun</span><span class="w"> </span><span class="nf">coinChangeGreedy</span><span class="p">(</span><span class="n">coins</span><span class="p">:</span><span class="w"> </span><span class="n">IntArray</span><span class="p">,</span><span class="w"> </span><span class="n">amt</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-3" name="__codelineno-11-3" href="#__codelineno-11-3"></a><span class="w">    </span><span class="c1">// 假设 coins 列表有序</span>
<a id="__codelineno-11-4" name="__codelineno-11-4" href="#__codelineno-11-4"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">am</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">amt</span>
<a id="__codelineno-11-5" name="__codelineno-11-5" href="#__codelineno-11-5"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="p">.</span><span class="na">size</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="m">1</span>
<a id="__codelineno-11-6" name="__codelineno-11-6" href="#__codelineno-11-6"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span>
<a id="__codelineno-11-7" name="__codelineno-11-7" href="#__codelineno-11-7"></a><span class="w">    </span><span class="c1">// 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-11-8" name="__codelineno-11-8" href="#__codelineno-11-8"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">am</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-9" name="__codelineno-11-9" href="#__codelineno-11-9"></a><span class="w">        </span><span class="c1">// 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-11-10" name="__codelineno-11-10" href="#__codelineno-11-10"></a><span class="w">        </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="m">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">am</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-11-11" name="__codelineno-11-11" href="#__codelineno-11-11"></a><span class="w">            </span><span class="n">i</span><span class="o">--</span>
<a id="__codelineno-11-12" name="__codelineno-11-12" href="#__codelineno-11-12"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-11-13" name="__codelineno-11-13" href="#__codelineno-11-13"></a><span class="w">        </span><span class="c1">// 选择 coins[i]</span>
<a id="__codelineno-11-14" name="__codelineno-11-14" href="#__codelineno-11-14"></a><span class="w">        </span><span class="n">am</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span>
<a id="__codelineno-11-15" name="__codelineno-11-15" href="#__codelineno-11-15"></a><span class="w">        </span><span class="n">count</span><span class="o">++</span>
<a id="__codelineno-11-16" name="__codelineno-11-16" href="#__codelineno-11-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-11-17" name="__codelineno-11-17" href="#__codelineno-11-17"></a><span class="w">    </span><span class="c1">// 若未找到可行方案，则返回 -1</span>
<a id="__codelineno-11-18" name="__codelineno-11-18" href="#__codelineno-11-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">am</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="m">0</span><span class="p">)</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="k">else</span><span class="w"> </span><span class="o">-</span><span class="m">1</span>
<a id="__codelineno-11-19" name="__codelineno-11-19" href="#__codelineno-11-19"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.rb</span><pre id="__code_12"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_12 > code"></button><code><a id="__codelineno-12-1" name="__codelineno-12-1" href="#__codelineno-12-1"></a><span class="c1">### 零钱兑换：贪心 ###</span>
<a id="__codelineno-12-2" name="__codelineno-12-2" href="#__codelineno-12-2"></a><span class="k">def</span><span class="w"> </span><span class="nf">coin_change_greedy</span><span class="p">(</span><span class="n">coins</span><span class="p">,</span><span class="w"> </span><span class="n">amt</span><span class="p">)</span>
<a id="__codelineno-12-3" name="__codelineno-12-3" href="#__codelineno-12-3"></a><span class="w">  </span><span class="c1"># 假设 coins 列表有序</span>
<a id="__codelineno-12-4" name="__codelineno-12-4" href="#__codelineno-12-4"></a><span class="w">  </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">coins</span><span class="o">.</span><span class="n">length</span><span class="w"> </span><span class="o">-</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-5" name="__codelineno-12-5" href="#__codelineno-12-5"></a><span class="w">  </span><span class="n">count</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-12-6" name="__codelineno-12-6" href="#__codelineno-12-6"></a><span class="w">  </span><span class="c1"># 循环进行贪心选择，直到无剩余金额</span>
<a id="__codelineno-12-7" name="__codelineno-12-7" href="#__codelineno-12-7"></a><span class="w">  </span><span class="k">while</span><span class="w"> </span><span class="n">amt</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span>
<a id="__codelineno-12-8" name="__codelineno-12-8" href="#__codelineno-12-8"></a><span class="w">    </span><span class="c1"># 找到小于且最接近剩余金额的硬币</span>
<a id="__codelineno-12-9" name="__codelineno-12-9" href="#__codelineno-12-9"></a><span class="w">    </span><span class="k">while</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">&amp;&amp;</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span><span class="w"> </span><span class="o">&gt;</span><span class="w"> </span><span class="n">amt</span>
<a id="__codelineno-12-10" name="__codelineno-12-10" href="#__codelineno-12-10"></a><span class="w">      </span><span class="n">i</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-11" name="__codelineno-12-11" href="#__codelineno-12-11"></a><span class="w">    </span><span class="k">end</span>
<a id="__codelineno-12-12" name="__codelineno-12-12" href="#__codelineno-12-12"></a><span class="w">    </span><span class="c1"># 选择 coins[i]</span>
<a id="__codelineno-12-13" name="__codelineno-12-13" href="#__codelineno-12-13"></a><span class="w">    </span><span class="n">amt</span><span class="w"> </span><span class="o">-=</span><span class="w"> </span><span class="n">coins</span><span class="o">[</span><span class="n">i</span><span class="o">]</span>
<a id="__codelineno-12-14" name="__codelineno-12-14" href="#__codelineno-12-14"></a><span class="w">    </span><span class="n">count</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span>
<a id="__codelineno-12-15" name="__codelineno-12-15" href="#__codelineno-12-15"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-12-16" name="__codelineno-12-16" href="#__codelineno-12-16"></a><span class="w">  </span><span class="c1"># 若未找到可行方案， 则返回 -1</span>
<a id="__codelineno-12-17" name="__codelineno-12-17" href="#__codelineno-12-17"></a><span class="w">  </span><span class="n">amt</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="mi">0</span><span class="w"> </span><span class="o">?</span><span class="w"> </span><span class="n">count</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="o">-</span><span class="mi">1</span>
<a id="__codelineno-12-18" name="__codelineno-12-18" href="#__codelineno-12-18"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">coin_change_greedy.zig</span><pre id="__code_13"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_13 > code"></button><code><a id="__codelineno-13-1" name="__codelineno-13-1" href="#__codelineno-13-1"></a><span class="p">[</span><span class="n">class</span><span class="p">]{}</span><span class="o">-</span><span class="p">[</span><span class="n">func</span><span class="p">]{</span><span class="n">coinChangeGreedy</span><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>

## 贪心优点与局限性

**贪心算法不仅操作直接、实现简单，而且通常效率也很高**。在以上代码中，记硬币最小面值为 $\min(coins)$ ，则贪心选择最多循环 $amt / \min(coins)$ 次，时间复杂度为 $O(amt / \min(coins))$ 。这比动态规划解法的时间复杂度 $O(n \times amt)$ 提升了一个数量级。

然而，**对于某些硬币面值组合，贪心算法并不能找到最优解**。下图给出了两个示例。

- **正例 $coins = [1, 5, 10, 20, 50, 100]$**：在该硬币组合下，给定任意 $amt$ ，贪心算法都可以找出最优解。
- **反例 $coins = [1, 20, 50]$**：假设 $amt = 60$ ，贪心算法只能找到 $50 + 1 \times 10$ 的兑换组合，共计 $11$ 枚硬币，但动态规划可以找到最优解 $20 + 20 + 20$ ，仅需 $3$ 枚硬币。
- **反例 $coins = [1, 49, 50]$**：假设 $amt = 98$ ，贪心算法只能找到 $50 + 1 \times 48$ 的兑换组合，共计 $49$ 枚硬币，但动态规划可以找到最优解 $49 + 49$ ，仅需 $2$ 枚硬币。

![贪心无法找出最优解的示例](greedy_algorithm.assets/coin_change_greedy_vs_dp.png)

也就是说，对于零钱兑换问题，贪心算法无法保证找到全局最优解，并且有可能找到非常差的解。它更适合用动态规划解决。

一般情况下，贪心算法适用于以下两类问题。

1. **可以保证找到最优解**：贪心算法在这种情况下往往是最优选择，因为它往往比回溯、动态规划更高效。
2. **可以找到近似最优解**：贪心算法在这种情况下也是可用的。对于很多复杂问题来说，寻找全局最优解是非常困难的，能以较高效率找到次优解也是非常不错的。

## 贪心算法特性

那么问题来了，什么样的问题适合用贪心算法求解呢？或者说，贪心算法在什么情况下可以保证找到最优解？

相较于动态规划，贪心算法的使用条件更加苛刻，其主要关注问题的两个性质。

- **贪心选择性质**：只有当局部最优选择始终可以导致全局最优解时，贪心算法才能保证得到最优解。
- **最优子结构**：原问题的最优解包含子问题的最优解。

最优子结构已经在动态规划章节中介绍过，不再赘述。值得注意的是，一些问题的最优子结构并不明显，但仍然可使用贪心算法解决。

我们主要探究贪心选择性质的判断方法。虽然它的描述看上去比较简单，**但实际上对于许多问题，证明贪心选择性质不是一件易事**。

例如零钱兑换问题，我们虽然能够容易地举出反例，对贪心选择性质进行证伪，但证实的难度较大。如果问：**满足什么条件的硬币组合可以使用贪心算法求解**？我们往往只能凭借直觉或举例子来给出一个模棱两可的答案，而难以给出严谨的数学证明。

!!! quote

    有一篇论文给出了一个 $O(n^3)$ 时间复杂度的算法，用于判断一个硬币组合是否可以使用贪心算法找出任何金额的最优解。

    Pearson, David. A polynomial-time algorithm for the change-making problem. Operations Research Letters 33.3 (2005): 231-234.

## 贪心解题步骤

贪心问题的解决流程大体可分为以下三步。

1. **问题分析**：梳理与理解问题特性，包括状态定义、优化目标和约束条件等。这一步在回溯和动态规划中都有涉及。
2. **确定贪心策略**：确定如何在每一步中做出贪心选择。这个策略能够在每一步减小问题的规模，并最终能解决整个问题。
3. **正确性证明**：通常需要证明问题具有贪心选择性质和最优子结构。这个步骤可能需要使用到数学证明，例如归纳法或反证法等。

确定贪心策略是求解问题的核心步骤，但实施起来可能并不容易，主要包含以下原因。

- **不同问题的贪心策略的差异较大**。对于许多问题来说，贪心策略都比较浅显，我们通过一些大概的思考与尝试就能得出。而对于一些复杂问题，贪心策略可能非常隐蔽，这种情况就非常考验个人的解题经验与算法能力了。
- **某些贪心策略具有较强的迷惑性**。当我们满怀信心设计好贪心策略，写出解题代码并提交运行，很可能发现部分测试样例无法通过。这是因为设计的贪心策略只是“部分正确”的，上文介绍的零钱兑换就是个典型案例。

为了保证正确性，我们应该对贪心策略进行严谨的数学证明，**通常需要用到反证法或数学归纳法**。

然而，正确性证明也很可能不是一件易事。如若没有头绪，我们通常会选择面向测试用例进行 Debug ，一步步修改与验证贪心策略。

## 贪心典型例题

贪心算法常常应用在满足贪心选择性质和最优子结构的优化问题中，以下列举了一些典型的贪心算法问题。

- **硬币找零问题**：在某些硬币组合下，贪心算法总是可以得到最优解。
- **区间调度问题**：假设你有一些任务，每个任务在一段时间内进行，你的目标是完成尽可能多的任务。如果每次都选择结束时间最早的任务，那么贪心算法就可以得到最优解。
- **分数背包问题**：给定一组物品和一个载重量，你的目标是选择一组物品，使得总重量不超过载重量，且总价值最大。如果每次都选择性价比最高（价值 / 重量）的物品，那么贪心算法在一些情况下可以得到最优解。
- **股票买卖问题**：给定一组股票的历史价格，你可以进行多次买卖，但如果你已经持有股票，那么在卖出之前不能再买，目标是获取最大利润。
- **霍夫曼编码**：霍夫曼编码是一种用于无损数据压缩的贪心算法。通过构建霍夫曼树，每次选择出现频率最小的两个节点合并，最后得到的霍夫曼树的带权路径长度（即编码长度）最小。
- **Dijkstra 算法**：它是一种解决给定源顶点到其余各顶点的最短路径问题的贪心算法。
