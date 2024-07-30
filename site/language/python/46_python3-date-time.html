<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3  日期和时间</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3  <span class="color_h1">日期和时间</span></h1>&#13;
&#13;
<p>Python 程序能用很多方式处理日期和时间，转换日期格式是一个常见的功能。</p>&#13;
<p>Python 提供了一个 time 和 calendar 模块可以用于格式化日期和时间。</p>&#13;
&#13;
&#13;
<p>时间间隔是以秒为单位的浮点小数。</p>&#13;
<p>每个时间戳都以自从 1970 年 1 月 1 日午夜（历元）经过了多长时间来表示。</p>&#13;
<p>Python 的 time 模块下有很多函数可以转换常见日期格式。如函数 time.time() 用于获取当前时间戳, 如下实例:</p><p>&#13;
&#13;
</p><div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span>  <span style="color: #a50"># 引入time模块</span><br/>
<br/>
ticks <span style="color: Gray;">=</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">time</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"当前时间戳为:"</span><span style="color: Gray;">,</span> ticks<span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
当前时间戳为: 1459996086.7115328&#13;
</pre>&#13;
&#13;
<p>&#13;
时间戳单位最适于做日期运算。但是1970年之前的日期就无法以此表示了。太遥远的日期也不行，UNIX和Windows只支持到2038年。&#13;
</p>&#13;
<br/><hr/>&#13;
<h2>什么是时间元组？</h2>&#13;
<p>很多Python函数用一个元组装起来的9组数字处理时间:</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:10%">序号&#13;
</th><th style="width:40%">字段</th><th>值</th>&#13;
</tr>&#13;
<tr><td>0</td><td>4位数年</td><td>2008</td></tr>&#13;
<tr><td>1</td><td>月</td><td>1 到 12</td></tr>&#13;
<tr><td>2</td><td>日</td><td>1到31</td></tr>&#13;
<tr><td>3</td><td>小时</td><td>0到23</td></tr>&#13;
<tr><td>4</td><td>分钟</td><td>0到59</td></tr>&#13;
<tr><td>5</td><td>秒</td><td>0到61 (60或61 是闰秒)</td></tr>&#13;
<tr><td>6</td><td>一周的第几日</td><td>0到6 (0是周一)</td></tr>&#13;
<tr><td>7</td><td>一年的第几日</td><td>1到366 (儒略历)</td></tr>&#13;
<tr><td>8</td><td>夏令时</td><td>-1, 0, 1, -1是决定是否为夏令时的标识</td></tr>&#13;
</tbody></table>&#13;
<p>上述也就是 struct_time 元组。这种结构具有如下属性：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:10%">序号</th><th style="width:40%">属性</th><th>值</th>&#13;
</tr>&#13;
<tr><td>0</td><td>tm_year</td><td>2008</td></tr>&#13;
<tr><td>1</td><td>tm_mon</td><td>1 到 12</td></tr>&#13;
<tr><td>2</td><td>tm_mday</td><td>1 到 31</td></tr>&#13;
<tr><td>3</td><td>tm_hour</td><td>0 到 23</td></tr>&#13;
<tr><td>4</td><td>tm_min</td><td>0 到 59</td></tr>&#13;
<tr><td>5</td><td>tm_sec</td><td>0 到 61 (60或61 是闰秒)</td></tr>&#13;
<tr><td>6</td><td>tm_wday</td><td>0 到 6 (0是周一)</td></tr>&#13;
<tr><td>7</td><td>tm_yday</td><td>一年中的第几天，1 到 366</td></tr>&#13;
<tr><td>8</td><td>tm_isdst</td><td>是否为夏令时，值有：1(夏令时)、0(不是夏令时)、-1(未知)，默认 -1 </td></tr>&#13;
</tbody></table>&#13;
<br/><hr/>&#13;
<h2>获取当前时间</h2>&#13;
<p>从返回浮点数的时间戳方式向时间元组转换，只要将浮点数传递给如localtime之类的函数。</p>&#13;
<pre>&#13;
#!/usr/bin/python3&#13;
&#13;
import time&#13;
&#13;
localtime = time.localtime(time.time())&#13;
print ("本地时间为 :", localtime)&#13;
</pre>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
本地时间为 : time.struct_time(tm_year=2016, tm_mon=4, tm_mday=7, tm_hour=10, tm_min=28, tm_sec=49, tm_wday=3, tm_yday=98, tm_isdst=0)&#13;
</pre>&#13;
<br/><hr/>&#13;
<h2>获取格式化的时间</h2>&#13;
<p>你可以根据需求选取各种格式，但是最简单的获取可读的时间模式的函数是asctime():</p>&#13;
&#13;
<pre>&#13;
#!/usr/bin/python3&#13;
&#13;
import time&#13;
&#13;
localtime = time.asctime( time.localtime(time.time()) )&#13;
print ("本地时间为 :", localtime)&#13;
</pre>&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
本地时间为 : Thu Apr  7 10:29:13 2016&#13;
</pre>&#13;
<hr/>&#13;
<h2>格式化日期</h2>&#13;
<p>我们可以使用 time 模块的 strftime 方法来格式化日期：</p>&#13;
<pre>&#13;
time.strftime(format[, t])&#13;
</pre>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">time</span><br/>
<br/>
<span style="color: #a50"># 格式化成2016-03-20 11:45:39形式</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">strftime</span><span style="color: Olive;">(</span><span style="color: #a11;">"%Y-%m-%d %H:%M:%S"</span><span style="color: Gray;">,</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">localtime</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
<br/>
<span style="color: #a50"># 格式化成Sat Mar 28 22:24:24 2016形式</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">strftime</span><span style="color: Olive;">(</span><span style="color: #a11;">"%a %b %d %H:%M:%S %Y"</span><span style="color: Gray;">,</span> <span style="color: #05a;">time</span>.<span style="color: #05a;">localtime</span><span style="color: Olive;">(</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
  <br/>
<span style="color: #a50"># 将格式字符串转换为时间戳</span><br/>
a <span style="color: Gray;">=</span> <span style="color: #a11;">"Sat Mar 28 22:24:24 2016"</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">mktime</span><span style="color: Olive;">(</span><span style="color: #05a;">time</span>.<span style="color: #05a;">strptime</span><span style="color: Olive;">(</span>a<span style="color: Gray;">,</span><span style="color: #a11;">"%a %b %d %H:%M:%S %Y"</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
2016-04-07 10:29:46&#13;
Thu Apr 07 10:29:46 2016&#13;
1459175064.0&#13;
</pre>&#13;
<p>python中时间日期格式化符号：</p>&#13;
<ul> <li>%y 两位数的年份表示（00-99）</li> <li>%Y 四位数的年份表示（000-9999）</li> <li>%m 月份（01-12）</li> <li>%d 月内中的一天（0-31）</li> <li>%H 24小时制小时数（0-23）</li> <li>%I 12小时制小时数（01-12）</li> <li>%M 分钟数（00=59）</li> <li>%S 秒（00-59）</li> <li>%a 本地简化星期名称</li> <li>%A 本地完整星期名称</li> <li>%b 本地简化的月份名称</li> <li>%B 本地完整的月份名称</li> <li>%c 本地相应的日期表示和时间表示</li> <li>%j 年内的一天（001-366）</li> <li>%p 本地A.M.或P.M.的等价符</li> <li>%U 一年中的星期数（00-53）星期天为星期的开始</li> <li>%w 星期（0-6），星期天为星期的开始</li> <li>%W 一年中的星期数（00-53）星期一为星期的开始</li> <li>%x 本地相应的日期表示</li> <li>%X 本地相应的时间表示</li> <li>%Z 当前时区的名称</li> <li>%% %号本身</li> </ul>&#13;
<hr/>&#13;
<h2>获取某月日历</h2>&#13;
<p>Calendar 模块有很广泛的方法用来处理年历和月历，例如打印某月的月历：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #a50">#!/usr/bin/python3</span><br/>
<br/>
<span style="color: Green;font-weight:bold;">import</span> <span style="color: #05a;">calendar</span><br/>
<br/>
cal <span style="color: Gray;">=</span> <span style="color: #05a;">calendar</span>.<span style="color: #05a;">month</span><span style="color: Olive;">(</span><span style="color: Maroon;">2016</span><span style="color: Gray;">,</span> <span style="color: Maroon;">1</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span><span style="color: #a11;">"以下输出2016年1月份的日历:"</span><span style="color: Olive;">)</span><br/>
<span style="color: Green;font-weight:bold;">print</span> <span style="color: Olive;">(</span>cal<span style="color: Olive;">)</span><br/>
</div></div>&#13;
&#13;
<p>以上实例输出结果：</p>&#13;
<pre>&#13;
以下输出2016年1月份的日历:&#13;
    January 2016&#13;
Mo Tu We Th Fr Sa Su&#13;
             1  2  3&#13;
 4  5  6  7  8  9 10&#13;
11 12 13 14 15 16 17&#13;
18 19 20 21 22 23 24&#13;
25 26 27 28 29 30 31&#13;
</pre>&#13;
<br/><hr/>&#13;
<h2>Time 模块</h2>&#13;
<p>Time 模块包含了以下内置函数，既有时间处理的，也有转换时间格式的：</p>&#13;
&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:5%">序号</th><th style="width:35%">函数及描述</th><th>实例</th></tr>&#13;
<tr><td>1</td><td>time.altzone<br/>返回格林威治西部的夏令时地区的偏移秒数。如果该地区在格林威治东部会返回负值（如西欧，包括英国）。对夏令时启用地区才能使用。</td>&#13;
<td>&#13;
<p>以下实例展示了 altzone()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print ("time.altzone %d " % time.altzone)&#13;
time.altzone -28800 &#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>2</td><td>time.asctime([tupletime])<br/>接受时间元组并返回一个可读的形式为"Tue Dec 11 18:07:14 2008"（2008年12月11日 周二18时07分14秒）的24个字符的字符串。</td>&#13;
<td>&#13;
<p>以下实例展示了 asctime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; t = time.localtime()&#13;
&gt;&gt;&gt; print ("time.asctime(t): %s " % time.asctime(t))&#13;
time.asctime(t): Thu Apr  7 10:36:20 2016 &#13;
</pre>&#13;
</td>&#13;
&#13;
</tr>&#13;
<tr><td>3</td><td><a href="python3-att-time-clock.html" target="_blank" rel="noopener noreferrer">time.clock()</a><br/>用以浮点数计算的秒数返回当前的CPU时间。用来衡量不同程序的耗时，比time.time()更有用。</td><td><p><a href="python3-att-time-clock.html" target="_blank" rel="noopener noreferrer">实例</a></p>&#13;
<p>由于该方法依赖操作系统，在 Python 3.3 以后不被推荐，而在 3.8 版本中被移除，需使用下列两个函数替代。</p>&#13;
<pre>time.perf_counter()  # 返回系统运行时间&#13;
time.process_time()  # 返回进程运行时间</pre>&#13;
&#13;
</td></tr>&#13;
<tr><td>4</td><td>time.ctime([secs])<br/>作用相当于asctime(localtime(secs))，未给参数相当于asctime()</td>&#13;
<td>&#13;
<p>以下实例展示了 ctime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print ("time.ctime() : %s" % time.ctime())&#13;
time.ctime() : Thu Apr  7 10:51:58 2016&#13;
</pre>&#13;
</td>&#13;
&#13;
&#13;
</tr>&#13;
<tr><td>5</td><td>time.gmtime([secs])<br/>接收时间戳（1970纪元后经过的浮点秒数）并返回格林威治天文时间下的时间元组t。注：t.tm_isdst始终为0</td>&#13;
<td>&#13;
<p>以下实例展示了 gmtime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print ("gmtime :", time.gmtime(1455508609.34375))&#13;
gmtime : time.struct_time(tm_year=2016, tm_mon=2, tm_mday=15, tm_hour=3, tm_min=56, tm_sec=49, tm_wday=0, tm_yday=46, tm_isdst=0)&#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>6</td><td>time.localtime([secs]<br/>接收时间戳（1970纪元后经过的浮点秒数）并返回当地时间下的时间元组t（t.tm_isdst可取0或1，取决于当地当时是不是夏令时）。</td>&#13;
<td>&#13;
<p>以下实例展示了 localtime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print ("localtime(): ", time.localtime(1455508609.34375))&#13;
localtime():  time.struct_time(tm_year=2016, tm_mon=2, tm_mday=15, tm_hour=11, tm_min=56, tm_sec=49, tm_wday=0, tm_yday=46, tm_isdst=0)&#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>7</td><td><a href="python3-att-time-mktime.html" target="_blank" rel="noopener noreferrer">time.mktime(tupletime)</a><br/>接受时间元组并返回时间戳（1970纪元后经过的浮点秒数）。</td><td><a href="python3-att-time-mktime.html" target="_blank" rel="noopener noreferrer">实例</a></td></tr>&#13;
<tr><td>8</td><td>time.sleep(secs)<br/>推迟调用线程的运行，secs指秒数。</td>&#13;
<td>&#13;
<p>以下实例展示了 sleep()函数的使用方法：</p>&#13;
<pre>&#13;
#!/usr/bin/python3&#13;
import time&#13;
&#13;
print ("Start : %s" % time.ctime())&#13;
time.sleep( 5 )&#13;
print ("End : %s" % time.ctime())&#13;
</pre>&#13;
</td>&#13;
&#13;
</tr>&#13;
<tr><td>9</td><td>time.strftime(fmt[,tupletime])<br/>接收以时间元组，并返回以可读字符串表示的当地时间，格式由fmt决定。</td>&#13;
<td>&#13;
<p>以下实例展示了 strftime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print (time.strftime("%Y-%m-%d %H:%M:%S", time.localtime()))&#13;
2016-04-07 11:18:05&#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>10</td><td>time.strptime(str,fmt='%a %b %d %H:%M:%S %Y')<br/>根据fmt的格式把一个时间字符串解析为时间元组。</td>&#13;
<td>&#13;
<p>以下实例展示了 strptime()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; struct_time = time.strptime("30 Nov 00", "%d %b %y")&#13;
&gt;&gt;&gt; print ("返回元组: ", struct_time)&#13;
返回元组:  time.struct_time(tm_year=2000, tm_mon=11, tm_mday=30, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=3, tm_yday=335, tm_isdst=-1)&#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>11</td><td>time.time( )<br/>返回当前时间的时间戳（1970纪元后经过的浮点秒数）。</td>&#13;
&#13;
<td>&#13;
<p>以下实例展示了 time()函数的使用方法：</p>&#13;
<pre>&#13;
&gt;&gt;&gt; import time&#13;
&gt;&gt;&gt; print(time.time())&#13;
1459999336.1963577&#13;
</pre>&#13;
</td>&#13;
</tr>&#13;
<tr><td>12</td><td><a href="python3-att-time-tzset.html" target="_blank" rel="noopener noreferrer">time.tzset()</a><br/>根据环境变量TZ重新初始化时间相关设置。 </td><td><a href="python3-att-time-tzset.html" target="_blank" rel="noopener noreferrer">实例</a></td></tr>&#13;
&#13;
<tr><td>13</td><td><b>&#13;
time.perf_counter()</b><br/>&#13;
&#13;
返回计时器的精准时间（系统的运行时间），包含整个系统的睡眠时间。由于返回值的基准点是未定义的，所以，只有连续调用的结果之间的差才是有效的。&#13;
</td><td>&#13;
<a href="#comment-35499">实例</a>&#13;
</td></tr>&#13;
<tr><td>14</td><td><b>&#13;
time.process_time() </b><br/>&#13;
&#13;
返回当前进程执行 CPU 的时间总和，不包含睡眠时间。由于返回值的基准点是未定义的，所以，只有连续调用的结果之间的差才是有效的。&#13;
</td><td>&#13;
 &#13;
</td></tr>&#13;
&#13;
</tbody></table>&#13;
<p>Time模块包含了以下2个非常重要的属性：</p>&#13;
&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:5%">序号</th><th style="width:95%">属性及描述</th></tr>&#13;
<tr><td>1</td><td><b>time.timezone</b><br/>属性time.timezone是当地时区（未启动夏令时）距离格林威治的偏移秒数（&gt;0，美洲;&lt;=0大部分欧洲，亚洲，非洲）。</td></tr>&#13;
<tr><td>2</td><td><b>time.tzname</b><br/>属性time.tzname包含一对根据情况的不同而不同的字符串，分别是带夏令时的本地时区名称，和不带的。</td></tr>&#13;
</tbody></table>&#13;
<br/><hr/>&#13;
<h2>日历（Calendar）模块</h2>&#13;
<p>此模块的函数都是日历相关的，例如打印某月的字符月历。</p>&#13;
<p>星期一是默认的每周第一天，星期天是默认的最后一天。更改设置需调用calendar.setfirstweekday()函数。模块包含了以下内置函数：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:5%">序号</th><th style="width:95%">函数及描述</th></tr>&#13;
<tr><td>1</td><td><b>calendar.calendar(year,w=2,l=1,c=6)</b><br/>返回一个多行字符串格式的 year 年年历，3 个月一行，间隔距离为 c。 每日宽度间隔为w字符。每行长度为 <span class="marked">21* W+18+2* C</span>。<strong>l</strong> 是每星期行数。</td></tr>&#13;
<tr><td>2</td><td><b>calendar.firstweekday( )</b><br/>返回当前每周起始日期的设置。默认情况下，首次载入 calendar 模块时返回 0，即星期一。</td></tr>&#13;
<tr><td>3</td><td><b>calendar.isleap(year)</b><br/><p> 是闰年返回 True，否则为 False。</p>&#13;
<pre>&gt;&gt;&gt; import calendar&#13;
&gt;&gt;&gt; print(calendar.isleap(2000))&#13;
True&#13;
&gt;&gt;&gt; print(calendar.isleap(1900))&#13;
False</pre>&#13;
 &#13;
&#13;
&#13;
</td></tr>&#13;
<tr><td>4</td><td><b>calendar.leapdays(y1,y2)</b><br/>返回在Y1，Y2两年之间的闰年总数。</td></tr>&#13;
<tr><td>5</td><td><b>calendar.month(year,month,w=2,l=1)</b><br/>返回一个多行字符串格式的year年month月日历，两行标题，一周一行。每日宽度间隔为w字符。每行的长度为7* w+6。l是每星期的行数。</td></tr>&#13;
<tr><td>6</td><td><b>calendar.monthcalendar(year,month)</b><br/>返回一个整数的单层嵌套列表。每个子列表装载代表一个星期的整数。Year年month月外的日期都设为0;范围内的日子都由该月第几日表示，从1开始。</td></tr>&#13;
<tr><td>7</td><td><b>calendar.monthrange(year,month)</b><br/><p>返回两个整数。第一个是该月的星期几，第二个是该月有几天。星期几是从0（星期一）到 6（星期日）。</p>&#13;
<pre>&gt;&gt;&gt; import calendar&#13;
&gt;&gt;&gt; calendar.monthrange(2014, 11)&#13;
(5, 30)</pre>&#13;
<p>(5, 30)解释：5 表示 2014 年 11 月份的第一天是周六，30 表示 2014 年 11 月份总共有 30 天。</p>&#13;
</td></tr>&#13;
<tr><td>8</td><td><b>calendar.prcal(year, w=0, l=0, c=6, m=3)</b><br/>相当于 print (calendar.calendar(year, w=0, l=0, c=6, m=3))。</td></tr>&#13;
<tr><td>9</td><td><b>calendar.prmonth(theyear, themonth, w=0, l=0)</b><br/>相当于 <span class="marked">print(calendar.month(theyear, themonth, w=0, l=0))</span>。</td></tr>&#13;
<tr><td>10</td><td><b>calendar.setfirstweekday(weekday)</b><br/>设置每周的起始日期码。0（星期一）到6（星期日）。</td></tr>&#13;
<tr><td>11</td><td><b>calendar.timegm(tupletime)</b><br/>和time.gmtime相反：接受一个时间元组形式，返回该时刻的时间戳（1970纪元后经过的浮点秒数）。</td></tr>&#13;
<tr><td>12</td><td><b>calendar.weekday(year,month,day)</b><br/>返回给定日期的日期码。0（星期一）到6（星期日）。月份为 1（一月） 到 12（12月）。</td></tr>&#13;
&#13;
&#13;
&#13;
</tbody></table>&#13;
<br/><hr/>&#13;
<h2>其他相关模块和函数</h2>&#13;
<p>在Python中，其他处理日期和时间的模块还有：</p>&#13;
&#13;
<ul>&#13;
<li><a href="https://docs.python.org/3/library/time.html" target="_blank" rel="nofollow noopener noreferrer">time 模块</a></li>&#13;
<li><a href="https://docs.python.org/3/library/datetime.html" target="_blank" rel="nofollow noopener noreferrer">datetime模块</a></li>&#13;
</ul>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>