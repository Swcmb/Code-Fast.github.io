<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 File(文件) 方法</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 File(文件) 方法</h1>&#13;
<h3>open() 方法&#13;
</h3>&#13;
<p>Python <span class="marked">open()</span> 方法用于打开一个文件，并返回文件对象。&#13;
</p><p>在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 <span class="marked">OSError</span>。</p>&#13;
<p><strong>注意：</strong>使用 <span class="marked">open()</span> 方法一定要保证关闭文件对象，即调用 <span class="marked">close()</span> 方法。</p>&#13;
<p><span class="marked">open()</span> 函数常用形式是接收两个参数：文件名(file)和模式(mode)。</p>&#13;
&#13;
<pre>open(file, mode='r')</pre>&#13;
&#13;
<p>完整的语法格式为：</p>&#13;
<pre>open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)</pre>&#13;
&#13;
<p>参数说明:</p>&#13;
<ul>&#13;
<li>file: 必需，文件路径（相对或者绝对路径）。</li>&#13;
<li>mode: 可选，文件打开模式</li>&#13;
<li>buffering: 设置缓冲</li>&#13;
<li>encoding: 一般使用utf8</li>&#13;
<li>errors: 报错级别</li>&#13;
<li>newline: 区分换行符</li>&#13;
<li>closefd: 传入的file参数类型</li>&#13;
<li>opener: 设置自定义开启器，开启器的返回值必须是一个打开的文件描述符。</li>&#13;
</ul>&#13;
&#13;
<p>mode 参数有：</p>&#13;
<table class="reference">&#13;
<tbody><tr><th style="width:10%">模式</th><th>描述</th></tr>&#13;
<tr><td>t</td><td>文本模式 (默认)。</td></tr>&#13;
<tr><td>x</td><td>写模式，新建一个文件，如果该文件已存在则会报错。</td></tr>&#13;
<tr><td>b</td><td>二进制模式。</td></tr>&#13;
<tr><td>+</td><td>打开一个文件进行更新(可读可写)。</td></tr>&#13;
<tr><td>U</td><td>通用换行模式（<strong style="color:red;">Python 3 不支持</strong>）。</td></tr>&#13;
<tr><td>r</td><td>以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。</td></tr>&#13;
<tr><td>rb</td><td>以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。</td></tr>&#13;
<tr><td>r+</td><td>打开一个文件用于读写。文件指针将会放在文件的开头。</td></tr>&#13;
<tr><td>rb+</td><td>以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。一般用于非文本文件如图片等。</td></tr>&#13;
<tr><td>w</td><td>打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr>&#13;
<tr><td>wb</td><td>以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。</td></tr>&#13;
<tr><td>w+</td><td>打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。</td></tr> &#13;
<tr><td>wb+</td><td>以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。</td></tr>&#13;
&#13;
&#13;
<tr><td>a</td><td>打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。</td></tr> &#13;
<tr><td>ab</td><td>以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。</td></tr> &#13;
<tr><td>a+</td><td>打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。</td></tr> &#13;
<tr><td>ab+</td><td>以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。</td></tr>&#13;
&#13;
</tbody></table>&#13;
&#13;
<p>默认为文本模式，如果要以二进制模式打开，加上 <span class="marked">b</span> 。</p>&#13;
<h3> file 对象</h3>&#13;
<p>&#13;
file 对象使用 open 函数来创建，下表列出了 file 对象常用的函数：&#13;
</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:5%">序号</th><th>方法及描述</th></tr>&#13;
<tr><td>1</td><td><p><a href="/python3/python3-file-close.html">file.close()</a></p><p>关闭文件。关闭后文件不能再进行读写操作。</p></td></tr>&#13;
<tr><td>2</td><td><p><a href="/python3/python3-file-flush.html">file.flush()</a></p><p>刷新文件内部缓冲，直接把内部缓冲区的数据立刻写入文件, 而不是被动的等待输出缓冲区写入。</p></td></tr>&#13;
<tr><td>3</td><td><p><a href="/python3/python3-file-fileno.html">file.fileno()</a></p><p>&#13;
返回一个整型的文件描述符(file descriptor FD 整型), 可以用在如os模块的read方法等一些底层操作上。</p></td></tr>&#13;
<tr><td>4</td><td><p><a href="/python3/python3-file-isatty.html">file.isatty()</a></p><p>如果文件连接到一个终端设备返回 True，否则返回 False。</p></td></tr>&#13;
<tr><td>5</td><td><p><a href="/python3/python3-file-next.html">file.next()</a></p><p><strong style="color:red;">Python 3 中的 File 对象不支持 next() 方法。</strong></p><p>返回文件下一行。</p></td></tr>&#13;
<tr><td>6</td><td><p><a href="/python3/python3-file-read.html">file.read([size])</a></p><p>从文件读取指定的字节数，如果未给定或为负则读取所有。</p></td></tr>&#13;
<tr><td>7</td><td><p><a href="/python3/python3-file-readline.html">file.readline([size])</a></p><p>读取整行，包括 "\n" 字符。</p></td></tr>&#13;
<tr><td>8</td><td><p><a href="/python3/python3-file-readlines.html">file.readlines([sizeint])</a></p><p>读取所有行并返回列表，若给定sizeint&gt;0，返回总和大约为sizeint字节的行, 实际读取值可能比 sizeint 较大, 因为需要填充缓冲区。</p></td></tr>&#13;
<tr><td>9</td><td><p><a href="/python3/python3-file-seek.html">file.seek(offset[, whence])</a></p><p>移动文件读取指针到指定位置</p></td></tr>&#13;
<tr><td>10</td><td><p><a href="/python3/python3-file-tell.html">file.tell()</a></p><p>返回文件当前位置。</p></td></tr>&#13;
<tr><td>11</td><td><p><a href="/python3/python3-file-truncate.html">file.truncate([size])</a></p><p>从文件的首行首字符开始截断，截断文件为 size&#13;
 个字符，无 size 表示从当前位置截断；截断之后后面的所有字符被删除，其中 windows 系统下的换行代表2个字符大小。 </p></td></tr>&#13;
<tr><td>12</td><td><p><a href="/python3/python3-file-write.html">file.write(str)</a></p><p>将字符串写入文件，返回的是写入的字符长度。</p></td></tr>&#13;
<tr><td>13</td><td><p><a href="/python3/python3-file-writelines.html">file.writelines(sequence)</a></p><p>向文件写入一个序列字符串列表，如果需要换行则要自己加入每行的换行符。</p></td></tr>&#13;
</tbody></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>