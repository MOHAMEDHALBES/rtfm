# Redirect websites to your apps


## Identifier

```deep_linking```


## Overall

apps that are installed via appdb support deep linking.


## Requirements

Configured associated URIs of your appdb app identifier in [appdb Publisher Area](https://publisher.appdb.to/apps/identifiers).

Associated URIs configuration is not being delivered via OTA, so it will be effective only with app update or reinstallation.

## Design

If customers want to redirect specific website to your app via deep linking, they need to enable plugin in Safari settings of the device.

You can invoke window with instructions how to do it by calling ```askCustomerToEnableOpenIn``` method of [appdb services framework](#).

Once enabled, when visiting associated URIs pattern, Safari will ask customer to open website in your app.

If action is approved, a redirection of ://deeplink=URI happens to your app.

You need to parse URI by usage of this [documentation](https://developer.apple.com/documentation/xcode/defining-a-custom-url-scheme-for-your-app)

## Drawbacks

Only Safari browser is supported, as there are no plugins available for any other browsers on mobile Apple-branded operating systems.

Last updated 19 Apr 2024.
