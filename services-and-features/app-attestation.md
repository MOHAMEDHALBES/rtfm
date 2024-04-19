# Attest your apps and data inside them


## Identifier

```app_attestation```


## Overall

appdb App Attestation service allows you to ensure your app integrity and make assertions on data that app is trying to send to your server.

## Design

App attestation for the first time creates unique key that may be used in future to ensure that app was not changed and data that is sent from an app is genuine.
appdb automatically manages key validation, extraction and storage during app attestation and then provides all information to you, so you can verify attestation on your behalf and then verify assertions of data in your app.

## Flow

### Initial configuration

1) Generate random challenge for initial attestation on your server.
2) Use this challenge to generate and register app attestation in your app via ```registerAppAttesation``` method of appdb services framework. You need to do it on every app reinstallation, except normal updates.
3) Notify your server about successful attestation for given app and installation UUID.
4) On your server, get attestation results and private key from [appdb Attestation Service getAttestationData method](https://attestrelay.dbservices.to/v1.0/spec/). 
5) Store these results on your server, you will need them in the future.

### Continuous usage

If you need to verify some data inside your app, e.g. payload of API request, do the following:

1) Use ```generateDataAssertion``` with your data to generate assertion object.
2) Pass it to your server alongside with the data; validate it and it's counter with Key that you obtained on Initial configuration stage. [Sample PHP code](https://github.com/appdb-official/php-app-attest-validator) to verify data assertion.
3) If it is valid, then request is coming from genuine copy of your app. Save counter to your database and wait for next assertion.


## Implementation

You need to:

- [Register your app identifier](https://publisher.appdb.to/apps/identifiers).
- [Upload your IPA package](https://publisher.appdb.to/apps/binary-packages).
- Assign IPA package to an app.
- [Create token of Attest Verification type](https://publisher.appdb.to/developer/tokens) with your app identifier.
- Create your own server to generate and send unique challenges to your app.
- Install app to your device and call ```registerAppAttestation``` method of [appdb services framework](#), so your app attestation will be registered on appdb.

## Verifying data assertions

Once ```registerAppAttestation``` returned true, you can use ```generateDataAssertion``` in your app to assert data. Send assertion alongside with the data to your server and verify it there.
[Sample PHP code](https://github.com/appdb-official/php-app-attest-validator) to verify data assertion.

## Drawbacks

At the moment Apple has not implemented interoperability for app attestation - there is no way for us to attest apps, as our framework works on app-level.
We have submitted interoperability request to Apple and waiting for implementation.
Only one Key with one ID may be assigned per installation UUID. So, upon reinstalling an app, make sure to update keys and attestation data by calling ```registerAppAttestation``` again.


Last updated 19 Apr 2024.
