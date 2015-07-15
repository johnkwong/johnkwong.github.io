---
published: false
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
