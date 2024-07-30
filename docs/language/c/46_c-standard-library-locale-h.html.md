<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C 标准库 - <locale.h></title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C 标准库 - <span class="color_h1">&lt;locale.h&gt;</span></h1>&#13;
&#13;
<h2>简介</h2>&#13;
<p><code>&lt;locale.h&gt;</code> 是 C 标准库中的一个头文件，用于支持程序的国际化和本地化。它提供了一组函数和宏来设置或查询程序的本地化信息，例如日期、时间、货币、数字格式等。</p>&#13;
&#13;
<p>接下来我们将介绍一些宏，以及一个重要的结构 <b>struct lconv</b> 和两个重要的函数。</p>&#13;
<h2>库宏</h2>&#13;
<p>下面列出了头文件 locale.h 中定义的宏，这些宏将在下列的两个函数中使用：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:10%">序号</th><th>宏 &amp; 描述</th></tr>&#13;
<tr><td>1 </td><td><b>LC_ALL</b><br/>用于设置或查询所有本地化类别。</td></tr>&#13;
<tr><td>2 </td><td><b>LC_COLLATE</b><br/>用于设置或查询字符串比较的本地化信息。</td></tr>&#13;
<tr><td>3 </td><td><b>LC_CTYPE</b><br/>用于设置或查询字符处理的本地化信息。</td></tr>&#13;
<tr><td>4 </td><td><b>LC_MONETARY</b><br/>用于设置或查询货币格式的本地化信息。</td></tr>&#13;
<tr><td>5 </td><td><b>LC_NUMERIC</b><br/>用于设置或查询数字格式的本地化信息（例如小数点的符号）。</td></tr>&#13;
<tr><td>6 </td><td><b>LC_TIME</b><br/>用于设置或查询时间格式的本地化信息。</td></tr>&#13;
<tr><td>7 </td><td><b>locale_t</b><br/>表示区域设置信息的类型。</td></tr>&#13;
</table>&#13;
&#13;
<h2>库函数</h2>&#13;
<p>下面列出了头文件 locale.h 中定义的函数：</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:5%">序号</th><th>函数 &amp; 描述</th></tr>&#13;
<tr><td>1</td><td><a href="c-function-setlocale.html">char *setlocale(int category, const char *locale)</a><br/>设置或读取地域化信息。</td></tr>&#13;
<tr><td>2</td><td><a href="c-function-localeconv.html">struct lconv *localeconv(void)</a><br/>设置或读取地域化信息。</td></tr>&#13;
<tr><td>3</td><td><a href="c-function-newlocale.html">locale_t newlocale(int category_mask, const char *locale, locale_t base)</a><br/>创建一个新的本地化对象。</td></tr>&#13;
<tr><td>4</td><td><a href="c-function-freelocale.html">freelocale(locale_t locale)</a><br/>释放一个本地化对象。</td></tr>&#13;
<tr><td>5</td><td><a href="c-function-uselocale.html">locale_t uselocale(locale_t newloc)</a><br/>设置或查询线程的本地化对象。</td></tr>&#13;
</table><h3>实例</h3>&#13;
<p>设置和查询本地化信息:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;locale.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #666666; font-style: italic;">// 设置本地化信息为用户环境变量中的默认设置</span><br/>
    <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_ALL<span style="color: #339933;">,</span> <span style="color: #a11;">""</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 获取和打印当前的本地化信息</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Current locale for LC_ALL: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_ALL<span style="color: #339933;">,</span> NULL<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Current locale for LC_TIME: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_TIME<span style="color: #339933;">,</span> NULL<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Current locale for LC_NUMERIC: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_NUMERIC<span style="color: #339933;">,</span> NULL<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
<p>编译输出结果为：</p>&#13;
<pre>Current locale for LC_ALL: zh_CN.UTF-8&#13;
Current locale for LC_TIME: zh_CN.UTF-8&#13;
Current locale for LC_NUMERIC: zh_CN.UTF-8</pre>&#13;
<p>&#13;
获取数字和货币格式信息:</p>&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;locale.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #666666; font-style: italic;">// 设置本地化信息为用户环境变量中的默认设置</span><br/>
    <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_ALL<span style="color: #339933;">,</span> <span style="color: #a11;">""</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 获取本地化的数字和货币格式信息</span><br/>
    <span style="color: #993333;">struct</span> lconv <span style="color: #339933;">*</span>lc <span style="color: #339933;">=</span> <span style="color: #000066;">localeconv</span><span style="color: #000;">(</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 打印数字和货币格式信息</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Decimal point character: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> lc<span style="color: #339933;">-&gt;</span>decimal_point<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Thousands separator: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> lc<span style="color: #339933;">-&gt;</span>thousands_sep<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Currency symbol: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> lc<span style="color: #339933;">-&gt;</span>currency_symbol<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
&#13;
<p>编译输出结果为：</p>&#13;
<pre>Decimal point character: .&#13;
Thousands separator: ,&#13;
Currency symbol: ￥</pre>&#13;
<p>&#13;
使用自定义本地化对象:</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #085;">#include &lt;stdio.h&gt;</span><br/>
<span style="color: #085;">#include &lt;locale.h&gt;</span><br/>
<span style="color: #085;">#include &lt;xlocale.h&gt;</span><br/>
<br/>
<span style="color: #993333;">int</span> main<span style="color: #000;">(</span><span style="color: #000;">)</span> <span style="color: #000;">{</span><br/>
    <span style="color: #666666; font-style: italic;">// 创建一个新的本地化对象，使用 "en_US.UTF-8" 区域设置</span><br/>
    locale_t newloc <span style="color: #339933;">=</span> newlocale<span style="color: #000;">(</span>LC_ALL_MASK<span style="color: #339933;">,</span> <span style="color: #a11;">"en_US.UTF-8"</span><span style="color: #339933;">,</span> <span style="color: #000;">(</span>locale_t<span style="color: #000;">)</span><span style="color: #164;">0</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 将当前线程的本地化对象设置为新的本地化对象</span><br/>
    locale_t oldloc <span style="color: #339933;">=</span> uselocale<span style="color: #000;">(</span>newloc<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 获取和打印当前线程的本地化信息</span><br/>
    <span style="color: #000066;">printf</span><span style="color: #000;">(</span><span style="color: #a11;">"Current locale for LC_NUMERIC: %s<span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #339933;">,</span> <span style="color: #000066;">setlocale</span><span style="color: #000;">(</span>LC_NUMERIC<span style="color: #339933;">,</span> NULL<span style="color: #000;">)</span><span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #666666; font-style: italic;">// 释放新的本地化对象</span><br/>
    uselocale<span style="color: #000;">(</span>oldloc<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
    freelocale<span style="color: #000;">(</span>newloc<span style="color: #000;">)</span><span style="color: #339933;">;</span><br/>
<br/>
    <span style="color: #708;">return</span> <span style="color: #164;">0</span><span style="color: #339933;">;</span><br/>
<span style="color: #000;">}</span><br/>
</div></div>&#13;
&#13;
<p>编译输出结果为：</p>&#13;
<pre>Current locale for LC_NUMERIC: C</pre>&#13;
<p>&#13;
</p><h2>库结构</h2>&#13;
<pre>&#13;
typedef struct {&#13;
   char *decimal_point;&#13;
   char *thousands_sep;&#13;
   char *grouping;    &#13;
   char *int_curr_symbol;&#13;
   char *currency_symbol;&#13;
   char *mon_decimal_point;&#13;
   char *mon_thousands_sep;&#13;
   char *mon_grouping;&#13;
   char *positive_sign;&#13;
   char *negative_sign;&#13;
   char int_frac_digits;&#13;
   char frac_digits;&#13;
   char p_cs_precedes;&#13;
   char p_sep_by_space;&#13;
   char n_cs_precedes;&#13;
   char n_sep_by_space;&#13;
   char p_sign_posn;&#13;
   char n_sign_posn;&#13;
} lconv&#13;
</pre>&#13;
<p>以下是各字段的描述：</p>&#13;
<table class="reference">&#13;
<tr><th style="width:10%">序号</th><th>字段 &amp; 描述</th></tr>&#13;
<tr><td>1 </td><td><b>decimal_point</b><br/>用于非货币值的小数点字符。</td></tr>&#13;
<tr><td>2 </td><td><b>thousands_sep</b><br/>用于非货币值的千位分隔符。</td></tr>&#13;
<tr><td>3 </td><td><b>grouping</b><br/>一个表示非货币量中每组数字大小的字符串。每个字符代表一个整数值，每个整数指定当前组的位数。值为 0 意味着前一个值将应用于剩余的分组。</td></tr>&#13;
<tr><td>4 </td><td><b>int_curr_symbol</b><br/>国际货币符号使用的字符串。前三个字符是由 ISO 4217:1987 指定的，第四个字符用于分隔货币符号和货币量。</td></tr>&#13;
<tr><td>5 </td><td><b>currency_symbol</b><br/>用于货币的本地符号。</td></tr>&#13;
<tr><td>6 </td><td><b>mon_decimal_point</b><br/>用于货币值的小数点字符。</td></tr>&#13;
<tr><td>7 </td><td><b>mon_thousands_sep</b><br/>用于货币值的千位分隔符。</td></tr>&#13;
<tr><td>8 </td><td><b>mon_grouping</b><br/>一个表示货币值中每组数字大小的字符串。每个字符代表一个整数值，每个整数指定当前组的位数。值为 0 意味着前一个值将应用于剩余的分组。</td></tr>&#13;
<tr><td>9 </td><td><b>positive_sign</b><br/>用于正货币值的字符。</td></tr>&#13;
<tr><td>10 </td><td><b>negative_sign</b><br/>用于负货币值的字符。</td></tr>&#13;
<tr><td>11 </td><td><b>int_frac_digits</b><br/>国际货币值中小数点后要显示的位数。</td></tr>&#13;
<tr><td>12 </td><td><b>frac_digits</b><br/>货币值中小数点后要显示的位数。</td></tr>&#13;
<tr><td>13 </td><td><b>p_cs_precedes</b><br/>如果等于 1，则 currency_symbol 出现在正货币值之前。如果等于 0，则 currency_symbol 出现在正货币值之后。</td></tr>&#13;
<tr><td>14 </td><td><b>p_sep_by_space</b><br/>如果等于 1，则 currency_symbol 和正货币值之间使用空格分隔。如果等于 0，则 currency_symbol 和正货币值之间不使用空格分隔。</td></tr>&#13;
<tr><td>15 </td><td><b>n_cs_precedes</b><br/>如果等于 1，则 currency_symbol 出现在负货币值之前。如果等于 0，则 currency_symbol 出现在负货币值之后。</td></tr>&#13;
<tr><td>16 </td><td><b>n_sep_by_space</b><br/>如果等于 1，则 currency_symbol 和负货币值之间使用空格分隔。如果等于 0，则 currency_symbol 和负货币值之间不使用空格分隔。</td></tr>&#13;
<tr><td>17 </td><td><b>p_sign_posn</b><br/>表示正货币值中正号的位置。</td></tr>&#13;
<tr><td>18 </td><td><b>n_sign_posn</b><br/>表示负货币值中负号的位置。</td></tr>&#13;
</table>&#13;
<p>下面的值用于 <b>p_sign_posn</b> 和 <b>n_sign_posn</b>:</p>&#13;
<table class="reference notranslate">&#13;
<tr><th style="width:10%">值</th><th>描述</th></tr>&#13;
<tr><td>0 </td><td>封装值和 currency_symbol 的括号。</td></tr>&#13;
<tr><td>1 </td><td>放置在值和 currency_symbol 之前的符号。</td></tr>&#13;
<tr><td>2 </td><td>放置在值和 currency_symbol 之后的符号。</td></tr>&#13;
<tr><td>3 </td><td>紧挨着放置在值和 currency_symbol 之前的符号。</td></tr>&#13;
<tr><td>4 </td><td>紧挨着放置在值和 currency_symbol 之后的符号。</td></tr>&#13;
</table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>