# Backing and restoring app data

## Identifier

```backup```

## Overall

appdb backup service allows you to store your app data backup and retrieve it in case of app reinstallation.
This service is designed to store app configuration, e.g. ```NSUserDefaults```.
**It is not designed to store big files, e.g. chat history in messaging app or big blobs of user content.**

## Design

Consider this as key-value, or, for better understanding, key-JSON storage.

Every configuration that you want to store is being converted to JSON that will be stored on appdb servers.
Each configuration is scoped by an app and its uniqueness is defined by ```store key``` which represents sha256 hash of your backup key.

## Generating store keys

You are generating store keys on your own, making them unique in order to prevent bruteforce.

> Choose your unique ```salt``` that you will add to hash generation, so it can not be easily guessed!

- To generate store key for a customer, use ```sha256(salt+getPersistentCustomerIdentifier)``` [more information is here](/app-development/identifiers?id=persistent-customer-identifier) - such backup will be available in every version of an app for your customer.
- To generate store key for a customer for specific app version, use ```sha256(salt+getPersistentCustomerIdentifier+appVersion)``` such backup will be available in specific version of an app for your customer.
- To generate store key for customer device, use ```sha256(salt+getPersistentCustomerIdentifier+getPersistentDeviceIdentifier)``` [more information is here](/app-development/identifiers?id=persistent-device-identifier) - such backup will be available in every version of an app for specific device of a customer.
- To generate store key for customer device for specific app version, use ```sha256(salt+getPersistentCustomerIdentifier+getPersistentDeviceIdentifier+appVersion)``` - such backup will be available in specific version of an app for specific device of a customer.

These are only examples, what inputs will you use to generate backup store keys depends only on you.

You may combine these store keys, e.g. if you updated your app version and your data formats are incompatible, you may get backup from older store key, modify it, and save with store key for newer version.

**Do not store sensitive information (or at least encrypt it prior to storage) in such backups, as they are not E-to-E encrypted and accessible to anyone who knows store key.**

## Available operations

[appdb services SDK](https://github.com/appdb-official/AppdbSDK) provides these methods to operate KV backups:

```storeBackupAtKey(backupDict, key)```

Stores backup data at key.

```getBackupAtKey(key)```

Gets backup data at key.

```purgeBackupAtKey(key)```

Purges backup data at key.

## Drawbacks

At the moment we do not have backup retention policy, so **purging of backup data responsibility is on your side**. Later on, we will introduce it, so your app will be GDPR-compliant as well.

Last updated 25 Apr 2024.
