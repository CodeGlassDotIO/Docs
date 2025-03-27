---
title: View - Application Instance Settings Window
description: Settings of an application instance you are or had profiled.
---
# Application Instance Settings Window
![assets/img/AppInstanceSettingsWindow/AppInstanceSettingsWindow.png](../../assets/img/AppInstanceSettingsWindow/AppInstanceSettingsWindow.png)

This view contains all the settings that apply to this application instance. Here you can see things like the start filters of the instance or the filters that are currently applied. Here you can also see some general information about the instance.

## Start Filters
In start filter section you can see the filters that were used at the start of the instance, for more information on this type of filter see [feature - application instance start filters](../features/ProfilingDataFiltering.md#application-instance-start-filters)

To see how your filters are behaving it loads in data from previously run instances, if you do not want to first run your application you can choose to [decompile](#decompilation) the application.


## Filters
In the filters section you can manage the [application instance filters](../features/ProfilingDataFiltering.md#application-instance-filters) that are currently used for the application instance.

{% include Filters/BasicFiltersViewExplaination.md  %}

By pressing the "Apply" button you can set the current filters as the new [application filters](../features/ProfilingDataFiltering.md#application-filters)<br>
By pressing the "Reset" button you reset the filters back to the [application filters](../features/ProfilingDataFiltering.md#application-filters)

### Create New Filters
By pressing the "Create new filter" button you open the add application filter window:

![assets/img/ApplicationSettingsWindow/AddApplicationFilter.png](../../assets/img/ApplicationSettingsWindow/AddApplicationFilter.png)

{% include Filters/BasicNewFilterViewExplaination.md  %}
You can also here [decompile](#decompilation) to have more preview data on how your new filter would react.

## Information
In the information section, you can see some information about this instance. One of the more important pieces of information is the [tick duration](#tick-duration).

### Tick Duration
A tick is the most accurate time we can collect. The duration of a tick is difference per machine, however if you have Hyper-V enabled on your pc it will always be 10,000,0000 in a second (10.000 in a ms).
In this screen you see how many ticks there are in a second and what the interval is between a tick. 

To get more information on how we measure time, see [feature - time measurements](../features/TimeMessurement.md)

## Decompilation
{% include Filters/DecompilationForFilters.md %}