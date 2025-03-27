---
title: Feature - Supported Runtimes
description: The runtimes we support in CodeGlass
---

# Runtime Support
At CodeGlass, we are striving to support as many languages as possible. Currently we only fully support .NET, but we have a few other languages available in our [Experimental Edition](../Editions/Experimental.md). 

Languages that are only supported in our Experimental Edition are:
- [JavaScript for websites](#javascript-website)
- [Julia](#julia)
- [Java](#java)

On of our requirements is that each supported runtime needs to be runnable without having CodeGlass installed.

## .NET Framework
.NET Framework 4.0 and up

### Notes on .NET Framework 2.0-3.5
.NET Framework 2.0-3.5 is not officially supported but it might work in the __[Experimental Edition](../Editions/Experimental.md)__, but please take note of the following:

CodeGlass needs to be started as administrator as we need to add some registry keys.

These keys will be removed when:
- You close the client on the machine that registered them.
- You start the client in administrator mode on the machine that registered them.
- You uninstall CodeGlass on the machine that registered them.


If, in the unlikely case, the registry keys stay behind, this is the key to remove:

```
HKEY_CLASSES_ROOT\CLSID\{2091c114-505f-51b5-8145-5eee1ed82fe1}
```
It is an Experimental Edition only feature because it works on some of our machines, but not all. It looks like it is a Windows version issue. But since .Net Framework 2.0 - 3.5 are pretty old we decided to not invest more time in it.

Let us know if you need official support of .NET Framework 2.0-3.5; we can probably make it. <br/>

## .NET Core & .NET (5.0+)
- .NET Core 1.0 and up.
- .NET 5 and up.

## ASP.NET Framework
- ASP.NET for .NET Framework 4 and up.

### Requirements
- IIS Express needs to be installed, which can be done from the CodeGlass Installer as an optional feature. 

### Known Issues
- If you have to make it work with IIS server installation, let us know; support can be made.

## ASP.NET Core 
.ASP.NET Core 1.0 And up.


### Known Issues
- Make sure that your appsettings.json and other configuration files are getting loaded. Some older ASP.NET Projects do not load them when starting with the dotnet CLI.
- The folder name must be the same as your built assembly ".dll."

## Any .NET

{% include alert.html  type="warning" title="Experimental Edition Feature" content="This feature is not user friendly and we are unsure if we can ever make it user friendly due to limitations by Microsoft. Because of this, it is only available to the <a href=\"../Editions/Experimental\">Experimental Edition</a> till it is more user friendly." %}

This "runtime" works that if a program starts in a specified folder or subfolder and then requests the user if it wants to profile the application or not.
However, this also means that if you set it to, for example, 'C:\', it will ask you if you want to profile any application that starts on that drive!

### Known Issues
- At this moment CodeGlass can only set one folder as enabled; this limitation will be removed in the future.
- The CodeGlass Client may state that the folder is enabled, but when restarting the client it states that it is not; this is due to the clearing of register keys (see [registry keys](#registry-keys) below). We will fix this before the release to the Pro version.
- If you close the client with the enabled folder, it will stop working (see [registry keys](#registry-keys) below)
- If you start the client with the enabled folder, it will stop working (see [registry keys](#registry-keys) below)
- It does not work for ASP.NET projects if the selected folder is not part of the path to your IIS Express installation folder. Because the running application is IIS Express and not your application.

#### Registry Keys
For this feature, we have to add some registry keys. To prevent it going all haywire, we do the following to clean them up:
- We remove them when you close the client on the machine with the active folder.
- We remove them when you start the client on the machine with the active folder in case that CodeGlass was closed incorrectly.
- We remove them when you uninstall CodeGlass on the machine with the active folder

If, in the unlikely case, the registry keys stay behind, these are the keys to remove:
```
HKEY_CURRENT_USER\Environment\cg_app_instance_config_base_file_path
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
{% include alert.html  type="warning" title="Only available for experimental" content="This feature is still very experimental, therefor this is only available in the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}
{% include alert.html  type="success" title="JetBrains editors are also supported" content="If you want to use a JetBrains editor like Rider checkout <a href=\"JetbrainsEditors\" target=\"_blank\">this</a> page." %}

The Visual Studio "runtime" allow you to profile supported runtime applications while debugging them in Visual Studio.


### Requirements
- Devenv.exe is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md)
- Requires the build folder to be in the same or the subfolder of the solution
- ASP.NET Framework specific requirement: iisexpress.exe x86 path is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md) or enforce using x64 IIS Express in the Visual Studio Settings.


### Known Issues
- Multiple startup projects might cause issues.
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) will only apply when you reopen visual studio through CodeGlass, NOT when you restart the VS debugger.
- You get 'System.AccessViolationException: Attempted to read protected memory' from the VS Debugger. Try the following: Start once without debugging (CTRL+F5), rebuild the solution or reopen the solution through CodeGlass, Restart your computer. We always manage to get rid of the message in testing after trying the above; let us know if you can't get rid of it.
- ASP.NET Framework specific issue: It might happen that it does not automatically open the web page. You have to open a browser yourself and go to the URL. If you do not know the URL, you can check IISExpress tray icon on the taskbar in the bottom right.
- ASP.NET Framework specific issue: [CodeGlass Console](AttachConsole.md) input might not work; output always works. 

## UWP
{% include alert.html  type="warning" title="Experimental but available to everyone" content="This feature sometimes has some issues when launching an UWP application, but we did want to make it available to everyone anyways. To solve some of the issues, work arounds are described below." %}

To profile a UWP application using CodeGlass, you need to run CodeGlass with administrator privileges. We are working on making it more stable and fixing this problem.

### Requirements
- Requires the app not to be compiled with the [.net native tool chain](https://docs.microsoft.com/en-us/dotnet/framework/net-native/). If you know a way around this, please let us know.
- Needs CodeGlass NOT to be started as administrator (not-elevated). <br/>
Microsoft does not allow UWP applications to start in elevated mode. Since CodeGlass is started in the elevated mode, it can't start the application with lower permissions (not-elevated). 

### Known Issues
- Only able to profile applications that are built in Debug Mode.
- Needs CodeGlass to be opened as administrator to [add UWP applications](../views/mainwindow/newapplication.md#uwp).
Microsoft does not allow us to query UWP applications without administrator rights. <br/>
- Needs CodeGlass NOT to be started as administrator (not-elevated) to start a UWP application.<br/>
Microsoft does not allow UWP applications to start in elevated mode. Since CodeGlass is started in the elevated mode, it can't start the application with lower permissions (not-elevated). 
- The application starts but is not visible on the foreground, please open Windows Task manager (CTRL + SHIFT + ESC), go to tab 'App History' and then right mouse button and press 'Switch to'.
- The application does not start anymore <br/>
Please check if it is not running in task manager and kill it if it is. After that ensure that it runs correctly when you start it normally (sometimes after a while it doesn't anymore). Restart the pc if necessary. After that you can try again to start it with CodeGlass. You could also try locating it in Task Manager under App History, and then left mouse button an Switch to. <br/>
If the application also does not start anymore without CodeGlass even after you restart the PC, you need to rebuild it again to fix it.


## JavaScript Website
{% include alert.html  type="warning" title="Only available for experimental" content="This feature is very experimental, because of this only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}

{% include alert.html  type="warning" title="Do not use CodeGlass Chromium Browser for other use cases." content="The browser should be as safe as the Chromium browser (after we fix the security sandbox), but for the sake of arguments, just assume it is not, so don't use it when you do not want to profile the website you visit." %}

The JavaScript website "runtime" makes it possible to profile websites built with Javascript; this includes Typescript and all frameworks built upon JavaScript, as they all compile to JavaScript.<br/>
It uses a custom version of the Chromium (read Chrome) browser made by us to make this possible.

It is currently in the early stages. Please check back when we release it to Pro and give it an another chance.

### Requirements
- CodeGlass Chromium Browser is installed (optional install option in the [CodeGlass Installer](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases){:target="_blank"}).
- CodeGlass Browser path is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md)

### Known Issues
- Security sanbox is disabled, we had fixed this but it broke again when we updated chromium.
- Page loading will fail with STATUS_BREAKPOINT, this happens because you loaded a cached page, please reload the page with CTRL + F5, and if that does not help open Dev tools (F12), go to network tab and check 'disable cache' and reload the page again with CTRL+F5
- Many features that work for the CLR profiler do not work for this runtime, including:
    - [Decompilation for Filters](Decompilation.md)
    - [Memory Profiling](MemoryProfiling.md)
    - [Garbage Collection Invocations](GarbageCollection.md)
    - (probably more, we have to update this list manually)
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) will apply when you relaunch the browser through CodeGlass, NOT when you reload the page or use another tab.
- CodeGlass always opens a new browser window instead of another tab.
- We currently do not update and build the browser for each CodeGlass update with the latest Chromium changes as it takes a lot of time (read hours); because of this, the browser might not have the latest changes of Chromium.
- Only x64 and Windows, Chromium takes a lot of time to build (See above), we want to first make x64 stable before we start compiling to other architectures.
- When launching the CodeGlass Browser through the CodeGlass client, you decide under which [application](../views/mainwindow/applicationInstance.md) (instance) the browser will put the profiled data. It is unaware if you leave the specified website and will keep putting the other website's data in the same application in CodeGlass. Keep this in mind when reading statistics and such.
- The browser is not uninstalled when you uninstall CodeGlass, you have to do it manually (CodeGlassChromium in Apps and Features in Windows)

### Limitations
- A new [Application Instance](../views/mainwindow/applicationInstance.md) is made for every separated javascript process that starts in the CodeGlass browser (Like every tab and every website)

## Julia
{% include alert.html  type="warning" title="Coming soon for experimental" content="This feature is not yet available, but will be made available soon. Also this feature is very experimental, because of this only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}

The Julia runtime allows you to profile your Julia applications. You can profile both a script you select or directly run your code in a REPL. See [add new Julia application](../views/mainwindow/newapplication.md#julia) on how to setup a REPL.

### Requirements
- CodeGlass Julia is installed using the provided installer. The installer can be found [here](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases){:target="_blank"} when it has been released.
- CodeGlass Julia path is set in the [Client settings view](../views/clientusersettingswindow/ClientSettings.md)

### Known Issues
- It is not possible to set any [filters](ProfilingDataFiltering.md). This is due to a bug in how we track exceptions in Julia. We are working on making filtering possible again.
- It is not possible to disable [memory profiling](MemoryProfiling.md). This is due to how we have to profile Julia. Julia uses precompiling for a lot of things. After something has been precompiled we cannot make our changes anymore. This makes it very hard to enable or disable specific parts. For this reason memory profiling is always enabled.
- Certain packages fail to precompile. Some packages (like AllocCheck) can fail to precompile on CodeGlass Julia.

### Limitations
- CodeGlass Julia is a completely separate installation from your normal Julia installation. This also means that non of your packages or configurations from you "normal" Julia installation are used in CodeGlass Julia. This might mean that you have to reinstall some of your packages. It is recommended to keep the amount of installed packages on CodeGlass Julia to a minimum because of precompiling. Julia tries to precompile every package that you install. CodeGlass tries to profile that precompilation process. This means that it can take a while to precompile all your packages. To speed up this process, you can try to install all your packages without having CodeGlass running. (All your CodeGlass Julia packages are installed in the folder `C:\Users\{USERNAME}\.codeglass-julia`)
- CodeGlass Julia does not automatically get uninstalled when you uninstall CodeGlass. You can do this in your Windows Settings.

## Java
{% include alert.html  type="warning" title="Only available for experimental" content="This feature is very experimental, because of this only available to the <a href=\"../Editions/Experimental\" target=\"_blanc\">Experimental Edition</a>." %}

The Java runtime allows you to profile your Java applications. You can profile .jar files or get Start Instruction on how to run your code using Gradle or Maven.

### Requirements
- Java is installed on the system
- (optional) Java path is set in the Client settings view

### Known Issues
- Inner classes are for now displayed as one class like OuterClass$InnerClass instead of sub classes.
- Object names are displayed including namespaces instead of just the object names. E.g. java/lang/Object instead of Object
- The generic type part \<T> is not yet profiled and displayed in CodeGlass. Instead, generic java/lang/Object will be displayed.

### Limitations
- It is not possible to profile Java specific/own namespaces.
- It is not possible to profile some specific libraries and packages like org.xml and org.apache.
- An error may occur if some not yet excluded libraries and packages that are like org.xml and org.apache are profiled. These packages can be added to the filter to bypass this issue. 
- Memory profiling is not yet implemented for Java.

# See Also:
 - [View - Add new Application](../views/mainwindow/newapplication.md)
 - [View - Client settings](../views/clientusersettingswindow/ClientSettings.md)
 - [Roadmap - Non .NET Profiler](../Roadmap/NonDotNetProfiler.md)