## Step 1 
In the first step, a Laravel project is created

    composer create-project laravel/laravel:^8.0 paypal
## Step 2 
Download this package in your project
[Laravel PayPal - Documentation (srmklive.github.io)](https://srmklive.github.io/laravel-paypal/docs.html)

    composer require srmklive/paypal: ~1.0

## Step 3 

Add this path inside a file /config/**app.php**   


 

      
    'providers' => [ *********  
    
	    Srmklive\PayPal\Providers\PayPalServiceProvider::class,
					   ]

## Step 4
create PayPalController

    php artisan make:controller PayPalController
You can review the [functions](https://github.com/mohamedadel80080/PayPal-Payment-App/blob/master/app/Http/Controllers/PayPalController.php) of the project from here    

## Step 5 
create Route

    Route::get('payment',[PayPalController::class,'payment'])->name ('payment');
    
    Route::get('cancel',[PayPalController::class,'cancel'])->name ('payment.cancel');
    
    Route::get('payment/success', [PayPalController::class, 'success'])->name('payment.success');


## Step 6
Create account on [PayPal](https://www.paypal.com/) 
After create account PayPal go to 

-   [My Apps & Credentials](https://developer.paypal.com/dashboard/applications/sandbox)
create App
- After create app go to   [Accounts](https://developer.paypal.com/dashboard/accounts)
- Go to your business account and click on View/Edit account
- Choose API Credentials
## Step 7 
go to `.env` add
 

  

    PAYPAL_MODE=sandbox
    PAYPAL_SANDBOX_API_USERNAME=
    PAYPAL_SANDBOX_API_PASSWORD=
    PAYPAL_SANDBOX_API_SECRET=
    PAYPAL_CURRENCY=USD
    PAYPAL_SANDBOX_API_CERTIFICATE=

and add Your account information from API Credentials PayPal
