---
layout: post
title:  "簡易 React Router 跟 Transition 的學習筆記"
date:   2016-03-14 04:07:49
categories: Frontend Development
banner_image: ""
featured: false
comments: true
---

以前在看 React 的時候覺得 Routing 應該很難，一直讓我覺得很困擾，本身沒有用過 Angular，所以對於這方面也沒有一定的知識或經驗，感覺就是有點艱難，成功之後覺得非常有成就感。

<!--more-->

## Solution

今天學會了如何使用 React 換頁面，加上簡單的 Fade In/Out 效果。

### 學習筆記

- v0.13 跟 v1 的 Router 使用方式不一樣
- Router 是使用 `component` 不再用 `handler`
- `cloneWithProps` 已不使用，換成 `cloneElements`
- transition 若沒有改變的話原因是因為要 `key: this.props.location.pathname` 要更新，不止 `this.props.children`，更多參考[這個連結](https://facebook.github.io/react/docs/top-level-api.html#react.cloneelement)
- 發現無法預設連結為 `active` 的原因是因為當初為 `Link to="start-here"`，應該 `Link to="/"` 才對，這樣就能預設是 root 進來的（花了好久時間才發現）。

### Demo
<p data-height="435" data-theme-id="0" data-slug-hash="JXJBvM" data-default-tab="result" data-user="whalesingswee" class="codepen">See the Pen <a href="http://codepen.io/whalesingswee/pen/JXJBvM/">React Router with Transition</a> by Hsiang Lee (<a href="http://codepen.io/whalesingswee">@whalesingswee</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>