# Apple app groups support

## Identifier

```apple_app_groups```

## Overall

Until interoperability in software is available, appdb configures an app with support of one Apple app group, so nested parts of your app may communicate with each other.

## Drawbacks

Not all installation methods support app groups. To get assigned app groups, use ```getAppleAppGroupIdentifier``` method of [appdb sevices framework](#).

If it does not return app group, then this feature is not supported and you should adjust your app logic.

Last updated 19 Apr 2024.
