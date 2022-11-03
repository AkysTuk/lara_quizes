#### 1. Which of the following Route Model Bindings would not work?
1. [ ]
    ```php
    // Route definition...
    Route::get('/roles/{role}', [RoleController::class, 'show']);
    
    // Controller method definition...
    public function show(Role $role)
    {
        return view('role.edit', ['role' => $role]);
    }
    ```
2. [x] 
    ```php
    // Route definition...
    Route::get('/users/{user}', [UserController::class, 'show']);
    
    // Controller method definition...
    public function show(User $admin)
    {
        return view('user.profile', ['user' => $admin]);
    }
    ```
3. [ ]
    ```php
    // Route definition...
    Route::get('/users/{user}', [UserController::class, 'show']);
    
    // Controller method definition...
    public function show(User $user)
    {
        return view('user.profile', ['user' => $user]);
    }
    ```
#### 2. Route parameters are always encased between what?
1. [x] {}
2. [ ] <>
3. [ ] []
4. [ ] ()

#### 3. Which method would you use if you would like a route parameter to always be constrained by a given regular expression?
1. [x]
    ```php
    Route::pattern('id', '[0-9]+');
    ```
2. [ ]
    ```php 
    Route::regex('id', '[0-9]+');
    ```
3. [ ]
    ```php
    Route::always('id', '[0-9]+');
    ```
4. [ ]
    ```php
    Route::global('id', '[0-9]+');
    ```
#### 4. Which of the following are not available router methods. (Select all that apply)
1. [ ]
    ```php 
    Route::put($uri, $callback);
    ```
2. [x]
    ```php 
    Route::once($uri, $callback); 
    ```
3. [ ]
    ```php 
    Route::get($uri, $callback);
    ```
4. [ ]
    ```php 
    Route::patch($uri, $callback);
    ```
5. [ ]
    ```php 
    Route::delete($uri, $callback);
    ```
6. [x]
    ```php 
    Route::regex($uri, $callback); 
    ```
7. [ ]
    ```php 
    Route::post($uri, $callback);
    ```

#### 5. You can return a view directly from a route.
1. [ ] False
2. [x] True

#### 6. To register an explicit binding, you use the router's ________ method to specify the class for a given parameter. You should define your explicit model bindings at the ________ of the ________ method of your RouteServiceProvider class.
1. [x] `model`, `beginning`, `boot`
2. [ ] `global`, `beginning`, `boot`
3. [ ] `model`, `beginning`, `register`
4. [ ] `model`, `end`, `boot`

#### 7. If you need to specify a route parameter that may not always be present in the URI. You may do so by placing a ? mark _______ the parameter name.
1. [x] After
2. [ ] Before

#### 8. If the incoming request does not match the route pattern constraints, a ___ HTTP response will be returned.
1. [x] 404
2. [ ] 301
3. [ ] 302
4. [ ] 403

#### 9. What does the following route closure do?
```php
Route::fallback(function () {
    //
});
```

1. [ ] Lets you define a route that will be executed when route middleware fails.
2. [ ] Returns the result of the the closure when a route results in 404.
3. [ ] Lets you define a route that will be executed when a Route Model Binding fails.
4. [x] Lets you define a route that will be executed when no other route matches the incoming request.

#### 10. When using a middleware route group, the middleware are executed in the order they are listed in the array.
1. [x] True
2. [ ] False

#### 11. Which of the following would match any HTTP verb for the given route:
1. [ ]
    ```php
    Route::*('/', function () {
        //
    });
    ```
2. [ ]
    ```php
    Route::all('/', function () {
        //
    });
    ```
3. [x]
    ```php
    Route::any('/', function () {
        //
    });
    ```
4. [ ]
    ```php
    Route::get('/', function () {
        //
    });
    ```

#### 12. When using route parameters in view routes, the following parameters are reserved by Laravel and cannot be used. (Select all that apply):
1. [x] status
2. [ ] destination
3. [x] headers
4. [x] view
5. [x] data
6. [ ] route

#### 13. By default, what status code does the following return:
```php
Route::redirect('/here', '/there');
```

1. [ ] 301
2. [ ] 403
3. [x] 302
4. [ ] 200

#### 14. Which of the following are available to get information about the current route? (Select all that apply)
1. [ ]
    ```php
    $action = Route::getAllParameters();
    ```
2. [x]
    ```php
    $action = Route::currentRouteAction();
    ```
3. [x]
    ```php
    $name = Route::currentRouteName();
    ```
4. [x]
    ```php
    $route = Route::current();
    ```

#### 15. By default, what would the following URL be:
1. [ ] /web/user
2. [x] /api/user
3. [ ] /user
4. [ ] /api/public/user

#### 16. Laravel can automatically respond to CORS OPTIONS HTTP requests with values that you configure.
1. [x] True
2. [ ] False

#### 17. If you would like to use resolve Route Model Bindings with a column other than ID, what would be the correct syntax?
1. [ ]
    ```php
    Route::get('/posts/{post{slug}}', [PostController::class, 'show'])
    ```
2.  [x]
     ```php
     Route::get('/posts/{post:slug}', [PostController::class, 'show'])
     ```
3. [ ]
    ```php
    Route::get('/posts/{post<slug>}', [PostController::class, 'show'])
    ```
4. [ ]
    ```php
    Route::get('/posts/{post}', [PostController::class, 'show'])->by('uuid');
    ```

#### 18. If your route has dependencies that you would like the Laravel service container to automatically inject into your route's callback, you should list your route parameters _______ your dependencies.
1. [ ] Before
2. [x] After

#### 19. What does the following class do?
```php
Illuminate\Foundation\Http\Kernel
```

1. [ ] Dispatch the request to the controller.
2. [ ] Hand the request off to the router for dispatching.
3. [ ] Loads the route files contained within your application's routes directory.
4. [x] Defines an array of bootstrappers that will be run before the request is executed.

#### 20. The router will dispatch the request to a route or controller, as well as run any route specific middleware.
1. [x] True
2. [ ] False

#### 21. Which service provider method gets called first?
1. [ ] Boot
2. [x] Register

#### 22. All incoming requests flow through which central locations? (Select all that apply)
1. [ ] Route Kernel
2. [ ] Session Kernel
3. [x] HTTP Kernel
4. [ ] Response Kernel
5. [x] Console Kernel

#### 23. What is the first step Laravel takes in its request lifecycle?
1. [x] Create an instance of the application / service container.
2. [ ] Verify the CSRF token.
3. [ ] Defines the list of middlewares.
4. [ ] Create an instance of the HTTP Kernel.
5. [ ] Detect the application environment.

#### 24. What does the following snippet do?
```php
use App\Services\Transistor;
use App\Services\PodcastParser;

$this->app->singleton(Transistor::class, function ($app) {
    return new Transistor($app->make(PodcastParser::class));
});
```

1. [ ] Binds the PodcastParser class to the container and will return a new instance on subsequent calls into the container.
2. [ ] Binds the Transistor class to the container and will return a new instance on subsequent calls into the container.
3. [ ] Binds the PodcastParser class to the container one time and will return the same instance on subsequent calls into the container.
4. [x] Binds the Transistor class to the container one time and will return the same instance on subsequent calls into the container.

#### 25. How do you bind an interface to an implementation?
1. [ ] `$this->app->instance($abstract, $concrete);`
2. [x] `$this->app->bind($abstract, $concrete);`
3. [ ] `$this->app->singleton($abstract, $concrete);`

#### 26. How do you bind an existing object instance to the container?
1. [ ] `$this->app->bind($abstract, $instance);`
2. [x] `$this->app->instance($abstract, $instance);`
3. [ ] `$this->app->transfer($abstract, $instance);`

#### 27. The service container can be used to bind primitive values to variables needed by your class.
1. [x] True
2. [ ] False

#### 28. You can only bind to the service container from inside a service provider.
1. [x] False
2. [ ] True

#### 29. Given the following code, what will be the expected behavior?
```php
$this->app->when(PhotoController::class)
    ->needs(Filesystem::class)
    ->give(function () {
      return Storage::disk('local');
    });
```
1. [ ] When the PhotoController resolves an instance of FileSystem, it will be given an instance of the s3 Storage disk.
2. [ ] When the FileSystem resolves an instance of PhotoController, it will be given an instance of the s3 Storage disk.
3. [ ] When the FileSystem resolves an instance of PhotoController, it will be given an instance of the local Storage disk.
4. [x] When the PhotoController resolves an instance of FileSystem, it will be given an instance of the local Storage disk.

#### 30. Within a service provider, what do you always have access to?
1. [ ] $this->application
2. [x] $this->app
3. [ ] $this->provider
4. [ ] $this->service

#### 31. What is the service container responsible for?
1. [ ] Creates the HTTP session.
2. [x] Managing class dependencies and performing dependency injection.
3. [ ] Registering service providers.
4. [ ] Passes your requests through the global stack of route middleware.

#### 32. What method do you use to resolve an instance from the container?
1. [x] make
2. [ ] construct
3. [ ] create
4. [ ] instantiate

#### 33. What config file has a list of the applications service providers?
1. [ ] providers.php
2. [ ] configs.php
3. [x] app.php
4. [ ] services.php

#### 34. What sort of things are registered by service providers? (Select all that apply)
1. [x] Routes
2. [x] Event Listeners
3. [x] Middleware
4. [x] Service Container Bindings

#### 35. When a service provider is not loaded on every request, but only when the services they provide are actually needed, it is called a ______ provider.
1. [ ] Temporary
2. [ ] Stalled
3. [x] Deferred
4. [ ] Background

#### 36. What should you do in the register method of your service providers?
1. [ ] Register event listeners.
2. [x] Bind things to the service container.
3. [ ] Register routes.

#### 37. If we need to register a view composer, which method of the service provider would we use?
1. [x] Boot
2. [ ] Register

#### 38. It's good practice to inject your facades into the constructors of the classes that will be using them.
1. [ ] False
2. [x] True

#### 39. You can't mock or stub a Facade for testing.
1. [x] False
2. [ ] True

#### 40. The Facade base class makes use of the ________ magic-method to defer calls from your facade to an object resolved from the container.
1. [ ] __wakeup()
2. [ ] __call()
3. [ ] __invoke()
4. [x] __callStatic()

#### 41. Laravel _____ serve as "static proxies" to underlying classes in the service container.
1. [x] Facades
2. [ ] Middleware
3. [ ] Service Providers
4. [ ] Responses

#### 42. When a middleware needs to do some work after the HTTP response has already been sent to the browser, it is called:
1. [ ] Finalable
2. [ ] Lazyable
3. [x] Terminable
4. [ ] Laterable

#### 43. Which one of the following middleware assignments to routes is incorrect?
1. [x]
    ```php
    Route::get('/profile', function () {
        //
    })->setMiddleware('auth');
    ```
2. [ ]
    ```php
    Route::get('/profile', function () {
        //
    })->middleware('auth');
    ```
3. [ ]
    ```php
    Route::get('/profile', function () {
        //
    })->middleware(EnsureTokenIsValid::class);
    ```
4. [ ]
    ```php
    Route::get('/', function () {
        //
    })->middleware(['first', 'second']);
    ```

#### 44. Which of the following is not a correct use of middleware parameters:
1. [x]
    ```php
    Route::put('/post/{id}', function ($id) {
        //
    })->middleware('role<editor>');
    ```
2. [ ]
    ```php
    Route::put('/post/{id}', function ($id) {
        //
    })->middleware('role:editor');
    ```
3. [ ]
    ```php
    Route::put('/post/{id}', function ($id) {
        //
    })->middleware('role:editor,permission:view');
    ```

#### 45. Middleware listed in the `$middleware` property of the HTTP Kernel gets run during every HTTP request.
1. [x] True
2. [ ] False

#### 46. Laravel lets you specify which middleware have priority over others.
1. [x] True
2. [ ] False

#### 47. Out of the box, the web and api middleware groups are automatically applied to your application's corresponding `routes/web.php` and `routes/api.php` files by the `App\Providers\RouteServiceProvider`.

1. [x] True
2. [ ] False

#### 48. The `withoutMiddleware()` method can only remove route middleware and does not apply to global middleware.
```php
Route::get('/profile', function () {
    //
})->withoutMiddleware([EnsureTokenIsValid::class]);
```

1. [ ] False
2. [x] True


#### 49. What route does the following scoped implicit model binding resource create?
```php
Route::resource('photos.comments', PhotoCommentController::class)->scoped([
    'comment' => 'slug',
]);
```
1. [x] /photos/{photo}/comments/{comment:slug}
2. [ ] /photos/{photo:slug}/comments/{comment}
3. [ ] /photos/{photo}/comments/{comment}/slug
4. [ ] /photo/{photo}/comment/{comment:slug}

#### 50. What would be the edit route for the following shallowly nested resource?
1. [ ] /photos/comments/{comment}/edit
2. [ ] /photos/{photo}/comments/{comment}/edit
3. [ ] /comment/{comment}/edit
4. [x] /comments/{comment}/edit

#### 51. If you need to add additional routes to a resource controller beyond the default set of resource routes, you should define those routes ______ your call to the Route::resource method.
1. [x] Before
2. [ ] After

#### 52. If you wanted to dedicate a controller to a single action, which PHP magic method would you use?
1. [ ] __wakeup
2. [x] __invoke
3. [ ] __construct
4. [ ] __clone

#### 53. A controller has to extend the BaseController.
1. [ ] True
2. [x] False

#### 54. What would the following middleware do in this controllers constructor?
```php
public function __construct()
{
    $this->middleware('auth');
    $this->middleware('log')->only('index');
    $this->middleware('subscribed')->except('store');
}
```

1. [ ] Nothing, you can't set middleware from a controllers constructor.
2. [x] Apply the auth middleware to all methods, Apply the log middleware only to the index method, Apply the subscribed middleware to all methods except the store method.
3. [ ] Apply the log middleware only to the index method, Apply the subscribed middleware to all methods except the store method.
4. [ ] Apply the auth middleware to all methods, Apply the log middleware to all methods except the index method, Apply the subscribed middleware to only the store method.

#### 55. Using resource controllers, what HTTP response will be generated if an implicitly bound resource model is not found?
1. [ ] 302
2. [ ] 301
3. [ ] 403
4. [x] 404

#### 56. When registering routes for single action controllers, you do not need to specify a controller method.
1. [ ] False
2. [x] True

#### 57. When using dependency injection in controller methods, if you have dependencies and route parameters, you should list your dependencies ______ your route parameters.
1. [x] Before
2. [ ] After

#### 58. If your validation field name contains a literal period, you can explicitly prevent this from being interpreted as "dot" syntax by escaping the period with a backslash:
```php
$request->validate([
    'title' => 'required|unique:posts|max:255',
    'v1\.0' => 'required',
]);
```
1. [ ] False
2. [x] True

#### 59. The field under validation must have a matching field of {field}_XXXXXXX. For example, if the field under validation is password, a matching password_XXXXXXX field must be present in the input.
1. [ ] match
2. [ ] confirmed
3. [ ] validated
4. [x] confirmation

#### 60. What does the `nullable` validation rule do?
1. [x] The field under validation may be null.
2. [ ] The field under validation must be null.
3. [ ] The field under validation should not be null.

#### 61. You can access the currently authenticated user inside a Form Requests `authorize` method using the `$this->user` property.
1. [ ] True
2. [x] False

#### 62. Select all the options that would allow the `Boolean` validation rule to pass:

1. [x] 0
2. [x] "0"
3. [x] 1
4. [x] true
5. [ ] "true"
6. [x] false
7. [ ] "false"
8. [x] "1"

#### 63. If validation does not pass, you must manually pass the old input back to your view.
1. [ ] True
2. [x] False

#### 64. If the authorize method of a Form Request class returns false, an HTTP response with a ___ status code will automatically be returned and your controller method will not execute.
1. [ ] 500
2. [ ] 401
3. [ ] 404
4. [x] 403

#### 65. Using the `required` validation method, a field is considered "empty" if one of the following conditions are true:
1. [x] The value is an empty string.
2. [ ] The value is false or 0.
3. [x] The value is an uploaded file with no path.
4. [x] The value is null.
5. [x] The value is an empty array or empty Countable object.

#### 66. If you need to prepare or sanitize any data from a Form Request before you apply your validation rules, you may use the _______ method.
1. [ ] bootValidation
2. [ ] registerValidation
3. [x] prepareForValidation
4. [ ] readyValidation
