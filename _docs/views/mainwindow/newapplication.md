---
title: View - Main Menu - Add Applciation
description: How to add a new application to profile
---
# Add a new Application
![assets/img/mainwindow/AddApplication.png](../../../assets/img/MainMenu/AddApplication.png)


Currently we support 2 types of application:

- [File or Folde applications](#file-or-folder) you select by selecting the .exe / .Dll, folder, etc.
- [UWP](#uwp) (Universal Windows Applications) as these cant be selected by File or folder.

Select one by using the buttons in the top middle and follow the instructions in that section.

### File or folder
![assets/img/mainwindow/AddApplication_FileOrFolder.png](../../../assets/img/MainMenu/AddApplication_FileOrFolder.png)


{% include alertNoTitle.html type="info" content="The File or folder selector is actually an inlined Windows Explorer from windows (pritty neat right?)" %}
{% include alertNoTitle.html type="warning" content="The only disadvantage it has is that it just opens files when you double click them, so be aware of that (might be fixed in the future)" %}

To add a new application select the file or folder in the explorer like you are used to when using Windows Explorer (again, do not double click your application)
After selecting select the appropriate runtime. Only applicable runtimes will be enabled, you can see why a runtime is unselectable by hovering over the disabled runtimes.

Check [Feature - Supported runtimes](../../features/supportedruntimes.md) for more info and troubleshooting steps if you are unable to select a runtime. 

After selecting the runtime press "Add Application" button in the lower right and you will be brought to the [Application Instance](applicationInstance.md) of the added application


Take note of for .Net Core and .Net 5 it allows you to select a .Exe File, it will run the .DLL instead.

### UWP
{% include alert.html  type="warning" title="Not available to the Community edition yet" content="See  <a href=\"../../features/supportedruntimes#uwp\" target=\"_blanc\">Uwp Runtime support</a> for more information about this. " %}

![assets/img/mainwindow/AddApplication_UWP.png](../../../assets/img/MainMenu/AddApplication_UWP.png)
{% include alert.html  type="warning" title="Run as Administrator" content="Windows does not allow you to request installed UWP packages when you did not run Code Glass as Administrator. 
We will add a administrator request popup in the future but for now the only way around is restarting the client in Administrator mode (Right click on CodeGlass.exe and press Run as administrator)" %}



You can select an UWP package in the Middle right, after selecting a package you have to select the application in that package, as UWP packages can contain multiple apps.

After selecting the application select the "Universal Windows Platform" runtime and press on "Add Application" button on the bottom right.


Check [Feature - Supported runtimes - UWP](../../features/supportedruntimes.md#uwp) for more information and troubleshooting steps if you are unable to select the Universal Windows Platform Runtime and hovering over it does not give you an answer why.

# Application Breadcrumbs: 
- [Splashscreen](../Splashscreen.md) / [Main Menu - Applications](application.md) /

# See Also:
 - [Main Window ](../mainwindow.md)
 - [Applications Tab](application.md)
 - [Feature -Supported runtimes](../../features/supportedruntimes.md)
 - [Client and user settings](../clientusersettingswindow.md)
 - [External - .Net Native Toolchain](https://docs.microsoft.com/en-us/dotnet/framework/net-native/)

