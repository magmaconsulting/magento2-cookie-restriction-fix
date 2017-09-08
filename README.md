# Magento 2 Cookie Restriction Fix

In order to comply with European Cookie Law we have to enable Magento Cookie Restriction Mode.

By enabling Cookie Restriction Mode Magento 2.1.x does not show Google Analytics Tracking code even if user allow cookies.

This is due to bug #5596 (<https://github.com/magento/magento2/issues/5596>) affecting magento 2.1.x versions.

This modules fix the issue and enable Google Analytics if user gives consent.

Not only Magento Google Analytics module benefits from this fix, but also every module using the standard Magento module Cookie.

## Installation

Install module:

```bash
composer config repositories.magento2-cookie-restriction-fix git https://github.com/magma/magento2-cookie-restriction-fix.git
composer require magma/magento2-cookie-restriction-fix
```

Enable module:

```bash
./bin/magento setup:upgrade
```


## Cookie Restriciton Mode and third-party modules

In order to comply with Cookie Law every third-party module should block tracking cookies unless the user accepts to save them.

Standard Magento Module Cookie Restriction Mode is meant to do so.

Third party developers can use this mechanism by checking the condition `isUserNotAllowSaveCookie` provided by the module Magento_Cookie.

## Compatibility

Tested on Magento 2.1.8.
It should work on older Magento 2.1.x versions.

## Suggested modules

* [Fooman Google Analytics + (Magento 2)](https://marketplace.magento.com/fooman-googleanalyticsplus-m2.html)
