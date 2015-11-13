title: egret使用心得
date: 2015-11-13 15:04:00
tags: [egret,编程]
---

前阶段用egret做了个小项目，这里总结一下：

命令行总结：
=========================
1.[官网命令行汇总](http://edn.egret.com/cn/index.php/article/index/id/582)
2.关于自动编译：
<pre><code>egret startserver -a    //启动服务器并自动编译（ctrl+s可以自动编译ts文件）</code>
<code>egret startserver -a -port 88    //修改端口</code></pre>
3.使用 <code>egret build -e</code>命令，引擎会自动把使用到的类库放到你的项目里，如何扩展模块:
 http://edn.egret.com/cn/index.php/article/index/id/650

4.可以安装httpster来启动一个服务，就算不用webstorm或者其他编辑器，也方便开发。
  安装httpster：<code>npm install -g httpster</code>
   修改端口号：<code> httpster -p 8080</code>
   详细教程地址：[搭建简单的本地服务器]( http://maoziliang.github.io/2013/05/15/%E5%9C%A8%E6%9C%AC%E5%9C%B0%E8%B0%83%E8%AF%95%E7%A7%BB%E5%8A%A8%E8%AE%BE%E5%A4%87%E4%B8%8A%E7%9A%84App/
  )

调试手机端，weinre使用 ：
===========================
1. [weinre官网](https://people.apache.org/~pmuellr/weinre-docs/latest/Running.html)
2. [Web移动应用远程调试工具 Weinre](https://dearb.me/archive/2013-11-21/web-inspector-remote-debugger-weinre/)

关于egret的一些不错的教程和资料地址：
=========================
1. [Egret大教程](http://bbs.egret.com/plugin.php?id=webpage&identifier=Egret)
1. [使用egret的资源加载机制（RES）](https://github.com/egret-labs/egret-core/wiki/Using-Resource-System)
2. [调tween动画的界面]( http://edn.egret.com/cn/index.php?g=&m=article&a=index&id=53)
3. [游戏--场景切换,自定义用户事件](http://bbs.egret.com/forum.php?mod=viewthread&tid=10391&highlight=%E5%88%87%E6%8D%A2)
4. [如何生成 .d.ts](http://edn.egret.com/cn/index.php/article/index/id/698)
5. [深度管理,实现类似css的index功能](http://edn.egret.com/cn/index.php/article/posts/id/70)


性能优化：
=====================
Egret包含多种显示对象，要限制内存使用量，需选择合适的显示对象。
*   对于非交互的简单形状，使用Shape。
*   对于没有重绘需求有子节点，使用DisplayObjectContainer 。
*   对于有重绘需求有子节点，使用Sprite。





