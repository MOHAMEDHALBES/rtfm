# Sending Push notifications to customers and devices

## Identifier

```push```

## Overall

appdb Push notification service allows you to send push notifications to your customers or/and to specific devices of your customers.

## Prerequisites

You need to:

- [Register your app identifier](https://publisher.appdb.to/apps/identifiers).
- [Upload your IPA package](https://publisher.appdb.to/apps/binary-packages).
- Assign IPA package to an app.
- [Create token of Push type](https://publisher.appdb.to/developer/tokens) with your app identifier.
- Optionally, add UDID of your device to [list of test devices](https://publisher.appdb.to/developer/test-devices), if you want to test or debug Pushes.
- Install app to your device and call ```registerPushNotifications``` method of [appdb services framework](#), so device token will be assigned and saved.

## Sending of Push notifications

Upon completing of Prerequisites, you can use [appdb push relay service](https://pushrelay.dbservices.to/v1.0/spec/) documentation to send push notifications to devices. You can get scoped tokenized persistent customer and device identifiers in your app by calling ```getPersistentCustomerIdentifier``` and ```getPersistentDeviceIdentifier``` methods of [appdb services framework](#).
Push notifications payloads are compatible with [Apple's defined schema](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).
We have created PHP library to send push notifications, you can find it on [Github](https://github.com/appdb-official/php-push-sender).

## Drawbacks

At the moment Apple has not implemented interoperability with our own push notification service, so your push notifications will be relayed to Apple systems.
Apple systems does not have differentiation of customers and their devices. As we are trying our best to ensure that routing works successfully on device level, we can not guarantee it 100% till interoperability will be effective, so some of your device-specific notifications may still be delivered to customer level instead of device level.

Notifications for alongside-installed applications will be delivered to all copies of an app, if multiple copies exist on customer device.

Last updated 11 Apr 2024.
