---
layout: post
title: Laravel 5 常用指令
category: Laravel
tags: laravel
keywords: null
description: null
published: true
---

## 視圖組件(View Composer)

<code>php artisan make:provider ViewComposerServiceProvider</code>
Edit App/Provider/ViewComposerServiceProvider
<pre><code>
	public function boot()
	{
		//$user = User::find(Auth::id());
		view()->composer('partials.nav', function($view) {
		$view->with('user_email', User::find(Auth::id())->email);
		});
	}
</code></pre>

Edit config/app.php
	'providers' => [
    'App\Providers\ViewComposerServiceProvider',
    ],
