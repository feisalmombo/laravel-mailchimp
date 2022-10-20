## Mailchimp Integration using Laravel

This application shows how to integrate mailchimp api in laravel.

Mailchimp provides manage subscribers, send emails using campaign and also track email results etc. Mailchimp through you can track how much subscribers open email and read. If you have newsletter website or any tutorial website then you should add email subscriber function that way we can inform through email.

 I use skovmand/mailchimp-laravel laravel package for mailchimp api in laravel 5.6 application. The following are some steps used to install this package


 ## Step 1: Create MailChimp Account Setting
 
 If you are from scratch, i mean if you don't have account then you can create new account from here : **[Create New Account](https://mailchimp.com/)**

 Ok, now you have to create new List, click on Lists on menu and create new list. After create successfully lists then select your list, got to settings->List name and defaults and copy your list id, we will use it on api.

Now we can get API Key so click here and get api key : **[API Key](https://us10.admin.mailchimp.com/account/api/)**

and Add the Audience Key/ List key : **[LIST ID](https://us10.admin.mailchimp.com/lists/settings/defaults)**

Open your .env file and paste here this way:

MAILCHIMP_API_KEY=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
MAILCHIMP_LIST_ID=xxxxxxxxxxxxxxx

## Step 2: Install Package

composer require skovmand/mailchimp-laravel

Now we need to add provider path and alias path in config/app.php file so open that file and add bellow code.

config/app.php

return [
	$provides => [
		Skovmand\Mailchimp\MailchimpServiceProvider::class,
	],
]


## Step 3: Add Form Collective Package

composer require "laravelcollective/html":"^5.6.0"

Next, add your new provider to the providers array of config/app.php:

  'providers' => [
    Collective\Html\HtmlServiceProvider::class,
  ],
Finally, add two class aliases to the aliases array of config/app.php:

  'aliases' => [
      'Form' => Collective\Html\FormFacade::class,
      'Html' => Collective\Html\HtmlFacade::class,
  ],
