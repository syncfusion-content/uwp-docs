---
layout: post
title: Validation Modes in UWP Gantt control | Syncfusion
platform: uwp
control: SfGantt
documentation: ug
---

# Validation Modes in UWP Gantt (SfGantt)

The Gantt control provides support to control the task scheduling. The start and finish dates of a task can be validated automatically or manually. The following validation modes can be set to the [`ValidationMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ValidationMode) property in SfGantt:

* `Manual`: Allows users to control the task scheduling and gives responsibility to track schedules on any task.
* `Auto`: Calculates the start and finish dates of a task based on its task dependencies and non-working days.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ValidationMode="Auto">

</gantt:SfGantt>

{% endhighlight %}

{% highlight c# %}

this.Gantt.ValidationMode = ValidationMode.Auto;

{% endhighlight %}

{% endtabs %}

N> By default, the validation mode is set to “Manual”.
