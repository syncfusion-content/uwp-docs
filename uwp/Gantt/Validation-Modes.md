---
layout: post
title: Validation Modes in UWP Gantt control | Syncfusion
description: Learn about Validation Modes support in Syncfusion UWP Gantt (SfGantt) control, covering setup, customization, and usage.
platform: uwp
control: SfGantt
documentation: ug
---

# Validation Modes in UWP Gantt (SfGantt)

The Gantt control provides support to control task scheduling. The start and finish dates of a task can be validated automatically or manually. The following validation modes can be set to the [`ValidationMode`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ValidationMode) property in SfGantt:

* `Manual`: Allows users to control task scheduling; the start and finish dates are preserved as set by the user and are not recalculated when predecessors or non-working days change. The user is responsible for tracking the schedule of the task.
* `Auto`: Calculates the start and finish dates of a task based on its task dependencies (predecessors) and non-working days. When a predecessor moves or its progress changes, dependent tasks are rescheduled automatically.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ValidationMode="Auto">

</gantt:SfGantt>

{% endhighlight %}

{% highlight c# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ValidationMode = ValidationMode.Auto;

{% endhighlight %}

{% endtabs %}

N> By default, the validation mode is set to “Manual”.
