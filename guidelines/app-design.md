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


