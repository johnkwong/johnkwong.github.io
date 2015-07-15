---
layout: post
title: L5 視圖組件
category: Laravel
tags: laravel
keywords: null
description: null
published: true
---


## 視圖組件(View Composer)

一個好的程式是盡量避免重疊編寫相同的程式碼。重疊編寫程式碼變得集亂，使我們難以維護，此外，系統效能也會減底。所以我們要學懂如何重複再用一段程式碼。
而我們可以從Model和View的關係入手, 我們之前學過在Controller再把Model的資料轉為Array, 最後Pass給View顯示資料內容。但現在我們可以用View Composer, 令到Model資料跟View直接綁定。因為有很多資料很常用, 每次使用時在Controller重寫, 倒不如View直接透過View Composer找Model取資料。我們又不用在每個Controller寫重疊的東西, 寫一個View Composer, 所以多個View也可以取得資料。有多好呢~
> 視圖組件(View Composer)
視圖組件就是在視圖被渲染前，會呼叫的閉包或類別方法。如果你想在每次渲染某些視圖時綁定資料，視圖組件可以把這樣的程式邏輯組織在同一個地方。



新增一個Service Provider
<code>php artisan make:provider ViewComposerServiceProvider</code>

編輯 App/Provider/ViewComposerServiceProvider

<pre><code>	public function boot()
	{
		view()->composer('partials.nav', function($view) {
		$view->with('user_email', User::find(Auth::id())->email);
		});
	}</code></pre>
	
編輯 config/app.php

<pre><code>	'providers' => [
	'App\Providers\ViewComposerServiceProvider',
	],</code></pre>
