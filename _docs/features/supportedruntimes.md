---
title: Feature - Supported Runtimes
description: The runtimes we support in CodeGlass
---

# Runtime Support

CodeGlass is designed to support as many languages and runtimes as possible. Full support is currently available for .NET, with additional runtimes accessible in the [Experimental Edition](../Editions/Experimental.md).

Languages supported only in the Experimental Edition:
- [JavaScript for websites](#javascript-website)
- [Julia](#julia)
- [Java](#java)

## .NET Framework

Supported versions: .NET Framework 4.0 and above.

### Notes on .NET Framework 2.0–3.5

While not officially supported, these versions may work in the [Experimental Edition](../Editions/Experimental.md). For this functionality, CodeGlass requires Admin rights to apply registry keys.

These keys will be removed when:
- You close the client on the machine that registered them.
- You start the client in administrator mode on the machine that registered them.
- You uninstall CodeGlass on the machine that registered them.

If, in the unlikely case, the registry keys stay behind, this is the key to remove:

```
HKEY_CLASSES_ROOT\CLSID\{2091c114-505f-51b5-8145-5eee1ed82fe1}
```

Let us know if you require full support for .NET Framework 2.0–3.5.

## .NET Core and .NET 5+

- Supported: .NET Core 1.0 and newer
- Supported: .NET 5 and newer

## ASP.NET Framework

- Supported: ASP.NET for .NET Framework 4 and newer

### Requirements

- IIS Express must be installed

### Known Issues

- For support with full IIS (non-Express), contact us.

## ASP.NET Core

- Supported: ASP.NET Core 1.0 and newer

### Known Issues

- Some older ASP.NET Projects do not load configuration fileswith the .NET CLI. Ensure configuration files (e.g., `appsettings.json`) are correctly loaded.
- The folder name must match the output `.dll` file name.

## Azure App Service

At this moment, profiling applications on Azure App Service is not officially supported by CodeGlass, but it is possible to configure manually. Below is a general outline of the steps required. If you encounter issues, feel free to contact us — we are happy to assist.

### Setup Instructions

1. **Add Profiler DLLs to Your Project**  
   Copy the CodeGlass profiler DLLs into a folder within your project. Ensure the files are included in your solution and are marked to be copied to the output directory on build.

2. **Publish Your Project to Azure**  
   Deploy the project to your Azure App Service as you normally would.

3. **Configure Environment Variables**  
   In the Azure Portal, navigate to your App Service. Under the **Settings** section in the sidebar, click **Configuration**, then under the **Application settings** tab, add the following environment variables. Ensure "Deployment slot setting" is checked for each one:

   | Key                      | Value                                                              |
   |--------------------------|--------------------------------------------------------------------|
   | `CG_ENABLE`              | `1`                                                                |
   | `CORCLR_ENABLE_PROFILING`| `1`                                                                |
   | `CORECLR_PROFILER`       | `{2091c114-505f-51b5-8145-5eee1ed82fe1}`                           |
   | `CG_IP`                  | IP address of the device running CodeGlass Hub                     |
   | `CG_PORT`                | `60341` (default port used by CodeGlass)                           |
   | `CG_TOKEN`               | Token of the application you created in CodeGlass                  |
   | `CORCLR_PROFILER_PATH_64`| Absolute path to x64 CodeGlass profiler DLL                        |
   | `CORCLR_PROFILER_PATH_32`| Absolute path to Win32 CodeGlass profiler DLL                      |

### Additional Notes

- **CG_IP** should point to a reachable device from the App Service. If targeting an Azure VM, ensure both services are on the same Virtual Network (VNet) and use the VM's internal IP address.
- **CG_PORT** must be open for inbound TCP traffic on the receiving device.
- **CG_TOKEN** is found in the [Start Instructions](../views/mainwindow/applicationInstance.md#start-instructions) section of the target application in CodeGlass.
- **DLL Paths** must be absolute. A common pattern is: `C:\home\site\wwwroot{your-folder-name}`. To confirm the correct base path, open the **Console** for your App Service from the Azure portal. The initial directory shown is the root path you should use.

This configuration enables your Azure-hosted application to send profiling data to your local or cloud-hosted CodeGlass instance.

## Visual Studio Solution

{% include alert.html  type="warning" title="Only available for experimental" content="This feature is still experimental and available only in the <a href=\"../Editions/Experimental\">Experimental Edition</a>." %}
{% include alert.html  type="success" title="JetBrains editors are also supported" content="JetBrains support is available. See the <a href=\"JetbrainsEditors\">JetBrains Editors</a> page." %}

Allows profiling of supported runtimes while debugging in Visual Studio.

### Requirements

- `devenv.exe` must be configured in [Client Settings](../views/clientusersettingswindow.md#client-settings)
- Build output must reside in or beneath the solution folder
-  ASP.NET Framework specific requirement: `iisexpress.exe` x86 path must be configured in the [Client Settings view](../views/clientusersettingswindow.md#client-settings), or alternatively, enforce the use of x64 IIS Express in the Visual Studio settings.

### Known Issues

- Multiple startup projects may cause conflicts
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) will only apply when Visual Studio is restarted through CodeGlass, **not** when you restart the VS debugger.
- You get 'System.AccessViolationException: Attempted to read protected memory' from the VS Debugger. Try the following: Start once without debugging (CTRL+F5), rebuild the solution or reopen the solution through CodeGlass, Restart your computer. Be sure to reach out to support if the problems persist.
- ASP.NET Framework specific issue: The web page might not be opened automatically. You should visit the web page manually. If you do not know the URL, you can check IISExpress tray icon on the taskbar in the bottom right.

## UWP

{% include alert.html  type="warning" title="Experimental but available to everyone" content="This feature has known issues but is available to all users." %}

### Requirements

- The application must not be compiled with the [.NET Native Tool Chain](https://docs.microsoft.com/en-us/dotnet/framework/net-native/). If you know a workaround for this limitation, please let us know.
- CodeGlass must **not** be started as administrator.  
  Microsoft prevents UWP applications from launching in elevated mode. If CodeGlass is running with elevated permissions, it cannot start UWP apps, which require standard (non-elevated) privileges.

### Known Issues

- Only applications built in **Debug Mode** can be profiled.
- To [add UWP applications](../views/mainwindow/newapplication.md#uwp), CodeGlass **must** be run as administrator.  
  This is because Microsoft restricts querying UWP app metadata without elevated permissions.
- To **start** UWP applications, CodeGlass must **not** be run as administrator due to elevation restrictions.
- The application might start but not appear in the foreground. If this happens:
  - Open Task Manager (Ctrl + Shift + Esc)
  - Go to the **App History** tab
  - Right-click the application and choose **Switch to**
- If the application does not start:
  - Ensure it is not already running in the background
  - Terminate it via Task Manager if needed
  - Verify that it runs correctly without CodeGlass
  - Restart the PC if necessary
  - Try launching it again from CodeGlass
  - If still unresponsive, rebuild the application and retry

## JavaScript Website

{% include alert.html  type="warning" title="Only available for experimental" content="This feature is very experimental and only available in the <a href=\"../Editions/Experimental\" target=\"_blank\">Experimental Edition</a>." %}

{% include alert.html  type="warning" title="Do not use CodeGlass Chromium Browser for other use cases." content="This browser is for profiling only. Do not use it for general browsing." %}

The JavaScript website runtime allows profiling of websites built with JavaScript, including TypeScript and frameworks like React, Angular, and Vue. Since these compile to JavaScript, they are all supported by this runtime.

This functionality is enabled via a custom Chromium-based browser developed specifically for CodeGlass.

The feature is still in early development. We recommend checking back when it reaches the Pro release.

### Requirements

- CodeGlass Chromium Browser must be [installed](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases){:target="_blank"}).
- The path to the browser must be set in the [Client Settings View](../views/clientusersettingswindow.md#client-settings).

### Known Issues

- The security sandbox is currently disabled. This was previously resolved but regressed with a Chromium update.
- You may encounter a `STATUS_BREAKPOINT` error when loading a cached page. To resolve:
  - Reload with **Ctrl + F5**
  - If that fails, open DevTools (F12), navigate to the Network tab, enable **Disable cache**, and reload again with **Ctrl + F5**
- Many features available in the CLR profiler do not work with this runtime, including:
  - [Decompilation for Filters](Decompilation.md)
  - [Memory Profiling](MemoryProfiling.md)
  - [Garbage Collection Invocations](GarbageCollection.md)
  - Additional limitations may apply
- New [start filters](ProfilingDataFiltering.md#application-instance-start-filters) are only applied when the browser is launched through CodeGlass. **not** when refreshing a tab or navigating to another page.
- Each session opens a new browser window rather than a tab.
- Chromium builds are not regenerated with every CodeGlass release due to long build times.
- Only x64 builds for Windows are supported at this time. Support for other platforms may follow once the x64 version is stable.
- When launched via CodeGlass, the browser continues logging data under the selected [application instance](../views/mainwindow/applicationInstance.md), regardless of navigation away from the original website.
- The browser is not removed when uninstalling CodeGlass. You must uninstall it manually via **Apps & Features** in Windows (look for "CodeGlassChromium").

### Limitations

- A new [Application Instance](../views/mainwindow/applicationInstance.md) is created for each isolated JavaScript process in the CodeGlass browser. This includes separate tabs and websites.

## Julia

{% include alert.html  type="warning" title="Coming soon for experimental" content="Will be available soon in the <a href=\"../Editions/Experimental\">Experimental Edition</a>." %}

Profiles both Julia scripts and REPL sessions.  See [add new Julia application](../views/mainwindow/newapplication.md#julia) on how to setup a REPL.

### Requirements

- CodeGlass Julia is installed using the provided installer. The installer can be found [here](https://github.com/CodeGlassDotIO/CodeGlassDotIO/releases){:target="_blank"} when it has been released.
- CodeGlass Julia path is set in the [Client settings view](../views/clientusersettingswindow.md#client-settings)

### Known Issues

- Filtering and memory profiling configuration are not currently supported
- Some packages may fail to precompile

### Limitations

- CodeGlass Julia is separate from your normal Julia installation. None of your "normal" packages or configurations are used in CodeGlass Julia. You might have to reinstall some of your packages. It is recommended to keep the amount of installed packages on CodeGlass Julia to a minimum because of precompiling. Julia tries to precompile every package that you install. CodeGlass tries to profile that precompilation process. This means that it can take a while to precompile all your packages. To speed up this process, you can try to install all your packages without having CodeGlass running. All your CodeGlass Julia packages are installed in the folder `C:\Users\{USERNAME}\.codeglass-julia`
- CodeGlass Julia does not automatically get uninstalled when you uninstall CodeGlass. You can do this in your Windows Settings.

## Java

{% include alert.html  type="warning" title="Only available for experimental" content="Available only in the <a href=\"../Editions/Experimental\">Experimental Edition</a>." %}

Profiles `.jar` files or code run via Gradle or Maven.

### Requirements

- Java must be installed
- CodeGlass Java path is set in the [Client settings view](../views/clientusersettingswindow.md#client-settings)

### Known Issues

- Inner classes appear as flat names. E.g. OuterClass$InnerClass
- Fully-qualified names are shown. E.g. java/lang/Object instead of Object
- Generic types are not displayed. E.g. generic java/lang/Object instead of java/lang/Object \<T>

### Limitations
- It is not possible to profile Java's own namespaces.
- It is not possible to profile certain libraries and packages such as `org.xml` and `org.apache`.
- An error may occur if some not yet excluded libraries and packages like `org.xml` and `org.apache` are profiled. These packages can be added to the filter to bypass this issue. 
- Memory profiling is not yet implemented for Java.

# See Also:
- [View - Add new Application](../views/mainwindow/newapplication.md)
- [View - Client settings](../views/clientusersettingswindow.md#client-settings)
- [Roadmap - Non .NET Profiler](../Roadmap/NonDotNetProfiler.md)