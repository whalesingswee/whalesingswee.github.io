---
layout: post
title:  "如何砍掉 NodeJS Error: listen EADDRINUSE 的問題"
date:   2016-03-14 04:07:49
categories: Frontend Development
banner_image: ""
featured: false
comments: true
---

有些時候跑太多 node 的東西的時候都會遇到 Error: listen EADDRINUSE 的問題，不清楚怎麼解覺得朋友覺得很困擾，到底是哪個 address 被用掉了？

<!--more-->

## Solution

有些時候跑太多 node 的東西的時候都會遇到 Error: listen EADDRINUSE 的問題，這時候可以用這方式：

<div class="container">

{% highlight linenos %}
# 假設 1234 是 port 的號碼
lsof -i tcp: 1234
{% endhighlight %}

	<div class="reference">
		<strong>備註</strong>
		<p># 是 shell 裡面的 comment，不要加進去喔</p>
	</div>
</div>


之後會顯示你的 PID 多少，例如 `27373`，然後使用 `kill -9 27373` 就砍掉囉！非常好用！