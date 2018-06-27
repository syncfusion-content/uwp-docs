---
layout: post
title: Validation Modes
platform: uwp
control: SfGantt
documentation: ug
---
# Validation mode

The SfGantt control provides support to control task scheduling. The start and finish  dates of the task can be validated automatically or manually. The following validation modes can be set to the [`ValidationMode`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~ValidationMode.html) property in SfGantt. 

* `Manual` - Allows user to control task scheduling and gives responsibility to track schedules on any task.

* `Auto` - Calculates the start and finish dates of any task based on its task dependencies and non-working days.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ValidationMode="Auto">

</gantt:SfGantt>

{% endhighlight %}

{% highlight c# %}

this.Gantt.ValidationMode = ValidationMode.Auto;

{% endhighlight %}

{% endtabs %}

N>The default validation mode is “Manual”.