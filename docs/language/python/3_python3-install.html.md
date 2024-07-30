<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <title>Python3 环境搭建</title>
</head>
<body>
<div class="article-intro" id="content">

    <h1>Python3 <span class="color_h1">环境搭建</span></h1>&#13;
    &#13;
    <p>本章节我们将向大家介绍如何在本地搭建 Python3 开发环境。</p>&#13;
    <p>Python3 可应用于多平台包括 Windows、Linux 和 Mac OS X。</p>&#13;
    &#13;
    &#13;
    <ul>&#13;
        <li>Unix (Solaris, Linux, FreeBSD, AIX, HP/UX, SunOS, IRIX, 等等。)</li>&#13;
        <li>Win 9x/NT/2000</li>&#13;
        <li>Macintosh (Intel, PPC, 68K)</li>&#13;
        <li>OS/2</li>&#13;
        <li>DOS (多个DOS版本)</li>&#13;
        <li>PalmOS</li>&#13;
        <li>Nokia 移动手机</li>&#13;
        <li>Windows CE</li>&#13;
        <li>Acorn/RISC OS</li>&#13;
        <li>BeOS</li>&#13;
        <li>Amiga</li>&#13;
        <li>VMS/OpenVMS</li>&#13;
        <li>QNX</li>&#13;
        <li>VxWorks</li>&#13;
        <li>Psion</li>&#13;
        <li>Python 同样可以移植到 Java 和 .NET 虚拟机上。</li>&#13;
    </ul>&#13;
    <br/>
    <hr/>
    <h2>Python3 下载</h2>&#13;
    <p>Python3 最新源码，二进制文档，新闻资讯等可以在 Python 的官网查看到：</p>&#13;
    <p>Python 官网：<a href="https://www.python.org/" rel="nofollow noopener noreferrer" target="_blank">https://www.python.org/</a>
    </p>&#13;
    <p>你可以在以下链接中下载 Python 的文档，你可以下载 HTML、PDF 和 PostScript 等格式的文档。</p>&#13;
    <p>Python文档下载地址：<a href="https://www.python.org/doc/" rel="nofollow noopener noreferrer" target="_blank">https://www.python.org/doc/</a>
    </p>&#13;
    &#13;
    <br/>
    <hr/>
    <h2>Python 安装</h2>&#13;
    <p>Python 已经被移植在许多平台上（经过改动使它能够工作在不同平台上）。</p>&#13;
    <p>您需要下载适用于您使用平台的二进制代码，然后安装 Python。</p>&#13;
    <p>如果您平台的二进制代码是不可用的，你需要使用C编译器手动编译源代码。</p>&#13;
    <p>编译的源代码，功能上有更多的选择性， 为 Python 安装提供了更多的灵活性。</p>&#13;
    <p>以下是各个平台安装包的下载地址：</p>&#13;
    <p><img decoding="async"
            src="https://www.runoob.com/wp-content/uploads/2018/07/F2135662-1078-4EE2-BEBB-353F8D8E521F.jpg"/></p>&#13;
    <p><strong>Source Code</strong> 可用于 Linux 上的安装。</p>&#13;
    <p>以下为不同平台上安装 Python3 的方法。</p>&#13;
    <h3>Unix &amp; Linux 平台安装 Python3:</h3>&#13;
    <p>以下为在 Unix &amp; Linux 平台上安装 Python 的简单步骤：</p>&#13;
    <ul class="list">&#13;
        <li>打开 WEB 浏览器访问 <a href="https://www.python.org/downloads/source/" rel="nofollow noopener noreferrer"
                                   target="_blank">https://www.python.org/downloads/source/</a></li>&#13;
        <li>选择适用于 Unix/Linux 的源码压缩包。</li>&#13;
        <li>下载及解压压缩包 <strong>Python-3.x.x.tgz</strong>，<strong>3.x.x</strong> 为你下载的对应版本号。</li>&#13;
        <li>如果你需要自定义一些选项修改 <i>Modules/Setup</i></li>&#13;
    </ul>&#13;
    <p>以<strong> Python3.6.1</strong> 版本为例：</p>&#13;
    <pre>&#13;
# tar -zxvf Python-3.6.1.tgz&#13;
# cd Python-3.6.1&#13;
# ./configure&#13;
# make &amp;&amp; make install&#13;
</pre>&#13;
    <p>检查 Python3 是否正常可用：</p>&#13;
    &#13;
    &#13;
    <pre># python3 -V&#13;
Python 3.6.1</pre>&#13;
    &#13;
    <h3>Window 平台安装 Python:</h3>&#13;
    <p>以下为在 Window 平台上安装 Python 的简单步骤。</p>&#13;
    <p>打开 WEB 浏览器访问 <a href="https://www.python.org/downloads/windows/" rel="nofollow noopener" target="_blank">https://www.python.org/downloads/windows/</a>
        ：&#13;
    </p>
    <p><img decoding="async"
            src="https://www.runoob.com/wp-content/uploads/2018/07/1bf7d20f853bf2c4a8f03c03c864982f.png"/></p>&#13;
    <p>这些链接提供了不同类型的 Python 安装文件，适用于不同类型的 Windows 系统和使用情景：</p>&#13;
    <ul>&#13;
        <li>&#13;
            <p><strong>Download Windows installer (64-bit)</strong>：64 位 Windows 系统的安装程序。</p>&#13;
        </li>&#13;
        <li>&#13;
            <p><strong>Download Windows installer (ARM64)</strong>：适用于 ARM64 架构的 Windows 设备的安装程序。</p>&#13;
        </li>&#13;
        <li>&#13;
            <p><strong>Download Windows embeddable package (64-bit)</strong>：64 位 Windows 系统的嵌入式包，可用于嵌入到应用程序中。
            </p>&#13;
        </li>&#13;
        <li>&#13;
            <p><strong>Download Windows embeddable package (32-bit)</strong>：32 位 Windows 系统的嵌入式包，同样可用于嵌入到应用程序中。
            </p>&#13;
        </li>&#13;
        <li>&#13;
            <p><strong>Download Windows embeddable package (ARM64)</strong>：适用于 ARM64 架构的 Windows 设备的嵌入式包。
            </p>&#13;
        </li>&#13;
        <li>&#13;
            <p><strong>Download Windows installer (32-bit)</strong>：32 位 Windows 系统的安装程序。</p>&#13;
        </li>&#13;
    </ul>&#13;
    <p>记得勾选 <strong>Add Python 3.6 to PATH</strong>。</p>&#13;
    <p><img decoding="async" src="https://www.runoob.com//wp-content/uploads/2018/07/20180226150011548.png"/></p>&#13;
    &#13;
    &#13;
    <p>按 <span class="marked">Win+R</span> 键，输入 cmd 调出命令提示符，输入 python:</p>&#13;
    <p><img decoding="async" src="https://www.runoob.com//wp-content/uploads/2018/07/20170707155742110.png"/></p>&#13;
    <p>也可以在开始菜单中搜索 <strong>IDLE</strong>：</p>&#13;
    &#13;
    &#13;
    <p><img decoding="async"
            src="https://www.runoob.com/wp-content/uploads/2018/07/460F6DFB-3BBF-4683-BEA0-23BE8DF021B0.jpg"/></p>&#13;
    <h3>MAC 平台安装 Python:</h3>&#13;
    <p>MAC 系统都自带有 Python2.7 环境，你可以在链接 <a href="https://www.python.org/downloads/mac-osx/"
                                                       rel="nofollow noopener noreferrer" target="_blank">https://www.python.org/downloads/mac-osx/</a>
        上下载最新版安装 Python 3.x。</p>&#13;
    &#13;
    <p>你也可以参考源码安装的方式来安装。</p>&#13;
    &#13;
    &#13;
    &#13;
    &#13;
    &#13;
    <br/>
    <hr/>
    <h2>环境变量配置</h2>&#13;
    &#13;
    <p>程序和可执行文件可以在许多目录，而这些路径很可能不在操作系统提供可执行文件的搜索路径中。</p>&#13;
    &#13;
    <p>
        path(路径)存储在环境变量中，这是由操作系统维护的一个命名的字符串。这些变量包含可用的命令行解释器和其他程序的信息。</p>&#13;
    &#13;
    <p>Unix 或 Windows 中路径变量为 PATH（UNIX 区分大小写，Windows 不区分大小写）。</p>&#13;
    &#13;
    <p>在 Mac OS 中，安装程序过程中改变了 Python 的安装路径。如果你需要在其他目录引用 Python，你必须在 path 中添加 Python
        目录。</p>&#13;
    &#13;
    <h3>在 Unix/Linux 设置环境变量</h3>&#13;
    <ul>&#13;
        <li><b>在 csh shell:</b> 输入 <br/>
            <pre>setenv PATH "$PATH:/usr/local/bin/python"</pre>
            , 按下 <strong>Enter</strong>。
        </li>&#13;
        <li><b>在 bash shell (Linux) 输入 :</b><br/>
            <pre>export PATH="$PATH:/usr/local/bin/python" </pre>
            按下 <strong>Enter</strong> 。
        </li>&#13;
        <li><b>在 sh 或者 ksh shell 输入:</b> <br/>
            <pre>PATH="$PATH:/usr/local/bin/python" </pre>
            按下 Enter。
        </li>&#13;
    </ul>&#13;
    &#13;
    <p><strong>注意: </strong>/usr/local/bin/python 是 Python 的安装目录。</p>&#13;
    <h3>在 Windows 设置环境变量</h3>&#13;
    <p>在环境变量中添加Python目录：</p>&#13;
    <p><b>在命令提示框中(cmd) :</b> 输入 <br/></p>
    <pre>path=%path%;C:\Python </pre>
    按下"Enter"。&#13;
    &#13;
    <p><strong>注意: </strong>C:\Python 是Python的安装目录。</p>&#13;
    <p>也可以通过以下方式设置：</p>&#13;
    <ul>
        <li>右键点击"计算机"，然后点击"属性"</li>
        <li>然后点击"高级系统设置"</li>
        <li>&#13;
            选择"系统变量"窗口下面的"Path",双击即可！
        </li>
        <li>&#13;
        </li>
        <li>&#13;
            然后在"Path"行，添加python安装路径即可(我的D:\Python32)，所以在后面，添加该路径即可。&#13;
            <b>ps：记住，路径直接用分号"；"隔开！</b></li>
        <li>&#13;
            &#13;
            最后设置成功以后，在cmd命令行，输入命令"python"，就可以有相关显示。
        </li>
    </ul>
    <p>&#13;
        <img decoding="async" src="https://www.runoob.com/wp-content/uploads/2013/11/201209201707594792.png"/></p>&#13;
    <hr/>&#13;
    <h2>Python 环境变量</h2>&#13;
    <p>下面几个重要的环境变量，它应用于Python：</p>&#13;
    &#13;
    <table class="reference">&#13;
        <tbody>
        <tr>
            <th>变量名</th>
            <th>描述</th>
        </tr>&#13;
        <tr>
            <td>PYTHONPATH</td>
            <td> PYTHONPATH是Python搜索路径，默认我们import的模块都会从PYTHONPATH里面寻找。</td>
        </tr>&#13;
        <tr>
            <td>PYTHONSTARTUP</td>
            <td>Python启动后，先寻找PYTHONSTARTUP环境变量，然后执行此变量指定的文件中的代码。</td>
        </tr>&#13;
        <tr>
            <td>PYTHONCASEOK</td>
            <td>加入PYTHONCASEOK的环境变量, 就会使python导入模块的时候不区分大小写.</td>
        </tr>&#13;
        <tr>
            <td>PYTHONHOME</td>
            <td>另一种模块搜索路径。它通常内嵌于的PYTHONSTARTUP或PYTHONPATH目录中，使得两个模块库更容易切换。</td>
        </tr>&#13;
        </tbody>
    </table>&#13;
    <br/>
    <hr/>&#13;
    <h2>运行 Python</h2>&#13;
    <p>有三种方式可以运行 Python：</p>&#13;
    <h3>1、交互式解释器：</h3>&#13;
    <p>你可以通过命令行窗口进入 Python 并开始在交互式解释器中开始编写 Python 代码。</p>&#13;
    <p>你可以在 Unix、DOS 或任何其他提供了命令行或者 shell 的系统进行 Python 编码工作。</p>&#13;
    &#13;
    <pre>$ python             # Unix/Linux&#13;
&#13;
或者  &#13;
&#13;
C:&gt;python           # Windows/DOS</pre>&#13;
    &#13;
    <p>以下为 Python 命令行参数：</p>&#13;
    <table class="reference">&#13;
        <tbody>
        <tr>&#13;
            <th>选项</th>
            <th>描述</th>
        </tr>&#13;
        <tr>
            <td>-d</td>
            <td>在解析时显示调试信息</td>
        </tr>&#13;
        <tr>
            <td>-O</td>
            <td>生成优化代码 ( .pyo 文件 )</td>
        </tr>&#13;
        <tr>
            <td>-S</td>
            <td>启动时不引入查找Python路径的位置</td>
        </tr>&#13;
        <tr>
            <td>-V</td>
            <td>输出Python版本号</td>
        </tr>&#13;
        <tr>
            <td>-X</td>
            <td>&#13;
                从 1.6版本之后基于内建的异常（仅仅用于字符串）已过时。
            </td>
        </tr>&#13;
        <tr>
            <td>-c cmd</td>
            <td>执行 Python 脚本，并将运行结果作为 cmd 字符串。</td>
        </tr>&#13;
        <tr>
            <td>file</td>
            <td>在给定的python文件执行python脚本。</td>
        </tr>&#13;
        </tbody>
    </table>&#13;
    &#13;
    <h3>2、命令行脚本</h3>&#13;
    <p>在你的应用程序中通过引入解释器可以在命令行中执行Python脚本，如下所示：</p>&#13;
    &#13;
    <pre>$ python  script.py          # Unix/Linux&#13;
&#13;
或者&#13;
&#13;
C:&gt;python script.py         # Windows/DOS</pre>&#13;
    &#13;
    <p><strong>注意：</strong>在执行脚本时，请检查脚本是否有可执行权限。</p>&#13;
    &#13;
    <h3>3、集成开发环境（IDE：Integrated Development Environment）: PyCharm </h3>&#13;
    <p>PyCharm 是由 JetBrains 打造的一款 Python IDE，支持 macOS、 Windows、 Linux 系统。</p>&#13;
    <p>PyCharm 功能 : 调试、语法高亮、Project管理、代码跳转、智能提示、自动完成、单元测试、版本控制……</p>&#13;
    <p>PyCharm 下载地址 : <a href="https://www.jetbrains.com/pycharm/download/" rel="noopener noreferrer"
                             target="_blank">https://www.jetbrains.com/pycharm/download/</a></p>&#13;
    &#13;
    <p>PyCharm 安装地址：<a href="//www.runoob.com/w3cnote/pycharm-windows-install.html" rel="noopener noreferrer"
                           target="_blank">http://www.runoob.com/w3cnote/pycharm-windows-install.html</a></p>&#13;
    <p>Professional（专业版，收费）：完整的功能，可试用 30 天。</p>&#13;
    <p>Community（社区版，免费）：阉割版的专业版。</p>&#13;
    <p><img decoding="async" src="//www.runoob.com/wp-content/uploads/2018/05/1525863037-6053-.png"/></p>&#13;
    <p>PyCharm 界面：</p>&#13;
    <p><img decoding="async"
            src="https://www.runoob.com/wp-content/uploads/2013/11/execute-python-hello-world-program.png"/></p>
    <p>&#13;
        安装 PyCharm 中文插件，打开菜单栏 File，选择 Settings，然后选 Plugins，点 Marketplace，搜索 chinese，然后点击 install
        安装：</p>&#13;
    <p><img decoding="async"
            src="https://www.runoob.com/wp-content/uploads/2013/11/aHR0cDovL3d3dy54aW1vcWluZy5jbi9kYXRhL3VwbG9hZHMvMjAyMDA0MjIvNTY1ODA1NTIyNDhhYTIwNmQzZThiMTQzNDVlZjc2NjEuanBn.jpeg"/>
    </p>&#13;
    <br/>
    <hr/>
    <h2>Anaconda 集成环境</h2>&#13;
    &#13;
    <p>Anaconda 发行版包含了 Python。</p>
    <p>&#13;
        Anaconda 是一个集成的数据科学和机器学习环境，其中包括了 Python 解释器以及大量常用的数据科学库和工具。</p>&#13;
    <p>Anaconda 包及其依赖项和环境的管理工具为 conda 命令，文与传统的 Python pip 工具相比 Anaconda 的conda
        可以更方便地在不同环境之间进行切换，环境管理较为简单。</p>&#13;
    <p>Anaconda详细安装与介绍参考：<a href="https://www.runoob.com/python-qt/anaconda-tutorial.html" rel="noopener"
                                     target="_blank">Anaconda 教程。</a></p>            <!-- 其他扩展 -->

</div>


</body>
</html>