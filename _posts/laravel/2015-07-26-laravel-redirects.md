---
layout: post
title: L5 Laravel Redirects 你知多少?
category: Laravel
tags: laravel
keywords: null
description: null
published: true
---
Laravel 的 redirect() function我們常用, 以下是所以有關Laravel 5 Redirects的用法。
## 簡單用法 (URL + Parameter)
例如你的網站Domain是 www.example.com。
<code>return redirect('homepage');</code>
Redirects 去 http://www.example.com/homepage
<code>return redirect('auth/login');</code>
Redirects 去 www.example.com/auth/login
<code>return redirect('');</code>
Redirects 去 主頁
<code></code>
<code></code>
<code></code>



