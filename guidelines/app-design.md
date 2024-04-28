# App publication guidelines

All apps that are published on appdb must comply with effective terms of free (or paid) app publication agreement that is signed by officially recognised developer prior to app publication.

We believe that you will duly test your apps before apps release on our platform. Please make sure that your app is bug-free, doesn't harm user experience.

## Additional app design requirements

Upon first launch app must show developer identification information interface, invoked with ```showDeveloperInformation``` method of appdb services framework, so your customers will know who is developer of an app and where they can get support.

## Requirements for apps with 3rd party payment options

If app is using 3rd party payment methods (not provided by appdb), prior to showing payment interface or user commitment to purchase, this information must be shown:

1) A notice that developer itself (not appdb) is responsible for paid functionality, support, refunds and chargebacks.
2) A valid link to support email or service of developer.
3) A clearly visible link to terms of paid features and a checkbox or other design element (by default - unchecked) that requires user interaction in order to commit their wish to purchase paid feature.

After purchase, users need to be able, inside app, or via link from app to external system:

1) Submit a complaint regarding functionality of paid features.
2) See history of their purchases.
3) Request refunds for non-working paid features.

## Requirements for apps with advertising

Before enabling of showing of ads, you need to get explicit consent of user to (usually it is included in frameworks and libraries of popular ad networks):

- Collect their identifiers to show personalised ads.
- DO NOT collect their identifiers and show them non-personalised ads.

## Mimic apps and functions

Apps that are pretend to mimic functionality, e.g. mimicking of GPS location, must explicitly state in their description that displayed data is not real.
Before mimicking any functionality, app must show message to users that requires their explict acknowledgement in order to continue to engaging of such functions.  

## Interference with Apple services

Apps must not interfere with Apple services. If you plan to publish an app on appdb, do not use services that require Apple servers interaction.

Example of services that you can not use:

1) Apple sign in.
2) Apple Maps.
3) iCloud Keychain.
4) Apple app attestation APIs

What you can use:

1) Your own or any other social sign in methods.
2) Google Maps.
3) Local on-device persistent keychain.
4) appdb app attestation APIs


