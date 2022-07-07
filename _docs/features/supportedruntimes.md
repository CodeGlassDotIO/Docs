---
title: Feature - Supported Runtimes
description: The runtimes we support in CodeGlass
---

# Runtime Support
At CodeGlass, we are striving to support as many languages as possible. Currently, we support .NET only but are currently working on a [new profiler](../Roadmap/NonDotNetProfiler.md) 

The requirement is for each runtime to run at least without CodeGlass on your machine.
Below are all our supported runtimes.

## .NET Framework
.NET Framework 4.0 and up

### Notes on .NET Framework 2.0-3.5
.NET Framework 2.0-3.5 is not officially supported but it might work in the __[experimental edition](../Editions/Experimental.md)__, take note of the following:

CodeGlass needs to be started as administrator as we need to add some registry keys.

These keys will be removed when:
- You close the client on the machine that registered them.
- You start the client in administrator mode on the machine that registered them.
- You uninstall Code Glass on the machine that registered them.


If, in the unlikely case, the registry keys stay behind, is the key to remove:

```
HKEY_CLASSES_ROOT\CLSID\{2091c114-505f-51b5-8145-5eee1ed82fe1}
```
It is an experimental edition only feature because it works on some of our machines, and on some, it does not. It looks like it is a Windows version issue. But since .Net Framework 2.0 - 3.5 are pretty old we decided to not invest more time in it.

Let us know if you need official support of .NET Framework 2.0-3.5; we can probably make it. <br/>

## .NET Core & .NET (5.0+)
- .NET Core 1.0 and up.
- .NET 5 and up.

## ASP.NET Framework
- ASP.NET for .NET Framework 4 and up.

### Requirements
- IIS Express needs to be installed, which can be done from the Code Glass Installer as an optional feature. 

### Known Issues
- If you have to make it work with IIS server installation, let us know; support can be made.

## ASP.NET Core 
.ASP.NET Core 1.0 And up.


### Known Issues
- Make sure that your appsettings.json and other configuration files are getting loaded. Some older ASP.NET Projects do not load them when starting with the dotnet CLI.
- The folder name must be the same as your built assembly ".dll."

## Any .NET

{% include alert.html  type="warning" title="Experimental Edition Feature" content="This feature is not user friendly and are unsure if we can make it ever user friendly due to limitations by Microsoft. Because of this, it is only available to the <a href=\"../Editions/Experimental\">Experimental Edition</a> till it is more user friendly." %}

This "runtime" works that if a program starts in a specified folder or subfolder and then requests the user if it wants to profile the application or not.
However, this also means that if you set it to, for example, 'C:\', it will ask you if you want to profile any application that starts on that drive!

### Known issues
- CodeGlass can set only one enabled folder currently; this limitation will be removed in the future
- The CodeGlass Client may state that the folder is enabled when restarting the client when it is not; this is due to the clearing of register keys (see [registery keys](#registery-keys) below). We will fix this before the release to the Pro version.
- If you close the client with the enabled folder, it will stop working (see [registery keys](#registery-keys) below)
- If you start the client with the enabled folder, it will stop working (see [registery keys](#registery-keys) below)
- It does not work for ASP.NET projects if the selected folder is not part of the path to your IIS Express installation folder. Because the running application is iisexpress and not your application.

#### Registery Keys
For this feature, we have to add some registry keys. To prevent it going all haywire, we do the following to clean them up:
- We remove them when you close the client on the machine with the active folder.
- We remove them when you start the client on the machine with the active folder if Code Glass was closed incorrectly.
- We remove them when you uninstall Code Glass on the machine with the active folder

If, in the unlikely case, the registry keys stay behind, these are the keys to remove:
```
HKEY_CURRENT_USER\Environment\clr_app_instance_config_base_file_path
HKEY_CURRENT_USER\Environment\clr_environment_active
HKEY_CURRENT_USER\Environment\cor_enable_profiling
HKEY_CURRENT_USER\Environment\cor_profiler
HKEY_CURRENT_USER\Environment\cor_profiler_path_32
HKEY_CURRENT_USER\Environment\cor_profiler_path_64
HKEY_CURRENT_USER\Environment\coreclr_enable_profiling
HKEY_CURRENT_USER\Environment\coreclr_profiler
HKEY_CURRENT_USER\Environment\coreclr_profiler_path_32
HKEY_CURRENT_USER\Environment\coreclr_profiler_path_64
```

## Visual Studio Solution
{% include alert.html  type="warning" title="Not available to the Community or Pro edition yet" content="This feature is very experimental, because of this only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}

The Visual studio "runtime" makes it possible to profile supported runtime applications while debugging them in Visual Studio. 

The supported runtimes are described in this document also.


### Requirements
- Devenv.exe is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md)
- Requires the build folder to be in the same or the subfolder of the solution
- ASP.NET Framework specific requirement: iisexpress.exe x86 path is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md) or enforce using x64 IIS Express in the Visual Studio Settings.


### Known issues
- Multiple startup projects might cause issues.
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) will apply when you reopen visual studio through CodeGlass, NOT when you restart the VS debugger.
- You get 'System.AccessViolationException: Attempted to read protected memory' from the VS Debugger. Try the following: Start once without debugging (CTRL+F5), rebuild the solution or reopen the solution through Code Glass, Restart your computer. We always manage to get rid of the message in testing after trying the above; let us know if you cant get rid of it.
- ASP.NET Framework specific issue: It might happen that it does not automatically open the web page. You have to open a browser yourself and go to the URL. If you do not know the URL, you can check IISExpress tray icon on the taskbar in the bottom right.
- ASP.NET Framework specific issue: [Code Glass Console](AttachConsole.md) input might not work; output always works. 

## UWP
{% include alert.html  type="warning" title="Not available to the Community edition yet" content="This feature has issues sometimes when launching an UWP application, previously it was only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a> but by request we released it to the <a href=\"../Editions/Pro\" target=\"_blanc\">Pro Edition</a>, work arounds are described below." %}

We are working on making it more stable and working on not explicitly needing not-elevated mode to start UWP applications.
When we solve all the issues, we will release this feature to the [Community Edition](../Editions/Community.md).

### Requirements
- Requires the app not to be compiled with the [.net native tool chain](https://docs.microsoft.com/en-us/dotnet/framework/net-native/) to be able to profile the application. If you know a way around this, please let us know.
- Needs Code Glass NOT to be started as administrator (not-elevated). <br/>
Microsoft does not allow UWP applications to start in elevated mode. Since Code Glass is started in the elevated mode, it can't start the application with lower permissions (not-elevated). 

### Known Issues
- Only able to profile applications that are built in Debug Mode.
- Needs Code Glass to be opened as administrator to [add UWP applications](../views/mainwindow/newapplication.md#uwp).
Microsoft does not allow us to query UWP applications without administrator rights. <br/>
- Needs Code Glass NOT to be started as administrator (not-elevated) to start a UWP application.<br/>
Microsoft does not allow UWP applications to start in elevated mode. Since Code Glass is started in the elevated mode, it can't start the application with lower permissions (not-elevated). 
- The application starts but is not visible on the foreground, please press ['Bring to front'](../views/ApplicationInstanceDockWindow/MenuBar.md#bring-to-front) button (multiple times), this might fix it.
- The application does not start anymore <br/>
Please check if it is not running in task manager and kill it if it is, ensure that it runs when you normally start it (sometimes after a while it doesn't anymore), restart the pc if necessary, and try again to start it with CodeGlass. <br/>
If the application also does not start anymore without CodeGlass even after you restart the PC, you need to rebuild it again to fix it.


## JavaScript Website
{% include alert.html  type="warning" title="Not available to the Community or Pro edition yet" content="This feature is very experimental, because of this only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}

{% include alert.html  type="warning" title="Do not use CodeGlass Browser for other use cases." content="The browser should be as safe as the Chromium browser, but for the sake of arguments, just assume it is not, so don't use it when you do not want to profile the website you visit." %}



The JavaScript website "runtime" makes it possible to profile websites built with Javascript; this includes Typescript and all frameworks built upon JavaScript, as they all compile to JavaScript.<br/>
It uses a custom version of the Chromium (read Chrome) browser made by us to make this possible.

It is currently in the early stages. Please check back when we release it to Pro and give it an a/another chance.




### Requirements
- CodeGlass Browser is installed by the seperated [CodeGlass Browser Installer](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases).
- CodeGlassBrowser.exe path is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md)

### Known Issues
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) will apply when you relaunch the browser through CodeGlass, NOT when you reload the page or use another tab.
- The browser always opens in a new window instead of another tab.
- We currently do not update and build the browser for each CodeGlass update with the latest Chromium changes as it takes a lot of time (read hours); because of this, the browser might not have the latest changes of Chromium.
- When launching the CodeGlass Browser through the CodeGlass client, you decide under which [application](../views/mainwindow/applicationInstance.md) (instance) the browser will put the profiled data. It is unaware if you leave the specified website and will keep putting the other website's data in the same application in CodeGlass. Keep this in mind when reading statistics and such.

## Limitations
- A new [Application Instance](../views/mainwindow/applicationInstance.md) is made for every separated javascript process that starts in the CodeGlass browser (Like every tab)


# See Also:
 - [View - Add new Application](../views/mainwindow/newapplication.md)
 - [View - Client settings](../views/clientusersettingswindow/ClientSettings.md)
 - [Roadmap - Non .NET Profiler](../Roadmap/NonDotNetProfiler.md)