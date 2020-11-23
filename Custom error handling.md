Custom error handling
=====================

If you want to log errors to an application monitoring system, you can use a custom error handler.

Register this in `public/index.php` before you cann the `kuusamo` function.

    Kuusamo\Vle\Exception\ErrorHandler::register(function($exception) {
        var_dump($exception->getMessage());
    });

Foe example, lets say you wanted to integrate Rollbar. Install the Rollbar library using Composer and then add the following to your `index.php` file.

    Rollbar\Rollbar::init([
        'access_token' => 'your_access_token',
        'environment' => 'production',
    ]);

    Kuusamo\Vle\Exception\ErrorHandler::register(function($exception) {
        Rollbar\Rollbar::report_exception($exception);
    });

Note that custom error handlers will only run when the project is in `production` mode. During development, the exception is presented to the developer.
