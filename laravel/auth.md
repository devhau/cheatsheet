# Authentication 

```php
// Determine if the current user is authenticated
Auth::check();
// Get the currently authenticated user
Auth::user();
// Get the ID of the currently authenticated user
Auth::id();
// Attempt to authenticate a user using the given credentials
Auth::attempt(array('email' => $email, 'password' => $password));
// 'Remember me' by passing true to Auth::attempt()
Auth::attempt($credentials, true);
// Log in for a single request
Auth::once($credentials);
// Log a user into the application
Auth::login(User::find(1));
// Log the given user ID into the application
Auth::loginUsingId(1);
// Log the user out of the application
Auth::logout();
// Validate a user's credentials
Auth::validate($credentials);
// Attempt to authenticate using HTTP Basic Auth
Auth::basic('username');
// Perform a stateless HTTP Basic login attempt
Auth::onceBasic();
// Send a password reminder to a user
Password::remind($credentials, function($message, $user){});
              
Authorization 
// Define abilities
Gate::define('update-post', 'Class@method');
Gate::define('update-post', function ($user, $post) {...});
// Passing multiple argument
Gate::define('delete-comment', function ($user, $post, $comment) {});

// Check abilities
Gate::denies('update-post', $post);
Gate::allows('update-post', $post);
Gate::check('update-post', $post);
// Specified a user for checking
Gate::forUser($user)->allows('update-post', $post);
// Through User model, using Authorizable trait
User::find(1)->can('update-post', $post);
User::find(1)->cannot('update-post', $post);

// Intercepting Authorization Checks
Gate::before(function ($user, $ability) {});
Gate::after(function ($user, $ability) {});

// Chekcing in Blade template
@can('update-post', $post)
@endcan
// with else
@can('update-post', $post)
@else
@endcan

// Generate a Policy
php artisan make:policy PostPolicy
// `policy` helper function
policy($post)->update($user, $post)

// Controller Authorization
$this->authorize('update', $post);
// for $user
$this->authorizeForUser($user, 'update', $post);
```