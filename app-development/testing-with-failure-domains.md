# Testing of an app with usage of failure domains

## How to add test device
Once IPA is attached to your app identifier in [Publisher Area](https://publisher.appdb.to/) of appdb, you
can assign test devices to install app to them and test various features prior app listing in the Store.

appdb has no separate testing environment, but production environment may behave differently for selected devices
based on **failure domains** that you will assign to these devices.

To get started with assignation of test devices, visit [test devices screen of Publisher Area](https://publisher.appdb.to/developer/test-devices).

To add test device, click "Add new test device".

Enter your device UDID. To get it from your device, visit [this link](https://dbservices.to/get-udid/).

And assign failure domain to your device.

## Failure domains description

```ok```

Assigning device to this domain will allow you to view app information in the Store and install version of your app that allows debugger attachment to this device.

```failure_payment```

Alongside with effect of ```ok``` domain, any payment on this device will fail.

```10_min_subscription```

Alongside with effect of ```ok``` domain, subscription length of in-app subscription on this device will be shortened to 10 minutes.

```10_min_failure_subscription_extension```

Alongside with effect of ```ok``` domain, subscription length of in-app subscription on this device will be shortened to 10 minutes and second (and future) payments for subscription will fail.

```no_fp_signing```

Alongside with effect of ```ok``` domain, [limited services and features](/services-and-features/overview) will be supported during app installation (check list of supported services inside app via ```getSupportedServicesIdentifiers``` method of [appdb services framework](#)).



