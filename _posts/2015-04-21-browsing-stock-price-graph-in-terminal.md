---
layout: post
title: Looking up stock price graph in Terminal
---
<p>Ever thought about browsing stock quotes in terminal? There was two nice posts on hackers news last month that fitted nicely together that enabled this. It also helped me learn more about coding in Go, which I must admit is pretty cool to learn, but not without its quirk.</p>
<p>Screen shots first:</p>
<p>Wide version:</p>
<p><img src="/content/images/generic_blog/expanded.png"  ></p>
<p>Narrow version (termui auto scaling):</p>
<p><img src="/content/images/generic_blog/shorten.png"  ></p>
<p>Take aways after writing this:</p>
<p>- With a typed language, it is easier to access elements inside a struct with accessor function, not Pluck (in Go's case, it's Reflect)<br>- Strict variable checking and module checking sometimes is a little annoying. By commenting out one line that consumes a variable, you will have to comment out the definition (if there is no other place that use this variable), and comments out the imports<br>- "go fmt" is nice to have, but don't run it too often as it slows you down<br>- I still don't know how to create an array using variable as size. From pointer perspective it makes sense. Just use append<br>- NewList is such a strange syntax. You have no way telling whether you are calling a plain function or creating a object by simply looking at the function name. <br>- what happened on January 2nd, 2006 at 3pm? why formatting a time requires me to remember this specific date? I rather remember one more person's birthday.<br>- var variable Int doesn't seemed to be needed in most use case. := is better. Though it increases the amount of documentation look up<br>- if you return an err object, you are forcing the caller to write some err handling code. Doesn't this lead to error handling everywhere?</p>
<p><span style="">Thanks for two hackers news community posts (links below) for providing inspiration.</span></p>
<p><a href="https://github.com/gizak/termui">termui</a> (<a href="https://github.com/gizak/termui">github</a>) HN: <a href="https://news.ycombinator.com/item?id=9276188">https://news.ycombinator.com/item?id=9276188</a></p>
<p><a href="https://github.com/doneland/yquotes">yquotes</a> (<a href="https://github.com/doneland/yquotes">github</a>) HN: <a href="https://news.ycombinator.com/item?id=9374373">https://news.ycombinator.com/item?id=9374373</a></p>
<p>Code on Gist: <a href="https://gist.github.com/63404185ba39fae9d254.git">https://gist.github.com/63404185ba39fae9d254.git</a></p>