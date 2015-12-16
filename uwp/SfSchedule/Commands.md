---
layout: post
title: Commands | SfSchedule | uwp | Syncfusion
description: Commands
platform: uwp
control: SfSchedule
documentation: ug
---

# Commands

Operations that are done by context menu can also be performed using Schedule commands. The following actions of context menu can be handled by executing schedule commands in the application.

* Adding new appointment
* Editing appointment
* Deleting appointment
* Copying appointment
* Pasting appointment
* Drag and drop appointment

## AddNewCommand


By triggering **AddNewCommand** of ScheduleCommands, the editor window can be opened with all the field with empty value based on last selected date time, without using any UI. After that you can specify the required value and save the appointment.

{% highlight c# %}

    ScheduleCommands.AddNewCommand.Execute(this.Schedule);

{% endhighlight %}

## EditCommand

By triggering **EditCommand** of ScheduleCommands, the editor window can be opened with all the field with the last selected appointment detail, without using any UI. After that you can modify the required value and save the appointment.

{% highlight c# %}

    ScheduleCommands.EditCommand.Execute(this.Schedule);

{% endhighlight %}

## CopyCommand

By triggering  **CopyCommand** of ScheduleCommands, last selected schedule appointment in schedule can be copied.

{% highlight c# %}

    ScheduleCommands.CopyCommand.Execute(this.Schedule);

{% endhighlight %}

## PasteCommand

By triggering **PasteCommand** of ScheduleCommands, last copied schedule appointment can be pasted in SfSchedule.

{% highlight c# %}

    ScheduleCommands.PasteCommand.Execute(this.Schedule);

{% endhighlight %}

## DragAndDropCommand

By triggering **DragAndDropCommand** of ScheduleCommands, the last selected appointment can be moved to drag drop and resize mode, without using context menu. 

{% highlight c# %}

    ScheduleCommands.DragAndDropCommand.Execute(this.Schedule);

{% endhighlight %}
