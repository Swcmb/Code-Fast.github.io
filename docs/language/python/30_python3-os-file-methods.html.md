<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Python3 OS 文件/目录方法</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Python3 OS 文件/目录方法</h1>&#13;
&#13;
<p><b>os</b> 模块提供了非常丰富的方法用来处理文件和目录。常用的方法如下表所示：</p>&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th style="width:5%">序号</th><th>方法及描述</th></tr>&#13;
<tr><td>1</td><td><p><a href="/python3/python3-os-access.html">os.access(path, mode)</a></p><br/>检验权限模式  </td></tr>&#13;
<tr><td>2</td><td><p><a href="/python3/python3-os-chdir.html">os.chdir(path)</a></p><br/>改变当前工作目录</td></tr>&#13;
<tr><td>3</td><td><p><a href="/python3/python3-os-chflags.html">os.chflags(path, flags)</a></p><br/>设置路径的标记为数字标记。</td></tr>&#13;
<tr><td>4</td><td><p><a href="/python3/python3-os-chmod.html">os.chmod(path, mode)</a></p><br/>更改权限 </td></tr>&#13;
<tr><td>5</td><td><p><a href="/python3/python3-os-chown.html">os.chown(path, uid, gid)</a></p><br/>更改文件所有者</td></tr>&#13;
<tr><td>6</td><td><p><a href="/python3/python3-os-chroot.html">os.chroot(path)</a></p><br/>改变当前进程的根目录  </td></tr>&#13;
<tr><td>7</td><td><p><a href="/python3/python3-os-close.html">os.close(fd)</a></p><br/>关闭文件描述符 fd</td></tr>&#13;
<tr><td>8</td><td><p><a href="/python3/python3-os-closerange.html">os.closerange(fd_low, fd_high)</a></p><br/>关闭所有文件描述符，从 fd_low (包含) 到 fd_high (不包含), 错误会忽略</td></tr>&#13;
<tr><td>9</td><td><p><a href="/python3/python3-os-dup.html">os.dup(fd)</a></p><br/>复制文件描述符 fd</td></tr>&#13;
<tr><td>10</td><td><p><a href="/python3/python3-os-dup2.html">os.dup2(fd, fd2)</a></p><br/>将一个文件描述符 fd 复制到另一个 fd2</td></tr>&#13;
<tr><td>11</td><td><p><a href="/python3/python3-os-fchdir.html">os.fchdir(fd)</a></p><br/>通过文件描述符改变当前工作目录</td></tr>&#13;
<tr><td>12</td><td><p><a href="/python3/python3-os-fchmod.html">os.fchmod(fd, mode)</a></p><br/>改变一个文件的访问权限，该文件由参数fd指定，参数mode是Unix下的文件访问权限。</td></tr>&#13;
<tr><td>13</td><td><p><a href="/python3/python3-os-fchown.html">os.fchown(fd, uid, gid)</a></p><br/>修改一个文件的所有权，这个函数修改一个文件的用户ID和用户组ID，该文件由文件描述符fd指定。 </td></tr>&#13;
<tr><td>14</td><td><p><a href="/python3/python3-os-fdatasync.html">os.fdatasync(fd)</a></p><br/>强制将文件写入磁盘，该文件由文件描述符fd指定，但是不强制更新文件的状态信息。</td></tr>&#13;
<tr><td>15</td><td><p><a href="/python3/python3-os-fdopen.html">os.fdopen(fd[, mode[, bufsize]])</a></p><br/>通过文件描述符 fd 创建一个文件对象，并返回这个文件对象 </td></tr>&#13;
<tr><td>16</td><td><p><a href="/python3/python3-os-fpathconf.html">os.fpathconf(fd, name)</a></p><br/>返回一个打开的文件的系统配置信息。name为检索的系统配置的值，它也许是一个定义系统值的字符串，这些名字在很多标准中指定（POSIX.1, Unix 95, Unix 98, 和其它）。</td></tr>&#13;
<tr><td>17</td><td><p><a href="/python3/python3-os-fstat.html">os.fstat(fd)</a></p><br/>返回文件描述符fd的状态，像stat()。 </td></tr>&#13;
<tr><td>18</td><td><p><a href="/python3/python3-os-fstatvfs.html">os.fstatvfs(fd)</a></p><br/>返回包含文件描述符fd的文件的文件系统的信息，Python 3.3 相等于 statvfs()。</td></tr>&#13;
&#13;
<tr><td>19</td><td><p><a href="/python3/python3-os-fsync.html">os.fsync(fd)</a></p><br/>强制将文件描述符为fd的文件写入硬盘。</td></tr>&#13;
<tr><td>20</td><td><p><a href="/python3/python3-os-ftruncate.html">os.ftruncate(fd, length)</a></p><br/>裁剪文件描述符fd对应的文件, 所以它最大不能超过文件大小。</td></tr>&#13;
<tr><td>21</td><td><p><a href="/python3/python3-os-getcwd.html">os.getcwd()</a></p><br/>返回当前工作目录 </td></tr>&#13;
<tr><td>22</td><td><p><a href="/python3/python3-os-getcwdb.html">os.getcwdb()</a></p><br/>返回一个当前工作目录的Unicode对象</td></tr>&#13;
<tr><td>23</td><td><p><a href="/python3/python3-os-isatty.html">os.isatty(fd)</a></p><br/>如果文件描述符fd是打开的，同时与tty(-like)设备相连，则返回true, 否则False。</td></tr>&#13;
<tr><td>24</td><td><p><a href="/python3/python3-os-lchflags.html">os.lchflags(path, flags)</a></p><br/>设置路径的标记为数字标记，类似 chflags()，但是没有软链接</td></tr>&#13;
<tr><td>25</td><td><p><a href="/python3/python3-os-lchmod.html">os.lchmod(path, mode)</a></p><br/>修改连接文件权限</td></tr>&#13;
<tr><td>26</td><td><p><a href="/python3/python3-os-lchown.html">os.lchown(path, uid, gid)</a></p><br/>更改文件所有者，类似 chown，但是不追踪链接。 </td></tr>&#13;
<tr><td>27</td><td><p><a href="/python3/python3-os-link.html">os.link(src, dst)</a></p><br/>创建硬链接，名为参数 dst，指向参数 src</td></tr>&#13;
<tr><td>28</td><td><p><a href="/python3/python3-os-listdir.html">os.listdir(path)</a></p><br/>返回path指定的文件夹包含的文件或文件夹的名字的列表。 </td></tr>&#13;
<tr><td>29</td><td><p><a href="/python3/python3-os-lseek.html">os.lseek(fd, pos, how)</a></p><br/>设置文件描述符 fd当前位置为pos, how方式修改: SEEK_SET 或者 0 设置从文件开始的计算的pos; SEEK_CUR或者 1 则从当前位置计算; os.SEEK_END或者2则从文件尾部开始. 在unix，Windows中有效</td></tr>&#13;
<tr><td>30</td><td><p><a href="/python3/python3-os-lstat.html">os.lstat(path)</a></p><br/>像stat(),但是没有软链接 </td></tr>&#13;
<tr><td>31</td><td><p><a href="/python3/python3-os-major.html">os.major(device)</a></p><br/>从原始的设备号中提取设备major号码 (使用stat中的st_dev或者st_rdev field)。</td></tr>&#13;
<tr><td>32</td><td><p><a href="/python3/python3-os-makedev.html">os.makedev(major, minor)</a></p><br/>以major和minor设备号组成一个原始设备号</td></tr>&#13;
<tr><td>33</td><td><p><a href="/python3/python3-os-makedirs.html">os.makedirs(path[, mode])</a></p><br/>递归文件夹创建函数。像mkdir(), 但创建的所有intermediate-level文件夹需要包含子文件夹。</td></tr>&#13;
<tr><td>34</td><td><p><a href="/python3/python3-os-minor.html">os.minor(device)</a></p><br/>从原始的设备号中提取设备minor号码 (使用stat中的st_dev或者st_rdev field )。</td></tr>&#13;
<tr><td>35</td><td><p><a href="/python3/python3-os-mkdir.html">os.mkdir(path[, mode])</a></p><br/>以数字mode的mode创建一个名为path的文件夹.默认的 mode 是 0777 (八进制)。 </td></tr>&#13;
<tr><td>36</td><td><p><a href="/python3/python3-os-mkfifo.html">os.mkfifo(path[, mode])</a></p><br/>创建命名管道，mode 为数字，默认为 0666 (八进制) </td></tr>&#13;
<tr><td>37</td><td><p><a href="/python3/python3-os-mknod.html">os.mknod(filename[, mode=0600, device])</a><br/>创建一个名为filename文件系统节点（文件，设备特别文件或者命名pipe）。</p></td></tr>&#13;
<tr><td>38</td><td><p><a href="/python3/python3-os-open.html">os.open(file, flags[, mode])</a></p><br/>打开一个文件，并且设置需要的打开选项，mode参数是可选的</td></tr>&#13;
<tr><td>39</td><td><p><a href="/python3/python3-os-openpty.html">os.openpty()</a></p><br/>打开一个新的伪终端对。返回 pty 和 tty的文件描述符。</td></tr>&#13;
<tr><td>40</td><td><p><a href="/python3/python3-os-pathconf.html">os.pathconf(path, name)</a></p><br/>&#13;
返回相关文件的系统配置信息。 </td></tr>&#13;
<tr><td>41</td><td><p><a href="/python3/python3-os-pipe.html">os.pipe()</a></p><br/>创建一个管道. 返回一对文件描述符(r, w) 分别为读和写</td></tr>&#13;
<tr><td>42</td><td><p><a href="/python3/python3-os-popen.html">os.popen(command[, mode[, bufsize]])</a></p><br/>从一个 command 打开一个管道</td></tr>&#13;
<tr><td>43</td><td><p><a href="/python3/python3-os-read.html">os.read(fd, n)</a></p><br/>从文件描述符 fd 中读取最多 n 个字节，返回包含读取字节的字符串，文件描述符 fd对应文件已达到结尾, 返回一个空字符串。</td></tr>&#13;
<tr><td>44</td><td><p><a href="/python3/python3-os-readlink.html">os.readlink(path)</a></p><br/>返回软链接所指向的文件 </td></tr>&#13;
<tr><td>45</td><td><p><a href="/python3/python3-os-remove.html">os.remove(path)</a></p><br/>删除路径为path的文件。如果path 是一个文件夹，将抛出OSError; 查看下面的rmdir()删除一个 directory。 </td></tr>&#13;
<tr><td>46</td><td><p><a href="/python3/python3-os-removedirs.html">os.removedirs(path)</a></p><br/>递归删除目录。</td></tr>&#13;
<tr><td>47</td><td><p><a href="/python3/python3-os-rename.html">os.rename(src, dst)</a></p><br/>重命名文件或目录，从 src 到 dst</td></tr>&#13;
<tr><td>48</td><td><p><a href="/python3/python3-os-renames.html">os.renames(old, new)</a></p><br/>递归地对目录进行更名，也可以对文件进行更名。</td></tr>&#13;
<tr><td>49</td><td><p><a href="/python3/python3-os-rmdir.html">os.rmdir(path)</a></p><br/>删除path指定的空目录，如果目录非空，则抛出一个OSError异常。</td></tr>&#13;
<tr><td>50</td><td><p><a href="/python3/python3-os-stat.html">os.stat(path)</a></p><br/>获取path指定的路径的信息，功能等同于C API中的stat()系统调用。</td></tr>&#13;
<tr><td>51</td><td><p><a href="/python3/python3-os-stat_float_times.html">os.stat_float_times([newvalue])</a><br/>决定stat_result是否以float对象显示时间戳</p></td></tr>&#13;
<tr><td>52</td><td><p><a href="/python3/python3-os-statvfs.html">os.statvfs(path)</a></p><br/>获取指定路径的文件系统统计信息</td></tr>&#13;
<tr><td>53</td><td><p><a href="/python3/python3-os-symlink.html">os.symlink(src, dst)</a></p><br/>创建一个软链接</td></tr>&#13;
<tr><td>54</td><td><p><a href="/python3/python3-os-tcgetpgrp.html">os.tcgetpgrp(fd)</a></p><br/>返回与终端fd（一个由os.open()返回的打开的文件描述符）关联的进程组 </td></tr>&#13;
<tr><td>55</td><td><p><a href="/python3/python3-os-tcsetpgrp.html">os.tcsetpgrp(fd, pg)</a></p><br/>设置与终端fd（一个由os.open()返回的打开的文件描述符）关联的进程组为pg。</td></tr>&#13;
<tr><td>56</td><td><p>os.tempnam([dir[, prefix]])</p><br/><strong style="color:red">Python3 中已删除。</strong>返回唯一的路径名用于创建临时文件。 </td></tr>&#13;
<tr><td>57</td><td><p>os.tmpfile()</p><br/><strong style="color:red">Python3 中已删除。</strong>返回一个打开的模式为(w+b)的文件对象 .这文件对象没有文件夹入口，没有文件描述符，将会自动删除。 </td></tr>&#13;
<tr><td>58</td><td><p>os.tmpnam()</p><br/><strong style="color:red">Python3 中已删除。</strong>为创建一个临时文件返回一个唯一的路径</td></tr>&#13;
<tr><td>59</td><td><p><a href="/python3/python3-os-ttyname.html">os.ttyname(fd)</a></p><br/>返回一个字符串，它表示与文件描述符fd 关联的终端设备。如果fd 没有与终端设备关联，则引发一个异常。</td></tr>&#13;
<tr><td>60</td><td><p><a href="/python3/python3-os-unlink.html">os.unlink(path)</a></p><br/>删除文件路径 </td></tr>&#13;
<tr><td>61</td><td><p><a href="/python3/python3-os-utime.html">os.utime(path, times)</a></p><br/>返回指定的path文件的访问和修改的时间。 </td></tr>&#13;
<tr><td>62</td><td><p><a href="/python3/python3-os-walk.html">os.walk(top[, topdown=True[, onerror=None[, followlinks=False]]])</a></p><br/>输出在文件夹中的文件名通过在树中游走，向上或者向下。</td></tr>&#13;
<tr><td>63</td><td><p><a href="/python3/python3-os-write.html">os.write(fd, str)</a></p><br/>写入字符串到文件描述符 fd中. 返回实际写入的字符串长度</td></tr>&#13;
<tr><td>64</td><td><p><a href="/python3/python3-os-path.html" rel="noopener noreferrer" target="_blank">os.path 模块</a></p><br/>获取文件的属性信息。</td></tr>&#13;
<tr><td>65</td><td><p><a href="/python/os-write.html"/><a href="/python3/python3-os-pardir.html" rel="noopener noreferrer" target="_blank">os.pardir()</a></p><br/>获取当前目录的父目录，以字符串形式显示目录名。</td></tr>&#13;
&#13;
<tr><td>66</td><td><p><a href="/python3/python3-os-replace.html" rel="noopener noreferrer" target="_blank">os.replace()</a></p><br/>重命名文件或目录。</td></tr>&#13;
&#13;
<tr><td>67</td><td><p><a href="/python3/python3-os-startfile.html" rel="noopener noreferrer" target="_blank">os.startfile()</a></p><br/>用于在 Windows 上打开一个文件或文件夹。</td></tr>&#13;
</tbody></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>