##Customizing "Whoops, looks like something went wrong."

If you would like to replace that message with 500.blade.php file shipped with Josh, please follow below tutorial.

to do so, we should override ````convertExceptionToResponse```` method in ````app/Exceptions/Handler.php````

add below code into your ````app/Exceptions/Handler.php````

````php
    /**
     * Convert the given exception into a Response instance.
     *
     * @param \Exception $e
     *
     * @return \Symfony\Component\HttpFoundation\Response
     */
    protected function convertExceptionToResponse(Exception $e)
    {
        $debug = config('app.debug', false);

        if ($debug) {
            return (new SymfonyDisplayer($debug))->createResponse($e);
        }

        return response()->view('admin.500');
    }
````

[credits](http://crynobone.com/posts/9/customizing-the-default-error-page-on-laravel-5.1)
    