# Bagisto Razorpay Payment Gateway - Free Plugin
Razorpay is a popular payment gateway in India. This package provides strong support for users to integrate the Razorpay payment gateway into their Bagisto Laravel e-commerce applications.

## Compatibility Notice
**<span style="color:red;">Support Bagisto v2.3.4 and above</span>**

## Installation

1. Use the command prompt to install this package:
```bash
composer require violet-waves/bagisto-razorpay
```

2. Open `bootstrap/providers.php` and register the Razorpay provider by adding the following line to the array:
```php
return [
  // ... other providers ...

  // Razorpay provider
  VioletWaves\Razorpay\Providers\RazorpayServiceProvider::class,
];
```
3. Navigate to the `admin panel -> Configure/Payment Methods`, where Razorpay will be visible at the end of the payment method list.

4. Add the Razorpay payment gateway route to CSRF token validation exception list in `bootstrap/app.php` inside `withoutMiddleware(function (Middleware $middleware)` array:
```php
$middleware->validateCsrfTokens(except: [
   '/razorpaycheck',
]);
```

5. Clear the configuration cache:
```bash
php artisan config:cache
```

## Troubleshooting

1. If you encounter an issue where you are not redirected to the payment gateway after placing an order and receive a route error, navigate to `bootstrap/cache` and delete all cache files.
