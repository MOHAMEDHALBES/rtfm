# Troubleshooting of app installations on appdb

## Common errors
- If you see "**internet connection is required to verify this app**" and app is not launching, and you are using publicly available free certificate, congratulations, Apple has blacklisted your device from running apps signed by current certificate. **You can try to change to another free available certificate (if any) at [features configuration page](https://appdb.to/my/configure), remove and install app again. If not, then the only way for you is to switch to your own or P2P-shared developer account.**

- If you see this while using **your own or P2P-shared developer account**, try to reboot your device. If it doesn't help, go to [Apple Developer Website](https://developer.apple.com/account/) and accept all pending agreements (or ask account owner to do it, their contact can be found on [PLUS status page](https://appdb.to/my/plus)).

- If app is installed, but you see "**developer mode is required**" popup when you try to launch it, go to Settings->Privacy & Security, scroll down to Developer mode and enable it. Device will be rebooted and apps will start to work.

## Other errors

If app is not opening, can not be installed or does not appear on your screen at all, please refer to this manual:

After you have tapped INSTALL button, tap Cancel on popup to go to [device status page](https://appdb.to/my/status) to check what's going on. Then, check the following symptoms:

- If you see "app is installed from another source" or "remove app icon and try again" error on appdb - tap "fix" on device status page and then tap "retry" on app installation command.

- If all commands are stuck in "new" state on device status page or device name is *null (null)*, or if you have used tools that are using MDC exploit or/and manually supervised your devices, *congratulations*, now security of your device is broken and secure app delivery protocol that appdb is using is broken as well. Restore your device to make it to work.

## Issues prior to app download to device
- Check that you have correct active device at your devices page.
- Try to clear command queue and install app again while **keeping your device awake and unlocked**.
- If you recently restored your device from iTunes/Finder or iCloud backup, visit [device status page](https://appdb.to/my/status) and reinstall your profile by tapping "Update profile" to let appdb know your fresh tokens issued by Apple.
- Try to reboot your device or reconnect to WiFi network or toggle airplane mode.
- Check internet connection on your device, you may be behind a proxy and your device can't contact apple servers and/or appdb. Direct connection is required.
- If you see "Device can not verify installation data (possible connection issue on device)" - make sure that you are not connected to internet via proxy. Apple (as well as appdb) requires devices to verify every installation request, and direct internet connection is required. If you connected to internet directly, feel free to send us logs to diagnose this issue.
- If you have something like this "Every time I try to install an app my phone keeps telling me device not linked, but it is linked" - Go to Settings->Safari and clear browsing data, then tap on appdb icon on your Home Screen.
- If everything here looks okay, and you see installation popup on your device, switch over to device itself:

## Issues after downloading of app to device

If you see "unable to download at this time", "app integrity can not be verified" error, or app stays grey or dimmed, or with cloud icon near name after installation, on your device, check the following:

1. Remove this app, it needs to be reinstalled.
2. Check type of sideloading that you are using, tap on Selected Device on appdb and see "Sideloading with..." written under device name.
3. If you are using free certificate without your personal developer account, your device may be blacklisted by Apple and you can no longer use this certificate. Switch to stable sideloading method. If you are using 3rd party certificate, check that it is not revoked. If you are using your own developer account or P2P-shared developer account, it is something unusual, create ticket in Helpdesk on [PLUS status page](https://appdb.to/my/plus).
4. If you are installing app after revocation, you need to remove old app and install new again (**not just reinstall it**). You can do it for all apps just with one tap from [IPA cache page](https://appdb.to/my/ipa-cache).
5. If you're installing an enhanced app or combining app enhancement and app, read app description and check if you have removed the original app (some enhanced apps can not be installed alongside with original ones).

If nothing helps, create ticket in support desk (link can be found on [PLUS status page](https://appdb.to/my/plus)) and provide email that you used to link your device and logs from your device (you should trigger sysdiagnose right after "unable to install at this time" popup appeared).

If app was successfully installed to your device, but still crashing, check that you disabled everything in advanced usage zone on [device features configuration page](https://appdb.to/my/configure), remove app and install it again.

Please note that user-contributed apps are not tested by appdb or developers and may be faulty or crash. In this case, please use apps that are published on appdb officially.

Useful links: [How to submit iOS device logs to appdb](/troubleshooting/logs-submission.md).

Last updated 3 Mar 2024.
