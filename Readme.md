# Thelia Hybrid Auth

This module allows users to connect and register with social networks such as Facebook, Google, LinkedIn ...

## Installation

### Manually

* Copy the module into ```<thelia_root>/local/modules/``` directory and be sure that the name of the module is TheliaHybridAuth.
* Activate it in your thelia administration panel

### Composer

Add it in your main thelia composer.json file

```
composer require thelia/thelia-hybrid-auth-module:~1.0.0
```

## Usage

First of all, to enable a provider, you need to create an app on the provider website.
See the links on the list below (for more information, contact the provider)

Then configure your module in modules, TheliaHybridAuth, configuration.

You need to enter the id and secret of your app in your module configuration. Use the edit button to do so.

It is then strongly advised to test the connection before to enable your provider (with the test button). Your website will try to connect you to the provider, you may be redirected to the provider website and have to authenticate.

If the test fail, you likely have type a wrong id/secret or haven't enable your website on the provider app configuration.

A default list of providers is available :

* OpenID
* Google
* Facebook
* Twitter
* Yahoo
* LinkedIn
* Foursquare

But you can add any other provider that are in the following list :

* Windows Live
* GitHub
* LastFM
* Vimeo
* Identica
* Tumblr
* Goodreads
* QQ
* Sina
* Murmur
* Pixnet
* Plurk
* Skyrock
* Geni
* FamilySearch
* MyHeritage
* 500px
* Vkontakte
* Mail.ru
* Yandex
* Odnoklassniki
* Instagram
* Twitch.tv
* Steam Community
* Dribbble


## Loop

[providers.list]

### Input arguments

|Argument |Description |
|---      |--- |
|enabled | A boolean value. If set to true, return only activated providers, if set to false, return only non active providers, if set to \*, return all providers.  <br/><br/> __default__ : true  <br/><br/> example : *enabled="\*"* |
|customer_id | An int value. Allows to get the providers associated with this customer id. |
|exclude | A string containing all the providers you want to exclude from the loop.  <br/><br/> example : _exclude="Facebook,Twitter,AOL"_|

### Output arguments

|Variable   |Description |
|---        |--- |
|$NAME    | the name of the Provider |
|$ENABLED | boolean value. true if the provider is enabled, false else |
