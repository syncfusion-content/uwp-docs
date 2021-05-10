---
layout: post
title: Critical Path in UWP Gantt control | Syncfusion
platform: uwp
control: SfGantt
documentation: ug
---

# Critical Path in UWP Gantt (SfGantt)

Critical path is a chain of linked critical tasks that defines the finish date of project. It can be highlighted by enabling the [`HighlightCriticalTasks`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_HighlightCriticalTasksProperty) property in SfGantt as demonstrated in the following code sample.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt HighlightCriticalTasks="True"/>

{% endhighlight %}

{% highlight c# %}

SfGantt gantt = new SfGantt
{
    HighlightCriticalTasks = true
};

{% endhighlight %}

{% endtabs %}

![UWP Gantt chart with highlighted critical tasks](CriticalPath_images/CriticalPathDefault.jpg)

## Customization

You can customize the color of critical path using the following properties:

* [`CriticalTaskBarBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_CriticalTaskBarBrushProperty): Specifies the color to highlight the critical task bar color.
* [`CriticalProgressBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_CriticalProgressBarBrushProperty): Specifies the color to highlight the critical task bar progress color.

N> The same [`CriticalTaskBarBrush`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_CriticalTaskBarBrushProperty)  is applied to connector lines that connect two critical tasks.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt HighlightCriticalTasks="True" CriticalTaskBarBrush="#ffdbe0" CriticalProgressBarBrush="Pink" />

{% endhighlight %}

{% highlight c# %}

SfGantt gantt = new SfGantt
    {
        HighlightCriticalTasks = true,
        CriticalTaskBarBrush = new SolidColorBrush(Color.FromArgb(255, 255, 219, 224)),
        CriticalProgressBarBrush = new SolidColorBrush(Colors.Pink)
    };

{% endhighlight %}

{% endtabs %}

![UWP Gantt chart with critical tasks highlighted with custom colors.](CriticalPath_images/CriticalPathCustomization.jpg)

N> By default, the HighlightCriticalTasks property is disabled.
