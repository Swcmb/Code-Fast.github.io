<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<title>Java 9 新特性
</title>
</head>
<body>
<div class="article-intro" id="content">
			
			<h1>Java 9 新特性&#13;
</h1>&#13;
<p>Java 9 发布于 2017 年 9 月 22 日，带来了很多新特性，其中最主要的变化是已经实现的模块化系统。接下来我们会详细介绍 Java 9 的新特性。</p>&#13;
<h2>&#13;
Java 9 新特性&#13;
</h2><ul><li>&#13;
<strong>模块系统</strong>：模块是一个包的容器，Java 9 最大的变化之一是引入了模块系统（Jigsaw 项目）。&#13;
</li><li>&#13;
<strong>REPL (JShell)</strong>：交互式编程环境。&#13;
</li><li>&#13;
<strong>HTTP 2 客户端</strong>：HTTP/2标准是HTTP协议的最新版本，新的 HTTPClient API 支持 WebSocket 和 HTTP2 流以及服务器推送特性。&#13;
</li><li>&#13;
<strong>改进的 Javadoc</strong>：Javadoc 现在支持在 API 文档中的进行搜索。另外，Javadoc 的输出现在符合兼容 HTML5 标准。&#13;
</li><li>&#13;
<strong>多版本兼容 JAR 包</strong>：多版本兼容 JAR 功能能让你创建仅在特定版本的 Java 环境中运行库程序时选择使用的 class 版本。</li><li>&#13;
<strong>集合工厂方法</strong>：List，Set 和 Map 接口中，新的静态工厂方法可以创建这些集合的不可变实例。</li><li>&#13;
<strong>私有接口方法</strong>：在接口中使用private私有方法。我们可以使用 private 访问修饰符在接口中编写私有方法。&#13;
</li><li>&#13;
&#13;
<strong>进程 API</strong>: 改进的 API 来控制和管理操作系统进程。引进 java.lang.ProcessHandle 及其嵌套接口 Info 来让开发者逃离时常因为要获取一个本地进程的 PID 而不得不使用本地代码的窘境。&#13;
</li><li>&#13;
<strong>改进的 Stream API</strong>：改进的 Stream API 添加了一些便利的方法，使流处理更容易，并使用收集器编写复杂的查询。&#13;
</li><li>&#13;
<strong>改进  try-with-resources</strong>：如果你已经有一个资源是 final 或等效于 final 变量,您可以在 try-with-resources 语句中使用该变量，而无需在 try-with-resources 语句中声明一个新变量。&#13;
</li><li>&#13;
<strong>改进的弃用注解  @Deprecated</strong>：注解 @Deprecated 可以标记 Java API 状态，可以表示被标记的 API 将会被移除，或者已经破坏。&#13;
</li><li>&#13;
<strong>改进钻石操作符(Diamond Operator) </strong>：匿名类可以使用钻石操作符(Diamond Operator)。&#13;
</li><li>&#13;
<strong>改进 Optional 类</strong>：java.util.Optional  添加了很多新的有用方法，Optional 可以直接转为 stream。&#13;
</li><li>&#13;
<strong>多分辨率图像 API</strong>：定义多分辨率图像API，开发者可以很容易的操作和展示不同分辨率的图像了。&#13;
</li><li>&#13;
<strong>改进的 CompletableFuture API</strong> ： CompletableFuture 类的异步机制可以在 ProcessHandle.onExit 方法退出时执行操作。&#13;
</li><li>&#13;
<strong>轻量级的 JSON API</strong>：内置了一个轻量级的JSON API&#13;
</li><li>&#13;
<strong>响应式流（Reactive Streams) API</strong>: Java 9中引入了新的响应式流 API 来支持 Java 9 中的响应式编程。</li></ul>&#13;
<p>更多的新特性可以参阅官网：<a target="_blank" href="https://docs.oracle.com/javase/9/whatsnew/toc.htm" rel="noopener noreferrer">What's New in JDK 9</a>&#13;
</p>&#13;
<p>JDK 9 下载地址：<a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk9-doc-downloads-3850606.html" rel="noopener noreferrer" target="_blank">http://www.oracle.com/technetwork/java/javase/downloads/jdk9-doc-downloads-3850606.html</a></p>&#13;
<p>在关于 Java 9 文章的实例，我们均使用 jdk 1.9 环境，你可以使用以下命令查看当前 jdk 的版本：</p>&#13;
&#13;
<pre>$ java -version&#13;
java version "9-ea"&#13;
Java(TM) SE Runtime Environment (build 9-ea+163)&#13;
Java HotSpot(TM) 64-Bit Server VM (build 9-ea+163, mixed mode)</pre>&#13;
&#13;
接下来我们将详细为大家简介 Java 9 的新特性：&#13;
&#13;
<table class="reference">&#13;
<tbody><tr>&#13;
<th>序号</th>&#13;
<th>特性</th>&#13;
&#13;
</tr>&#13;
<tr>&#13;
<td>1</td>&#13;
<td><a href="/java/java9-module-system.html" rel="noopener noreferrer" target="_blank">模块系统</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>2</td>&#13;
<td><a href="/java/java9-repl.html" rel="noopener noreferrer" target="_blank">REPL (JShell)</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>3</td>&#13;
<td><a href="/java/java9-improved-javadocs.html" rel="noopener noreferrer" target="_blank">改进的 Javadoc</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>4</td>&#13;
<td><a href="/java/java9-multirelease-jar.html" rel="noopener noreferrer" target="_blank">多版本兼容 JAR 包</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>5</td>&#13;
<td><a href="/java/java9-collection-factory-methods.html" rel="noopener noreferrer" target="_blank">集合工厂方法</a></td>&#13;
</tr>&#13;
&#13;
&#13;
<tr>&#13;
<td>6</td>&#13;
<td><a href="/java/java9-private-interface-methods.html" rel="noopener noreferrer" target="_blank">私有接口方法</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>7</td>&#13;
<td><a href="/java/java9-process-api-improvements.html" rel="noopener noreferrer" target="_blank">进程 API</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>8</td>&#13;
<td><a href="/java/java9-stream-api-improvements.html" rel="noopener noreferrer" target="_blank">Stream API</a></td>&#13;
</tr>&#13;
&#13;
<tr>&#13;
<td>9</td>&#13;
<td><a href="/java/java9-try-with-resources-improvement.html" rel="noopener noreferrer" target="_blank">try-with-resources</a></td>&#13;
</tr>&#13;
&#13;
&#13;
<tr>&#13;
<td>10</td>&#13;
<td><a href="/java/java9-enhanced-deprecated-annotation.html" rel="noopener noreferrer" target="_blank">@Deprecated</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>11</td>&#13;
<td><a href="/java/java9-inner-class-diamond-operator.html" rel="noopener noreferrer" target="_blank">内部类的钻石操作符(Diamond Operator)</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>12</td>&#13;
<td><a href="/java/java9-optional-class-improvements.html" rel="noopener noreferrer" target="_blank">Optional 类</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>13</td>&#13;
<td><a href="/java/java9-multiresolution-image_api.html" rel="noopener noreferrer" target="_blank">多分辨率图像 API</a></td>&#13;
</tr>&#13;
<tr>&#13;
<td>14</td>&#13;
<td><a href="/java/java9-completablefuture-api-improvements.html" rel="noopener noreferrer" target="_blank">CompletableFuture API</a></td>&#13;
</tr>&#13;
&#13;
&#13;
&#13;
&#13;
</tbody></table>			<!-- 其他扩展 -->
						
			</div>
			
		
</body>
</html>