---
layout: post
title: Holidays | SfGantt | Uwp | Syncfusion
description: The following section describes the holiday support in SfGantt.
platform: uwp
control: SfGantt
documentation: ug
---

## Holidays

The holidays support is used to highlight the non-working days in the Gantt chart.

The holidays can be specified in a task using the [`Holidays`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~Holidays.html) property in the SfGantt, which holds a collection of [`GanttHoliday`](https://help.syncfusion.com/cr/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~Holidays.html).

The following properties in the [`GanttHoliday`](https://help.syncfusion.com/cr/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~Holidays.html) are used to define the holidays:

* [`Day`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.GanttHoliday~Day.html): Specifies the dates of the holidays.
* [`Background`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.GanttHoliday~Background.html): Specifies the colors to highlight the holidays.

The following code sample demonstrates how to define the holidays.

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" ShowNonWorkingDays="True" >
    <gantt:SfGantt.Holidays>
        <gantt:GanttHolidayCollection>
            <gantt:GanttHoliday Day="5/28/2018"
                                Background="CadetBlue" />
        </gantt:GanttHolidayCollection>
    </gantt:SfGantt.Holidays>
</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.ShowNonWorkingDays = True;

sfGantt.Holidays = new GanttHolidayCollection()
{
    new GanttHoliday()
    {
        Day = new DateTime(2018, 5, 28),
        Background = new SolidColorBrush(Colors.CadetBlue)
    }
};

{% endhighlight %}

{% endtabs %}

![](SfGantt_images/Holidays.png)

N> To highligh the holidays in the Gantt chart, the ['ShowNonWorkingDays'](https://help.syncfusion.com/cr/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~ShowNonWorkingDays.html) property must be enabled.
