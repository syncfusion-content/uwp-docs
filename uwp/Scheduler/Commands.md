---
layout: post
title: Commands | SfSchedule | uwp | Syncfusion
description: Commands
platform: uwp
control: SfSchedule
documentation: ug
---

# Commands

Operations that are done by the context menu can also be performed using Schedule commands. The following actions of the context menu can be handled by executing schedule commands in the application.

* Adding new appointment
* Editing appointment
* Deleting appointment
* Copying appointment
* Pasting appointment

## AddNewCommand


By triggering **AddNewCommand** of ScheduleCommands, the editor window can be opened with all fields with empty values based on the last selected date time, without using any UI. After that, you can specify the required values and save the appointment.

{% highlight c# %}

    ScheduleCommands.AddNewCommand.Execute(this.Schedule);

{% endhighlight %}

## EditCommand

By triggering **EditCommand** of ScheduleCommands, the editor window can be opened with all the fields with the last selected appointment details, without using any UI. After that, you can modify the required values and save the appointment.

{% highlight c# %}

    ScheduleCommands.EditCommand.Execute(this.Schedule);

{% endhighlight %}

## CopyCommand

By triggering **CopyCommand** of ScheduleCommands, the last selected schedule appointment in the schedule can be copied.

{% highlight c# %}

    ScheduleCommands.CopyCommand.Execute(this.Schedule);

{% endhighlight %}

## PasteCommand

By triggering **PasteCommand** of ScheduleCommands, the last copied schedule appointment can be pasted in SfSchedule.

{% highlight c# %}

    ScheduleCommands.PasteCommand.Execute(this.Schedule);

{% endhighlight %}


