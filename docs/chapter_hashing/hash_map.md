# 哈希表

「哈希表 hash table」，又称「散列表」，其通过建立键 `key` 与值 `value` 之间的映射，实现高效的元素查询。具体而言，我们向哈希表输入一个键 `key` ，则可以在 $O(1)$ 时间内获取对应的值 `value` 。

如下图所示，给定 $n$ 个学生，每个学生都有“姓名”和“学号”两项数据。假如我们希望实现“输入一个学号，返回对应的姓名”的查询功能，则可以采用下图所示的哈希表来实现。

![哈希表的抽象表示](hash_map.assets/hash_table_lookup.png)

除哈希表外，数组和链表也可以实现查询功能，它们的效率对比如下表所示。

- **添加元素**：仅需将元素添加至数组（链表）的尾部即可，使用 $O(1)$ 时间。
- **查询元素**：由于数组（链表）是乱序的，因此需要遍历其中的所有元素，使用 $O(n)$ 时间。
- **删除元素**：需要先查询到元素，再从数组（链表）中删除，使用 $O(n)$ 时间。

<p align="center"> 表 <id> &nbsp; 元素查询效率对比 </p>

|          | 数组   | 链表   | 哈希表 |
| -------- | ------ | ------ | ------ |
| 查找元素 | $O(n)$ | $O(n)$ | $O(1)$ |
| 添加元素 | $O(1)$ | $O(1)$ | $O(1)$ |
| 删除元素 | $O(n)$ | $O(n)$ | $O(1)$ |

观察发现，**在哈希表中进行增删查改的时间复杂度都是 $O(1)$** ，非常高效。

## 哈希表常用操作

哈希表的常见操作包括：初始化、查询操作、添加键值对和删除键值对等。

=== "Python"

    ```python title="hash_map.py"
    # 初始化哈希表
    hmap: dict = {}
    
    # 添加操作
    # 在哈希表中添加键值对 (key, value)
    hmap[12836] = "小哈"
    hmap[15937] = "小啰"
    hmap[16750] = "小算"
    hmap[13276] = "小法"
    hmap[10583] = "小鸭"
    
    # 查询操作
    # 向哈希表输入键 key ，得到值 value
    name: str = hmap[15937]
    
    # 删除操作
    # 在哈希表中删除键值对 (key, value)
    hmap.pop(10583)
    ```

=== "C++"

    ```cpp title="hash_map.cpp"
    /* 初始化哈希表 */
    unordered_map<int, string> map;
    
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map[12836] = "小哈";
    map[15937] = "小啰";
    map[16750] = "小算";
    map[13276] = "小法";
    map[10583] = "小鸭";
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    string name = map[15937];
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.erase(10583);
    ```

=== "Java"

    ```java title="hash_map.java"
    /* 初始化哈希表 */
    Map<Integer, String> map = new HashMap<>();
    
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map.put(12836, "小哈");   
    map.put(15937, "小啰");   
    map.put(16750, "小算");   
    map.put(13276, "小法");
    map.put(10583, "小鸭");
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    String name = map.get(15937);
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.remove(10583);
    ```

=== "C#"

    ```csharp title="hash_map.cs"
    /* 初始化哈希表 */
    Dictionary<int, string> map = new() {
        /* 添加操作 */
        // 在哈希表中添加键值对 (key, value)
        { 12836, "小哈" },
        { 15937, "小啰" },
        { 16750, "小算" },
        { 13276, "小法" },
        { 10583, "小鸭" }
    };
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    string name = map[15937];
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.Remove(10583);
    ```

=== "Go"

    ```go title="hash_map_test.go"
    /* 初始化哈希表 */
    hmap := make(map[int]string)
    
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    hmap[12836] = "小哈"
    hmap[15937] = "小啰"
    hmap[16750] = "小算"
    hmap[13276] = "小法"
    hmap[10583] = "小鸭"
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    name := hmap[15937]
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    delete(hmap, 10583)
    ```

=== "Swift"

    ```swift title="hash_map.swift"
    /* 初始化哈希表 */
    var map: [Int: String] = [:]
    
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map[12836] = "小哈"
    map[15937] = "小啰"
    map[16750] = "小算"
    map[13276] = "小法"
    map[10583] = "小鸭"
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    let name = map[15937]!
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.removeValue(forKey: 10583)
    ```

=== "JS"

    ```javascript title="hash_map.js"
    /* 初始化哈希表 */
    const map = new Map();
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map.set(12836, '小哈');
    map.set(15937, '小啰');
    map.set(16750, '小算');
    map.set(13276, '小法');
    map.set(10583, '小鸭');
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    let name = map.get(15937);
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.delete(10583);
    ```

=== "TS"

    ```typescript title="hash_map.ts"
    /* 初始化哈希表 */
    const map = new Map<number, string>();
    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map.set(12836, '小哈');
    map.set(15937, '小啰');
    map.set(16750, '小算');
    map.set(13276, '小法');
    map.set(10583, '小鸭');
    console.info('\n添加完成后，哈希表为\nKey -> Value');
    console.info(map);
    
    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    let name = map.get(15937);
    console.info('\n输入学号 15937 ，查询到姓名 ' + name);
    
    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.delete(10583);
    console.info('\n删除 10583 后，哈希表为\nKey -> Value');
    console.info(map);
    ```

=== "Dart"

    ```dart title="hash_map.dart"
    /* 初始化哈希表 */
    Map<int, String> map = {};

    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map[12836] = "小哈";
    map[15937] = "小啰";
    map[16750] = "小算";
    map[13276] = "小法";
    map[10583] = "小鸭";

    /* 查询操作 */
    // 向哈希表输入键 key ，得到值 value
    String name = map[15937];

    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    map.remove(10583);
    ```

=== "Rust"

    ```rust title="hash_map.rs"
    use std::collections::HashMap;
    
    /* 初始化哈希表 */
    let mut map: HashMap<i32, String> = HashMap::new();

    /* 添加操作 */
    // 在哈希表中添加键值对 (key, value)
    map.insert(12836, "小哈".to_string());
    map.insert(15937, "小啰".to_string());
    map.insert(16750, "小算".to_string());
    map.insert(13279, "小法".to_string());
    map.insert(10583, "小鸭".to_string());

    /* 查询操作 */
    // 向哈希表中输入键 key ，得到值 value
    let _name: Option<&String> = map.get(&15937);

    /* 删除操作 */
    // 在哈希表中删除键值对 (key, value)
    let _removed_value: Option<String> = map.remove(&10583);
    ```

=== "C"

    ```c title="hash_map.c"
    // C 未提供内置哈希表
    ```

=== "Zig"

    ```zig title="hash_map.zig"

    ```

哈希表有三种常用遍历方式：遍历键值对、遍历键和遍历值。

=== "Python"

    ```python title="hash_map.py"
    # 遍历哈希表
    # 遍历键值对 key->value
    for key, value in hmap.items():
        print(key, "->", value)
    # 单独遍历键 key
    for key in hmap.keys():
        print(key)
    # 单独遍历值 value
    for value in hmap.values():
        print(value)
    ```

=== "C++"

    ```cpp title="hash_map.cpp"
    /* 遍历哈希表 */
    // 遍历键值对 key->value
    for (auto kv: map) {
        cout << kv.first << " -> " << kv.second << endl;
    }
    // 使用迭代器遍历 key->value
    for (auto iter = map.begin(); iter != map.end(); iter++) {
        cout << iter->first << "->" << iter->second << endl;
    }
    ```

=== "Java"

    ```java title="hash_map.java"
    /* 遍历哈希表 */
    // 遍历键值对 key->value
    for (Map.Entry <Integer, String> kv: map.entrySet()) {
        System.out.println(kv.getKey() + " -> " + kv.getValue());
    }
    // 单独遍历键 key
    for (int key: map.keySet()) {
        System.out.println(key);
    }
    // 单独遍历值 value
    for (String val: map.values()) {
        System.out.println(val);
    }
    ```

=== "C#"

    ```csharp title="hash_map.cs"
    /* 遍历哈希表 */
    // 遍历键值对 Key->Value
    foreach (var kv in map) {
        Console.WriteLine(kv.Key + " -> " + kv.Value);
    }
    // 单独遍历键 key
    foreach (int key in map.Keys) {
        Console.WriteLine(key);
    }
    // 单独遍历值 value
    foreach (string val in map.Values) {
        Console.WriteLine(val);
    }
    ```

=== "Go"

    ```go title="hash_map_test.go"
    /* 遍历哈希表 */
    // 遍历键值对 key->value
    for key, value := range hmap {
        fmt.Println(key, "->", value)
    }
    // 单独遍历键 key
    for key := range hmap {
        fmt.Println(key)
    }
    // 单独遍历值 value
    for _, value := range hmap {
        fmt.Println(value)
    }
    ```

=== "Swift"

    ```swift title="hash_map.swift"
    /* 遍历哈希表 */
    // 遍历键值对 Key->Value
    for (key, value) in map {
        print("\(key) -> \(value)")
    }
    // 单独遍历键 Key
    for key in map.keys {
        print(key)
    }
    // 单独遍历值 Value
    for value in map.values {
        print(value)
    }
    ```

=== "JS"

    ```javascript title="hash_map.js"
    /* 遍历哈希表 */
    console.info('\n遍历键值对 Key->Value');
    for (const [k, v] of map.entries()) {
        console.info(k + ' -> ' + v);
    }
    console.info('\n单独遍历键 Key');
    for (const k of map.keys()) {
        console.info(k);
    }
    console.info('\n单独遍历值 Value');
    for (const v of map.values()) {
        console.info(v);
    }
    ```

=== "TS"

    ```typescript title="hash_map.ts"
    /* 遍历哈希表 */
    console.info('\n遍历键值对 Key->Value');
    for (const [k, v] of map.entries()) {
        console.info(k + ' -> ' + v);
    }
    console.info('\n单独遍历键 Key');
    for (const k of map.keys()) {
        console.info(k);
    }
    console.info('\n单独遍历值 Value');
    for (const v of map.values()) {
        console.info(v);
    }
    ```

=== "Dart"

    ```dart title="hash_map.dart"
    /* 遍历哈希表 */
    // 遍历键值对 Key->Value
    map.forEach((key, value) {
      print('$key -> $value');
    });

    // 单独遍历键 Key
    map.keys.forEach((key) {
      print(key);
    });

    // 单独遍历值 Value
    map.values.forEach((value) {
      print(value);
    });
    ```

=== "Rust"

    ```rust title="hash_map.rs"
    /* 遍历哈希表 */
    // 遍历键值对 Key->Value
    for (key, value) in &map {
        println!("{key} -> {value}");
    }

    // 单独遍历键 Key
    for key in map.keys() {
        println!("{key}"); 
    }

    // 单独遍历值 Value
    for value in map.values() {
        println!("{value}");
    }
    ```

=== "C"

    ```c title="hash_map.c"
    // C 未提供内置哈希表
    ```

=== "Zig"

    ```zig title="hash_map.zig"

    ```

## 哈希表简单实现

我们先考虑最简单的情况，**仅用一个数组来实现哈希表**。在哈希表中，我们将数组中的每个空位称为「桶 bucket」，每个桶可存储一个键值对。因此，查询操作就是找到 `key` 对应的桶，并在桶中获取 `value` 。

那么，如何基于 `key` 来定位对应的桶呢？这是通过「哈希函数 hash function」实现的。哈希函数的作用是将一个较大的输入空间映射到一个较小的输出空间。在哈希表中，输入空间是所有 `key` ，输出空间是所有桶（数组索引）。换句话说，输入一个 `key` ，**我们可以通过哈希函数得到该 `key` 对应的键值对在数组中的存储位置**。

输入一个 `key` ，哈希函数的计算过程分为以下两步。

1. 通过某种哈希算法 `hash()` 计算得到哈希值。
2. 将哈希值对桶数量（数组长度）`capacity` 取模，从而获取该 `key` 对应的数组索引 `index` 。

```shell
index = hash(key) % capacity
```

随后，我们就可以利用 `index` 在哈希表中访问对应的桶，从而获取 `value` 。

设数组长度 `capacity = 100`、哈希算法 `hash(key) = key` ，易得哈希函数为 `key % 100` 。下图以 `key` 学号和 `value` 姓名为例，展示了哈希函数的工作原理。

![哈希函数工作原理](hash_map.assets/hash_function.png)

以下代码实现了一个简单哈希表。其中，我们将 `key` 和 `value` 封装成一个类 `Pair` ，以表示键值对。

<div class="tabbed-set tabbed-alternate" data-tabs="3:14" style="--md-indicator-x: 115px; --md-indicator-width: 52px;"><input checked="checked" id="__tabbed_3_1" name="__tabbed_3" type="radio"><input id="__tabbed_3_2" name="__tabbed_3" type="radio"><input id="__tabbed_3_3" name="__tabbed_3" type="radio"><input id="__tabbed_3_4" name="__tabbed_3" type="radio"><input id="__tabbed_3_5" name="__tabbed_3" type="radio"><input id="__tabbed_3_6" name="__tabbed_3" type="radio"><input id="__tabbed_3_7" name="__tabbed_3" type="radio"><input id="__tabbed_3_8" name="__tabbed_3" type="radio"><input id="__tabbed_3_9" name="__tabbed_3" type="radio"><input id="__tabbed_3_10" name="__tabbed_3" type="radio"><input id="__tabbed_3_11" name="__tabbed_3" type="radio"><input id="__tabbed_3_12" name="__tabbed_3" type="radio"><input id="__tabbed_3_13" name="__tabbed_3" type="radio"><input id="__tabbed_3_14" name="__tabbed_3" type="radio"><div class="tabbed-labels tabbed-labels--linked"><label for="__tabbed_3_1"><a href="#__tabbed_3_1" tabindex="-1">Python</a></label><label for="__tabbed_3_2"><a href="#__tabbed_3_2" tabindex="-1">C++</a></label><label for="__tabbed_3_3"><a href="#__tabbed_3_3" tabindex="-1">Java</a></label><label for="__tabbed_3_4"><a href="#__tabbed_3_4" tabindex="-1">C#</a></label><label for="__tabbed_3_5"><a href="#__tabbed_3_5" tabindex="-1">Go</a></label><label for="__tabbed_3_6"><a href="#__tabbed_3_6" tabindex="-1">Swift</a></label><label for="__tabbed_3_7"><a href="#__tabbed_3_7" tabindex="-1">JS</a></label><label for="__tabbed_3_8"><a href="#__tabbed_3_8" tabindex="-1">TS</a></label><label for="__tabbed_3_9"><a href="#__tabbed_3_9" tabindex="-1">Dart</a></label><label for="__tabbed_3_10"><a href="#__tabbed_3_10" tabindex="-1">Rust</a></label><label for="__tabbed_3_11"><a href="#__tabbed_3_11" tabindex="-1">C</a></label><label for="__tabbed_3_12"><a href="#__tabbed_3_12" tabindex="-1">Kotlin</a></label><label for="__tabbed_3_13"><a href="#__tabbed_3_13" tabindex="-1">Ruby</a></label><label for="__tabbed_3_14"><a href="#__tabbed_3_14" tabindex="-1">Zig</a></label></div>
<div class="tabbed-content">
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.py</span><pre id="__code_29"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_29 > code"></button><code><a id="__codelineno-29-1" name="__codelineno-29-1" href="#__codelineno-29-1"></a><span class="k">class</span> <span class="nc">Pair</span><span class="p">:</span>
<a id="__codelineno-29-2" name="__codelineno-29-2" href="#__codelineno-29-2"></a><span class="w">    </span><span class="sd">"""键值对"""</span>
<a id="__codelineno-29-3" name="__codelineno-29-3" href="#__codelineno-29-3"></a>
<a id="__codelineno-29-4" name="__codelineno-29-4" href="#__codelineno-29-4"></a>    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">:</span> <span class="nb">int</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">str</span><span class="p">):</span>
<a id="__codelineno-29-5" name="__codelineno-29-5" href="#__codelineno-29-5"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">key</span> <span class="o">=</span> <span class="n">key</span>
<a id="__codelineno-29-6" name="__codelineno-29-6" href="#__codelineno-29-6"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">val</span> <span class="o">=</span> <span class="n">val</span>
<a id="__codelineno-29-7" name="__codelineno-29-7" href="#__codelineno-29-7"></a>
<a id="__codelineno-29-8" name="__codelineno-29-8" href="#__codelineno-29-8"></a><span class="k">class</span> <span class="nc">ArrayHashMap</span><span class="p">:</span>
<a id="__codelineno-29-9" name="__codelineno-29-9" href="#__codelineno-29-9"></a><span class="w">    </span><span class="sd">"""基于数组实现的哈希表"""</span>
<a id="__codelineno-29-10" name="__codelineno-29-10" href="#__codelineno-29-10"></a>
<a id="__codelineno-29-11" name="__codelineno-29-11" href="#__codelineno-29-11"></a>    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<a id="__codelineno-29-12" name="__codelineno-29-12" href="#__codelineno-29-12"></a><span class="w">        </span><span class="sd">"""构造方法"""</span>
<a id="__codelineno-29-13" name="__codelineno-29-13" href="#__codelineno-29-13"></a>        <span class="c1"># 初始化数组，包含 100 个桶</span>
<a id="__codelineno-29-14" name="__codelineno-29-14" href="#__codelineno-29-14"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="n">Pair</span> <span class="o">|</span> <span class="kc">None</span><span class="p">]</span> <span class="o">=</span> <span class="p">[</span><span class="kc">None</span><span class="p">]</span> <span class="o">*</span> <span class="mi">100</span>
<a id="__codelineno-29-15" name="__codelineno-29-15" href="#__codelineno-29-15"></a>
<a id="__codelineno-29-16" name="__codelineno-29-16" href="#__codelineno-29-16"></a>    <span class="k">def</span> <span class="nf">hash_func</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">int</span><span class="p">:</span>
<a id="__codelineno-29-17" name="__codelineno-29-17" href="#__codelineno-29-17"></a><span class="w">        </span><span class="sd">"""哈希函数"""</span>
<a id="__codelineno-29-18" name="__codelineno-29-18" href="#__codelineno-29-18"></a>        <span class="n">index</span> <span class="o">=</span> <span class="n">key</span> <span class="o">%</span> <span class="mi">100</span>
<a id="__codelineno-29-19" name="__codelineno-29-19" href="#__codelineno-29-19"></a>        <span class="k">return</span> <span class="n">index</span>
<a id="__codelineno-29-20" name="__codelineno-29-20" href="#__codelineno-29-20"></a>
<a id="__codelineno-29-21" name="__codelineno-29-21" href="#__codelineno-29-21"></a>    <span class="k">def</span> <span class="nf">get</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">:</span> <span class="nb">int</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">str</span><span class="p">:</span>
<a id="__codelineno-29-22" name="__codelineno-29-22" href="#__codelineno-29-22"></a><span class="w">        </span><span class="sd">"""查询操作"""</span>
<a id="__codelineno-29-23" name="__codelineno-29-23" href="#__codelineno-29-23"></a>        <span class="n">index</span><span class="p">:</span> <span class="nb">int</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-29-24" name="__codelineno-29-24" href="#__codelineno-29-24"></a>        <span class="n">pair</span><span class="p">:</span> <span class="n">Pair</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span>
<a id="__codelineno-29-25" name="__codelineno-29-25" href="#__codelineno-29-25"></a>        <span class="k">if</span> <span class="n">pair</span> <span class="ow">is</span> <span class="kc">None</span><span class="p">:</span>
<a id="__codelineno-29-26" name="__codelineno-29-26" href="#__codelineno-29-26"></a>            <span class="k">return</span> <span class="kc">None</span>
<a id="__codelineno-29-27" name="__codelineno-29-27" href="#__codelineno-29-27"></a>        <span class="k">return</span> <span class="n">pair</span><span class="o">.</span><span class="n">val</span>
<a id="__codelineno-29-28" name="__codelineno-29-28" href="#__codelineno-29-28"></a>
<a id="__codelineno-29-29" name="__codelineno-29-29" href="#__codelineno-29-29"></a>    <span class="k">def</span> <span class="nf">put</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">:</span> <span class="nb">int</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">str</span><span class="p">):</span>
<a id="__codelineno-29-30" name="__codelineno-29-30" href="#__codelineno-29-30"></a><span class="w">        </span><span class="sd">"""添加操作"""</span>
<a id="__codelineno-29-31" name="__codelineno-29-31" href="#__codelineno-29-31"></a>        <span class="n">pair</span> <span class="o">=</span> <span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">,</span> <span class="n">val</span><span class="p">)</span>
<a id="__codelineno-29-32" name="__codelineno-29-32" href="#__codelineno-29-32"></a>        <span class="n">index</span><span class="p">:</span> <span class="nb">int</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-29-33" name="__codelineno-29-33" href="#__codelineno-29-33"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span> <span class="o">=</span> <span class="n">pair</span>
<a id="__codelineno-29-34" name="__codelineno-29-34" href="#__codelineno-29-34"></a>
<a id="__codelineno-29-35" name="__codelineno-29-35" href="#__codelineno-29-35"></a>    <span class="k">def</span> <span class="nf">remove</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">key</span><span class="p">:</span> <span class="nb">int</span><span class="p">):</span>
<a id="__codelineno-29-36" name="__codelineno-29-36" href="#__codelineno-29-36"></a><span class="w">        </span><span class="sd">"""删除操作"""</span>
<a id="__codelineno-29-37" name="__codelineno-29-37" href="#__codelineno-29-37"></a>        <span class="n">index</span><span class="p">:</span> <span class="nb">int</span> <span class="o">=</span> <span class="bp">self</span><span class="o">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-29-38" name="__codelineno-29-38" href="#__codelineno-29-38"></a>        <span class="c1"># 置为 None ，代表删除</span>
<a id="__codelineno-29-39" name="__codelineno-29-39" href="#__codelineno-29-39"></a>        <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span>
<a id="__codelineno-29-40" name="__codelineno-29-40" href="#__codelineno-29-40"></a>
<a id="__codelineno-29-41" name="__codelineno-29-41" href="#__codelineno-29-41"></a>    <span class="k">def</span> <span class="nf">entry_set</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">list</span><span class="p">[</span><span class="n">Pair</span><span class="p">]:</span>
<a id="__codelineno-29-42" name="__codelineno-29-42" href="#__codelineno-29-42"></a><span class="w">        </span><span class="sd">"""获取所有键值对"""</span>
<a id="__codelineno-29-43" name="__codelineno-29-43" href="#__codelineno-29-43"></a>        <span class="n">result</span><span class="p">:</span> <span class="nb">list</span><span class="p">[</span><span class="n">Pair</span><span class="p">]</span> <span class="o">=</span> <span class="p">[]</span>
<a id="__codelineno-29-44" name="__codelineno-29-44" href="#__codelineno-29-44"></a>        <span class="k">for</span> <span class="n">pair</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">:</span>
<a id="__codelineno-29-45" name="__codelineno-29-45" href="#__codelineno-29-45"></a>            <span class="k">if</span> <span class="n">pair</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">:</span>
<a id="__codelineno-29-46" name="__codelineno-29-46" href="#__codelineno-29-46"></a>                <span class="n">result</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">pair</span><span class="p">)</span>
<a id="__codelineno-29-47" name="__codelineno-29-47" href="#__codelineno-29-47"></a>        <span class="k">return</span> <span class="n">result</span>
<a id="__codelineno-29-48" name="__codelineno-29-48" href="#__codelineno-29-48"></a>
<a id="__codelineno-29-49" name="__codelineno-29-49" href="#__codelineno-29-49"></a>    <span class="k">def</span> <span class="nf">key_set</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">list</span><span class="p">[</span><span class="nb">int</span><span class="p">]:</span>
<a id="__codelineno-29-50" name="__codelineno-29-50" href="#__codelineno-29-50"></a><span class="w">        </span><span class="sd">"""获取所有键"""</span>
<a id="__codelineno-29-51" name="__codelineno-29-51" href="#__codelineno-29-51"></a>        <span class="n">result</span> <span class="o">=</span> <span class="p">[]</span>
<a id="__codelineno-29-52" name="__codelineno-29-52" href="#__codelineno-29-52"></a>        <span class="k">for</span> <span class="n">pair</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">:</span>
<a id="__codelineno-29-53" name="__codelineno-29-53" href="#__codelineno-29-53"></a>            <span class="k">if</span> <span class="n">pair</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">:</span>
<a id="__codelineno-29-54" name="__codelineno-29-54" href="#__codelineno-29-54"></a>                <span class="n">result</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">pair</span><span class="o">.</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-29-55" name="__codelineno-29-55" href="#__codelineno-29-55"></a>        <span class="k">return</span> <span class="n">result</span>
<a id="__codelineno-29-56" name="__codelineno-29-56" href="#__codelineno-29-56"></a>
<a id="__codelineno-29-57" name="__codelineno-29-57" href="#__codelineno-29-57"></a>    <span class="k">def</span> <span class="nf">value_set</span><span class="p">(</span><span class="bp">self</span><span class="p">)</span> <span class="o">-&gt;</span> <span class="nb">list</span><span class="p">[</span><span class="nb">str</span><span class="p">]:</span>
<a id="__codelineno-29-58" name="__codelineno-29-58" href="#__codelineno-29-58"></a><span class="w">        </span><span class="sd">"""获取所有值"""</span>
<a id="__codelineno-29-59" name="__codelineno-29-59" href="#__codelineno-29-59"></a>        <span class="n">result</span> <span class="o">=</span> <span class="p">[]</span>
<a id="__codelineno-29-60" name="__codelineno-29-60" href="#__codelineno-29-60"></a>        <span class="k">for</span> <span class="n">pair</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">:</span>
<a id="__codelineno-29-61" name="__codelineno-29-61" href="#__codelineno-29-61"></a>            <span class="k">if</span> <span class="n">pair</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">:</span>
<a id="__codelineno-29-62" name="__codelineno-29-62" href="#__codelineno-29-62"></a>                <span class="n">result</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="n">pair</span><span class="o">.</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-29-63" name="__codelineno-29-63" href="#__codelineno-29-63"></a>        <span class="k">return</span> <span class="n">result</span>
<a id="__codelineno-29-64" name="__codelineno-29-64" href="#__codelineno-29-64"></a>
<a id="__codelineno-29-65" name="__codelineno-29-65" href="#__codelineno-29-65"></a>    <span class="k">def</span> <span class="nf">print</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
<a id="__codelineno-29-66" name="__codelineno-29-66" href="#__codelineno-29-66"></a><span class="w">        </span><span class="sd">"""打印哈希表"""</span>
<a id="__codelineno-29-67" name="__codelineno-29-67" href="#__codelineno-29-67"></a>        <span class="k">for</span> <span class="n">pair</span> <span class="ow">in</span> <span class="bp">self</span><span class="o">.</span><span class="n">buckets</span><span class="p">:</span>
<a id="__codelineno-29-68" name="__codelineno-29-68" href="#__codelineno-29-68"></a>            <span class="k">if</span> <span class="n">pair</span> <span class="ow">is</span> <span class="ow">not</span> <span class="kc">None</span><span class="p">:</span>
<a id="__codelineno-29-69" name="__codelineno-29-69" href="#__codelineno-29-69"></a>                <span class="nb">print</span><span class="p">(</span><span class="n">pair</span><span class="o">.</span><span class="n">key</span><span class="p">,</span> <span class="s2">"-&gt;"</span><span class="p">,</span> <span class="n">pair</span><span class="o">.</span><span class="n">val</span><span class="p">)</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.cpp</span><pre id="__code_30"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_30 > code"></button><code><a id="__codelineno-30-1" name="__codelineno-30-1" href="#__codelineno-30-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-30-2" name="__codelineno-30-2" href="#__codelineno-30-2"></a><span class="k">struct</span><span class="w"> </span><span class="nc">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-3" name="__codelineno-30-3" href="#__codelineno-30-3"></a><span class="w">  </span><span class="k">public</span><span class="o">:</span>
<a id="__codelineno-30-4" name="__codelineno-30-4" href="#__codelineno-30-4"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-30-5" name="__codelineno-30-5" href="#__codelineno-30-5"></a><span class="w">    </span><span class="n">string</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-30-6" name="__codelineno-30-6" href="#__codelineno-30-6"></a><span class="w">    </span><span class="n">Pair</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">string</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-7" name="__codelineno-30-7" href="#__codelineno-30-7"></a><span class="w">        </span><span class="k">this</span><span class="o">-&gt;</span><span class="n">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-30-8" name="__codelineno-30-8" href="#__codelineno-30-8"></a><span class="w">        </span><span class="k">this</span><span class="o">-&gt;</span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-30-9" name="__codelineno-30-9" href="#__codelineno-30-9"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-10" name="__codelineno-30-10" href="#__codelineno-30-10"></a><span class="p">};</span>
<a id="__codelineno-30-11" name="__codelineno-30-11" href="#__codelineno-30-11"></a>
<a id="__codelineno-30-12" name="__codelineno-30-12" href="#__codelineno-30-12"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-30-13" name="__codelineno-30-13" href="#__codelineno-30-13"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-14" name="__codelineno-30-14" href="#__codelineno-30-14"></a><span class="w">  </span><span class="k">private</span><span class="o">:</span>
<a id="__codelineno-30-15" name="__codelineno-30-15" href="#__codelineno-30-15"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">Pair</span><span class="w"> </span><span class="o">*&gt;</span><span class="w"> </span><span class="n">buckets</span><span class="p">;</span>
<a id="__codelineno-30-16" name="__codelineno-30-16" href="#__codelineno-30-16"></a>
<a id="__codelineno-30-17" name="__codelineno-30-17" href="#__codelineno-30-17"></a><span class="w">  </span><span class="k">public</span><span class="o">:</span>
<a id="__codelineno-30-18" name="__codelineno-30-18" href="#__codelineno-30-18"></a><span class="w">    </span><span class="n">ArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-19" name="__codelineno-30-19" href="#__codelineno-30-19"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-30-20" name="__codelineno-30-20" href="#__codelineno-30-20"></a><span class="w">        </span><span class="n">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">Pair</span><span class="w"> </span><span class="o">*&gt;</span><span class="p">(</span><span class="mi">100</span><span class="p">);</span>
<a id="__codelineno-30-21" name="__codelineno-30-21" href="#__codelineno-30-21"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-22" name="__codelineno-30-22" href="#__codelineno-30-22"></a>
<a id="__codelineno-30-23" name="__codelineno-30-23" href="#__codelineno-30-23"></a><span class="w">    </span><span class="o">~</span><span class="n">ArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-24" name="__codelineno-30-24" href="#__codelineno-30-24"></a><span class="w">        </span><span class="c1">// 释放内存</span>
<a id="__codelineno-30-25" name="__codelineno-30-25" href="#__codelineno-30-25"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="k">const</span><span class="w"> </span><span class="k">auto</span><span class="w"> </span><span class="o">&amp;</span><span class="n">bucket</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-26" name="__codelineno-30-26" href="#__codelineno-30-26"></a><span class="w">            </span><span class="k">delete</span><span class="w"> </span><span class="n">bucket</span><span class="p">;</span>
<a id="__codelineno-30-27" name="__codelineno-30-27" href="#__codelineno-30-27"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-30-28" name="__codelineno-30-28" href="#__codelineno-30-28"></a><span class="w">        </span><span class="n">buckets</span><span class="p">.</span><span class="n">clear</span><span class="p">();</span>
<a id="__codelineno-30-29" name="__codelineno-30-29" href="#__codelineno-30-29"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-30" name="__codelineno-30-30" href="#__codelineno-30-30"></a>
<a id="__codelineno-30-31" name="__codelineno-30-31" href="#__codelineno-30-31"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-30-32" name="__codelineno-30-32" href="#__codelineno-30-32"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-33" name="__codelineno-30-33" href="#__codelineno-30-33"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span><span class="p">;</span>
<a id="__codelineno-30-34" name="__codelineno-30-34" href="#__codelineno-30-34"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">index</span><span class="p">;</span>
<a id="__codelineno-30-35" name="__codelineno-30-35" href="#__codelineno-30-35"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-36" name="__codelineno-30-36" href="#__codelineno-30-36"></a>
<a id="__codelineno-30-37" name="__codelineno-30-37" href="#__codelineno-30-37"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-30-38" name="__codelineno-30-38" href="#__codelineno-30-38"></a><span class="w">    </span><span class="n">string</span><span class="w"> </span><span class="n">get</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-39" name="__codelineno-30-39" href="#__codelineno-30-39"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-30-40" name="__codelineno-30-40" href="#__codelineno-30-40"></a><span class="w">        </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">];</span>
<a id="__codelineno-30-41" name="__codelineno-30-41" href="#__codelineno-30-41"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="k">nullptr</span><span class="p">)</span>
<a id="__codelineno-30-42" name="__codelineno-30-42" href="#__codelineno-30-42"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="s">""</span><span class="p">;</span>
<a id="__codelineno-30-43" name="__codelineno-30-43" href="#__codelineno-30-43"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-30-44" name="__codelineno-30-44" href="#__codelineno-30-44"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-45" name="__codelineno-30-45" href="#__codelineno-30-45"></a>
<a id="__codelineno-30-46" name="__codelineno-30-46" href="#__codelineno-30-46"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-30-47" name="__codelineno-30-47" href="#__codelineno-30-47"></a><span class="w">    </span><span class="kt">void</span><span class="w"> </span><span class="n">put</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">string</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-48" name="__codelineno-30-48" href="#__codelineno-30-48"></a><span class="w">        </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-30-49" name="__codelineno-30-49" href="#__codelineno-30-49"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-30-50" name="__codelineno-30-50" href="#__codelineno-30-50"></a><span class="w">        </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span><span class="p">;</span>
<a id="__codelineno-30-51" name="__codelineno-30-51" href="#__codelineno-30-51"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-52" name="__codelineno-30-52" href="#__codelineno-30-52"></a>
<a id="__codelineno-30-53" name="__codelineno-30-53" href="#__codelineno-30-53"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-30-54" name="__codelineno-30-54" href="#__codelineno-30-54"></a><span class="w">    </span><span class="kt">void</span><span class="w"> </span><span class="n">remove</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-55" name="__codelineno-30-55" href="#__codelineno-30-55"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-30-56" name="__codelineno-30-56" href="#__codelineno-30-56"></a><span class="w">        </span><span class="c1">// 释放内存并置为 nullptr</span>
<a id="__codelineno-30-57" name="__codelineno-30-57" href="#__codelineno-30-57"></a><span class="w">        </span><span class="k">delete</span><span class="w"> </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">];</span>
<a id="__codelineno-30-58" name="__codelineno-30-58" href="#__codelineno-30-58"></a><span class="w">        </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">nullptr</span><span class="p">;</span>
<a id="__codelineno-30-59" name="__codelineno-30-59" href="#__codelineno-30-59"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-60" name="__codelineno-30-60" href="#__codelineno-30-60"></a>
<a id="__codelineno-30-61" name="__codelineno-30-61" href="#__codelineno-30-61"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-30-62" name="__codelineno-30-62" href="#__codelineno-30-62"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">Pair</span><span class="w"> </span><span class="o">*&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-63" name="__codelineno-30-63" href="#__codelineno-30-63"></a><span class="w">        </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">Pair</span><span class="w"> </span><span class="o">*&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="p">;</span>
<a id="__codelineno-30-64" name="__codelineno-30-64" href="#__codelineno-30-64"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">pair</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-65" name="__codelineno-30-65" href="#__codelineno-30-65"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">nullptr</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-66" name="__codelineno-30-66" href="#__codelineno-30-66"></a><span class="w">                </span><span class="n">pairSet</span><span class="p">.</span><span class="n">push_back</span><span class="p">(</span><span class="n">pair</span><span class="p">);</span>
<a id="__codelineno-30-67" name="__codelineno-30-67" href="#__codelineno-30-67"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-30-68" name="__codelineno-30-68" href="#__codelineno-30-68"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-30-69" name="__codelineno-30-69" href="#__codelineno-30-69"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pairSet</span><span class="p">;</span>
<a id="__codelineno-30-70" name="__codelineno-30-70" href="#__codelineno-30-70"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-71" name="__codelineno-30-71" href="#__codelineno-30-71"></a>
<a id="__codelineno-30-72" name="__codelineno-30-72" href="#__codelineno-30-72"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-30-73" name="__codelineno-30-73" href="#__codelineno-30-73"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-74" name="__codelineno-30-74" href="#__codelineno-30-74"></a><span class="w">        </span><span class="n">vector</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="p">;</span>
<a id="__codelineno-30-75" name="__codelineno-30-75" href="#__codelineno-30-75"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">pair</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-76" name="__codelineno-30-76" href="#__codelineno-30-76"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">nullptr</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-77" name="__codelineno-30-77" href="#__codelineno-30-77"></a><span class="w">                </span><span class="n">keySet</span><span class="p">.</span><span class="n">push_back</span><span class="p">(</span><span class="n">pair</span><span class="o">-&gt;</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-30-78" name="__codelineno-30-78" href="#__codelineno-30-78"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-30-79" name="__codelineno-30-79" href="#__codelineno-30-79"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-30-80" name="__codelineno-30-80" href="#__codelineno-30-80"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">keySet</span><span class="p">;</span>
<a id="__codelineno-30-81" name="__codelineno-30-81" href="#__codelineno-30-81"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-82" name="__codelineno-30-82" href="#__codelineno-30-82"></a>
<a id="__codelineno-30-83" name="__codelineno-30-83" href="#__codelineno-30-83"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-30-84" name="__codelineno-30-84" href="#__codelineno-30-84"></a><span class="w">    </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">string</span><span class="o">&gt;</span><span class="w"> </span><span class="n">valueSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-85" name="__codelineno-30-85" href="#__codelineno-30-85"></a><span class="w">        </span><span class="n">vector</span><span class="o">&lt;</span><span class="n">string</span><span class="o">&gt;</span><span class="w"> </span><span class="n">valueSet</span><span class="p">;</span>
<a id="__codelineno-30-86" name="__codelineno-30-86" href="#__codelineno-30-86"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">pair</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-87" name="__codelineno-30-87" href="#__codelineno-30-87"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">nullptr</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-88" name="__codelineno-30-88" href="#__codelineno-30-88"></a><span class="w">                </span><span class="n">valueSet</span><span class="p">.</span><span class="n">push_back</span><span class="p">(</span><span class="n">pair</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-30-89" name="__codelineno-30-89" href="#__codelineno-30-89"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-30-90" name="__codelineno-30-90" href="#__codelineno-30-90"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-30-91" name="__codelineno-30-91" href="#__codelineno-30-91"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">valueSet</span><span class="p">;</span>
<a id="__codelineno-30-92" name="__codelineno-30-92" href="#__codelineno-30-92"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-93" name="__codelineno-30-93" href="#__codelineno-30-93"></a>
<a id="__codelineno-30-94" name="__codelineno-30-94" href="#__codelineno-30-94"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-30-95" name="__codelineno-30-95" href="#__codelineno-30-95"></a><span class="w">    </span><span class="kt">void</span><span class="w"> </span><span class="n">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-96" name="__codelineno-30-96" href="#__codelineno-30-96"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">kv</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="n">pairSet</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-30-97" name="__codelineno-30-97" href="#__codelineno-30-97"></a><span class="w">            </span><span class="n">cout</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">kv</span><span class="o">-&gt;</span><span class="n">key</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="s">" -&gt; "</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">kv</span><span class="o">-&gt;</span><span class="n">val</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">endl</span><span class="p">;</span>
<a id="__codelineno-30-98" name="__codelineno-30-98" href="#__codelineno-30-98"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-30-99" name="__codelineno-30-99" href="#__codelineno-30-99"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-30-100" name="__codelineno-30-100" href="#__codelineno-30-100"></a><span class="p">};</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.java</span><pre id="__code_31"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_31 > code"></button><code><a id="__codelineno-31-1" name="__codelineno-31-1" href="#__codelineno-31-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-31-2" name="__codelineno-31-2" href="#__codelineno-31-2"></a><span class="kd">class</span> <span class="nc">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-3" name="__codelineno-31-3" href="#__codelineno-31-3"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-31-4" name="__codelineno-31-4" href="#__codelineno-31-4"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">String</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-31-5" name="__codelineno-31-5" href="#__codelineno-31-5"></a>
<a id="__codelineno-31-6" name="__codelineno-31-6" href="#__codelineno-31-6"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="nf">Pair</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">String</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-7" name="__codelineno-31-7" href="#__codelineno-31-7"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="na">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-31-8" name="__codelineno-31-8" href="#__codelineno-31-8"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="na">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-31-9" name="__codelineno-31-9" href="#__codelineno-31-9"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-10" name="__codelineno-31-10" href="#__codelineno-31-10"></a><span class="p">}</span>
<a id="__codelineno-31-11" name="__codelineno-31-11" href="#__codelineno-31-11"></a>
<a id="__codelineno-31-12" name="__codelineno-31-12" href="#__codelineno-31-12"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-31-13" name="__codelineno-31-13" href="#__codelineno-31-13"></a><span class="kd">class</span> <span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-14" name="__codelineno-31-14" href="#__codelineno-31-14"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">buckets</span><span class="p">;</span>
<a id="__codelineno-31-15" name="__codelineno-31-15" href="#__codelineno-31-15"></a>
<a id="__codelineno-31-16" name="__codelineno-31-16" href="#__codelineno-31-16"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="nf">ArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-17" name="__codelineno-31-17" href="#__codelineno-31-17"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-31-18" name="__codelineno-31-18" href="#__codelineno-31-18"></a><span class="w">        </span><span class="n">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;&gt;</span><span class="p">();</span>
<a id="__codelineno-31-19" name="__codelineno-31-19" href="#__codelineno-31-19"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">100</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-20" name="__codelineno-31-20" href="#__codelineno-31-20"></a><span class="w">            </span><span class="n">buckets</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-31-21" name="__codelineno-31-21" href="#__codelineno-31-21"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-31-22" name="__codelineno-31-22" href="#__codelineno-31-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-23" name="__codelineno-31-23" href="#__codelineno-31-23"></a>
<a id="__codelineno-31-24" name="__codelineno-31-24" href="#__codelineno-31-24"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-31-25" name="__codelineno-31-25" href="#__codelineno-31-25"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="nf">hashFunc</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-26" name="__codelineno-31-26" href="#__codelineno-31-26"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span><span class="p">;</span>
<a id="__codelineno-31-27" name="__codelineno-31-27" href="#__codelineno-31-27"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">index</span><span class="p">;</span>
<a id="__codelineno-31-28" name="__codelineno-31-28" href="#__codelineno-31-28"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-29" name="__codelineno-31-29" href="#__codelineno-31-29"></a>
<a id="__codelineno-31-30" name="__codelineno-31-30" href="#__codelineno-31-30"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-31-31" name="__codelineno-31-31" href="#__codelineno-31-31"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">String</span><span class="w"> </span><span class="nf">get</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-32" name="__codelineno-31-32" href="#__codelineno-31-32"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-31-33" name="__codelineno-31-33" href="#__codelineno-31-33"></a><span class="w">        </span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">buckets</span><span class="p">.</span><span class="na">get</span><span class="p">(</span><span class="n">index</span><span class="p">);</span>
<a id="__codelineno-31-34" name="__codelineno-31-34" href="#__codelineno-31-34"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-31-35" name="__codelineno-31-35" href="#__codelineno-31-35"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-31-36" name="__codelineno-31-36" href="#__codelineno-31-36"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="na">val</span><span class="p">;</span>
<a id="__codelineno-31-37" name="__codelineno-31-37" href="#__codelineno-31-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-38" name="__codelineno-31-38" href="#__codelineno-31-38"></a>
<a id="__codelineno-31-39" name="__codelineno-31-39" href="#__codelineno-31-39"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-31-40" name="__codelineno-31-40" href="#__codelineno-31-40"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="nf">put</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">String</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-41" name="__codelineno-31-41" href="#__codelineno-31-41"></a><span class="w">        </span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-31-42" name="__codelineno-31-42" href="#__codelineno-31-42"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-31-43" name="__codelineno-31-43" href="#__codelineno-31-43"></a><span class="w">        </span><span class="n">buckets</span><span class="p">.</span><span class="na">set</span><span class="p">(</span><span class="n">index</span><span class="p">,</span><span class="w"> </span><span class="n">pair</span><span class="p">);</span>
<a id="__codelineno-31-44" name="__codelineno-31-44" href="#__codelineno-31-44"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-45" name="__codelineno-31-45" href="#__codelineno-31-45"></a>
<a id="__codelineno-31-46" name="__codelineno-31-46" href="#__codelineno-31-46"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-31-47" name="__codelineno-31-47" href="#__codelineno-31-47"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="nf">remove</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-48" name="__codelineno-31-48" href="#__codelineno-31-48"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-31-49" name="__codelineno-31-49" href="#__codelineno-31-49"></a><span class="w">        </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-31-50" name="__codelineno-31-50" href="#__codelineno-31-50"></a><span class="w">        </span><span class="n">buckets</span><span class="p">.</span><span class="na">set</span><span class="p">(</span><span class="n">index</span><span class="p">,</span><span class="w"> </span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-31-51" name="__codelineno-31-51" href="#__codelineno-31-51"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-52" name="__codelineno-31-52" href="#__codelineno-31-52"></a>
<a id="__codelineno-31-53" name="__codelineno-31-53" href="#__codelineno-31-53"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-31-54" name="__codelineno-31-54" href="#__codelineno-31-54"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="nf">pairSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-55" name="__codelineno-31-55" href="#__codelineno-31-55"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;&gt;</span><span class="p">();</span>
<a id="__codelineno-31-56" name="__codelineno-31-56" href="#__codelineno-31-56"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-57" name="__codelineno-31-57" href="#__codelineno-31-57"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-31-58" name="__codelineno-31-58" href="#__codelineno-31-58"></a><span class="w">                </span><span class="n">pairSet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">);</span>
<a id="__codelineno-31-59" name="__codelineno-31-59" href="#__codelineno-31-59"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-31-60" name="__codelineno-31-60" href="#__codelineno-31-60"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pairSet</span><span class="p">;</span>
<a id="__codelineno-31-61" name="__codelineno-31-61" href="#__codelineno-31-61"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-62" name="__codelineno-31-62" href="#__codelineno-31-62"></a>
<a id="__codelineno-31-63" name="__codelineno-31-63" href="#__codelineno-31-63"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-31-64" name="__codelineno-31-64" href="#__codelineno-31-64"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Integer</span><span class="o">&gt;</span><span class="w"> </span><span class="nf">keySet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-65" name="__codelineno-31-65" href="#__codelineno-31-65"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Integer</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;&gt;</span><span class="p">();</span>
<a id="__codelineno-31-66" name="__codelineno-31-66" href="#__codelineno-31-66"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-67" name="__codelineno-31-67" href="#__codelineno-31-67"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-31-68" name="__codelineno-31-68" href="#__codelineno-31-68"></a><span class="w">                </span><span class="n">keySet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="na">key</span><span class="p">);</span>
<a id="__codelineno-31-69" name="__codelineno-31-69" href="#__codelineno-31-69"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-31-70" name="__codelineno-31-70" href="#__codelineno-31-70"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">keySet</span><span class="p">;</span>
<a id="__codelineno-31-71" name="__codelineno-31-71" href="#__codelineno-31-71"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-72" name="__codelineno-31-72" href="#__codelineno-31-72"></a>
<a id="__codelineno-31-73" name="__codelineno-31-73" href="#__codelineno-31-73"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-31-74" name="__codelineno-31-74" href="#__codelineno-31-74"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">String</span><span class="o">&gt;</span><span class="w"> </span><span class="nf">valueSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-75" name="__codelineno-31-75" href="#__codelineno-31-75"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="n">String</span><span class="o">&gt;</span><span class="w"> </span><span class="n">valueSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="w"> </span><span class="n">ArrayList</span><span class="o">&lt;&gt;</span><span class="p">();</span>
<a id="__codelineno-31-76" name="__codelineno-31-76" href="#__codelineno-31-76"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-77" name="__codelineno-31-77" href="#__codelineno-31-77"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-31-78" name="__codelineno-31-78" href="#__codelineno-31-78"></a><span class="w">                </span><span class="n">valueSet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="na">val</span><span class="p">);</span>
<a id="__codelineno-31-79" name="__codelineno-31-79" href="#__codelineno-31-79"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-31-80" name="__codelineno-31-80" href="#__codelineno-31-80"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">valueSet</span><span class="p">;</span>
<a id="__codelineno-31-81" name="__codelineno-31-81" href="#__codelineno-31-81"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-82" name="__codelineno-31-82" href="#__codelineno-31-82"></a>
<a id="__codelineno-31-83" name="__codelineno-31-83" href="#__codelineno-31-83"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-31-84" name="__codelineno-31-84" href="#__codelineno-31-84"></a><span class="w">    </span><span class="kd">public</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="nf">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-85" name="__codelineno-31-85" href="#__codelineno-31-85"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="n">kv</span><span class="w"> </span><span class="p">:</span><span class="w"> </span><span class="n">pairSet</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-31-86" name="__codelineno-31-86" href="#__codelineno-31-86"></a><span class="w">            </span><span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">kv</span><span class="p">.</span><span class="na">key</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="s">" -&gt; "</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">kv</span><span class="p">.</span><span class="na">val</span><span class="p">);</span>
<a id="__codelineno-31-87" name="__codelineno-31-87" href="#__codelineno-31-87"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-31-88" name="__codelineno-31-88" href="#__codelineno-31-88"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-31-89" name="__codelineno-31-89" href="#__codelineno-31-89"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.cs</span><pre id="__code_32"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_32 > code"></button><code><a id="__codelineno-32-1" name="__codelineno-32-1" href="#__codelineno-32-1"></a><span class="cm">/* 键值对 int-&gt;string */</span>
<a id="__codelineno-32-2" name="__codelineno-32-2" href="#__codelineno-32-2"></a><span class="k">class</span><span class="w"> </span><span class="nf">Pair</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="kt">string</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-3" name="__codelineno-32-3" href="#__codelineno-32-3"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-32-4" name="__codelineno-32-4" href="#__codelineno-32-4"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">string</span><span class="w"> </span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-32-5" name="__codelineno-32-5" href="#__codelineno-32-5"></a><span class="p">}</span>
<a id="__codelineno-32-6" name="__codelineno-32-6" href="#__codelineno-32-6"></a>
<a id="__codelineno-32-7" name="__codelineno-32-7" href="#__codelineno-32-7"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-32-8" name="__codelineno-32-8" href="#__codelineno-32-8"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-9" name="__codelineno-32-9" href="#__codelineno-32-9"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">?&gt;</span><span class="w"> </span><span class="n">buckets</span><span class="p">;</span>
<a id="__codelineno-32-10" name="__codelineno-32-10" href="#__codelineno-32-10"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nf">ArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-11" name="__codelineno-32-11" href="#__codelineno-32-11"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-32-12" name="__codelineno-32-12" href="#__codelineno-32-12"></a><span class="w">        </span><span class="n">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-32-13" name="__codelineno-32-13" href="#__codelineno-32-13"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="m">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="m">100</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-14" name="__codelineno-32-14" href="#__codelineno-32-14"></a><span class="w">            </span><span class="n">buckets</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="k">null</span><span class="p">);</span>
<a id="__codelineno-32-15" name="__codelineno-32-15" href="#__codelineno-32-15"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-32-16" name="__codelineno-32-16" href="#__codelineno-32-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-17" name="__codelineno-32-17" href="#__codelineno-32-17"></a>
<a id="__codelineno-32-18" name="__codelineno-32-18" href="#__codelineno-32-18"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-32-19" name="__codelineno-32-19" href="#__codelineno-32-19"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="nf">HashFunc</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-20" name="__codelineno-32-20" href="#__codelineno-32-20"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m">100</span><span class="p">;</span>
<a id="__codelineno-32-21" name="__codelineno-32-21" href="#__codelineno-32-21"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">index</span><span class="p">;</span>
<a id="__codelineno-32-22" name="__codelineno-32-22" href="#__codelineno-32-22"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-23" name="__codelineno-32-23" href="#__codelineno-32-23"></a>
<a id="__codelineno-32-24" name="__codelineno-32-24" href="#__codelineno-32-24"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-32-25" name="__codelineno-32-25" href="#__codelineno-32-25"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="kt">string?</span><span class="w"> </span><span class="n">Get</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-26" name="__codelineno-32-26" href="#__codelineno-32-26"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">HashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-32-27" name="__codelineno-32-27" href="#__codelineno-32-27"></a><span class="w">        </span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">];</span>
<a id="__codelineno-32-28" name="__codelineno-32-28" href="#__codelineno-32-28"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="k">null</span><span class="p">)</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="k">null</span><span class="p">;</span>
<a id="__codelineno-32-29" name="__codelineno-32-29" href="#__codelineno-32-29"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-32-30" name="__codelineno-32-30" href="#__codelineno-32-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-31" name="__codelineno-32-31" href="#__codelineno-32-31"></a>
<a id="__codelineno-32-32" name="__codelineno-32-32" href="#__codelineno-32-32"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-32-33" name="__codelineno-32-33" href="#__codelineno-32-33"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="k">void</span><span class="w"> </span><span class="nf">Put</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="kt">string</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-34" name="__codelineno-32-34" href="#__codelineno-32-34"></a><span class="w">        </span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">new</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-32-35" name="__codelineno-32-35" href="#__codelineno-32-35"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">HashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-32-36" name="__codelineno-32-36" href="#__codelineno-32-36"></a><span class="w">        </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span><span class="p">;</span>
<a id="__codelineno-32-37" name="__codelineno-32-37" href="#__codelineno-32-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-38" name="__codelineno-32-38" href="#__codelineno-32-38"></a>
<a id="__codelineno-32-39" name="__codelineno-32-39" href="#__codelineno-32-39"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-32-40" name="__codelineno-32-40" href="#__codelineno-32-40"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="k">void</span><span class="w"> </span><span class="nf">Remove</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-41" name="__codelineno-32-41" href="#__codelineno-32-41"></a><span class="w">        </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">HashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-32-42" name="__codelineno-32-42" href="#__codelineno-32-42"></a><span class="w">        </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-32-43" name="__codelineno-32-43" href="#__codelineno-32-43"></a><span class="w">        </span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">null</span><span class="p">;</span>
<a id="__codelineno-32-44" name="__codelineno-32-44" href="#__codelineno-32-44"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-45" name="__codelineno-32-45" href="#__codelineno-32-45"></a>
<a id="__codelineno-32-46" name="__codelineno-32-46" href="#__codelineno-32-46"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-32-47" name="__codelineno-32-47" href="#__codelineno-32-47"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">PairSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-48" name="__codelineno-32-48" href="#__codelineno-32-48"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-32-49" name="__codelineno-32-49" href="#__codelineno-32-49"></a><span class="w">        </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-50" name="__codelineno-32-50" href="#__codelineno-32-50"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">null</span><span class="p">)</span>
<a id="__codelineno-32-51" name="__codelineno-32-51" href="#__codelineno-32-51"></a><span class="w">                </span><span class="n">pairSet</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="n">pair</span><span class="p">);</span>
<a id="__codelineno-32-52" name="__codelineno-32-52" href="#__codelineno-32-52"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-32-53" name="__codelineno-32-53" href="#__codelineno-32-53"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pairSet</span><span class="p">;</span>
<a id="__codelineno-32-54" name="__codelineno-32-54" href="#__codelineno-32-54"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-55" name="__codelineno-32-55" href="#__codelineno-32-55"></a>
<a id="__codelineno-32-56" name="__codelineno-32-56" href="#__codelineno-32-56"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-32-57" name="__codelineno-32-57" href="#__codelineno-32-57"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">KeySet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-58" name="__codelineno-32-58" href="#__codelineno-32-58"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-32-59" name="__codelineno-32-59" href="#__codelineno-32-59"></a><span class="w">        </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-60" name="__codelineno-32-60" href="#__codelineno-32-60"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">null</span><span class="p">)</span>
<a id="__codelineno-32-61" name="__codelineno-32-61" href="#__codelineno-32-61"></a><span class="w">                </span><span class="n">keySet</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-32-62" name="__codelineno-32-62" href="#__codelineno-32-62"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-32-63" name="__codelineno-32-63" href="#__codelineno-32-63"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">keySet</span><span class="p">;</span>
<a id="__codelineno-32-64" name="__codelineno-32-64" href="#__codelineno-32-64"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-65" name="__codelineno-32-65" href="#__codelineno-32-65"></a>
<a id="__codelineno-32-66" name="__codelineno-32-66" href="#__codelineno-32-66"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-32-67" name="__codelineno-32-67" href="#__codelineno-32-67"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">string</span><span class="o">&gt;</span><span class="w"> </span><span class="n">ValueSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-68" name="__codelineno-32-68" href="#__codelineno-32-68"></a><span class="w">        </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">string</span><span class="o">&gt;</span><span class="w"> </span><span class="n">valueSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-32-69" name="__codelineno-32-69" href="#__codelineno-32-69"></a><span class="w">        </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-70" name="__codelineno-32-70" href="#__codelineno-32-70"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="k">null</span><span class="p">)</span>
<a id="__codelineno-32-71" name="__codelineno-32-71" href="#__codelineno-32-71"></a><span class="w">                </span><span class="n">valueSet</span><span class="p">.</span><span class="n">Add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-32-72" name="__codelineno-32-72" href="#__codelineno-32-72"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-32-73" name="__codelineno-32-73" href="#__codelineno-32-73"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">valueSet</span><span class="p">;</span>
<a id="__codelineno-32-74" name="__codelineno-32-74" href="#__codelineno-32-74"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-75" name="__codelineno-32-75" href="#__codelineno-32-75"></a>
<a id="__codelineno-32-76" name="__codelineno-32-76" href="#__codelineno-32-76"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-32-77" name="__codelineno-32-77" href="#__codelineno-32-77"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="k">void</span><span class="w"> </span><span class="nf">Print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-78" name="__codelineno-32-78" href="#__codelineno-32-78"></a><span class="w">        </span><span class="k">foreach</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="n">kv</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">PairSet</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-32-79" name="__codelineno-32-79" href="#__codelineno-32-79"></a><span class="w">            </span><span class="n">Console</span><span class="p">.</span><span class="n">WriteLine</span><span class="p">(</span><span class="n">kv</span><span class="p">.</span><span class="n">key</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="s">" -&gt; "</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="n">kv</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-32-80" name="__codelineno-32-80" href="#__codelineno-32-80"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-32-81" name="__codelineno-32-81" href="#__codelineno-32-81"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-32-82" name="__codelineno-32-82" href="#__codelineno-32-82"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.go</span><pre id="__code_33"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_33 > code"></button><code><a id="__codelineno-33-1" name="__codelineno-33-1" href="#__codelineno-33-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-33-2" name="__codelineno-33-2" href="#__codelineno-33-2"></a><span class="kd">type</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="kd">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-3" name="__codelineno-33-3" href="#__codelineno-33-3"></a><span class="w">    </span><span class="nx">key</span><span class="w"> </span><span class="kt">int</span>
<a id="__codelineno-33-4" name="__codelineno-33-4" href="#__codelineno-33-4"></a><span class="w">    </span><span class="nx">val</span><span class="w"> </span><span class="kt">string</span>
<a id="__codelineno-33-5" name="__codelineno-33-5" href="#__codelineno-33-5"></a><span class="p">}</span>
<a id="__codelineno-33-6" name="__codelineno-33-6" href="#__codelineno-33-6"></a>
<a id="__codelineno-33-7" name="__codelineno-33-7" href="#__codelineno-33-7"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-33-8" name="__codelineno-33-8" href="#__codelineno-33-8"></a><span class="kd">type</span><span class="w"> </span><span class="nx">arrayHashMap</span><span class="w"> </span><span class="kd">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-9" name="__codelineno-33-9" href="#__codelineno-33-9"></a><span class="w">    </span><span class="nx">buckets</span><span class="w"> </span><span class="p">[]</span><span class="o">*</span><span class="nx">pair</span>
<a id="__codelineno-33-10" name="__codelineno-33-10" href="#__codelineno-33-10"></a><span class="p">}</span>
<a id="__codelineno-33-11" name="__codelineno-33-11" href="#__codelineno-33-11"></a>
<a id="__codelineno-33-12" name="__codelineno-33-12" href="#__codelineno-33-12"></a><span class="cm">/* 初始化哈希表 */</span>
<a id="__codelineno-33-13" name="__codelineno-33-13" href="#__codelineno-33-13"></a><span class="kd">func</span><span class="w"> </span><span class="nx">newArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-14" name="__codelineno-33-14" href="#__codelineno-33-14"></a><span class="w">    </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-33-15" name="__codelineno-33-15" href="#__codelineno-33-15"></a><span class="w">    </span><span class="nx">buckets</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nb">make</span><span class="p">([]</span><span class="o">*</span><span class="nx">pair</span><span class="p">,</span><span class="w"> </span><span class="mi">100</span><span class="p">)</span>
<a id="__codelineno-33-16" name="__codelineno-33-16" href="#__codelineno-33-16"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="o">&amp;</span><span class="nx">arrayHashMap</span><span class="p">{</span><span class="nx">buckets</span><span class="p">:</span><span class="w"> </span><span class="nx">buckets</span><span class="p">}</span>
<a id="__codelineno-33-17" name="__codelineno-33-17" href="#__codelineno-33-17"></a><span class="p">}</span>
<a id="__codelineno-33-18" name="__codelineno-33-18" href="#__codelineno-33-18"></a>
<a id="__codelineno-33-19" name="__codelineno-33-19" href="#__codelineno-33-19"></a><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-33-20" name="__codelineno-33-20" href="#__codelineno-33-20"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-21" name="__codelineno-33-21" href="#__codelineno-33-21"></a><span class="w">    </span><span class="nx">index</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span>
<a id="__codelineno-33-22" name="__codelineno-33-22" href="#__codelineno-33-22"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">index</span>
<a id="__codelineno-33-23" name="__codelineno-33-23" href="#__codelineno-33-23"></a><span class="p">}</span>
<a id="__codelineno-33-24" name="__codelineno-33-24" href="#__codelineno-33-24"></a>
<a id="__codelineno-33-25" name="__codelineno-33-25" href="#__codelineno-33-25"></a><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-33-26" name="__codelineno-33-26" href="#__codelineno-33-26"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">get</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="kt">string</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-27" name="__codelineno-33-27" href="#__codelineno-33-27"></a><span class="w">    </span><span class="nx">index</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span>
<a id="__codelineno-33-28" name="__codelineno-33-28" href="#__codelineno-33-28"></a><span class="w">    </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span>
<a id="__codelineno-33-29" name="__codelineno-33-29" href="#__codelineno-33-29"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">nil</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-30" name="__codelineno-33-30" href="#__codelineno-33-30"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="s">"Not Found"</span>
<a id="__codelineno-33-31" name="__codelineno-33-31" href="#__codelineno-33-31"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-33-32" name="__codelineno-33-32" href="#__codelineno-33-32"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span>
<a id="__codelineno-33-33" name="__codelineno-33-33" href="#__codelineno-33-33"></a><span class="p">}</span>
<a id="__codelineno-33-34" name="__codelineno-33-34" href="#__codelineno-33-34"></a>
<a id="__codelineno-33-35" name="__codelineno-33-35" href="#__codelineno-33-35"></a><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-33-36" name="__codelineno-33-36" href="#__codelineno-33-36"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">put</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">int</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-37" name="__codelineno-33-37" href="#__codelineno-33-37"></a><span class="w">    </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="o">&amp;</span><span class="nx">pair</span><span class="p">{</span><span class="nx">key</span><span class="p">:</span><span class="w"> </span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">:</span><span class="w"> </span><span class="nx">val</span><span class="p">}</span>
<a id="__codelineno-33-38" name="__codelineno-33-38" href="#__codelineno-33-38"></a><span class="w">    </span><span class="nx">index</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span>
<a id="__codelineno-33-39" name="__codelineno-33-39" href="#__codelineno-33-39"></a><span class="w">    </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nx">pair</span>
<a id="__codelineno-33-40" name="__codelineno-33-40" href="#__codelineno-33-40"></a><span class="p">}</span>
<a id="__codelineno-33-41" name="__codelineno-33-41" href="#__codelineno-33-41"></a>
<a id="__codelineno-33-42" name="__codelineno-33-42" href="#__codelineno-33-42"></a><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-33-43" name="__codelineno-33-43" href="#__codelineno-33-43"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">remove</span><span class="p">(</span><span class="nx">key</span><span class="w"> </span><span class="kt">int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-44" name="__codelineno-33-44" href="#__codelineno-33-44"></a><span class="w">    </span><span class="nx">index</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span>
<a id="__codelineno-33-45" name="__codelineno-33-45" href="#__codelineno-33-45"></a><span class="w">    </span><span class="c1">// 置为 nil ，代表删除</span>
<a id="__codelineno-33-46" name="__codelineno-33-46" href="#__codelineno-33-46"></a><span class="w">    </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="kc">nil</span>
<a id="__codelineno-33-47" name="__codelineno-33-47" href="#__codelineno-33-47"></a><span class="p">}</span>
<a id="__codelineno-33-48" name="__codelineno-33-48" href="#__codelineno-33-48"></a>
<a id="__codelineno-33-49" name="__codelineno-33-49" href="#__codelineno-33-49"></a><span class="cm">/* 获取所有键对 */</span>
<a id="__codelineno-33-50" name="__codelineno-33-50" href="#__codelineno-33-50"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">pairSet</span><span class="p">()</span><span class="w"> </span><span class="p">[]</span><span class="o">*</span><span class="nx">pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-51" name="__codelineno-33-51" href="#__codelineno-33-51"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">pairs</span><span class="w"> </span><span class="p">[]</span><span class="o">*</span><span class="nx">pair</span>
<a id="__codelineno-33-52" name="__codelineno-33-52" href="#__codelineno-33-52"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-53" name="__codelineno-33-53" href="#__codelineno-33-53"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">nil</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-54" name="__codelineno-33-54" href="#__codelineno-33-54"></a><span class="w">            </span><span class="nx">pairs</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">append</span><span class="p">(</span><span class="nx">pairs</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="p">)</span>
<a id="__codelineno-33-55" name="__codelineno-33-55" href="#__codelineno-33-55"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-33-56" name="__codelineno-33-56" href="#__codelineno-33-56"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-33-57" name="__codelineno-33-57" href="#__codelineno-33-57"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">pairs</span>
<a id="__codelineno-33-58" name="__codelineno-33-58" href="#__codelineno-33-58"></a><span class="p">}</span>
<a id="__codelineno-33-59" name="__codelineno-33-59" href="#__codelineno-33-59"></a>
<a id="__codelineno-33-60" name="__codelineno-33-60" href="#__codelineno-33-60"></a><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-33-61" name="__codelineno-33-61" href="#__codelineno-33-61"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">keySet</span><span class="p">()</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-62" name="__codelineno-33-62" href="#__codelineno-33-62"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">keys</span><span class="w"> </span><span class="p">[]</span><span class="kt">int</span>
<a id="__codelineno-33-63" name="__codelineno-33-63" href="#__codelineno-33-63"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-64" name="__codelineno-33-64" href="#__codelineno-33-64"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">nil</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-65" name="__codelineno-33-65" href="#__codelineno-33-65"></a><span class="w">            </span><span class="nx">keys</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">append</span><span class="p">(</span><span class="nx">keys</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">key</span><span class="p">)</span>
<a id="__codelineno-33-66" name="__codelineno-33-66" href="#__codelineno-33-66"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-33-67" name="__codelineno-33-67" href="#__codelineno-33-67"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-33-68" name="__codelineno-33-68" href="#__codelineno-33-68"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">keys</span>
<a id="__codelineno-33-69" name="__codelineno-33-69" href="#__codelineno-33-69"></a><span class="p">}</span>
<a id="__codelineno-33-70" name="__codelineno-33-70" href="#__codelineno-33-70"></a>
<a id="__codelineno-33-71" name="__codelineno-33-71" href="#__codelineno-33-71"></a><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-33-72" name="__codelineno-33-72" href="#__codelineno-33-72"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nx">valueSet</span><span class="p">()</span><span class="w"> </span><span class="p">[]</span><span class="kt">string</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-73" name="__codelineno-33-73" href="#__codelineno-33-73"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nx">values</span><span class="w"> </span><span class="p">[]</span><span class="kt">string</span>
<a id="__codelineno-33-74" name="__codelineno-33-74" href="#__codelineno-33-74"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-75" name="__codelineno-33-75" href="#__codelineno-33-75"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">nil</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-76" name="__codelineno-33-76" href="#__codelineno-33-76"></a><span class="w">            </span><span class="nx">values</span><span class="w"> </span><span class="p">=</span><span class="w"> </span><span class="nb">append</span><span class="p">(</span><span class="nx">values</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="p">)</span>
<a id="__codelineno-33-77" name="__codelineno-33-77" href="#__codelineno-33-77"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-33-78" name="__codelineno-33-78" href="#__codelineno-33-78"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-33-79" name="__codelineno-33-79" href="#__codelineno-33-79"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="nx">values</span>
<a id="__codelineno-33-80" name="__codelineno-33-80" href="#__codelineno-33-80"></a><span class="p">}</span>
<a id="__codelineno-33-81" name="__codelineno-33-81" href="#__codelineno-33-81"></a>
<a id="__codelineno-33-82" name="__codelineno-33-82" href="#__codelineno-33-82"></a><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-33-83" name="__codelineno-33-83" href="#__codelineno-33-83"></a><span class="kd">func</span><span class="w"> </span><span class="p">(</span><span class="nx">a</span><span class="w"> </span><span class="o">*</span><span class="nx">arrayHashMap</span><span class="p">)</span><span class="w"> </span><span class="nb">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-84" name="__codelineno-33-84" href="#__codelineno-33-84"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="nx">_</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">:=</span><span class="w"> </span><span class="k">range</span><span class="w"> </span><span class="nx">a</span><span class="p">.</span><span class="nx">buckets</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-85" name="__codelineno-33-85" href="#__codelineno-33-85"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">nil</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-33-86" name="__codelineno-33-86" href="#__codelineno-33-86"></a><span class="w">            </span><span class="nx">fmt</span><span class="p">.</span><span class="nx">Println</span><span class="p">(</span><span class="nx">pair</span><span class="p">.</span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="s">"-&gt;"</span><span class="p">,</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="p">)</span>
<a id="__codelineno-33-87" name="__codelineno-33-87" href="#__codelineno-33-87"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-33-88" name="__codelineno-33-88" href="#__codelineno-33-88"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-33-89" name="__codelineno-33-89" href="#__codelineno-33-89"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.swift</span><pre id="__code_34"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_34 > code"></button><code><a id="__codelineno-34-1" name="__codelineno-34-1" href="#__codelineno-34-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-34-2" name="__codelineno-34-2" href="#__codelineno-34-2"></a><span class="kd">class</span> <span class="nc">Pair</span><span class="p">:</span> <span class="nb">Equatable</span> <span class="p">{</span>
<a id="__codelineno-34-3" name="__codelineno-34-3" href="#__codelineno-34-3"></a>    <span class="kd">public</span> <span class="kd">var</span> <span class="nv">key</span><span class="p">:</span> <span class="nb">Int</span>
<a id="__codelineno-34-4" name="__codelineno-34-4" href="#__codelineno-34-4"></a>    <span class="kd">public</span> <span class="kd">var</span> <span class="nv">val</span><span class="p">:</span> <span class="nb">String</span>
<a id="__codelineno-34-5" name="__codelineno-34-5" href="#__codelineno-34-5"></a>
<a id="__codelineno-34-6" name="__codelineno-34-6" href="#__codelineno-34-6"></a>    <span class="kd">public</span> <span class="kd">init</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">Int</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-34-7" name="__codelineno-34-7" href="#__codelineno-34-7"></a>        <span class="kc">self</span><span class="p">.</span><span class="n">key</span> <span class="p">=</span> <span class="n">key</span>
<a id="__codelineno-34-8" name="__codelineno-34-8" href="#__codelineno-34-8"></a>        <span class="kc">self</span><span class="p">.</span><span class="n">val</span> <span class="p">=</span> <span class="n">val</span>
<a id="__codelineno-34-9" name="__codelineno-34-9" href="#__codelineno-34-9"></a>    <span class="p">}</span>
<a id="__codelineno-34-10" name="__codelineno-34-10" href="#__codelineno-34-10"></a>
<a id="__codelineno-34-11" name="__codelineno-34-11" href="#__codelineno-34-11"></a>    <span class="kd">public</span> <span class="kd">static</span> <span class="kd">func</span> <span class="p">==</span> <span class="p">(</span><span class="n">lhs</span><span class="p">:</span> <span class="n">Pair</span><span class="p">,</span> <span class="n">rhs</span><span class="p">:</span> <span class="n">Pair</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Bool</span> <span class="p">{</span>
<a id="__codelineno-34-12" name="__codelineno-34-12" href="#__codelineno-34-12"></a>        <span class="n">lhs</span><span class="p">.</span><span class="n">key</span> <span class="p">==</span> <span class="n">rhs</span><span class="p">.</span><span class="n">key</span> <span class="o">&amp;&amp;</span> <span class="n">lhs</span><span class="p">.</span><span class="n">val</span> <span class="p">==</span> <span class="n">rhs</span><span class="p">.</span><span class="n">val</span>
<a id="__codelineno-34-13" name="__codelineno-34-13" href="#__codelineno-34-13"></a>    <span class="p">}</span>
<a id="__codelineno-34-14" name="__codelineno-34-14" href="#__codelineno-34-14"></a><span class="p">}</span>
<a id="__codelineno-34-15" name="__codelineno-34-15" href="#__codelineno-34-15"></a>
<a id="__codelineno-34-16" name="__codelineno-34-16" href="#__codelineno-34-16"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-34-17" name="__codelineno-34-17" href="#__codelineno-34-17"></a><span class="kd">class</span> <span class="nc">ArrayHashMap</span> <span class="p">{</span>
<a id="__codelineno-34-18" name="__codelineno-34-18" href="#__codelineno-34-18"></a>    <span class="kd">private</span> <span class="kd">var</span> <span class="nv">buckets</span><span class="p">:</span> <span class="p">[</span><span class="n">Pair</span><span class="p">?]</span>
<a id="__codelineno-34-19" name="__codelineno-34-19" href="#__codelineno-34-19"></a>
<a id="__codelineno-34-20" name="__codelineno-34-20" href="#__codelineno-34-20"></a>    <span class="kd">init</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-34-21" name="__codelineno-34-21" href="#__codelineno-34-21"></a>        <span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-34-22" name="__codelineno-34-22" href="#__codelineno-34-22"></a>        <span class="n">buckets</span> <span class="p">=</span> <span class="nb">Array</span><span class="p">(</span><span class="n">repeating</span><span class="p">:</span> <span class="kc">nil</span><span class="p">,</span> <span class="bp">count</span><span class="p">:</span> <span class="mi">100</span><span class="p">)</span>
<a id="__codelineno-34-23" name="__codelineno-34-23" href="#__codelineno-34-23"></a>    <span class="p">}</span>
<a id="__codelineno-34-24" name="__codelineno-34-24" href="#__codelineno-34-24"></a>
<a id="__codelineno-34-25" name="__codelineno-34-25" href="#__codelineno-34-25"></a>    <span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-34-26" name="__codelineno-34-26" href="#__codelineno-34-26"></a>    <span class="kd">private</span> <span class="kd">func</span> <span class="nf">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">Int</span> <span class="p">{</span>
<a id="__codelineno-34-27" name="__codelineno-34-27" href="#__codelineno-34-27"></a>        <span class="kd">let</span> <span class="nv">index</span> <span class="p">=</span> <span class="n">key</span> <span class="o">%</span> <span class="mi">100</span>
<a id="__codelineno-34-28" name="__codelineno-34-28" href="#__codelineno-34-28"></a>        <span class="k">return</span> <span class="n">index</span>
<a id="__codelineno-34-29" name="__codelineno-34-29" href="#__codelineno-34-29"></a>    <span class="p">}</span>
<a id="__codelineno-34-30" name="__codelineno-34-30" href="#__codelineno-34-30"></a>
<a id="__codelineno-34-31" name="__codelineno-34-31" href="#__codelineno-34-31"></a>    <span class="cm">/* 查询操作 */</span>
<a id="__codelineno-34-32" name="__codelineno-34-32" href="#__codelineno-34-32"></a>    <span class="kd">func</span> <span class="nf">get</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">-&gt;</span> <span class="nb">String</span><span class="p">?</span> <span class="p">{</span>
<a id="__codelineno-34-33" name="__codelineno-34-33" href="#__codelineno-34-33"></a>        <span class="kd">let</span> <span class="nv">index</span> <span class="p">=</span> <span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="n">key</span><span class="p">)</span>
<a id="__codelineno-34-34" name="__codelineno-34-34" href="#__codelineno-34-34"></a>        <span class="kd">let</span> <span class="nv">pair</span> <span class="p">=</span> <span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span>
<a id="__codelineno-34-35" name="__codelineno-34-35" href="#__codelineno-34-35"></a>        <span class="k">return</span> <span class="n">pair</span><span class="p">?.</span><span class="n">val</span>
<a id="__codelineno-34-36" name="__codelineno-34-36" href="#__codelineno-34-36"></a>    <span class="p">}</span>
<a id="__codelineno-34-37" name="__codelineno-34-37" href="#__codelineno-34-37"></a>
<a id="__codelineno-34-38" name="__codelineno-34-38" href="#__codelineno-34-38"></a>    <span class="cm">/* 添加操作 */</span>
<a id="__codelineno-34-39" name="__codelineno-34-39" href="#__codelineno-34-39"></a>    <span class="kd">func</span> <span class="nf">put</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">Int</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="nb">String</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-34-40" name="__codelineno-34-40" href="#__codelineno-34-40"></a>        <span class="kd">let</span> <span class="nv">pair</span> <span class="p">=</span> <span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="n">key</span><span class="p">,</span> <span class="n">val</span><span class="p">:</span> <span class="n">val</span><span class="p">)</span>
<a id="__codelineno-34-41" name="__codelineno-34-41" href="#__codelineno-34-41"></a>        <span class="kd">let</span> <span class="nv">index</span> <span class="p">=</span> <span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="n">key</span><span class="p">)</span>
<a id="__codelineno-34-42" name="__codelineno-34-42" href="#__codelineno-34-42"></a>        <span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span> <span class="p">=</span> <span class="n">pair</span>
<a id="__codelineno-34-43" name="__codelineno-34-43" href="#__codelineno-34-43"></a>    <span class="p">}</span>
<a id="__codelineno-34-44" name="__codelineno-34-44" href="#__codelineno-34-44"></a>
<a id="__codelineno-34-45" name="__codelineno-34-45" href="#__codelineno-34-45"></a>    <span class="cm">/* 删除操作 */</span>
<a id="__codelineno-34-46" name="__codelineno-34-46" href="#__codelineno-34-46"></a>    <span class="kd">func</span> <span class="nf">remove</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="nb">Int</span><span class="p">)</span> <span class="p">{</span>
<a id="__codelineno-34-47" name="__codelineno-34-47" href="#__codelineno-34-47"></a>        <span class="kd">let</span> <span class="nv">index</span> <span class="p">=</span> <span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">:</span> <span class="n">key</span><span class="p">)</span>
<a id="__codelineno-34-48" name="__codelineno-34-48" href="#__codelineno-34-48"></a>        <span class="c1">// 置为 nil ，代表删除</span>
<a id="__codelineno-34-49" name="__codelineno-34-49" href="#__codelineno-34-49"></a>        <span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span> <span class="p">=</span> <span class="kc">nil</span>
<a id="__codelineno-34-50" name="__codelineno-34-50" href="#__codelineno-34-50"></a>    <span class="p">}</span>
<a id="__codelineno-34-51" name="__codelineno-34-51" href="#__codelineno-34-51"></a>
<a id="__codelineno-34-52" name="__codelineno-34-52" href="#__codelineno-34-52"></a>    <span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-34-53" name="__codelineno-34-53" href="#__codelineno-34-53"></a>    <span class="kd">func</span> <span class="nf">pairSet</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="p">[</span><span class="n">Pair</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-34-54" name="__codelineno-34-54" href="#__codelineno-34-54"></a>        <span class="n">buckets</span><span class="p">.</span><span class="n">compactMap</span> <span class="p">{</span> <span class="nv">$0</span> <span class="p">}</span>
<a id="__codelineno-34-55" name="__codelineno-34-55" href="#__codelineno-34-55"></a>    <span class="p">}</span>
<a id="__codelineno-34-56" name="__codelineno-34-56" href="#__codelineno-34-56"></a>
<a id="__codelineno-34-57" name="__codelineno-34-57" href="#__codelineno-34-57"></a>    <span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-34-58" name="__codelineno-34-58" href="#__codelineno-34-58"></a>    <span class="kd">func</span> <span class="nf">keySet</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="p">[</span><span class="nb">Int</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-34-59" name="__codelineno-34-59" href="#__codelineno-34-59"></a>        <span class="n">buckets</span><span class="p">.</span><span class="n">compactMap</span> <span class="p">{</span> <span class="nv">$0</span><span class="p">?.</span><span class="n">key</span> <span class="p">}</span>
<a id="__codelineno-34-60" name="__codelineno-34-60" href="#__codelineno-34-60"></a>    <span class="p">}</span>
<a id="__codelineno-34-61" name="__codelineno-34-61" href="#__codelineno-34-61"></a>
<a id="__codelineno-34-62" name="__codelineno-34-62" href="#__codelineno-34-62"></a>    <span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-34-63" name="__codelineno-34-63" href="#__codelineno-34-63"></a>    <span class="kd">func</span> <span class="nf">valueSet</span><span class="p">()</span> <span class="p">-&gt;</span> <span class="p">[</span><span class="nb">String</span><span class="p">]</span> <span class="p">{</span>
<a id="__codelineno-34-64" name="__codelineno-34-64" href="#__codelineno-34-64"></a>        <span class="n">buckets</span><span class="p">.</span><span class="n">compactMap</span> <span class="p">{</span> <span class="nv">$0</span><span class="p">?.</span><span class="n">val</span> <span class="p">}</span>
<a id="__codelineno-34-65" name="__codelineno-34-65" href="#__codelineno-34-65"></a>    <span class="p">}</span>
<a id="__codelineno-34-66" name="__codelineno-34-66" href="#__codelineno-34-66"></a>
<a id="__codelineno-34-67" name="__codelineno-34-67" href="#__codelineno-34-67"></a>    <span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-34-68" name="__codelineno-34-68" href="#__codelineno-34-68"></a>    <span class="kd">func</span> <span class="nf">print</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-34-69" name="__codelineno-34-69" href="#__codelineno-34-69"></a>        <span class="k">for</span> <span class="n">pair</span> <span class="k">in</span> <span class="n">pairSet</span><span class="p">()</span> <span class="p">{</span>
<a id="__codelineno-34-70" name="__codelineno-34-70" href="#__codelineno-34-70"></a>            <span class="n">Swift</span><span class="p">.</span><span class="bp">print</span><span class="p">(</span><span class="s">"</span><span class="si">\(</span><span class="n">pair</span><span class="p">.</span><span class="n">key</span><span class="si">)</span><span class="s"> -&gt; </span><span class="si">\(</span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="si">)</span><span class="s">"</span><span class="p">)</span>
<a id="__codelineno-34-71" name="__codelineno-34-71" href="#__codelineno-34-71"></a>        <span class="p">}</span>
<a id="__codelineno-34-72" name="__codelineno-34-72" href="#__codelineno-34-72"></a>    <span class="p">}</span>
<a id="__codelineno-34-73" name="__codelineno-34-73" href="#__codelineno-34-73"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.js</span><pre id="__code_35"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_35 > code"></button><code><a id="__codelineno-35-1" name="__codelineno-35-1" href="#__codelineno-35-1"></a><span class="cm">/* 键值对 Number -&gt; String */</span>
<a id="__codelineno-35-2" name="__codelineno-35-2" href="#__codelineno-35-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-3" name="__codelineno-35-3" href="#__codelineno-35-3"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">(</span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-4" name="__codelineno-35-4" href="#__codelineno-35-4"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">key</span><span class="p">;</span>
<a id="__codelineno-35-5" name="__codelineno-35-5" href="#__codelineno-35-5"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-35-6" name="__codelineno-35-6" href="#__codelineno-35-6"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-7" name="__codelineno-35-7" href="#__codelineno-35-7"></a><span class="p">}</span>
<a id="__codelineno-35-8" name="__codelineno-35-8" href="#__codelineno-35-8"></a>
<a id="__codelineno-35-9" name="__codelineno-35-9" href="#__codelineno-35-9"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-35-10" name="__codelineno-35-10" href="#__codelineno-35-10"></a><span class="kd">class</span><span class="w"> </span><span class="nx">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-11" name="__codelineno-35-11" href="#__codelineno-35-11"></a><span class="w">    </span><span class="err">#</span><span class="nx">buckets</span><span class="p">;</span>
<a id="__codelineno-35-12" name="__codelineno-35-12" href="#__codelineno-35-12"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-13" name="__codelineno-35-13" href="#__codelineno-35-13"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-35-14" name="__codelineno-35-14" href="#__codelineno-35-14"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nb">Array</span><span class="p">(</span><span class="mf">100</span><span class="p">).</span><span class="nx">fill</span><span class="p">(</span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-35-15" name="__codelineno-35-15" href="#__codelineno-35-15"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-16" name="__codelineno-35-16" href="#__codelineno-35-16"></a>
<a id="__codelineno-35-17" name="__codelineno-35-17" href="#__codelineno-35-17"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-35-18" name="__codelineno-35-18" href="#__codelineno-35-18"></a><span class="w">    </span><span class="err">#</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-19" name="__codelineno-35-19" href="#__codelineno-35-19"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mf">100</span><span class="p">;</span>
<a id="__codelineno-35-20" name="__codelineno-35-20" href="#__codelineno-35-20"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-21" name="__codelineno-35-21" href="#__codelineno-35-21"></a>
<a id="__codelineno-35-22" name="__codelineno-35-22" href="#__codelineno-35-22"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-35-23" name="__codelineno-35-23" href="#__codelineno-35-23"></a><span class="w">    </span><span class="nx">get</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-24" name="__codelineno-35-24" href="#__codelineno-35-24"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-35-25" name="__codelineno-35-25" href="#__codelineno-35-25"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">];</span>
<a id="__codelineno-35-26" name="__codelineno-35-26" href="#__codelineno-35-26"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">pair</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-35-27" name="__codelineno-35-27" href="#__codelineno-35-27"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-35-28" name="__codelineno-35-28" href="#__codelineno-35-28"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-29" name="__codelineno-35-29" href="#__codelineno-35-29"></a>
<a id="__codelineno-35-30" name="__codelineno-35-30" href="#__codelineno-35-30"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-35-31" name="__codelineno-35-31" href="#__codelineno-35-31"></a><span class="w">    </span><span class="nx">set</span><span class="p">(</span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-32" name="__codelineno-35-32" href="#__codelineno-35-32"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-35-33" name="__codelineno-35-33" href="#__codelineno-35-33"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nx">Pair</span><span class="p">(</span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-35-34" name="__codelineno-35-34" href="#__codelineno-35-34"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-35" name="__codelineno-35-35" href="#__codelineno-35-35"></a>
<a id="__codelineno-35-36" name="__codelineno-35-36" href="#__codelineno-35-36"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-35-37" name="__codelineno-35-37" href="#__codelineno-35-37"></a><span class="w">    </span><span class="ow">delete</span><span class="p">(</span><span class="nx">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-38" name="__codelineno-35-38" href="#__codelineno-35-38"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-35-39" name="__codelineno-35-39" href="#__codelineno-35-39"></a><span class="w">        </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-35-40" name="__codelineno-35-40" href="#__codelineno-35-40"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-35-41" name="__codelineno-35-41" href="#__codelineno-35-41"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-42" name="__codelineno-35-42" href="#__codelineno-35-42"></a>
<a id="__codelineno-35-43" name="__codelineno-35-43" href="#__codelineno-35-43"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-35-44" name="__codelineno-35-44" href="#__codelineno-35-44"></a><span class="w">    </span><span class="nx">entries</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-45" name="__codelineno-35-45" href="#__codelineno-35-45"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-35-46" name="__codelineno-35-46" href="#__codelineno-35-46"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-47" name="__codelineno-35-47" href="#__codelineno-35-47"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-48" name="__codelineno-35-48" href="#__codelineno-35-48"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">]);</span>
<a id="__codelineno-35-49" name="__codelineno-35-49" href="#__codelineno-35-49"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-35-50" name="__codelineno-35-50" href="#__codelineno-35-50"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-35-51" name="__codelineno-35-51" href="#__codelineno-35-51"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-35-52" name="__codelineno-35-52" href="#__codelineno-35-52"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-53" name="__codelineno-35-53" href="#__codelineno-35-53"></a>
<a id="__codelineno-35-54" name="__codelineno-35-54" href="#__codelineno-35-54"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-35-55" name="__codelineno-35-55" href="#__codelineno-35-55"></a><span class="w">    </span><span class="nx">keys</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-56" name="__codelineno-35-56" href="#__codelineno-35-56"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-35-57" name="__codelineno-35-57" href="#__codelineno-35-57"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-58" name="__codelineno-35-58" href="#__codelineno-35-58"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-59" name="__codelineno-35-59" href="#__codelineno-35-59"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">].</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-35-60" name="__codelineno-35-60" href="#__codelineno-35-60"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-35-61" name="__codelineno-35-61" href="#__codelineno-35-61"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-35-62" name="__codelineno-35-62" href="#__codelineno-35-62"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-35-63" name="__codelineno-35-63" href="#__codelineno-35-63"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-64" name="__codelineno-35-64" href="#__codelineno-35-64"></a>
<a id="__codelineno-35-65" name="__codelineno-35-65" href="#__codelineno-35-65"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-35-66" name="__codelineno-35-66" href="#__codelineno-35-66"></a><span class="w">    </span><span class="nx">values</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-67" name="__codelineno-35-67" href="#__codelineno-35-67"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-35-68" name="__codelineno-35-68" href="#__codelineno-35-68"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-69" name="__codelineno-35-69" href="#__codelineno-35-69"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-70" name="__codelineno-35-70" href="#__codelineno-35-70"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="err">#</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">].</span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-35-71" name="__codelineno-35-71" href="#__codelineno-35-71"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-35-72" name="__codelineno-35-72" href="#__codelineno-35-72"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-35-73" name="__codelineno-35-73" href="#__codelineno-35-73"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-35-74" name="__codelineno-35-74" href="#__codelineno-35-74"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-75" name="__codelineno-35-75" href="#__codelineno-35-75"></a>
<a id="__codelineno-35-76" name="__codelineno-35-76" href="#__codelineno-35-76"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-35-77" name="__codelineno-35-77" href="#__codelineno-35-77"></a><span class="w">    </span><span class="nx">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-78" name="__codelineno-35-78" href="#__codelineno-35-78"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">entries</span><span class="p">();</span>
<a id="__codelineno-35-79" name="__codelineno-35-79" href="#__codelineno-35-79"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">pairSet</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-35-80" name="__codelineno-35-80" href="#__codelineno-35-80"></a><span class="w">            </span><span class="nx">console</span><span class="p">.</span><span class="nx">info</span><span class="p">(</span><span class="sb">`</span><span class="si">${</span><span class="nx">pair</span><span class="p">.</span><span class="nx">key</span><span class="si">}</span><span class="sb"> -&gt; </span><span class="si">${</span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="si">}</span><span class="sb">`</span><span class="p">);</span>
<a id="__codelineno-35-81" name="__codelineno-35-81" href="#__codelineno-35-81"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-35-82" name="__codelineno-35-82" href="#__codelineno-35-82"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-35-83" name="__codelineno-35-83" href="#__codelineno-35-83"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.ts</span><pre id="__code_36"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_36 > code"></button><code><a id="__codelineno-36-1" name="__codelineno-36-1" href="#__codelineno-36-1"></a><span class="cm">/* 键值对 Number -&gt; String */</span>
<a id="__codelineno-36-2" name="__codelineno-36-2" href="#__codelineno-36-2"></a><span class="kd">class</span><span class="w"> </span><span class="nx">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-3" name="__codelineno-36-3" href="#__codelineno-36-3"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">;</span>
<a id="__codelineno-36-4" name="__codelineno-36-4" href="#__codelineno-36-4"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">val</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">;</span>
<a id="__codelineno-36-5" name="__codelineno-36-5" href="#__codelineno-36-5"></a>
<a id="__codelineno-36-6" name="__codelineno-36-6" href="#__codelineno-36-6"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-7" name="__codelineno-36-7" href="#__codelineno-36-7"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">key</span><span class="p">;</span>
<a id="__codelineno-36-8" name="__codelineno-36-8" href="#__codelineno-36-8"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-36-9" name="__codelineno-36-9" href="#__codelineno-36-9"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-10" name="__codelineno-36-10" href="#__codelineno-36-10"></a><span class="p">}</span>
<a id="__codelineno-36-11" name="__codelineno-36-11" href="#__codelineno-36-11"></a>
<a id="__codelineno-36-12" name="__codelineno-36-12" href="#__codelineno-36-12"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-36-13" name="__codelineno-36-13" href="#__codelineno-36-13"></a><span class="kd">class</span><span class="w"> </span><span class="nx">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-14" name="__codelineno-36-14" href="#__codelineno-36-14"></a><span class="w">    </span><span class="k">private</span><span class="w"> </span><span class="k">readonly</span><span class="w"> </span><span class="nx">buckets</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="nx">Pair</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">null</span><span class="p">)[];</span>
<a id="__codelineno-36-15" name="__codelineno-36-15" href="#__codelineno-36-15"></a>
<a id="__codelineno-36-16" name="__codelineno-36-16" href="#__codelineno-36-16"></a><span class="w">    </span><span class="kr">constructor</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-17" name="__codelineno-36-17" href="#__codelineno-36-17"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-36-18" name="__codelineno-36-18" href="#__codelineno-36-18"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nb">Array</span><span class="p">(</span><span class="mf">100</span><span class="p">).</span><span class="nx">fill</span><span class="p">(</span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-36-19" name="__codelineno-36-19" href="#__codelineno-36-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-20" name="__codelineno-36-20" href="#__codelineno-36-20"></a>
<a id="__codelineno-36-21" name="__codelineno-36-21" href="#__codelineno-36-21"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-36-22" name="__codelineno-36-22" href="#__codelineno-36-22"></a><span class="w">    </span><span class="k">private</span><span class="w"> </span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-23" name="__codelineno-36-23" href="#__codelineno-36-23"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mf">100</span><span class="p">;</span>
<a id="__codelineno-36-24" name="__codelineno-36-24" href="#__codelineno-36-24"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-25" name="__codelineno-36-25" href="#__codelineno-36-25"></a>
<a id="__codelineno-36-26" name="__codelineno-36-26" href="#__codelineno-36-26"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-36-27" name="__codelineno-36-27" href="#__codelineno-36-27"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">get</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">null</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-28" name="__codelineno-36-28" href="#__codelineno-36-28"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-36-29" name="__codelineno-36-29" href="#__codelineno-36-29"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">];</span>
<a id="__codelineno-36-30" name="__codelineno-36-30" href="#__codelineno-36-30"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="nx">pair</span><span class="w"> </span><span class="o">===</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-36-31" name="__codelineno-36-31" href="#__codelineno-36-31"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="p">;</span>
<a id="__codelineno-36-32" name="__codelineno-36-32" href="#__codelineno-36-32"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-33" name="__codelineno-36-33" href="#__codelineno-36-33"></a>
<a id="__codelineno-36-34" name="__codelineno-36-34" href="#__codelineno-36-34"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-36-35" name="__codelineno-36-35" href="#__codelineno-36-35"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">set</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="o">:</span><span class="w"> </span><span class="kt">string</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-36" name="__codelineno-36-36" href="#__codelineno-36-36"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-36-37" name="__codelineno-36-37" href="#__codelineno-36-37"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="ow">new</span><span class="w"> </span><span class="nx">Pair</span><span class="p">(</span><span class="nx">key</span><span class="p">,</span><span class="w"> </span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-36-38" name="__codelineno-36-38" href="#__codelineno-36-38"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-39" name="__codelineno-36-39" href="#__codelineno-36-39"></a>
<a id="__codelineno-36-40" name="__codelineno-36-40" href="#__codelineno-36-40"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-36-41" name="__codelineno-36-41" href="#__codelineno-36-41"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="ow">delete</span><span class="p">(</span><span class="nx">key</span><span class="o">:</span><span class="w"> </span><span class="kt">number</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-42" name="__codelineno-36-42" href="#__codelineno-36-42"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">hashFunc</span><span class="p">(</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-36-43" name="__codelineno-36-43" href="#__codelineno-36-43"></a><span class="w">        </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-36-44" name="__codelineno-36-44" href="#__codelineno-36-44"></a><span class="w">        </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-36-45" name="__codelineno-36-45" href="#__codelineno-36-45"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-46" name="__codelineno-36-46" href="#__codelineno-36-46"></a>
<a id="__codelineno-36-47" name="__codelineno-36-47" href="#__codelineno-36-47"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-36-48" name="__codelineno-36-48" href="#__codelineno-36-48"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">entries</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="nx">Pair</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">null</span><span class="p">)[]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-49" name="__codelineno-36-49" href="#__codelineno-36-49"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="nx">Pair</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">null</span><span class="p">)[]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-36-50" name="__codelineno-36-50" href="#__codelineno-36-50"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-51" name="__codelineno-36-51" href="#__codelineno-36-51"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-52" name="__codelineno-36-52" href="#__codelineno-36-52"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">]);</span>
<a id="__codelineno-36-53" name="__codelineno-36-53" href="#__codelineno-36-53"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-36-54" name="__codelineno-36-54" href="#__codelineno-36-54"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-36-55" name="__codelineno-36-55" href="#__codelineno-36-55"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-36-56" name="__codelineno-36-56" href="#__codelineno-36-56"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-57" name="__codelineno-36-57" href="#__codelineno-36-57"></a>
<a id="__codelineno-36-58" name="__codelineno-36-58" href="#__codelineno-36-58"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-36-59" name="__codelineno-36-59" href="#__codelineno-36-59"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">keys</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="kt">number</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="p">)[]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-60" name="__codelineno-36-60" href="#__codelineno-36-60"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="kt">number</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="p">)[]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-36-61" name="__codelineno-36-61" href="#__codelineno-36-61"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-62" name="__codelineno-36-62" href="#__codelineno-36-62"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-63" name="__codelineno-36-63" href="#__codelineno-36-63"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">].</span><span class="nx">key</span><span class="p">);</span>
<a id="__codelineno-36-64" name="__codelineno-36-64" href="#__codelineno-36-64"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-36-65" name="__codelineno-36-65" href="#__codelineno-36-65"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-36-66" name="__codelineno-36-66" href="#__codelineno-36-66"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-36-67" name="__codelineno-36-67" href="#__codelineno-36-67"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-68" name="__codelineno-36-68" href="#__codelineno-36-68"></a>
<a id="__codelineno-36-69" name="__codelineno-36-69" href="#__codelineno-36-69"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-36-70" name="__codelineno-36-70" href="#__codelineno-36-70"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">values</span><span class="p">()</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="p">)[]</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-71" name="__codelineno-36-71" href="#__codelineno-36-71"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">arr</span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="kt">string</span><span class="w"> </span><span class="o">|</span><span class="w"> </span><span class="kc">undefined</span><span class="p">)[]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-36-72" name="__codelineno-36-72" href="#__codelineno-36-72"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">let</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mf">0</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">.</span><span class="nx">length</span><span class="p">;</span><span class="w"> </span><span class="nx">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-73" name="__codelineno-36-73" href="#__codelineno-36-73"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">])</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-74" name="__codelineno-36-74" href="#__codelineno-36-74"></a><span class="w">                </span><span class="nx">arr</span><span class="p">.</span><span class="nx">push</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="nx">buckets</span><span class="p">[</span><span class="nx">i</span><span class="p">].</span><span class="nx">val</span><span class="p">);</span>
<a id="__codelineno-36-75" name="__codelineno-36-75" href="#__codelineno-36-75"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-36-76" name="__codelineno-36-76" href="#__codelineno-36-76"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-36-77" name="__codelineno-36-77" href="#__codelineno-36-77"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="nx">arr</span><span class="p">;</span>
<a id="__codelineno-36-78" name="__codelineno-36-78" href="#__codelineno-36-78"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-79" name="__codelineno-36-79" href="#__codelineno-36-79"></a>
<a id="__codelineno-36-80" name="__codelineno-36-80" href="#__codelineno-36-80"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-36-81" name="__codelineno-36-81" href="#__codelineno-36-81"></a><span class="w">    </span><span class="k">public</span><span class="w"> </span><span class="nx">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-82" name="__codelineno-36-82" href="#__codelineno-36-82"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="nx">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="nx">entries</span><span class="p">();</span>
<a id="__codelineno-36-83" name="__codelineno-36-83" href="#__codelineno-36-83"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">const</span><span class="w"> </span><span class="nx">pair</span><span class="w"> </span><span class="k">of</span><span class="w"> </span><span class="nx">pairSet</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-36-84" name="__codelineno-36-84" href="#__codelineno-36-84"></a><span class="w">            </span><span class="nx">console</span><span class="p">.</span><span class="nx">info</span><span class="p">(</span><span class="sb">`</span><span class="si">${</span><span class="nx">pair</span><span class="p">.</span><span class="nx">key</span><span class="si">}</span><span class="sb"> -&gt; </span><span class="si">${</span><span class="nx">pair</span><span class="p">.</span><span class="nx">val</span><span class="si">}</span><span class="sb">`</span><span class="p">);</span>
<a id="__codelineno-36-85" name="__codelineno-36-85" href="#__codelineno-36-85"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-36-86" name="__codelineno-36-86" href="#__codelineno-36-86"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-36-87" name="__codelineno-36-87" href="#__codelineno-36-87"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.dart</span><pre id="__code_37"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_37 > code"></button><code><a id="__codelineno-37-1" name="__codelineno-37-1" href="#__codelineno-37-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-37-2" name="__codelineno-37-2" href="#__codelineno-37-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-3" name="__codelineno-37-3" href="#__codelineno-37-3"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-37-4" name="__codelineno-37-4" href="#__codelineno-37-4"></a><span class="w">  </span><span class="kt">String</span><span class="w"> </span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-37-5" name="__codelineno-37-5" href="#__codelineno-37-5"></a><span class="w">  </span><span class="n">Pair</span><span class="p">(</span><span class="k">this</span><span class="p">.</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="k">this</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-37-6" name="__codelineno-37-6" href="#__codelineno-37-6"></a><span class="p">}</span>
<a id="__codelineno-37-7" name="__codelineno-37-7" href="#__codelineno-37-7"></a>
<a id="__codelineno-37-8" name="__codelineno-37-8" href="#__codelineno-37-8"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-37-9" name="__codelineno-37-9" href="#__codelineno-37-9"></a><span class="kd">class</span><span class="w"> </span><span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-10" name="__codelineno-37-10" href="#__codelineno-37-10"></a><span class="w">  </span><span class="kd">late</span><span class="w"> </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">?&gt;</span><span class="w"> </span><span class="n">_buckets</span><span class="p">;</span>
<a id="__codelineno-37-11" name="__codelineno-37-11" href="#__codelineno-37-11"></a>
<a id="__codelineno-37-12" name="__codelineno-37-12" href="#__codelineno-37-12"></a><span class="w">  </span><span class="n">ArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-13" name="__codelineno-37-13" href="#__codelineno-37-13"></a><span class="w">    </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-37-14" name="__codelineno-37-14" href="#__codelineno-37-14"></a><span class="w">    </span><span class="n">_buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">List</span><span class="p">.</span><span class="n">filled</span><span class="p">(</span><span class="m">100</span><span class="p">,</span><span class="w"> </span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-37-15" name="__codelineno-37-15" href="#__codelineno-37-15"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-16" name="__codelineno-37-16" href="#__codelineno-37-16"></a>
<a id="__codelineno-37-17" name="__codelineno-37-17" href="#__codelineno-37-17"></a><span class="w">  </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-37-18" name="__codelineno-37-18" href="#__codelineno-37-18"></a><span class="w">  </span><span class="kt">int</span><span class="w"> </span><span class="n">_hashFunc</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-19" name="__codelineno-37-19" href="#__codelineno-37-19"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m">100</span><span class="p">;</span>
<a id="__codelineno-37-20" name="__codelineno-37-20" href="#__codelineno-37-20"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">index</span><span class="p">;</span>
<a id="__codelineno-37-21" name="__codelineno-37-21" href="#__codelineno-37-21"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-22" name="__codelineno-37-22" href="#__codelineno-37-22"></a>
<a id="__codelineno-37-23" name="__codelineno-37-23" href="#__codelineno-37-23"></a><span class="w">  </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-37-24" name="__codelineno-37-24" href="#__codelineno-37-24"></a><span class="w">  </span><span class="kt">String</span><span class="o">?</span><span class="w"> </span><span class="kd">get</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-25" name="__codelineno-37-25" href="#__codelineno-37-25"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-37-26" name="__codelineno-37-26" href="#__codelineno-37-26"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_buckets</span><span class="p">[</span><span class="n">index</span><span class="p">];</span>
<a id="__codelineno-37-27" name="__codelineno-37-27" href="#__codelineno-37-27"></a><span class="w">    </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-28" name="__codelineno-37-28" href="#__codelineno-37-28"></a><span class="w">      </span><span class="k">return</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-37-29" name="__codelineno-37-29" href="#__codelineno-37-29"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-30" name="__codelineno-37-30" href="#__codelineno-37-30"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-37-31" name="__codelineno-37-31" href="#__codelineno-37-31"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-32" name="__codelineno-37-32" href="#__codelineno-37-32"></a>
<a id="__codelineno-37-33" name="__codelineno-37-33" href="#__codelineno-37-33"></a><span class="w">  </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-37-34" name="__codelineno-37-34" href="#__codelineno-37-34"></a><span class="w">  </span><span class="kt">void</span><span class="w"> </span><span class="n">put</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="kt">String</span><span class="w"> </span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-35" name="__codelineno-37-35" href="#__codelineno-37-35"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-37-36" name="__codelineno-37-36" href="#__codelineno-37-36"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-37-37" name="__codelineno-37-37" href="#__codelineno-37-37"></a><span class="w">    </span><span class="n">_buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span><span class="p">;</span>
<a id="__codelineno-37-38" name="__codelineno-37-38" href="#__codelineno-37-38"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-39" name="__codelineno-37-39" href="#__codelineno-37-39"></a>
<a id="__codelineno-37-40" name="__codelineno-37-40" href="#__codelineno-37-40"></a><span class="w">  </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-37-41" name="__codelineno-37-41" href="#__codelineno-37-41"></a><span class="w">  </span><span class="kt">void</span><span class="w"> </span><span class="n">remove</span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-42" name="__codelineno-37-42" href="#__codelineno-37-42"></a><span class="w">    </span><span class="kd">final</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">_hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-37-43" name="__codelineno-37-43" href="#__codelineno-37-43"></a><span class="w">    </span><span class="n">_buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-37-44" name="__codelineno-37-44" href="#__codelineno-37-44"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-45" name="__codelineno-37-45" href="#__codelineno-37-45"></a>
<a id="__codelineno-37-46" name="__codelineno-37-46" href="#__codelineno-37-46"></a><span class="w">  </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-37-47" name="__codelineno-37-47" href="#__codelineno-37-47"></a><span class="w">  </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-48" name="__codelineno-37-48" href="#__codelineno-37-48"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="n">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-37-49" name="__codelineno-37-49" href="#__codelineno-37-49"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">_buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-50" name="__codelineno-37-50" href="#__codelineno-37-50"></a><span class="w">      </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-51" name="__codelineno-37-51" href="#__codelineno-37-51"></a><span class="w">        </span><span class="n">pairSet</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">pair</span><span class="p">);</span>
<a id="__codelineno-37-52" name="__codelineno-37-52" href="#__codelineno-37-52"></a><span class="w">      </span><span class="p">}</span>
<a id="__codelineno-37-53" name="__codelineno-37-53" href="#__codelineno-37-53"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-54" name="__codelineno-37-54" href="#__codelineno-37-54"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">pairSet</span><span class="p">;</span>
<a id="__codelineno-37-55" name="__codelineno-37-55" href="#__codelineno-37-55"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-56" name="__codelineno-37-56" href="#__codelineno-37-56"></a>
<a id="__codelineno-37-57" name="__codelineno-37-57" href="#__codelineno-37-57"></a><span class="w">  </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-37-58" name="__codelineno-37-58" href="#__codelineno-37-58"></a><span class="w">  </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-59" name="__codelineno-37-59" href="#__codelineno-37-59"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">int</span><span class="o">&gt;</span><span class="w"> </span><span class="n">keySet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-37-60" name="__codelineno-37-60" href="#__codelineno-37-60"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">_buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-61" name="__codelineno-37-61" href="#__codelineno-37-61"></a><span class="w">      </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-62" name="__codelineno-37-62" href="#__codelineno-37-62"></a><span class="w">        </span><span class="n">keySet</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-37-63" name="__codelineno-37-63" href="#__codelineno-37-63"></a><span class="w">      </span><span class="p">}</span>
<a id="__codelineno-37-64" name="__codelineno-37-64" href="#__codelineno-37-64"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-65" name="__codelineno-37-65" href="#__codelineno-37-65"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">keySet</span><span class="p">;</span>
<a id="__codelineno-37-66" name="__codelineno-37-66" href="#__codelineno-37-66"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-67" name="__codelineno-37-67" href="#__codelineno-37-67"></a>
<a id="__codelineno-37-68" name="__codelineno-37-68" href="#__codelineno-37-68"></a><span class="w">  </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-37-69" name="__codelineno-37-69" href="#__codelineno-37-69"></a><span class="w">  </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">String</span><span class="o">&gt;</span><span class="w"> </span><span class="n">values</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-70" name="__codelineno-37-70" href="#__codelineno-37-70"></a><span class="w">    </span><span class="n">List</span><span class="o">&lt;</span><span class="kt">String</span><span class="o">&gt;</span><span class="w"> </span><span class="n">valueSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">[];</span>
<a id="__codelineno-37-71" name="__codelineno-37-71" href="#__codelineno-37-71"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="o">?</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">_buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-72" name="__codelineno-37-72" href="#__codelineno-37-72"></a><span class="w">      </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-73" name="__codelineno-37-73" href="#__codelineno-37-73"></a><span class="w">        </span><span class="n">valueSet</span><span class="p">.</span><span class="n">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-37-74" name="__codelineno-37-74" href="#__codelineno-37-74"></a><span class="w">      </span><span class="p">}</span>
<a id="__codelineno-37-75" name="__codelineno-37-75" href="#__codelineno-37-75"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-76" name="__codelineno-37-76" href="#__codelineno-37-76"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">valueSet</span><span class="p">;</span>
<a id="__codelineno-37-77" name="__codelineno-37-77" href="#__codelineno-37-77"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-78" name="__codelineno-37-78" href="#__codelineno-37-78"></a>
<a id="__codelineno-37-79" name="__codelineno-37-79" href="#__codelineno-37-79"></a><span class="w">  </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-37-80" name="__codelineno-37-80" href="#__codelineno-37-80"></a><span class="w">  </span><span class="kt">void</span><span class="w"> </span><span class="n">printHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-81" name="__codelineno-37-81" href="#__codelineno-37-81"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kd">final</span><span class="w"> </span><span class="n">Pair</span><span class="w"> </span><span class="n">kv</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">pairSet</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-37-82" name="__codelineno-37-82" href="#__codelineno-37-82"></a><span class="w">      </span><span class="n">print</span><span class="p">(</span><span class="s2">"</span><span class="si">${</span><span class="n">kv</span><span class="p">.</span><span class="n">key</span><span class="si">}</span><span class="s2"> -&gt; </span><span class="si">${</span><span class="n">kv</span><span class="p">.</span><span class="n">val</span><span class="si">}</span><span class="s2">"</span><span class="p">);</span>
<a id="__codelineno-37-83" name="__codelineno-37-83" href="#__codelineno-37-83"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-37-84" name="__codelineno-37-84" href="#__codelineno-37-84"></a><span class="w">  </span><span class="p">}</span>
<a id="__codelineno-37-85" name="__codelineno-37-85" href="#__codelineno-37-85"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.rs</span><pre id="__code_38"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_38 > code"></button><code><a id="__codelineno-38-1" name="__codelineno-38-1" href="#__codelineno-38-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-38-2" name="__codelineno-38-2" href="#__codelineno-38-2"></a><span class="cp">#[derive(Debug, Clone, PartialEq)]</span>
<a id="__codelineno-38-3" name="__codelineno-38-3" href="#__codelineno-38-3"></a><span class="k">pub</span><span class="w"> </span><span class="k">struct</span> <span class="nc">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-4" name="__codelineno-38-4" href="#__codelineno-38-4"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="n">key</span>: <span class="kt">i32</span><span class="p">,</span>
<a id="__codelineno-38-5" name="__codelineno-38-5" href="#__codelineno-38-5"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="n">val</span>: <span class="nb">String</span><span class="p">,</span>
<a id="__codelineno-38-6" name="__codelineno-38-6" href="#__codelineno-38-6"></a><span class="p">}</span>
<a id="__codelineno-38-7" name="__codelineno-38-7" href="#__codelineno-38-7"></a>
<a id="__codelineno-38-8" name="__codelineno-38-8" href="#__codelineno-38-8"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-38-9" name="__codelineno-38-9" href="#__codelineno-38-9"></a><span class="k">pub</span><span class="w"> </span><span class="k">struct</span> <span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-10" name="__codelineno-38-10" href="#__codelineno-38-10"></a><span class="w">    </span><span class="n">buckets</span>: <span class="nb">Vec</span><span class="o">&lt;</span><span class="nb">Option</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;&gt;</span><span class="p">,</span>
<a id="__codelineno-38-11" name="__codelineno-38-11" href="#__codelineno-38-11"></a><span class="p">}</span>
<a id="__codelineno-38-12" name="__codelineno-38-12" href="#__codelineno-38-12"></a>
<a id="__codelineno-38-13" name="__codelineno-38-13" href="#__codelineno-38-13"></a><span class="k">impl</span><span class="w"> </span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-14" name="__codelineno-38-14" href="#__codelineno-38-14"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">new</span><span class="p">()</span><span class="w"> </span>-&gt; <span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-15" name="__codelineno-38-15" href="#__codelineno-38-15"></a><span class="w">        </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-38-16" name="__codelineno-38-16" href="#__codelineno-38-16"></a><span class="w">        </span><span class="bp">Self</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-17" name="__codelineno-38-17" href="#__codelineno-38-17"></a><span class="w">            </span><span class="n">buckets</span>: <span class="nc">vec</span><span class="o">!</span><span class="p">[</span><span class="nb">None</span><span class="p">;</span><span class="w"> </span><span class="mi">100</span><span class="p">],</span>
<a id="__codelineno-38-18" name="__codelineno-38-18" href="#__codelineno-38-18"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-38-19" name="__codelineno-38-19" href="#__codelineno-38-19"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-20" name="__codelineno-38-20" href="#__codelineno-38-20"></a>
<a id="__codelineno-38-21" name="__codelineno-38-21" href="#__codelineno-38-21"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-38-22" name="__codelineno-38-22" href="#__codelineno-38-22"></a><span class="w">    </span><span class="k">fn</span> <span class="nf">hash_func</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span>: <span class="kt">i32</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="kt">usize</span> <span class="p">{</span>
<a id="__codelineno-38-23" name="__codelineno-38-23" href="#__codelineno-38-23"></a><span class="w">        </span><span class="n">key</span><span class="w"> </span><span class="k">as</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span>
<a id="__codelineno-38-24" name="__codelineno-38-24" href="#__codelineno-38-24"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-25" name="__codelineno-38-25" href="#__codelineno-38-25"></a>
<a id="__codelineno-38-26" name="__codelineno-38-26" href="#__codelineno-38-26"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-38-27" name="__codelineno-38-27" href="#__codelineno-38-27"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">get</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span>: <span class="kt">i32</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Option</span><span class="o">&lt;&amp;</span><span class="nb">String</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-28" name="__codelineno-38-28" href="#__codelineno-38-28"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-38-29" name="__codelineno-38-29" href="#__codelineno-38-29"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">].</span><span class="n">as_ref</span><span class="p">().</span><span class="n">map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="o">&amp;</span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-38-30" name="__codelineno-38-30" href="#__codelineno-38-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-31" name="__codelineno-38-31" href="#__codelineno-38-31"></a>
<a id="__codelineno-38-32" name="__codelineno-38-32" href="#__codelineno-38-32"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-38-33" name="__codelineno-38-33" href="#__codelineno-38-33"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">put</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span>: <span class="kt">i32</span><span class="p">,</span><span class="w"> </span><span class="n">val</span>: <span class="kp">&amp;</span><span class="kt">str</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-34" name="__codelineno-38-34" href="#__codelineno-38-34"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-38-35" name="__codelineno-38-35" href="#__codelineno-38-35"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Some</span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-36" name="__codelineno-38-36" href="#__codelineno-38-36"></a><span class="w">            </span><span class="n">key</span><span class="p">,</span>
<a id="__codelineno-38-37" name="__codelineno-38-37" href="#__codelineno-38-37"></a><span class="w">            </span><span class="n">val</span>: <span class="nc">val</span><span class="p">.</span><span class="n">to_string</span><span class="p">(),</span>
<a id="__codelineno-38-38" name="__codelineno-38-38" href="#__codelineno-38-38"></a><span class="w">        </span><span class="p">});</span>
<a id="__codelineno-38-39" name="__codelineno-38-39" href="#__codelineno-38-39"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-40" name="__codelineno-38-40" href="#__codelineno-38-40"></a>
<a id="__codelineno-38-41" name="__codelineno-38-41" href="#__codelineno-38-41"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-38-42" name="__codelineno-38-42" href="#__codelineno-38-42"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">remove</span><span class="p">(</span><span class="o">&amp;</span><span class="k">mut</span><span class="w"> </span><span class="bp">self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span>: <span class="kt">i32</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-43" name="__codelineno-38-43" href="#__codelineno-38-43"></a><span class="w">        </span><span class="kd">let</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-38-44" name="__codelineno-38-44" href="#__codelineno-38-44"></a><span class="w">        </span><span class="c1">// 置为 None ，代表删除</span>
<a id="__codelineno-38-45" name="__codelineno-38-45" href="#__codelineno-38-45"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">None</span><span class="p">;</span>
<a id="__codelineno-38-46" name="__codelineno-38-46" href="#__codelineno-38-46"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-47" name="__codelineno-38-47" href="#__codelineno-38-47"></a>
<a id="__codelineno-38-48" name="__codelineno-38-48" href="#__codelineno-38-48"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-38-49" name="__codelineno-38-49" href="#__codelineno-38-49"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">entry_set</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Vec</span><span class="o">&lt;&amp;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-50" name="__codelineno-38-50" href="#__codelineno-38-50"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span>
<a id="__codelineno-38-51" name="__codelineno-38-51" href="#__codelineno-38-51"></a><span class="w">            </span><span class="p">.</span><span class="n">iter</span><span class="p">()</span>
<a id="__codelineno-38-52" name="__codelineno-38-52" href="#__codelineno-38-52"></a><span class="w">            </span><span class="p">.</span><span class="n">filter_map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">as_ref</span><span class="p">())</span>
<a id="__codelineno-38-53" name="__codelineno-38-53" href="#__codelineno-38-53"></a><span class="w">            </span><span class="p">.</span><span class="n">collect</span><span class="p">()</span>
<a id="__codelineno-38-54" name="__codelineno-38-54" href="#__codelineno-38-54"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-55" name="__codelineno-38-55" href="#__codelineno-38-55"></a>
<a id="__codelineno-38-56" name="__codelineno-38-56" href="#__codelineno-38-56"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-38-57" name="__codelineno-38-57" href="#__codelineno-38-57"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">key_set</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Vec</span><span class="o">&lt;&amp;</span><span class="kt">i32</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-58" name="__codelineno-38-58" href="#__codelineno-38-58"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span>
<a id="__codelineno-38-59" name="__codelineno-38-59" href="#__codelineno-38-59"></a><span class="w">            </span><span class="p">.</span><span class="n">iter</span><span class="p">()</span>
<a id="__codelineno-38-60" name="__codelineno-38-60" href="#__codelineno-38-60"></a><span class="w">            </span><span class="p">.</span><span class="n">filter_map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">as_ref</span><span class="p">().</span><span class="n">map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="o">&amp;</span><span class="n">pair</span><span class="p">.</span><span class="n">key</span><span class="p">))</span>
<a id="__codelineno-38-61" name="__codelineno-38-61" href="#__codelineno-38-61"></a><span class="w">            </span><span class="p">.</span><span class="n">collect</span><span class="p">()</span>
<a id="__codelineno-38-62" name="__codelineno-38-62" href="#__codelineno-38-62"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-63" name="__codelineno-38-63" href="#__codelineno-38-63"></a>
<a id="__codelineno-38-64" name="__codelineno-38-64" href="#__codelineno-38-64"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-38-65" name="__codelineno-38-65" href="#__codelineno-38-65"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">value_set</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span>-&gt; <span class="nb">Vec</span><span class="o">&lt;&amp;</span><span class="nb">String</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-66" name="__codelineno-38-66" href="#__codelineno-38-66"></a><span class="w">        </span><span class="bp">self</span><span class="p">.</span><span class="n">buckets</span>
<a id="__codelineno-38-67" name="__codelineno-38-67" href="#__codelineno-38-67"></a><span class="w">            </span><span class="p">.</span><span class="n">iter</span><span class="p">()</span>
<a id="__codelineno-38-68" name="__codelineno-38-68" href="#__codelineno-38-68"></a><span class="w">            </span><span class="p">.</span><span class="n">filter_map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">as_ref</span><span class="p">().</span><span class="n">map</span><span class="p">(</span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="o">&amp;</span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">))</span>
<a id="__codelineno-38-69" name="__codelineno-38-69" href="#__codelineno-38-69"></a><span class="w">            </span><span class="p">.</span><span class="n">collect</span><span class="p">()</span>
<a id="__codelineno-38-70" name="__codelineno-38-70" href="#__codelineno-38-70"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-71" name="__codelineno-38-71" href="#__codelineno-38-71"></a>
<a id="__codelineno-38-72" name="__codelineno-38-72" href="#__codelineno-38-72"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-38-73" name="__codelineno-38-73" href="#__codelineno-38-73"></a><span class="w">    </span><span class="k">pub</span><span class="w"> </span><span class="k">fn</span> <span class="nf">print</span><span class="p">(</span><span class="o">&amp;</span><span class="bp">self</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-74" name="__codelineno-38-74" href="#__codelineno-38-74"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="bp">self</span><span class="p">.</span><span class="n">entry_set</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-38-75" name="__codelineno-38-75" href="#__codelineno-38-75"></a><span class="w">            </span><span class="fm">println!</span><span class="p">(</span><span class="s">"{} -&gt; {}"</span><span class="p">,</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-38-76" name="__codelineno-38-76" href="#__codelineno-38-76"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-38-77" name="__codelineno-38-77" href="#__codelineno-38-77"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-38-78" name="__codelineno-38-78" href="#__codelineno-38-78"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.c</span><pre id="__code_39"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_39 > code"></button><code><a id="__codelineno-39-1" name="__codelineno-39-1" href="#__codelineno-39-1"></a><span class="cm">/* 键值对 int-&gt;string */</span>
<a id="__codelineno-39-2" name="__codelineno-39-2" href="#__codelineno-39-2"></a><span class="k">typedef</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-3" name="__codelineno-39-3" href="#__codelineno-39-3"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-39-4" name="__codelineno-39-4" href="#__codelineno-39-4"></a><span class="w">    </span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-39-5" name="__codelineno-39-5" href="#__codelineno-39-5"></a><span class="p">}</span><span class="w"> </span><span class="n">Pair</span><span class="p">;</span>
<a id="__codelineno-39-6" name="__codelineno-39-6" href="#__codelineno-39-6"></a>
<a id="__codelineno-39-7" name="__codelineno-39-7" href="#__codelineno-39-7"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-39-8" name="__codelineno-39-8" href="#__codelineno-39-8"></a><span class="k">typedef</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-9" name="__codelineno-39-9" href="#__codelineno-39-9"></a><span class="w">    </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">buckets</span><span class="p">[</span><span class="n">MAX_SIZE</span><span class="p">];</span>
<a id="__codelineno-39-10" name="__codelineno-39-10" href="#__codelineno-39-10"></a><span class="p">}</span><span class="w"> </span><span class="n">ArrayHashMap</span><span class="p">;</span>
<a id="__codelineno-39-11" name="__codelineno-39-11" href="#__codelineno-39-11"></a>
<a id="__codelineno-39-12" name="__codelineno-39-12" href="#__codelineno-39-12"></a><span class="cm">/* 构造函数 */</span>
<a id="__codelineno-39-13" name="__codelineno-39-13" href="#__codelineno-39-13"></a><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="nf">newArrayHashMap</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-14" name="__codelineno-39-14" href="#__codelineno-39-14"></a><span class="w">    </span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="p">));</span>
<a id="__codelineno-39-15" name="__codelineno-39-15" href="#__codelineno-39-15"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-16" name="__codelineno-39-16" href="#__codelineno-39-16"></a><span class="w">        </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">;</span>
<a id="__codelineno-39-17" name="__codelineno-39-17" href="#__codelineno-39-17"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-18" name="__codelineno-39-18" href="#__codelineno-39-18"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="n">hmap</span><span class="p">;</span>
<a id="__codelineno-39-19" name="__codelineno-39-19" href="#__codelineno-39-19"></a><span class="p">}</span>
<a id="__codelineno-39-20" name="__codelineno-39-20" href="#__codelineno-39-20"></a>
<a id="__codelineno-39-21" name="__codelineno-39-21" href="#__codelineno-39-21"></a><span class="cm">/* 析构函数 */</span>
<a id="__codelineno-39-22" name="__codelineno-39-22" href="#__codelineno-39-22"></a><span class="kt">void</span><span class="w"> </span><span class="nf">delArrayHashMap</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-23" name="__codelineno-39-23" href="#__codelineno-39-23"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-24" name="__codelineno-39-24" href="#__codelineno-39-24"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-25" name="__codelineno-39-25" href="#__codelineno-39-25"></a><span class="w">            </span><span class="n">free</span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-39-26" name="__codelineno-39-26" href="#__codelineno-39-26"></a><span class="w">            </span><span class="n">free</span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]);</span>
<a id="__codelineno-39-27" name="__codelineno-39-27" href="#__codelineno-39-27"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-28" name="__codelineno-39-28" href="#__codelineno-39-28"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-29" name="__codelineno-39-29" href="#__codelineno-39-29"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">hmap</span><span class="p">);</span>
<a id="__codelineno-39-30" name="__codelineno-39-30" href="#__codelineno-39-30"></a><span class="p">}</span>
<a id="__codelineno-39-31" name="__codelineno-39-31" href="#__codelineno-39-31"></a>
<a id="__codelineno-39-32" name="__codelineno-39-32" href="#__codelineno-39-32"></a><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-39-33" name="__codelineno-39-33" href="#__codelineno-39-33"></a><span class="kt">void</span><span class="w"> </span><span class="nf">put</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="k">const</span><span class="w"> </span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-34" name="__codelineno-39-34" href="#__codelineno-39-34"></a><span class="w">    </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">Pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">Pair</span><span class="p">));</span>
<a id="__codelineno-39-35" name="__codelineno-39-35" href="#__codelineno-39-35"></a><span class="w">    </span><span class="n">Pair</span><span class="o">-&gt;</span><span class="n">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-39-36" name="__codelineno-39-36" href="#__codelineno-39-36"></a><span class="w">    </span><span class="n">Pair</span><span class="o">-&gt;</span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="n">strlen</span><span class="p">(</span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-39-37" name="__codelineno-39-37" href="#__codelineno-39-37"></a><span class="w">    </span><span class="n">strcpy</span><span class="p">(</span><span class="n">Pair</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-39-38" name="__codelineno-39-38" href="#__codelineno-39-38"></a>
<a id="__codelineno-39-39" name="__codelineno-39-39" href="#__codelineno-39-39"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-39-40" name="__codelineno-39-40" href="#__codelineno-39-40"></a><span class="w">    </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Pair</span><span class="p">;</span>
<a id="__codelineno-39-41" name="__codelineno-39-41" href="#__codelineno-39-41"></a><span class="p">}</span>
<a id="__codelineno-39-42" name="__codelineno-39-42" href="#__codelineno-39-42"></a>
<a id="__codelineno-39-43" name="__codelineno-39-43" href="#__codelineno-39-43"></a><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-39-44" name="__codelineno-39-44" href="#__codelineno-39-44"></a><span class="kt">void</span><span class="w"> </span><span class="nf">removeItem</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="k">const</span><span class="w"> </span><span class="kt">int</span><span class="w"> </span><span class="n">key</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-45" name="__codelineno-39-45" href="#__codelineno-39-45"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-39-46" name="__codelineno-39-46" href="#__codelineno-39-46"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-39-47" name="__codelineno-39-47" href="#__codelineno-39-47"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]);</span>
<a id="__codelineno-39-48" name="__codelineno-39-48" href="#__codelineno-39-48"></a><span class="w">    </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">;</span>
<a id="__codelineno-39-49" name="__codelineno-39-49" href="#__codelineno-39-49"></a><span class="p">}</span>
<a id="__codelineno-39-50" name="__codelineno-39-50" href="#__codelineno-39-50"></a>
<a id="__codelineno-39-51" name="__codelineno-39-51" href="#__codelineno-39-51"></a><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-39-52" name="__codelineno-39-52" href="#__codelineno-39-52"></a><span class="kt">void</span><span class="w"> </span><span class="nf">pairSet</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="n">MapSet</span><span class="w"> </span><span class="o">*</span><span class="n">set</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-53" name="__codelineno-39-53" href="#__codelineno-39-53"></a><span class="w">    </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">entries</span><span class="p">;</span>
<a id="__codelineno-39-54" name="__codelineno-39-54" href="#__codelineno-39-54"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-55" name="__codelineno-39-55" href="#__codelineno-39-55"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">total</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-56" name="__codelineno-39-56" href="#__codelineno-39-56"></a><span class="w">    </span><span class="cm">/* 统计有效键值对数量 */</span>
<a id="__codelineno-39-57" name="__codelineno-39-57" href="#__codelineno-39-57"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-58" name="__codelineno-39-58" href="#__codelineno-39-58"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-59" name="__codelineno-39-59" href="#__codelineno-39-59"></a><span class="w">            </span><span class="n">total</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-60" name="__codelineno-39-60" href="#__codelineno-39-60"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-61" name="__codelineno-39-61" href="#__codelineno-39-61"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-62" name="__codelineno-39-62" href="#__codelineno-39-62"></a><span class="w">    </span><span class="n">entries</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="k">sizeof</span><span class="p">(</span><span class="n">Pair</span><span class="p">)</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="n">total</span><span class="p">);</span>
<a id="__codelineno-39-63" name="__codelineno-39-63" href="#__codelineno-39-63"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-64" name="__codelineno-39-64" href="#__codelineno-39-64"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-65" name="__codelineno-39-65" href="#__codelineno-39-65"></a><span class="w">            </span><span class="n">entries</span><span class="p">[</span><span class="n">index</span><span class="p">].</span><span class="n">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-39-66" name="__codelineno-39-66" href="#__codelineno-39-66"></a><span class="w">            </span><span class="n">entries</span><span class="p">[</span><span class="n">index</span><span class="p">].</span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="n">strlen</span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">)</span><span class="w"> </span><span class="o">+</span><span class="w"> </span><span class="mi">1</span><span class="p">);</span>
<a id="__codelineno-39-67" name="__codelineno-39-67" href="#__codelineno-39-67"></a><span class="w">            </span><span class="n">strcpy</span><span class="p">(</span><span class="n">entries</span><span class="p">[</span><span class="n">index</span><span class="p">].</span><span class="n">val</span><span class="p">,</span><span class="w"> </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-39-68" name="__codelineno-39-68" href="#__codelineno-39-68"></a><span class="w">            </span><span class="n">index</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-69" name="__codelineno-39-69" href="#__codelineno-39-69"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-70" name="__codelineno-39-70" href="#__codelineno-39-70"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-71" name="__codelineno-39-71" href="#__codelineno-39-71"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">entries</span><span class="p">;</span>
<a id="__codelineno-39-72" name="__codelineno-39-72" href="#__codelineno-39-72"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">len</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">total</span><span class="p">;</span>
<a id="__codelineno-39-73" name="__codelineno-39-73" href="#__codelineno-39-73"></a><span class="p">}</span>
<a id="__codelineno-39-74" name="__codelineno-39-74" href="#__codelineno-39-74"></a>
<a id="__codelineno-39-75" name="__codelineno-39-75" href="#__codelineno-39-75"></a><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-39-76" name="__codelineno-39-76" href="#__codelineno-39-76"></a><span class="kt">void</span><span class="w"> </span><span class="nf">keySet</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="n">MapSet</span><span class="w"> </span><span class="o">*</span><span class="n">set</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-77" name="__codelineno-39-77" href="#__codelineno-39-77"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="o">*</span><span class="n">keys</span><span class="p">;</span>
<a id="__codelineno-39-78" name="__codelineno-39-78" href="#__codelineno-39-78"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-79" name="__codelineno-39-79" href="#__codelineno-39-79"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">total</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-80" name="__codelineno-39-80" href="#__codelineno-39-80"></a><span class="w">    </span><span class="cm">/* 统计有效键值对数量 */</span>
<a id="__codelineno-39-81" name="__codelineno-39-81" href="#__codelineno-39-81"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-82" name="__codelineno-39-82" href="#__codelineno-39-82"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-83" name="__codelineno-39-83" href="#__codelineno-39-83"></a><span class="w">            </span><span class="n">total</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-84" name="__codelineno-39-84" href="#__codelineno-39-84"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-85" name="__codelineno-39-85" href="#__codelineno-39-85"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-86" name="__codelineno-39-86" href="#__codelineno-39-86"></a><span class="w">    </span><span class="n">keys</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="n">total</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="k">sizeof</span><span class="p">(</span><span class="kt">int</span><span class="p">));</span>
<a id="__codelineno-39-87" name="__codelineno-39-87" href="#__codelineno-39-87"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-88" name="__codelineno-39-88" href="#__codelineno-39-88"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-89" name="__codelineno-39-89" href="#__codelineno-39-89"></a><span class="w">            </span><span class="n">keys</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">key</span><span class="p">;</span>
<a id="__codelineno-39-90" name="__codelineno-39-90" href="#__codelineno-39-90"></a><span class="w">            </span><span class="n">index</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-91" name="__codelineno-39-91" href="#__codelineno-39-91"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-92" name="__codelineno-39-92" href="#__codelineno-39-92"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-93" name="__codelineno-39-93" href="#__codelineno-39-93"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">keys</span><span class="p">;</span>
<a id="__codelineno-39-94" name="__codelineno-39-94" href="#__codelineno-39-94"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">len</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">total</span><span class="p">;</span>
<a id="__codelineno-39-95" name="__codelineno-39-95" href="#__codelineno-39-95"></a><span class="p">}</span>
<a id="__codelineno-39-96" name="__codelineno-39-96" href="#__codelineno-39-96"></a>
<a id="__codelineno-39-97" name="__codelineno-39-97" href="#__codelineno-39-97"></a><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-39-98" name="__codelineno-39-98" href="#__codelineno-39-98"></a><span class="kt">void</span><span class="w"> </span><span class="nf">valueSet</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="n">MapSet</span><span class="w"> </span><span class="o">*</span><span class="n">set</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-99" name="__codelineno-39-99" href="#__codelineno-39-99"></a><span class="w">    </span><span class="kt">char</span><span class="w"> </span><span class="o">**</span><span class="n">vals</span><span class="p">;</span>
<a id="__codelineno-39-100" name="__codelineno-39-100" href="#__codelineno-39-100"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">,</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-101" name="__codelineno-39-101" href="#__codelineno-39-101"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">total</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-39-102" name="__codelineno-39-102" href="#__codelineno-39-102"></a><span class="w">    </span><span class="cm">/* 统计有效键值对数量 */</span>
<a id="__codelineno-39-103" name="__codelineno-39-103" href="#__codelineno-39-103"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-104" name="__codelineno-39-104" href="#__codelineno-39-104"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-105" name="__codelineno-39-105" href="#__codelineno-39-105"></a><span class="w">            </span><span class="n">total</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-106" name="__codelineno-39-106" href="#__codelineno-39-106"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-107" name="__codelineno-39-107" href="#__codelineno-39-107"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-108" name="__codelineno-39-108" href="#__codelineno-39-108"></a><span class="w">    </span><span class="n">vals</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">malloc</span><span class="p">(</span><span class="n">total</span><span class="w"> </span><span class="o">*</span><span class="w"> </span><span class="k">sizeof</span><span class="p">(</span><span class="kt">char</span><span class="w"> </span><span class="o">*</span><span class="p">));</span>
<a id="__codelineno-39-109" name="__codelineno-39-109" href="#__codelineno-39-109"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">MAX_SIZE</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-110" name="__codelineno-39-110" href="#__codelineno-39-110"></a><span class="w">        </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="nb">NULL</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-111" name="__codelineno-39-111" href="#__codelineno-39-111"></a><span class="w">            </span><span class="n">vals</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hmap</span><span class="o">-&gt;</span><span class="n">buckets</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">-&gt;</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-39-112" name="__codelineno-39-112" href="#__codelineno-39-112"></a><span class="w">            </span><span class="n">index</span><span class="o">++</span><span class="p">;</span>
<a id="__codelineno-39-113" name="__codelineno-39-113" href="#__codelineno-39-113"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-39-114" name="__codelineno-39-114" href="#__codelineno-39-114"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-115" name="__codelineno-39-115" href="#__codelineno-39-115"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">vals</span><span class="p">;</span>
<a id="__codelineno-39-116" name="__codelineno-39-116" href="#__codelineno-39-116"></a><span class="w">    </span><span class="n">set</span><span class="o">-&gt;</span><span class="n">len</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">total</span><span class="p">;</span>
<a id="__codelineno-39-117" name="__codelineno-39-117" href="#__codelineno-39-117"></a><span class="p">}</span>
<a id="__codelineno-39-118" name="__codelineno-39-118" href="#__codelineno-39-118"></a>
<a id="__codelineno-39-119" name="__codelineno-39-119" href="#__codelineno-39-119"></a><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-39-120" name="__codelineno-39-120" href="#__codelineno-39-120"></a><span class="kt">void</span><span class="w"> </span><span class="nf">print</span><span class="p">(</span><span class="n">ArrayHashMap</span><span class="w"> </span><span class="o">*</span><span class="n">hmap</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-121" name="__codelineno-39-121" href="#__codelineno-39-121"></a><span class="w">    </span><span class="kt">int</span><span class="w"> </span><span class="n">i</span><span class="p">;</span>
<a id="__codelineno-39-122" name="__codelineno-39-122" href="#__codelineno-39-122"></a><span class="w">    </span><span class="n">MapSet</span><span class="w"> </span><span class="n">set</span><span class="p">;</span>
<a id="__codelineno-39-123" name="__codelineno-39-123" href="#__codelineno-39-123"></a><span class="w">    </span><span class="n">pairSet</span><span class="p">(</span><span class="n">hmap</span><span class="p">,</span><span class="w"> </span><span class="o">&amp;</span><span class="n">set</span><span class="p">);</span>
<a id="__codelineno-39-124" name="__codelineno-39-124" href="#__codelineno-39-124"></a><span class="w">    </span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="n">entries</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="p">(</span><span class="n">Pair</span><span class="w"> </span><span class="o">*</span><span class="p">)</span><span class="n">set</span><span class="p">.</span><span class="n">set</span><span class="p">;</span>
<a id="__codelineno-39-125" name="__codelineno-39-125" href="#__codelineno-39-125"></a><span class="w">    </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="n">set</span><span class="p">.</span><span class="n">len</span><span class="p">;</span><span class="w"> </span><span class="n">i</span><span class="o">++</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-39-126" name="__codelineno-39-126" href="#__codelineno-39-126"></a><span class="w">        </span><span class="n">printf</span><span class="p">(</span><span class="s">"%d -&gt; %s</span><span class="se">\n</span><span class="s">"</span><span class="p">,</span><span class="w"> </span><span class="n">entries</span><span class="p">[</span><span class="n">i</span><span class="p">].</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">entries</span><span class="p">[</span><span class="n">i</span><span class="p">].</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-39-127" name="__codelineno-39-127" href="#__codelineno-39-127"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-39-128" name="__codelineno-39-128" href="#__codelineno-39-128"></a><span class="w">    </span><span class="n">free</span><span class="p">(</span><span class="n">set</span><span class="p">.</span><span class="n">set</span><span class="p">);</span>
<a id="__codelineno-39-129" name="__codelineno-39-129" href="#__codelineno-39-129"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.kt</span><pre id="__code_40"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_40 > code"></button><code><a id="__codelineno-40-1" name="__codelineno-40-1" href="#__codelineno-40-1"></a><span class="cm">/* 键值对 */</span>
<a id="__codelineno-40-2" name="__codelineno-40-2" href="#__codelineno-40-2"></a><span class="kd">class</span><span class="w"> </span><span class="nc">Pair</span><span class="p">(</span>
<a id="__codelineno-40-3" name="__codelineno-40-3" href="#__codelineno-40-3"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">key</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">,</span>
<a id="__codelineno-40-4" name="__codelineno-40-4" href="#__codelineno-40-4"></a><span class="w">    </span><span class="kd">var</span><span class="w"> </span><span class="nv">_val</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span>
<a id="__codelineno-40-5" name="__codelineno-40-5" href="#__codelineno-40-5"></a><span class="p">)</span>
<a id="__codelineno-40-6" name="__codelineno-40-6" href="#__codelineno-40-6"></a>
<a id="__codelineno-40-7" name="__codelineno-40-7" href="#__codelineno-40-7"></a><span class="cm">/* 基于数组实现的哈希表 */</span>
<a id="__codelineno-40-8" name="__codelineno-40-8" href="#__codelineno-40-8"></a><span class="kd">class</span><span class="w"> </span><span class="nc">ArrayHashMap</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-9" name="__codelineno-40-9" href="#__codelineno-40-9"></a><span class="w">    </span><span class="c1">// 初始化数组，包含 100 个桶</span>
<a id="__codelineno-40-10" name="__codelineno-40-10" href="#__codelineno-40-10"></a><span class="w">    </span><span class="kd">private</span><span class="w"> </span><span class="kd">val</span><span class="w"> </span><span class="nv">buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">arrayOfNulls</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="p">(</span><span class="m">100</span><span class="p">)</span>
<a id="__codelineno-40-11" name="__codelineno-40-11" href="#__codelineno-40-11"></a>
<a id="__codelineno-40-12" name="__codelineno-40-12" href="#__codelineno-40-12"></a><span class="w">    </span><span class="cm">/* 哈希函数 */</span>
<a id="__codelineno-40-13" name="__codelineno-40-13" href="#__codelineno-40-13"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">Int</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-14" name="__codelineno-40-14" href="#__codelineno-40-14"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="m">100</span>
<a id="__codelineno-40-15" name="__codelineno-40-15" href="#__codelineno-40-15"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">index</span>
<a id="__codelineno-40-16" name="__codelineno-40-16" href="#__codelineno-40-16"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-17" name="__codelineno-40-17" href="#__codelineno-40-17"></a>
<a id="__codelineno-40-18" name="__codelineno-40-18" href="#__codelineno-40-18"></a><span class="w">    </span><span class="cm">/* 查询操作 */</span>
<a id="__codelineno-40-19" name="__codelineno-40-19" href="#__codelineno-40-19"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">get</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">):</span><span class="w"> </span><span class="kt">String?</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-20" name="__codelineno-40-20" href="#__codelineno-40-20"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-40-21" name="__codelineno-40-21" href="#__codelineno-40-21"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span><span class="w"> </span><span class="o">?:</span><span class="w"> </span><span class="k">return</span><span class="w"> </span><span class="kc">null</span>
<a id="__codelineno-40-22" name="__codelineno-40-22" href="#__codelineno-40-22"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="na">_val</span>
<a id="__codelineno-40-23" name="__codelineno-40-23" href="#__codelineno-40-23"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-24" name="__codelineno-40-24" href="#__codelineno-40-24"></a>
<a id="__codelineno-40-25" name="__codelineno-40-25" href="#__codelineno-40-25"></a><span class="w">    </span><span class="cm">/* 添加操作 */</span>
<a id="__codelineno-40-26" name="__codelineno-40-26" href="#__codelineno-40-26"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">put</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">,</span><span class="w"> </span><span class="n">_val</span><span class="p">:</span><span class="w"> </span><span class="kt">String</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-27" name="__codelineno-40-27" href="#__codelineno-40-27"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Pair</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">_val</span><span class="p">)</span>
<a id="__codelineno-40-28" name="__codelineno-40-28" href="#__codelineno-40-28"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-40-29" name="__codelineno-40-29" href="#__codelineno-40-29"></a><span class="w">        </span><span class="n">buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span>
<a id="__codelineno-40-30" name="__codelineno-40-30" href="#__codelineno-40-30"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-31" name="__codelineno-40-31" href="#__codelineno-40-31"></a>
<a id="__codelineno-40-32" name="__codelineno-40-32" href="#__codelineno-40-32"></a><span class="w">    </span><span class="cm">/* 删除操作 */</span>
<a id="__codelineno-40-33" name="__codelineno-40-33" href="#__codelineno-40-33"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">remove</span><span class="p">(</span><span class="n">key</span><span class="p">:</span><span class="w"> </span><span class="kt">Int</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-34" name="__codelineno-40-34" href="#__codelineno-40-34"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-40-35" name="__codelineno-40-35" href="#__codelineno-40-35"></a><span class="w">        </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-40-36" name="__codelineno-40-36" href="#__codelineno-40-36"></a><span class="w">        </span><span class="n">buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span>
<a id="__codelineno-40-37" name="__codelineno-40-37" href="#__codelineno-40-37"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-38" name="__codelineno-40-38" href="#__codelineno-40-38"></a>
<a id="__codelineno-40-39" name="__codelineno-40-39" href="#__codelineno-40-39"></a><span class="w">    </span><span class="cm">/* 获取所有键值对 */</span>
<a id="__codelineno-40-40" name="__codelineno-40-40" href="#__codelineno-40-40"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">pairSet</span><span class="p">():</span><span class="w"> </span><span class="n">MutableList</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-41" name="__codelineno-40-41" href="#__codelineno-40-41"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">pairSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">mutableListOf</span><span class="o">&lt;</span><span class="n">Pair</span><span class="o">&gt;</span><span class="p">()</span>
<a id="__codelineno-40-42" name="__codelineno-40-42" href="#__codelineno-40-42"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-43" name="__codelineno-40-43" href="#__codelineno-40-43"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-40-44" name="__codelineno-40-44" href="#__codelineno-40-44"></a><span class="w">                </span><span class="n">pairSet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">)</span>
<a id="__codelineno-40-45" name="__codelineno-40-45" href="#__codelineno-40-45"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-40-46" name="__codelineno-40-46" href="#__codelineno-40-46"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">pairSet</span>
<a id="__codelineno-40-47" name="__codelineno-40-47" href="#__codelineno-40-47"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-48" name="__codelineno-40-48" href="#__codelineno-40-48"></a>
<a id="__codelineno-40-49" name="__codelineno-40-49" href="#__codelineno-40-49"></a><span class="w">    </span><span class="cm">/* 获取所有键 */</span>
<a id="__codelineno-40-50" name="__codelineno-40-50" href="#__codelineno-40-50"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">keySet</span><span class="p">():</span><span class="w"> </span><span class="n">MutableList</span><span class="o">&lt;</span><span class="kt">Int</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-51" name="__codelineno-40-51" href="#__codelineno-40-51"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">keySet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">mutableListOf</span><span class="o">&lt;</span><span class="kt">Int</span><span class="o">&gt;</span><span class="p">()</span>
<a id="__codelineno-40-52" name="__codelineno-40-52" href="#__codelineno-40-52"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-53" name="__codelineno-40-53" href="#__codelineno-40-53"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-40-54" name="__codelineno-40-54" href="#__codelineno-40-54"></a><span class="w">                </span><span class="n">keySet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="na">key</span><span class="p">)</span>
<a id="__codelineno-40-55" name="__codelineno-40-55" href="#__codelineno-40-55"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-40-56" name="__codelineno-40-56" href="#__codelineno-40-56"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">keySet</span>
<a id="__codelineno-40-57" name="__codelineno-40-57" href="#__codelineno-40-57"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-58" name="__codelineno-40-58" href="#__codelineno-40-58"></a>
<a id="__codelineno-40-59" name="__codelineno-40-59" href="#__codelineno-40-59"></a><span class="w">    </span><span class="cm">/* 获取所有值 */</span>
<a id="__codelineno-40-60" name="__codelineno-40-60" href="#__codelineno-40-60"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">valueSet</span><span class="p">():</span><span class="w"> </span><span class="n">MutableList</span><span class="o">&lt;</span><span class="kt">String</span><span class="o">&gt;</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-61" name="__codelineno-40-61" href="#__codelineno-40-61"></a><span class="w">        </span><span class="kd">val</span><span class="w"> </span><span class="nv">valueSet</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">mutableListOf</span><span class="o">&lt;</span><span class="kt">String</span><span class="o">&gt;</span><span class="p">()</span>
<a id="__codelineno-40-62" name="__codelineno-40-62" href="#__codelineno-40-62"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">buckets</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-63" name="__codelineno-40-63" href="#__codelineno-40-63"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">pair</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span>
<a id="__codelineno-40-64" name="__codelineno-40-64" href="#__codelineno-40-64"></a><span class="w">                </span><span class="n">valueSet</span><span class="p">.</span><span class="na">add</span><span class="p">(</span><span class="n">pair</span><span class="p">.</span><span class="na">_val</span><span class="p">)</span>
<a id="__codelineno-40-65" name="__codelineno-40-65" href="#__codelineno-40-65"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-40-66" name="__codelineno-40-66" href="#__codelineno-40-66"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">valueSet</span>
<a id="__codelineno-40-67" name="__codelineno-40-67" href="#__codelineno-40-67"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-68" name="__codelineno-40-68" href="#__codelineno-40-68"></a>
<a id="__codelineno-40-69" name="__codelineno-40-69" href="#__codelineno-40-69"></a><span class="w">    </span><span class="cm">/* 打印哈希表 */</span>
<a id="__codelineno-40-70" name="__codelineno-40-70" href="#__codelineno-40-70"></a><span class="w">    </span><span class="kd">fun</span><span class="w"> </span><span class="nf">print</span><span class="p">()</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-71" name="__codelineno-40-71" href="#__codelineno-40-71"></a><span class="w">        </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">kv</span><span class="w"> </span><span class="k">in</span><span class="w"> </span><span class="n">pairSet</span><span class="p">())</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-40-72" name="__codelineno-40-72" href="#__codelineno-40-72"></a><span class="w">            </span><span class="kd">val</span><span class="w"> </span><span class="nv">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">kv</span><span class="p">.</span><span class="na">key</span>
<a id="__codelineno-40-73" name="__codelineno-40-73" href="#__codelineno-40-73"></a><span class="w">            </span><span class="kd">val</span><span class="w"> </span><span class="nv">_val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">kv</span><span class="p">.</span><span class="na">_val</span>
<a id="__codelineno-40-74" name="__codelineno-40-74" href="#__codelineno-40-74"></a><span class="w">            </span><span class="n">println</span><span class="p">(</span><span class="s">"</span><span class="si">$</span><span class="n">key</span><span class="s"> -&gt; </span><span class="si">$</span><span class="n">_val</span><span class="s">"</span><span class="p">)</span>
<a id="__codelineno-40-75" name="__codelineno-40-75" href="#__codelineno-40-75"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-40-76" name="__codelineno-40-76" href="#__codelineno-40-76"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-40-77" name="__codelineno-40-77" href="#__codelineno-40-77"></a><span class="p">}</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.rb</span><pre id="__code_41"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_41 > code"></button><code><a id="__codelineno-41-1" name="__codelineno-41-1" href="#__codelineno-41-1"></a><span class="c1">### 键值对 ###</span>
<a id="__codelineno-41-2" name="__codelineno-41-2" href="#__codelineno-41-2"></a><span class="k">class</span><span class="w"> </span><span class="nc">Pair</span>
<a id="__codelineno-41-3" name="__codelineno-41-3" href="#__codelineno-41-3"></a><span class="w">  </span><span class="kp">attr_accessor</span><span class="w"> </span><span class="ss">:key</span><span class="p">,</span><span class="w"> </span><span class="ss">:val</span>
<a id="__codelineno-41-4" name="__codelineno-41-4" href="#__codelineno-41-4"></a>
<a id="__codelineno-41-5" name="__codelineno-41-5" href="#__codelineno-41-5"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">initialize</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-41-6" name="__codelineno-41-6" href="#__codelineno-41-6"></a><span class="w">    </span><span class="vi">@key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span>
<a id="__codelineno-41-7" name="__codelineno-41-7" href="#__codelineno-41-7"></a><span class="w">    </span><span class="vi">@val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span>
<a id="__codelineno-41-8" name="__codelineno-41-8" href="#__codelineno-41-8"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-9" name="__codelineno-41-9" href="#__codelineno-41-9"></a><span class="k">end</span>
<a id="__codelineno-41-10" name="__codelineno-41-10" href="#__codelineno-41-10"></a>
<a id="__codelineno-41-11" name="__codelineno-41-11" href="#__codelineno-41-11"></a><span class="c1">### 基于数组实现的哈希表 ###</span>
<a id="__codelineno-41-12" name="__codelineno-41-12" href="#__codelineno-41-12"></a><span class="k">class</span><span class="w"> </span><span class="nc">ArrayHashMap</span>
<a id="__codelineno-41-13" name="__codelineno-41-13" href="#__codelineno-41-13"></a><span class="w">  </span><span class="c1">### 构造方法 ###</span>
<a id="__codelineno-41-14" name="__codelineno-41-14" href="#__codelineno-41-14"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">initialize</span>
<a id="__codelineno-41-15" name="__codelineno-41-15" href="#__codelineno-41-15"></a><span class="w">    </span><span class="c1"># 初始化数组，包含 100 个桶</span>
<a id="__codelineno-41-16" name="__codelineno-41-16" href="#__codelineno-41-16"></a><span class="w">    </span><span class="vi">@buckets</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">Array</span><span class="o">.</span><span class="n">new</span><span class="p">(</span><span class="mi">100</span><span class="p">)</span>
<a id="__codelineno-41-17" name="__codelineno-41-17" href="#__codelineno-41-17"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-18" name="__codelineno-41-18" href="#__codelineno-41-18"></a>
<a id="__codelineno-41-19" name="__codelineno-41-19" href="#__codelineno-41-19"></a><span class="w">  </span><span class="c1">### 哈希函数 ###</span>
<a id="__codelineno-41-20" name="__codelineno-41-20" href="#__codelineno-41-20"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-21" name="__codelineno-41-21" href="#__codelineno-41-21"></a><span class="w">    </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span>
<a id="__codelineno-41-22" name="__codelineno-41-22" href="#__codelineno-41-22"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-23" name="__codelineno-41-23" href="#__codelineno-41-23"></a>
<a id="__codelineno-41-24" name="__codelineno-41-24" href="#__codelineno-41-24"></a><span class="w">  </span><span class="c1">### 查询操作 ###</span>
<a id="__codelineno-41-25" name="__codelineno-41-25" href="#__codelineno-41-25"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">get</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-26" name="__codelineno-41-26" href="#__codelineno-41-26"></a><span class="w">    </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-27" name="__codelineno-41-27" href="#__codelineno-41-27"></a><span class="w">    </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="vi">@buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span>
<a id="__codelineno-41-28" name="__codelineno-41-28" href="#__codelineno-41-28"></a>
<a id="__codelineno-41-29" name="__codelineno-41-29" href="#__codelineno-41-29"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">if</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">nil?</span>
<a id="__codelineno-41-30" name="__codelineno-41-30" href="#__codelineno-41-30"></a><span class="w">    </span><span class="n">pair</span><span class="o">.</span><span class="n">val</span>
<a id="__codelineno-41-31" name="__codelineno-41-31" href="#__codelineno-41-31"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-32" name="__codelineno-41-32" href="#__codelineno-41-32"></a>
<a id="__codelineno-41-33" name="__codelineno-41-33" href="#__codelineno-41-33"></a><span class="w">  </span><span class="c1">### 添加操作 ###</span>
<a id="__codelineno-41-34" name="__codelineno-41-34" href="#__codelineno-41-34"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">put</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-41-35" name="__codelineno-41-35" href="#__codelineno-41-35"></a><span class="w">    </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="no">Pair</span><span class="o">.</span><span class="n">new</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">)</span>
<a id="__codelineno-41-36" name="__codelineno-41-36" href="#__codelineno-41-36"></a><span class="w">    </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-37" name="__codelineno-41-37" href="#__codelineno-41-37"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span>
<a id="__codelineno-41-38" name="__codelineno-41-38" href="#__codelineno-41-38"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-39" name="__codelineno-41-39" href="#__codelineno-41-39"></a>
<a id="__codelineno-41-40" name="__codelineno-41-40" href="#__codelineno-41-40"></a><span class="w">  </span><span class="c1">### 删除操作 ###</span>
<a id="__codelineno-41-41" name="__codelineno-41-41" href="#__codelineno-41-41"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">remove</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-42" name="__codelineno-41-42" href="#__codelineno-41-42"></a><span class="w">    </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hash_func</span><span class="p">(</span><span class="n">key</span><span class="p">)</span>
<a id="__codelineno-41-43" name="__codelineno-41-43" href="#__codelineno-41-43"></a><span class="w">    </span><span class="c1"># 置为 nil ，代表删除</span>
<a id="__codelineno-41-44" name="__codelineno-41-44" href="#__codelineno-41-44"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">[</span><span class="n">index</span><span class="o">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kp">nil</span>
<a id="__codelineno-41-45" name="__codelineno-41-45" href="#__codelineno-41-45"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-46" name="__codelineno-41-46" href="#__codelineno-41-46"></a>
<a id="__codelineno-41-47" name="__codelineno-41-47" href="#__codelineno-41-47"></a><span class="w">  </span><span class="c1">### 获取所有键值对 ###</span>
<a id="__codelineno-41-48" name="__codelineno-41-48" href="#__codelineno-41-48"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">entry_set</span>
<a id="__codelineno-41-49" name="__codelineno-41-49" href="#__codelineno-41-49"></a><span class="w">    </span><span class="n">result</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[]</span>
<a id="__codelineno-41-50" name="__codelineno-41-50" href="#__codelineno-41-50"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">.</span><span class="n">each</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">result</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="k">unless</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">nil?</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-41-51" name="__codelineno-41-51" href="#__codelineno-41-51"></a><span class="w">    </span><span class="n">result</span>
<a id="__codelineno-41-52" name="__codelineno-41-52" href="#__codelineno-41-52"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-53" name="__codelineno-41-53" href="#__codelineno-41-53"></a>
<a id="__codelineno-41-54" name="__codelineno-41-54" href="#__codelineno-41-54"></a><span class="w">  </span><span class="c1">### 获取所有键 ###</span>
<a id="__codelineno-41-55" name="__codelineno-41-55" href="#__codelineno-41-55"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">key_set</span>
<a id="__codelineno-41-56" name="__codelineno-41-56" href="#__codelineno-41-56"></a><span class="w">    </span><span class="n">result</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[]</span>
<a id="__codelineno-41-57" name="__codelineno-41-57" href="#__codelineno-41-57"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">.</span><span class="n">each</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">result</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">key</span><span class="w"> </span><span class="k">unless</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">nil?</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-41-58" name="__codelineno-41-58" href="#__codelineno-41-58"></a><span class="w">    </span><span class="n">result</span>
<a id="__codelineno-41-59" name="__codelineno-41-59" href="#__codelineno-41-59"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-60" name="__codelineno-41-60" href="#__codelineno-41-60"></a>
<a id="__codelineno-41-61" name="__codelineno-41-61" href="#__codelineno-41-61"></a><span class="w">  </span><span class="c1">### 获取所有值 ###</span>
<a id="__codelineno-41-62" name="__codelineno-41-62" href="#__codelineno-41-62"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">value_set</span>
<a id="__codelineno-41-63" name="__codelineno-41-63" href="#__codelineno-41-63"></a><span class="w">    </span><span class="n">result</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="o">[]</span>
<a id="__codelineno-41-64" name="__codelineno-41-64" href="#__codelineno-41-64"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">.</span><span class="n">each</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="n">result</span><span class="w"> </span><span class="o">&lt;&lt;</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">val</span><span class="w"> </span><span class="k">unless</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">nil?</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-41-65" name="__codelineno-41-65" href="#__codelineno-41-65"></a><span class="w">    </span><span class="n">result</span>
<a id="__codelineno-41-66" name="__codelineno-41-66" href="#__codelineno-41-66"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-67" name="__codelineno-41-67" href="#__codelineno-41-67"></a>
<a id="__codelineno-41-68" name="__codelineno-41-68" href="#__codelineno-41-68"></a><span class="w">  </span><span class="c1">### 打印哈希表 ###</span>
<a id="__codelineno-41-69" name="__codelineno-41-69" href="#__codelineno-41-69"></a><span class="w">  </span><span class="k">def</span><span class="w"> </span><span class="nf">print</span>
<a id="__codelineno-41-70" name="__codelineno-41-70" href="#__codelineno-41-70"></a><span class="w">    </span><span class="vi">@buckets</span><span class="o">.</span><span class="n">each</span><span class="w"> </span><span class="p">{</span><span class="w"> </span><span class="o">|</span><span class="n">pair</span><span class="o">|</span><span class="w"> </span><span class="nb">puts</span><span class="w"> </span><span class="s2">"</span><span class="si">#{</span><span class="n">pair</span><span class="o">.</span><span class="n">key</span><span class="si">}</span><span class="s2"> -&gt; </span><span class="si">#{</span><span class="n">pair</span><span class="o">.</span><span class="n">val</span><span class="si">}</span><span class="s2">"</span><span class="w"> </span><span class="k">unless</span><span class="w"> </span><span class="n">pair</span><span class="o">.</span><span class="n">nil?</span><span class="w"> </span><span class="p">}</span>
<a id="__codelineno-41-71" name="__codelineno-41-71" href="#__codelineno-41-71"></a><span class="w">  </span><span class="k">end</span>
<a id="__codelineno-41-72" name="__codelineno-41-72" href="#__codelineno-41-72"></a><span class="k">end</span>
</code></pre></div>
</div>
<div class="tabbed-block">
<div class="highlight"><span class="filename">array_hash_map.zig</span><pre id="__code_42"><span></span><button class="md-clipboard md-icon" title="复制" data-clipboard-target="#__code_42 > code"></button><code><a id="__codelineno-42-1" name="__codelineno-42-1" href="#__codelineno-42-1"></a><span class="c1">// 键值对</span>
<a id="__codelineno-42-2" name="__codelineno-42-2" href="#__codelineno-42-2"></a><span class="kr">const</span><span class="w"> </span><span class="n">Pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-3" name="__codelineno-42-3" href="#__codelineno-42-3"></a><span class="w">    </span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">undefined</span><span class="p">,</span>
<a id="__codelineno-42-4" name="__codelineno-42-4" href="#__codelineno-42-4"></a><span class="w">    </span><span class="n">val</span><span class="o">:</span><span class="w"> </span><span class="p">[]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">undefined</span><span class="p">,</span>
<a id="__codelineno-42-5" name="__codelineno-42-5" href="#__codelineno-42-5"></a>
<a id="__codelineno-42-6" name="__codelineno-42-6" href="#__codelineno-42-6"></a><span class="w">   </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">init</span><span class="p">(</span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="o">:</span><span class="w"> </span><span class="p">[]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="p">)</span><span class="w"> </span><span class="n">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-7" name="__codelineno-42-7" href="#__codelineno-42-7"></a><span class="w">        </span><span class="k">return</span><span class="w"> </span><span class="n">Pair</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-8" name="__codelineno-42-8" href="#__codelineno-42-8"></a><span class="w">            </span><span class="p">.</span><span class="n">key</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="p">,</span>
<a id="__codelineno-42-9" name="__codelineno-42-9" href="#__codelineno-42-9"></a><span class="w">            </span><span class="p">.</span><span class="n">val</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">val</span><span class="p">,</span>
<a id="__codelineno-42-10" name="__codelineno-42-10" href="#__codelineno-42-10"></a><span class="w">        </span><span class="p">};</span>
<a id="__codelineno-42-11" name="__codelineno-42-11" href="#__codelineno-42-11"></a><span class="w">    </span><span class="p">}</span>
<a id="__codelineno-42-12" name="__codelineno-42-12" href="#__codelineno-42-12"></a><span class="p">};</span>
<a id="__codelineno-42-13" name="__codelineno-42-13" href="#__codelineno-42-13"></a>
<a id="__codelineno-42-14" name="__codelineno-42-14" href="#__codelineno-42-14"></a><span class="c1">// 基于数组实现的哈希表</span>
<a id="__codelineno-42-15" name="__codelineno-42-15" href="#__codelineno-42-15"></a><span class="k">fn</span><span class="w"> </span><span class="n">ArrayHashMap</span><span class="p">(</span><span class="kr">comptime</span><span class="w"> </span><span class="n">T</span><span class="o">:</span><span class="w"> </span><span class="kt">type</span><span class="p">)</span><span class="w"> </span><span class="kt">type</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-16" name="__codelineno-42-16" href="#__codelineno-42-16"></a><span class="w">    </span><span class="k">return</span><span class="w"> </span><span class="k">struct</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-17" name="__codelineno-42-17" href="#__codelineno-42-17"></a><span class="w">        </span><span class="n">bucket</span><span class="o">:</span><span class="w"> </span><span class="o">?</span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="o">?</span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">,</span>
<a id="__codelineno-42-18" name="__codelineno-42-18" href="#__codelineno-42-18"></a><span class="w">        </span><span class="n">mem_allocator</span><span class="o">:</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">mem</span><span class="p">.</span><span class="n">Allocator</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">undefined</span><span class="p">,</span>
<a id="__codelineno-42-19" name="__codelineno-42-19" href="#__codelineno-42-19"></a>
<a id="__codelineno-42-20" name="__codelineno-42-20" href="#__codelineno-42-20"></a><span class="w">        </span><span class="kr">const</span><span class="w"> </span><span class="n">Self</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="nb">@This</span><span class="p">();</span>
<a id="__codelineno-42-21" name="__codelineno-42-21" href="#__codelineno-42-21"></a>
<a id="__codelineno-42-22" name="__codelineno-42-22" href="#__codelineno-42-22"></a><span class="w">        </span><span class="c1">// 构造函数</span>
<a id="__codelineno-42-23" name="__codelineno-42-23" href="#__codelineno-42-23"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">allocator</span><span class="o">:</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">mem</span><span class="p">.</span><span class="n">Allocator</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-24" name="__codelineno-42-24" href="#__codelineno-42-24"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">allocator</span><span class="p">;</span>
<a id="__codelineno-42-25" name="__codelineno-42-25" href="#__codelineno-42-25"></a><span class="w">            </span><span class="c1">// 初始化一个长度为 100 的桶（数组）</span>
<a id="__codelineno-42-26" name="__codelineno-42-26" href="#__codelineno-42-26"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="o">?</span><span class="n">T</span><span class="p">).</span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">);</span>
<a id="__codelineno-42-27" name="__codelineno-42-27" href="#__codelineno-42-27"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">i</span><span class="o">:</span><span class="w"> </span><span class="kt">i32</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="mi">0</span><span class="p">;</span>
<a id="__codelineno-42-28" name="__codelineno-42-28" href="#__codelineno-42-28"></a><span class="w">            </span><span class="k">while</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">&lt;</span><span class="w"> </span><span class="mi">100</span><span class="p">)</span><span class="w"> </span><span class="o">:</span><span class="w"> </span><span class="p">(</span><span class="n">i</span><span class="w"> </span><span class="o">+=</span><span class="w"> </span><span class="mi">1</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-29" name="__codelineno-42-29" href="#__codelineno-42-29"></a><span class="w">                </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="kc">null</span><span class="p">);</span>
<a id="__codelineno-42-30" name="__codelineno-42-30" href="#__codelineno-42-30"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-42-31" name="__codelineno-42-31" href="#__codelineno-42-31"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-32" name="__codelineno-42-32" href="#__codelineno-42-32"></a>
<a id="__codelineno-42-33" name="__codelineno-42-33" href="#__codelineno-42-33"></a><span class="w">        </span><span class="c1">// 析构函数</span>
<a id="__codelineno-42-34" name="__codelineno-42-34" href="#__codelineno-42-34"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">deinit</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-35" name="__codelineno-42-35" href="#__codelineno-42-35"></a><span class="w">            </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="w"> </span><span class="o">!=</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">deinit</span><span class="p">();</span>
<a id="__codelineno-42-36" name="__codelineno-42-36" href="#__codelineno-42-36"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-37" name="__codelineno-42-37" href="#__codelineno-42-37"></a>
<a id="__codelineno-42-38" name="__codelineno-42-38" href="#__codelineno-42-38"></a><span class="w">        </span><span class="c1">// 哈希函数</span>
<a id="__codelineno-42-39" name="__codelineno-42-39" href="#__codelineno-42-39"></a><span class="w">        </span><span class="k">fn</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="kt">usize</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-40" name="__codelineno-42-40" href="#__codelineno-42-40"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">key</span><span class="w"> </span><span class="o">%</span><span class="w"> </span><span class="mi">100</span><span class="p">;</span>
<a id="__codelineno-42-41" name="__codelineno-42-41" href="#__codelineno-42-41"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">index</span><span class="p">;</span>
<a id="__codelineno-42-42" name="__codelineno-42-42" href="#__codelineno-42-42"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-43" name="__codelineno-42-43" href="#__codelineno-42-43"></a>
<a id="__codelineno-42-44" name="__codelineno-42-44" href="#__codelineno-42-44"></a><span class="w">        </span><span class="c1">// 查询操作</span>
<a id="__codelineno-42-45" name="__codelineno-42-45" href="#__codelineno-42-45"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">get</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="p">[]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-46" name="__codelineno-42-46" href="#__codelineno-42-46"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-42-47" name="__codelineno-42-47" href="#__codelineno-42-47"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">index</span><span class="p">];</span>
<a id="__codelineno-42-48" name="__codelineno-42-48" href="#__codelineno-42-48"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">pair</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">val</span><span class="p">;</span>
<a id="__codelineno-42-49" name="__codelineno-42-49" href="#__codelineno-42-49"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-50" name="__codelineno-42-50" href="#__codelineno-42-50"></a>
<a id="__codelineno-42-51" name="__codelineno-42-51" href="#__codelineno-42-51"></a><span class="w">        </span><span class="c1">// 添加操作</span>
<a id="__codelineno-42-52" name="__codelineno-42-52" href="#__codelineno-42-52"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">put</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="o">:</span><span class="w"> </span><span class="p">[]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-53" name="__codelineno-42-53" href="#__codelineno-42-53"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">pair</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">Pair</span><span class="p">.</span><span class="n">init</span><span class="p">(</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-42-54" name="__codelineno-42-54" href="#__codelineno-42-54"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-42-55" name="__codelineno-42-55" href="#__codelineno-42-55"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">pair</span><span class="p">;</span>
<a id="__codelineno-42-56" name="__codelineno-42-56" href="#__codelineno-42-56"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-57" name="__codelineno-42-57" href="#__codelineno-42-57"></a>
<a id="__codelineno-42-58" name="__codelineno-42-58" href="#__codelineno-42-58"></a><span class="w">        </span><span class="c1">// 删除操作</span>
<a id="__codelineno-42-59" name="__codelineno-42-59" href="#__codelineno-42-59"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">remove</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">,</span><span class="w"> </span><span class="n">key</span><span class="o">:</span><span class="w"> </span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-60" name="__codelineno-42-60" href="#__codelineno-42-60"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">index</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">hashFunc</span><span class="p">(</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-42-61" name="__codelineno-42-61" href="#__codelineno-42-61"></a><span class="w">            </span><span class="c1">// 置为 null ，代表删除</span>
<a id="__codelineno-42-62" name="__codelineno-42-62" href="#__codelineno-42-62"></a><span class="w">            </span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">[</span><span class="n">index</span><span class="p">]</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="kc">null</span><span class="p">;</span>
<a id="__codelineno-42-63" name="__codelineno-42-63" href="#__codelineno-42-63"></a><span class="w">        </span><span class="p">}</span><span class="w">       </span>
<a id="__codelineno-42-64" name="__codelineno-42-64" href="#__codelineno-42-64"></a>
<a id="__codelineno-42-65" name="__codelineno-42-65" href="#__codelineno-42-65"></a><span class="w">        </span><span class="c1">// 获取所有键值对</span>
<a id="__codelineno-42-66" name="__codelineno-42-66" href="#__codelineno-42-66"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">pairSet</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="n">T</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-67" name="__codelineno-42-67" href="#__codelineno-42-67"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">entry_set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="n">T</span><span class="p">).</span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">);</span>
<a id="__codelineno-42-68" name="__codelineno-42-68" href="#__codelineno-42-68"></a><span class="w">            </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">)</span><span class="w"> </span><span class="o">|</span><span class="n">item</span><span class="o">|</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-69" name="__codelineno-42-69" href="#__codelineno-42-69"></a><span class="w">                </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">item</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">continue</span><span class="p">;</span>
<a id="__codelineno-42-70" name="__codelineno-42-70" href="#__codelineno-42-70"></a><span class="w">                </span><span class="k">try</span><span class="w"> </span><span class="n">entry_set</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">item</span><span class="p">.</span><span class="o">?</span><span class="p">);</span>
<a id="__codelineno-42-71" name="__codelineno-42-71" href="#__codelineno-42-71"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-42-72" name="__codelineno-42-72" href="#__codelineno-42-72"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">entry_set</span><span class="p">;</span>
<a id="__codelineno-42-73" name="__codelineno-42-73" href="#__codelineno-42-73"></a><span class="w">        </span><span class="p">}</span><span class="w">  </span>
<a id="__codelineno-42-74" name="__codelineno-42-74" href="#__codelineno-42-74"></a>
<a id="__codelineno-42-75" name="__codelineno-42-75" href="#__codelineno-42-75"></a><span class="w">        </span><span class="c1">// 获取所有键</span>
<a id="__codelineno-42-76" name="__codelineno-42-76" href="#__codelineno-42-76"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">keySet</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="kt">usize</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-77" name="__codelineno-42-77" href="#__codelineno-42-77"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">key_set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">(</span><span class="kt">usize</span><span class="p">).</span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">);</span>
<a id="__codelineno-42-78" name="__codelineno-42-78" href="#__codelineno-42-78"></a><span class="w">            </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">)</span><span class="w"> </span><span class="o">|</span><span class="n">item</span><span class="o">|</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-79" name="__codelineno-42-79" href="#__codelineno-42-79"></a><span class="w">                </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">item</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">continue</span><span class="p">;</span>
<a id="__codelineno-42-80" name="__codelineno-42-80" href="#__codelineno-42-80"></a><span class="w">                </span><span class="k">try</span><span class="w"> </span><span class="n">key_set</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">item</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">key</span><span class="p">);</span>
<a id="__codelineno-42-81" name="__codelineno-42-81" href="#__codelineno-42-81"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-42-82" name="__codelineno-42-82" href="#__codelineno-42-82"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">key_set</span><span class="p">;</span>
<a id="__codelineno-42-83" name="__codelineno-42-83" href="#__codelineno-42-83"></a><span class="w">        </span><span class="p">}</span><span class="w">  </span>
<a id="__codelineno-42-84" name="__codelineno-42-84" href="#__codelineno-42-84"></a>
<a id="__codelineno-42-85" name="__codelineno-42-85" href="#__codelineno-42-85"></a><span class="w">        </span><span class="c1">// 获取所有值</span>
<a id="__codelineno-42-86" name="__codelineno-42-86" href="#__codelineno-42-86"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">valueSet</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">([]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="p">)</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-87" name="__codelineno-42-87" href="#__codelineno-42-87"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">value_set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="n">std</span><span class="p">.</span><span class="n">ArrayList</span><span class="p">([]</span><span class="kr">const</span><span class="w"> </span><span class="kt">u8</span><span class="p">).</span><span class="n">init</span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">mem_allocator</span><span class="p">);</span>
<a id="__codelineno-42-88" name="__codelineno-42-88" href="#__codelineno-42-88"></a><span class="w">            </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">self</span><span class="p">.</span><span class="n">bucket</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">items</span><span class="p">)</span><span class="w"> </span><span class="o">|</span><span class="n">item</span><span class="o">|</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-89" name="__codelineno-42-89" href="#__codelineno-42-89"></a><span class="w">                </span><span class="k">if</span><span class="w"> </span><span class="p">(</span><span class="n">item</span><span class="w"> </span><span class="o">==</span><span class="w"> </span><span class="kc">null</span><span class="p">)</span><span class="w"> </span><span class="k">continue</span><span class="p">;</span>
<a id="__codelineno-42-90" name="__codelineno-42-90" href="#__codelineno-42-90"></a><span class="w">                </span><span class="k">try</span><span class="w"> </span><span class="n">value_set</span><span class="p">.</span><span class="n">append</span><span class="p">(</span><span class="n">item</span><span class="p">.</span><span class="o">?</span><span class="p">.</span><span class="n">val</span><span class="p">);</span>
<a id="__codelineno-42-91" name="__codelineno-42-91" href="#__codelineno-42-91"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-42-92" name="__codelineno-42-92" href="#__codelineno-42-92"></a><span class="w">            </span><span class="k">return</span><span class="w"> </span><span class="n">value_set</span><span class="p">;</span>
<a id="__codelineno-42-93" name="__codelineno-42-93" href="#__codelineno-42-93"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-94" name="__codelineno-42-94" href="#__codelineno-42-94"></a>
<a id="__codelineno-42-95" name="__codelineno-42-95" href="#__codelineno-42-95"></a><span class="w">        </span><span class="c1">// 打印哈希表</span>
<a id="__codelineno-42-96" name="__codelineno-42-96" href="#__codelineno-42-96"></a><span class="w">        </span><span class="kr">pub</span><span class="w"> </span><span class="k">fn</span><span class="w"> </span><span class="n">print</span><span class="p">(</span><span class="n">self</span><span class="o">:</span><span class="w"> </span><span class="o">*</span><span class="n">Self</span><span class="p">)</span><span class="w"> </span><span class="o">!</span><span class="kt">void</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-97" name="__codelineno-42-97" href="#__codelineno-42-97"></a><span class="w">            </span><span class="kr">var</span><span class="w"> </span><span class="n">entry_set</span><span class="w"> </span><span class="o">=</span><span class="w"> </span><span class="k">try</span><span class="w"> </span><span class="n">self</span><span class="p">.</span><span class="n">pairSet</span><span class="p">();</span>
<a id="__codelineno-42-98" name="__codelineno-42-98" href="#__codelineno-42-98"></a><span class="w">            </span><span class="k">defer</span><span class="w"> </span><span class="n">entry_set</span><span class="p">.</span><span class="n">deinit</span><span class="p">();</span>
<a id="__codelineno-42-99" name="__codelineno-42-99" href="#__codelineno-42-99"></a><span class="w">            </span><span class="k">for</span><span class="w"> </span><span class="p">(</span><span class="n">entry_set</span><span class="p">.</span><span class="n">items</span><span class="p">)</span><span class="w"> </span><span class="o">|</span><span class="n">item</span><span class="o">|</span><span class="w"> </span><span class="p">{</span>
<a id="__codelineno-42-100" name="__codelineno-42-100" href="#__codelineno-42-100"></a><span class="w">                </span><span class="n">std</span><span class="p">.</span><span class="n">debug</span><span class="p">.</span><span class="n">print</span><span class="p">(</span><span class="s">"{} -&gt; {s}</span><span class="se">\n</span><span class="s">"</span><span class="p">,</span><span class="w"> </span><span class="p">.{</span><span class="n">item</span><span class="p">.</span><span class="n">key</span><span class="p">,</span><span class="w"> </span><span class="n">item</span><span class="p">.</span><span class="n">val</span><span class="p">});</span>
<a id="__codelineno-42-101" name="__codelineno-42-101" href="#__codelineno-42-101"></a><span class="w">            </span><span class="p">}</span>
<a id="__codelineno-42-102" name="__codelineno-42-102" href="#__codelineno-42-102"></a><span class="w">        </span><span class="p">}</span>
<a id="__codelineno-42-103" name="__codelineno-42-103" href="#__codelineno-42-103"></a><span class="w">    </span><span class="p">};</span>
<a id="__codelineno-42-104" name="__codelineno-42-104" href="#__codelineno-42-104"></a><span class="p">}</span>
</code></pre></div>
</div>
</div>
<div class="tabbed-control tabbed-control--prev" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div><div class="tabbed-control tabbed-control--next" hidden=""><button class="tabbed-button" tabindex="-1" aria-hidden="true"></button></div></div>
## 哈希冲突与扩容

本质上看，哈希函数的作用是将所有 `key` 构成的输入空间映射到数组所有索引构成的输出空间，而输入空间往往远大于输出空间。因此，**理论上一定存在“多个输入对应相同输出”的情况**。

对于上述示例中的哈希函数，当输入的 `key` 后两位相同时，哈希函数的输出结果也相同。例如，查询学号为 12836 和 20336 的两个学生时，我们得到：

```shell
12836 % 100 = 36
20336 % 100 = 36
```

如下图所示，两个学号指向了同一个姓名，这显然是不对的。我们将这种多个输入对应同一输出的情况称为「哈希冲突 hash collision」。

![哈希冲突示例](hash_map.assets/hash_collision.png)

容易想到，哈希表容量 $n$ 越大，多个 `key` 被分配到同一个桶中的概率就越低，冲突就越少。因此，**我们可以通过扩容哈希表来减少哈希冲突**。

如下图所示，扩容前键值对 `(136, A)` 和 `(236, D)` 发生冲突，扩容后冲突消失。

![哈希表扩容](hash_map.assets/hash_table_reshash.png)

类似于数组扩容，哈希表扩容需将所有键值对从原哈希表迁移至新哈希表，非常耗时。并且由于哈希表容量 `capacity` 改变，我们需要通过哈希函数来重新计算所有键值对的存储位置，这进一步提高了扩容过程的计算开销。为此，编程语言通常会预留足够大的哈希表容量，防止频繁扩容。

「负载因子 load factor」是哈希表的一个重要概念，其定义为哈希表的元素数量除以桶数量，用于衡量哈希冲突的严重程度，**也常被作为哈希表扩容的触发条件**。例如在 Java 中，当负载因子超过 $0.75$ 时，系统会将哈希表容量扩展为原先的 $2$ 倍。
