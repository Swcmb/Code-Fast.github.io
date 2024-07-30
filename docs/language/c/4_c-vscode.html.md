<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>C VScode</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>C VScode</h1>&#13;
<p>在上一章节中我们已经介绍了 C 基本概念及实例，本章节我们将介绍 C 代码的编辑器 -- VScode。</p>&#13;
<p>VSCode（全称：Visual Studio Code）是一款由微软开发且跨平台的免费源代码编辑器，VSCode 开发环境非常简单易用。</p><p>&#13;
VSCode 支持 C/C++ 是由微软提供的 Visual Studio Code 的一个扩展，它使得在 Windows、Linux 和 macOS 上进行跨平台的 C 和 C++ 开发成为可能。</p><p>当你创建一个 <span class="marked">*.c</span> 或 <span class="marked">*.cpp</span>文件时，该扩展会添加一些功能，比如语法高亮（着色）、智能补全和悬停以及错误检查。</p>&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2024/04/msg-intellisense.png"/></p>&#13;
<h3>安装 VS Code</h3>&#13;
&#13;
<p>VSCode 安装也很简单，打开官网 <a href="https://code.visualstudio.com/" rel="noopener" target="_blank">https://code.visualstudio.com/</a>，下载软件包，一步步安装即可，安装过程注意安装路径设置、环境变量默认自动添加到系统中，勾选以下所有选项：</p>&#13;
&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2021/08/RM04TZb.png"/></p>&#13;
<p>VSCode 完整安装教程参考：<a href="https://www.runoob.com/w3cnote/vscode-tutorial.html" rel="noopener" target="_blank">https://www.runoob.com/w3cnote/vscode-tutorial.html</a></p>&#13;
<h3>安装 C/C++ 扩展</h3>&#13;
<ul>&#13;
<li>1、打开 VS Code。</li>&#13;
<li>点击左侧菜单栏选择扩展图标或使用键盘快捷键 (<span class="marked">⇧⌘X</span>) 打开扩展界面。</li>&#13;
<li>搜索<code><span class="marked">C++</span></code>。</li>&#13;
<li>选择以下扩展点击 <strong>Install</strong>。</li>&#13;
</ul>&#13;
&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2024/04/cpp-extension.png"/></p>&#13;
<hr/><h2>&#13;
创建一个 C 代码文件</h2>&#13;
<p>打开 VScode，然后点击新建文件：</p>&#13;
<p><img decoding="async" width="60%" src="https://www.runoob.com/wp-content/uploads/2021/08/vscode-py-1.jpeg"/></p>&#13;
<p>点击选择语言：</p>&#13;
<p><img decoding="async" width="60%" src="https://www.runoob.com/wp-content/uploads/2021/08/vscode-py-2.jpg"/></p>&#13;
<p>在搜索框输入 <span class="marked">c</span>，创建 <span class="marked">test.c</span> 文件：</p>&#13;
<p><img decoding="async" width="60%" src="https://www.runoob.com/wp-content/uploads/2024/04/68913738ed9af6c37be969bd4f9555e0.png"/></p>&#13;
<p>输入代码，保存 test.c 文件代码，右击文件名，在集成终端执行以下命令：</p>&#13;
&#13;
<div class="example"><h2 class="example">实例</h2> <div class="example_code">
<span style="color: #060;">#include &lt;stdio.h&gt;</span><br/>
 <br/>
<span style="color: #05a;">int</span> main<span style="color: #008000;">(</span><span style="color: #008000;">)</span><br/>
<span style="color: #008000;">{</span><br/>
    <span style="color: #696969;; font-style: italic;">/* 我的第一个 C 程序 */</span><br/>
    <span style="color: #05a;">printf</span><span style="color: #008000;">(</span><span style="color: #a11;">"Hello, World! <span style="color: #000099; font-weight: bold;">\n</span>"</span><span style="color: #008000;">)</span><span style="color: #008080;">;</span><br/>
 <br/>
    <span style="color: #05a;">return</span> <span style="color: #0000dd;">0</span><span style="color: #008080;">;</span><br/>
<span style="color: #008000;">}</span><br/>
</div></div>&#13;
&#13;
<p><img decoding="async" src="https://www.runoob.com/wp-content/uploads/2024/04/1f8feb000ac189aeee671ba3bea3dd87.png"/></p>&#13;
			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>