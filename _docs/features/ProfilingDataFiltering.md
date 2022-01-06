---
title: Feature - Profiling Data Filtering
description: Filter what data you want to collect while profiling.
---
# Profiling Data Filtering
To improve the performance of your program while profiling, it is essential to filter out the data you need. We try to make this as easy as possible for you by the many ways you can filter and configure them.

{% include alertNoTitle.html  type="info" content="This page does not go into much detail on how to configure them but more on how they work. However, you will find links to the views where you can configure them." %}


## Filtering in general
Our filter systems work with a set of rules you can give them. Each [data item](#data-item) in the application will run against the ruleset. 
The rules will be processed in [Order](#filter-order) and [match](#matching-filters) against a filter rule that will decide if it will or will not filter the item.


We currently have 3 [types of filters rules](#filter-rule-types) that you can apply on every [Filter Groups](#filter-groups). 



## Matching Filters.
Every [data item](#data-item) is run agains the rules you provide in [Order](#filter-order) 
Only the first [filter](#filter-types) that a [data item](#data-item) matches against is checked if it should filter the item or not.
It does this by checking that filter's [allowed access modifiers](#access-modifiers).

It should always find a user-specified rule or the [root filter](#root-filter); however, if it does not, the default behavior is that it will not be filtered.


## Access Modifiers
On each [filter](#filter-rule-types), you can set one or more modifiers it should allow. By assigning no access modifiers, the item is filtered completely.

The assignable access modifiers are:
- Public 
- Protected
- Internal
- Private


## Filter Order
The order of the filters is critical as this is the order they will try to [match](#matching-filters) with [data items](#data-item).

We manage the order by processing the rules on the known [data items](#data-items) from previous [application instances](../views/mainwindow/applicationInstance.md); or [decompilations](#decompilation) and making it through various views easy to manage.

However, it might be handy to know how it works in the background.
The order is made by the creation / update date of the [filter rule](#filter-rule-types).
Currently, there is no direct way to see the order as this is not needed by how we show it in our views.

( if you have a use case for it, please let us know by creating a GitHub issue. )



To explain this, we created the following example.
Take this as an example application that you are profiling:

{% highlight csharp linenos %}

namespace HelloWorld
{
    class Hello 
    {         
        static void Main(string[] args)
        {
            WriteHello();
        }

        public static void WriteHello()
        {
            DebugWrite("Hello World!");
        }

        private void DebugWrite(string text)
        {
            System.Diagnostics.Debug.Write(text);
        }

    }
}
{% endhighlight %}


**Example 1**: With only the [root filter](#root-filter-rule) supplied that allows all [access modifiers](#access-modifiers) 

```
id: 4: Root filter   : <namespaces>       : All Modifiers Allowed.
```
```csharp
static void Main(string[] args); // Data received (rule 4) [line 5]
public static void WriteHello(); // Data Received (rule 4) [line 10]
private void DebugWrite(string text);  // Data received (rule 4) [line 15]
public static void System.Diagnostics.Debug.Write(text);  // Data received (rule 4) [line 17]
```


**Example 2**: Let's imagine you now have supplied the following filters where you only get data from public members in the HelloWorld Namespace.
```
id: 5: namespace filter : HelloWorld    : Only public modifiers are allowed
id: 4: Root filter      : <namespaces>  : No Modifiers Allowed.
```


It will result in the following:

```csharp
static void Main(string[] args); // No data received (rule 5) [line 5]
public static void WriteHello(); //Received (rule 5) [line 10]
private void DebugWrite(string text);  // No data received (rule 5) [line 15]
public static void System.Diagnostics.Debug.Write(text);  // No data received (rule 4) [line 17]
```

**Example 3**: let's add another rule:
```
id: 6: Regex filter     : Debug              : All modifiers allowed.
id: 5: namespace filter : HelloWorld.Hello   : Only public modifiers are allowed
id: 4: Root filter      : <namespaces>       : No Modifiers Allowed.
```

It will result in the following:

```csharp
static void Main(string[] args); // No Data received (rule 5) [line 5]
public static void WriteHello(); // Data Received (rule 5) [line 10]
private void DebugWrite(string text);  // Data received (rule 6) [line 15]
public static void System.Diagnostics.Debug.Write(text);  // Data received (rule 6) [line 17]
```

**Example 4**: If we now change de [root filter](#root-filter-rule) to allow everything:
```
id: 4: Root filter      : <namespaces>       : All Modifiers Allowed.
id: 7: Regex filter     : Debug              : All modifiers allowed.
id: 5: namespace filter : HelloWorld.Hello   : Only public modifiers are allowed.
```

It will result in the following (just like example 1):

```csharp
static void Main(string[] args); // Data received (rule 4) [line 5]
public static void WriteHello(); // Data Received (rule 4) [line 10]
private void DebugWrite(string text);  // Data received (rule 4) [line 15]
public static void System.Diagnostics.Debug.Write(text);  // Data received (rule 4) [line 17]
```

However, since we cleanup [namespace filters](#namespace-filter-rule) that becomes unreachable the actual filter order looks like this:

```
id: 4: Root filter  : <namespaces>       : All Modifiers Allowed.
id: 7: Regex filter : Debug              : All modifiers allowed. <- Is unreachable, but we do not remove regex filters automatically.
```






# Filter Rule Types
We currently have three types of filters rules that you can apply on every [Filter Groups](#filter-groups). 


Below we go into more detail about each type.

## Namespace filter Rule
With this filter, you can supply a [namespace path](#namespace-path) to an item you want to filter or not by setting the allowed [Access modifiers](#access-modifiers).
If you supply a path that has other items below it (like a namespace), the rule will also apply to those items. To exempt an item you have to override it with another rule.

If a namespace filter becomes unreachable by another [rule](#filter-rule-types) it will be deleted to improve performance.

Examples
```
id: 6: namespace filter : HelloWorld        : No modifiers are allowed
id: 5: namespace filter : HelloWorld.Hello  : No modifiers are allowed <= rule is unreachable, so it will be deleted.
id: 4: Root filter      : <namespaces>      : All Modifiers Allowed.
```
```
id: 6: namespace filter : HelloWorld        : Public modifiers are allowed
id: 5: namespace filter : HelloWorld.Hello  : No modifiers are allowed <= Rule is Reachable! so it will NOT be deleted.
id: 4: Root filter      : <namespaces>      : All Modifiers Allowed.
```


## Regex filter Rule
With this filter, you can supply a regex pattern to match a [data item](#data-item). For example, if you fill in "Debug" you can filter any item that has Debug in its [namespace path](#namespace-path).

We do not remove regex filters automatically when it becomes unreachable by another [rule](#filter-rule-types). Because regex filters are all created by the user, and we can imagine that it is not very pleasant to have your well-written regexes removed by one click (e.g. by Changing the [root filter](#root-filter-rule))

Examples
```
id: 5: Root filter      : <namespaces>      : No Modifiers Allowed.
id: 6: Regex Filter     : Debug             : Public modifiers are allowed <= Rule is unreachable
```
```
id: 6: namespace filter : HelloWorld        : Public modifiers are allowed
id: 5: Root filter      : <namespaces>      : No Modifiers Allowed.
id: 6: Regex Filter     : Debug             : Public modifiers are allowed <= Rule is NOT uncreachble as HelloWorld COULD contain Debug paths.
```

{% include alertNoTitle.html  type="info" content="When a plain regex filter is unreachable, the filter text is white in views where you can edit them." %}



## Root filter Rule
This rule is a special rule that matches every [data item](#data-item), and you can only have one in each [group](#filter-groups); you cant also create it yourself.
By setting the [Allowed access modifiers](#access-modifiers), you can define what the default behavior is of every [data item](#data-item), and you can override it by creating new rules on top of it.

{% include alertNoTitle.html  type="info" content="In the views where you can change the root filter rule, it is visible as <namespaces\>." %}

# Filter Groups
We define the filters in multiple groups; we do this to prevent you from having to write the filters repeatedly or accidentally starting an application with the wrong filters and making incorrect assumptions accordingly.

Below we go into more detail about each group.

## Default Filters
The default filter group is the default filters that will be created for new [users](../Others/Account.md) as [User Global Filters](#user-global-filters]) on the current [Hub](CodeGlassHub.md).
We shipped this list with Code Glass as we thought most people were not interested in profiling anyway. 
It currently exists out of the following [namespace filters](#namespace-filter-rule) that are [fully filtered](#access-modifiers):
- System
- Microsoft
- Windows
- MS (Also from Microsoft)

You cant edit this group, but you can remove or edit them on your [User Global Filters](#user-global-filters)

This group will grow over time, and if you have recommendations for default namespaces, please suggest them by creating a GitHub issue.


## User Global Filters
The User Global Filters group is the filters of the current [User](../Others/Account.md) on the current [Hub](CodeGlassHub.md); these filters act as a template for [new applications](../views/mainwindow/new application).

You can manage these filters from the [Global Filters view](../views/clientusersettingswindow/global filters)



## Application Filters
The Application Filters group are filters of an [Application](../views/mainwindow/application.md) and is used as a template for new [application instances](../views/mainwindow/applicationInstance.md)

You can manage these filters from the [Application filters view](../views/applicationsettingswindow/ApplicationFilters.md) 



## Application Instance Start Filters
The Application Instance Start Filters Group is a special group that you cant manage. This group is created from the current [application instance filters](#application-instance-filters.md) when the application starts and makes sure the data is not collected.

The reason why you can't change or manage them is that all supported [profilers](CodeGlassProfilers.md) do not allow you to change what you want and do not want to collect after the [data items](#data-item) is loaded for the first time.

You can view the current start filters of an application instance in the [Application Instance Settings Window](../views/ApplicationInstanceSettingsWindow/StartFilters.md)


## Application Instance Filters
The Application Instance Filters group are the current filters of an [application instance](../views/ApplicationInstanceDockWindow.md). These filters are used to filter [data](#data-item) visually instead of preventing them from being profiled in the first place. 

You can manage these from various places, including:
- [Application Instance Settings Window](../views/ApplicationInstanceSettingsWindow/Filters.md)
- [Application Explorer Tool Window](../views/ApplicationInstanceDockWindow/ApplicationExplorer.md) 
- [Application Instance statistics window](../views/ApplicationInstanceDockWindow/StatisticsWIndow.md)
- [Application Instance Heatmap rendering](../views/ApplicationInstanceDockWindow/CodeHeatMap.md)
- [Application Instance Call Tree rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
- [Application Instance Call Stack rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
- [Application Instance Grouped Call Stack rendering](../views/ApplicationInstanceDockWindow/GroupedCallStackRendering.md)


# References
### Namespace path
With the namespace path, we mean the path to the [data item](#data-item). This is best explained with an example:

```csharp
namespace CodeGlass.Profiler.Engine //Path is: CodeGlass.Profiler.Engine
{
    public class FilterEngine //Path is: CodeGlass.Profiler.Engine.FilterEngine
    {
        public bool IsRunning //Path is: CodeGlass.Profiler.Engine.FilterEngine.IsRunning
        { 
            get; //Path is: CodeGlass.Profiler.Engine.FilterEngine.IsRunning.get
            set; //Path is: CodeGlass.Profiler.Engine.FilterEngine.IsRunning.set
        }
     
        public bool CheckMatch(DataItem item) //Path is: CodeGlass.Profiler.Engine.FilterEngine.CheckMatch
        {
            ...
        }
    }
}
```


Currently, it is not possible to filter functions based on their parameters. If you want this, please let us know by submitting a ticket.


### Data item
We mean anything our profiler can stumble upon with data items, like modules, namespaces, properties, functions/methods, etc.
Data items can also be already known by previous [application instances](../views/mainwindow/applicationInstance.md) or [decompilations](decompilation.md) if the view allows it. 

# Views using this feature
 - [Global Fitlers](../views/clientusersettingswindow/globalfilters.md)
 - [Application Fitlers](../views/applicationsettingswindow/ApplicationFilters.md)
 - [Application Instance Window - File Menu](../views/ApplicationInstanceDockWindow/MenuBar.md#file-menu)
 - [Application Explorer](../views/ApplicationInstanceDockWindow/ApplicationExplorer.md)
 - [Realtime Call Tree Rendering](../views/ApplicationInstanceDockWindow/CallTreeRendering.md)
 - [Realtime Call Stack Rendering](../views/ApplicationInstanceDockWindow/CallStackRendering.md)
 - [Realtime Grouped Call Stack Rendering](../views/ApplicationInstanceDockWindow/GroupedCallStackRendering.md)



# See Also:
 - [CodeGlass Account](../Others/Account.md)
 - [Code Glass Hub](CodeGlassHub.md)
```

