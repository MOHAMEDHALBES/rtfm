# Identification of app, customer, device

[appdb services SDK](https://github.com/appdb-official/AppdbSDK) provides a way to identify app installation method, customers, devices and other identifiers.

## Requirements

In order to proceed with other methods and features, you need to call ```isInstalledViaAppdb``` method of a framework.

If it returns false, we encourage you to softly warn user about this fact and limit available app features. Please do not harm customer experience, as your app may be distributed via other channels, not via appdb only.

## Identifiers

### Persistent Customer identifier

This identifier represents customer of your app. It is a constant. You can get it via ```getPersistentCustomerIdentifier``` method of a framework.

**Customer identifier is an anonymous, scoped by app persistent identifier**, it means that per every app it is different, but persistent during app updates. It also means that even in two different apps from you, this identifier will be different.
This is done this way in order to prevent profiling.
Scope of this identifier is defined by appdb app identifier.

### Persistent Device identifier

This identifier represents customer device. It is a constant. You can get it via ```getPersistentDeviceIdentifier``` method of a framework.

**Device identifier is an anonymous, scoped by app persistent identifier**, it means that per every app it is different, but persistent during app updates. It also means that even in two different apps from you, this identifier will be different.
This is done this way in order to prevent profiling.
Scope of this identifier is defined by appdb app identifier.

### appdb app identifier

This identifier identifies app on appdb, it is a constant. You can get it via ```getAppdbAppIdentifier``` method of a framework.

### appdb installation UUID

This identifier identifies and app installation UUID. You can get it via ```getInstallationUUID``` method of a framework.

Installation UUIDs are persistent during reinstallation of an app of the same version (even if was removed from user device and then user installed the same version again).
UUIDs are changing if customer installs other version of app (newer or older), or installs app as alongside in order to have two or more copies of your app.

### appdb app alongside identifier

This identifier identifies copy of app that is installed to user device, it is a variable. You can get it via ```getAlonsideIdentifier``` method of a framework.
By default, it is ```""```, an empty string (app installed, no app copies exist on device). But if app is installed alongside (e.g. two or more copies of app exist on device), it may be up to 5 alphanumeric symbols.

### Apple bundle identifier

This identifier represents Apple bundle identifies, **it is a variable**, as it is assigned during app deployment to customer device You can get it via ```getAppleBundleIdentifier``` method of a framework.

Please adjust you code, so it will use this method to get bundle identifier, and make your PlugIns or bundled binaries relative to it. **Do not hard-code** Apple bundle identifier inside your app, as even upon removal and installation of your app from appdb it may change and may break your app logic, if you will hard-code it.

### Apple app group identifier

This identifier represents Apple app group identifier, that nested parts of your app communicate with each other, **it is a variable**, as it is assigned during app deployment to customer device You can get it via ```getAppleAppGroupIdentifier``` method of a framework.

Please adjust you code, so it will use this method to get app group identifier, and make your PlugIns or bundled binaries relative to it. **Do not hard-code** Apple app group identifier inside your app, as even upon removal and installation of your app from appdb it may change and may break your app logic, if you will hard-code it.

Please note that due to different installation methods, this identifier may not be supported, then you should adjust your app logic accordingly.

[Read more about Apple app group identifiers](/services-and-features/group-identifiers).

Last updated 19 Apr 2024.

