# Easy certificate linking to appdb

Until Apple Inc allows developers to sign apps by themselves without limitations or/and until our interoperability request will be fulfilled, we offer apple developer certificate providers to implement
easy linking of certificates to appdb.

## Preparation

1. Create [appdb publisher ID](https://publisherid.appdb.to/auth?authAppID=staff_area).
2. Navigate to appdb+certificate program and integration panel in [appdb staff area](https://a.appdb.to/acp.php?action=pluscerts).
3. Create a website, fill in required details, then proceed to integration itself and testing.

## Integration flow

![Integration flow](img.png)

## Credentials linking process

Upon user tapping on easy credentials linking button, he will be redirected to providers URL with these GET parameters:

1. ```udid``` (string) - device UDID.
2. ```model```  (string) - device model identifier (e.g. iPhone 10,4).
3. ```email``` (string) - user email.
4. ```at``` (string) - parameter (encrypted action ticket for appdb API).
5. ```returnto``` (string) - to return user to this URL after flow is complete.
6. ```is_plus``` (int) - does PLUS activation required by user or not (1 if yes, 0 if not).

Then credential provider must request ***[configure](https://api.dbservices.to/v1.7/spec/#/partner/post_configure_)*** API method with defined parameters.

Upon receiving success, redirect user back to ***returnto***.

## Listing on frontpage

If you want to sell appdb+certificate bundles and your website to be listed on the [installation method configuration manual frontpage](https://appdb.to/my/buy), after you have completed all tests, click on “Activate front page” and buy PLUS activations. After this, we will enable your website on the front page. You need to top-up PLUS activations from time to time to be continued to be listed on the front page.

If you do not want to do this, this is totally fine, then you can do your own business and be listed on [device features configuration page](https://appdb.to/my/configure), without any limitations or payments, so you users can enjoy access to app installations from appdb.

Last updated 14 May 2024.
