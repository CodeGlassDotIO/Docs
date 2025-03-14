---
title: View - Splashscreen
description: The splashscreen with login.
---
# Splashscreen
![assets/img/splashscreen/Splashscreen.png](../../assets/img/Splashscreen/Splashscreen.png)

This is the loading screen of CodeGlass, it shows you the current loading status of the application, and if something goes wrong a error code.  
After load it will go to the [login screen](#login) or [main menu](mainwindow.md) if you have logged in before. 

# Login
![assets/img/splashscreen/SplashscreenLogin.png](../../assets/img/Splashscreen/SplashscreenLogin.png)

Here you can login into CodeGlass with your [CodeGlass account](../Others/Account.md#licensespring-codeglass-account) to get access to CodeGlass.

After a successful login you go to the [main menu](mainwindow.md).

CodeGlass will remember your login next time you start so you will skip the login screen, to log out press [logout](../views/mainwindow/application.md) on the main menu.

# Information Screens
You might see a few information screens before or after login, they can be one of the following:


## Maximum Activations
![assets/img/splashscreen/SplashScreen_ToManActivations.png](../../assets/img/Splashscreen/SplashScreen_ToManActivations.png)

You get this screen when you activated your subscription on too many devices, for a more detailed explanation to deactivate a device, click [here](../Others/CodeGlassLicensePortal.md#deactivate-devices)


## Hub Version Mismatch
![assets/img/splashscreen/SplashScreen_HubVersionMismatch.png](../../assets/img/Splashscreen/SplashScreen_HubVersionMismatch.png)

You get this screen when your [client](../features/CodeGlassClient.md) is running a different version than the local [hub](../features/CodeGlassHub.md) you are connecting to.<br/>
It will also show which versions both are running.



## Remote Hub Version Mismatch
![assets/img/splashscreen/SplashScreen_RemoteHubVersionMismatch.png](../../assets/img/Splashscreen/SplashScreen_RemoteHubVersionMismatch.png)

You get this screen when your [client](../features/CodeGlassClient.md) is running a different version than the [remote Hub](../features/CodeGlassHub.md#remote) you are connecting to.<br/>
It will also show which versions both are running.


## Version End of Life (EOL)
![assets/img/splashscreen/SplashScreen_HubEOL.png](../../assets/img/Splashscreen/SplashScreen_HubEOL.png)

You get this screen when the version the hub is running is end-of-life (EOL); you should rarely or never see this screen.
We are not planning to make versions EOL. It is just a safety precaution for builds containing a major issue.
You might even see this more often on versions that are just released than versions that are years old.

We still have never made a version that is EOL.



## Failed To Validate Subscription
![assets/img/splashscreen/SplashScreen_FailedToValidateSubscription.png](../../assets/img/Splashscreen/SplashScreen_FailedToValidateSubscription.png)

You get this screen when we cannot validate your license for any reason. You can continue using the application, but you are locked to [Trail Edition](../Editions/Trail.md) Features only.

## Subscription Expired
![assets/img/splashscreen/SplashScreen_SubscriptionExpired.png](../../assets/img/Splashscreen/SplashScreen_SubscriptionExpired.png)

You get this screen when your subscription is expired. Click [here](../Others/ChangeSubscription.md) to change your subscription.

## Experimental Required
![assets/img/splashscreen/SplashScreen_ExperimentalRequired.png](../../assets/img/Splashscreen/SplashScreen_ExperimentalRequired.png)


You should never see this screen when starting the [client](../features/CodeGlassClient.md). <br/>
Only on infrequent occasions get it when starting the [profiler](../features/CodeGlassProfilers.md), and the client did not catch earlier that you are trying to start a [runtime](../features/supportedruntimes.md) only available to the [experimental edition](../Editions/Experimental.md).

It will also always display a reason for showing this screen.



## Upgrade To Experimental Edition
![assets/img/splashscreen/SplashScreen_UpdageExperimental.png](../../assets/img/Splashscreen/SplashScreen_UpdageExperimental.png)

You get this screen when clicking "Upgrade" on the [Experimental Edition Required](#experimental-required) Info Screen. <br/>
A browser will have opened on the [Change Subscription](../Others/ChangeSubscription.md) Page that will help you through upgrading your subscription.

When you click "Continue", it will check if your subscription has upgraded and continue if it has. If the upgrade were insufficient, it would show the [Experimental Upgrade not finished](../views/Dialogs.md#upgrade-to-experimental-edition-not-finished) dialog.


## Inception
![assets/img/splashscreen/SplashScreen_Inception.png](../../assets/img/Splashscreen/SplashScreen_Inception.png)

You will get this screen when you try to profile CodeGlass with CodeGlass.

# Application Breadcrumb:
This is the root of the application, the first view you see when you start the [CodeGlass Client](../features/CodeGlassClient.md)


# See Also:
- [View - Main Menu](mainwindow.md)

