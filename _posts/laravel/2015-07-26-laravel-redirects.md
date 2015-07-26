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

## Redirecting Back

這個用法可以回到上一頁。
<code>return redirect()->back();</code>

## 帶Data的Redirects

這個方法會把error這個key和Something went wrong這個value 增加到Session Flash Data裡。
<code>return redirect()->back()->with('error', 'Something went wrong.');</code>
你同時可以帶多個DataRedirects回上一頁。
<code>return redirect()->back()->with('error', 'Something went wrong.')->with('order_value', $value);</code>
比較方便的作法是使用array。
<code>$parameters = ['error' => 'Something went wrong.', 'order_value' => $value];
return redirect()->back()->with($parameters);</code>
你可以用old($key)取得之前Form填寫的資料, 他也可以使用withInput()方法 Redirect回填寫的資料回Form
<code>return redirect()->back()->withInput();</code>
<code></code>

## Redirect 到 Route那裡
<code>get('books', ['as' => 'books_list', 'uses' => 'BooksController@index']);</code>
<code>return redirect()->route('books');</code>

<code>get('book/{id}', ['as' => 'book_view', 'uses' => 'BooksController@show']);</code>
<code>return redirect()->route('book_view', 1);</code>

<code>get('book/{category}/{id}', ['as' => 'book_view', 'uses' => 'BooksController@show']);</code>
<code>return redirect()->route('book_view', [513, 1]);</code>
<code>return redirect()->route('book_view', ['category'=>513, 'id'=>1]);</code>
<code></code>

<code></code>

