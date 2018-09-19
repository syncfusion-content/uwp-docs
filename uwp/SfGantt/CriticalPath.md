---
layout: post
title: Critical Path
platform: uwp
control: SfGantt
documentation: ug
---

# Critical Path

Critical path is the chain of linked critical tasks that defines the project finish date. It can be highlighted by enabling the [`HighlightCriticalTasks`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~HighlightCriticalTasksProperty.html) property in SfGantt as like in the following code sample.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt HighlightCriticalTasks="True">

{% endhighlight %}

{% highlight c# %}

this.Gantt.HighlightCriticalTasks = True;

{% endhighlight %}

{% endtabs %}

![UWP Gantt chart with highlighted critical tasks](CriticalPath_images/CriticalPathDefault.jpg)

## Customization

We can customize the critical path color with the following properties

* [`CriticalTaskBarBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~CriticalTaskBarBrushProperty.html) property can be used to specify the color to highlight the critical task bar color.
* [`CriticalProgressBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~CriticalProgressBarBrushProperty.html) property can be used to specify the color to highlight the critical task bar progress color.

N> The same [`CriticalTaskBarBrush`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~CriticalTaskBarBrushProperty.html) is applied to connector lines that connects two critical tasks.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt HighlightCriticalTasks="True" CriticalTaskBarBrush="#ffdbe0" CriticalProgressBarBrush="Pink" />

{% endhighlight %}

{% highlight c# %}

this.GanttControl.CriticalTaskBarBrush = new SolidColorBrush(Color.FromArgb(255, 255, 219, 224));
this.GanttControl.CriticalProgressBarBrush = new SolidColorBrush(Colors.Pink);

{% endhighlight %}

{% endtabs %}

![UWP Gantt chart with critical tasks highlighted with custom colors.](CriticalPath_images/CriticalPathCustomization.jpg)

N> By default, the HighlightCriticalTasks feature is disabled.