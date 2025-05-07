---
title: Feature - JetBrain Editor Support
description: Profiling right from your JetBrains editor
---

# JetBrains Editor Support

CodeGlass allows you to initiate profiling directly from your JetBrains editor. This guide explains how to set up profiling for .NET solutions. The instructions use [Rider](https://www.jetbrains.com/rider/){:target="_blank"} as an example, but similar steps apply to other JetBrains IDEs and supported languages. If you encounter issues, join our [Discord server](https://discord.com/invite/ytczAxSmX4){:target="_blank"} for assistance.

## Adding Your Application

Start by adding your application to CodeGlass using the **"Other"** template, unless you’ve already configured it. Other .NET-related templates may also work, though the steps may vary slightly. After selecting "Other", click **Next**, provide a name for your application, and click **Create**.

![assets/img/Features/JetBrainsSupport/SelectAppType.png](../../assets/img/Features/JetBrainsSupport/SelectAppType.png)

## Getting Start Instructions

To inform CodeGlass that profiling should begin when your application runs, you'll need to configure environment variables in your editor. CodeGlass provides these settings via the **Start Instructions** button.

![assets/img/Features/JetBrainsSupport/StartInstructionsButton.png](../../assets/img/Features/JetBrainsSupport/StartInstructionsButton.png)

Clicking this button opens a screen listing supported environments variables. Since you selected the "Other" template, CodeGlass shows all available options. Your list may differ based on your CodeGlass version and available integrations.

![assets/img/Features/JetBrainsSupport/StartIntructionsScreen.png](../../assets/img/Features/JetBrainsSupport/StartIntructionsScreen.png)

The following environment variables are critical for .NET profiling:

- `CG_ENABLE`
- `CG_TOKEN`
- `CORECLR_PROFILER`
- `CORECLR_PROFILER_PATH_32`
- `CORECLR_PROFILER_PATH_64`
- `CORECLR_ENABLE_PROFILING`
- `COR_PROFILER`
- `COR_PROFILER_PATH_32`
- `COR_PROFILER_PATH_64`
- `COR_ENABLE_PROFILING`

**Explanation:**
- `CG_ENABLE`: Enables the profiler. Set to `'1'` to attach, or `'0'` to disable.
- `CG_TOKEN`: Identifies which application instance to associate with. Each application has a unique token.
- The remaining variables inform the .NET runtime about profiler presence and file paths.

## Integrating With Your Editor

Open your solution in Rider (we used 2024.3.4). In the top-right corner, click the **Run/Debug Configurations** dropdown and select **Edit Configurations**.

![assets/img/Features/JetBrainsSupport/RunDebugConfigurationButton.png](../../assets/img/Features/JetBrainsSupport/RunDebugConfigurationButton.png)

In the configuration screen, paste all required environment variables into the **Environment variables** field. Use the icon on the right to open a structured editor for easier entry.

![assets/img/Features/JetBrainsSupport/RunDebugConfigurationScreen.png](../../assets/img/Features/JetBrainsSupport/RunDebugConfigurationScreen.png)

> **Note:**  
> Remove any double quotes from the variables. Quoted values may prevent Rider from correctly reading the settings.

Once configured, you can run your application as usual. CodeGlass will automatically detect and attach to the running instance.

![assets/img/Features/JetBrainsSupport/EnvironmentSettings.png](../../assets/img/Features/JetBrainsSupport/EnvironmentSettings.png)

Each time you launch the application, a new instance will appear in CodeGlass:

![assets/img/Features/JetBrainsSupport/RunningApplication.png](../../assets/img/Features/JetBrainsSupport/RunningApplication.png)

## Troubleshooting

If your application instance does not appear in CodeGlass, verify the following:

- Is `CG_ENABLE` set to `'1'` in the environment variables?
- Recopy and reapply the `CG_TOKEN` value from CodeGlass. It may have been invalidated.
- Ensure all `*_PROFILER_PATH_*` variables point to valid file paths.

If issues persist, join our [Discord server](https://discord.com/invite/ytczAxSmX4){:target="_blank"} for direct support.
