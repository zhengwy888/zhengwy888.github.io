---
layout: post
title: windows7下蓝屏win32k.sys 0x0050修复方法
---
<p>原文请参照<a href="http://answers.microsoft.com/en-us/windows/forum/windows_7-windows_update/blue-screen-stop-0x50-after-applying-update/6da4d264-02d8-458e-89e2-a78fe68766fd"> 这里</a></p>
<p>
本人windows 7 64位专业版，最近微软装补丁抽风了。
具体信息为
<code>win32k.sys error 0x0050:  page_fault_in_nonpaged_area</code>
安全模式都无法进入，命令行正常模式都是蓝屏
</p>

解决办法就是找到自己能用的一个启动环境，可以是windows的安装光盘，也可以是自己装得Ubuntu。我常年在电脑上面备用一个Ubuntu，没想到今天派上用场了

<p>在能访问硬盘内容的情况下吧C:\Windows\System32\FNSCACHE.DAT给删了。
</p>
<pre>windows:
del C:\Windows\System32\FNSCACHE.DAT


linux:
rm /Windows/System32/FNSCACHE.DAT
</pre>

重启之后浏览器里面所有中文字都成了方块豆腐的乱码。再重启一遍就好