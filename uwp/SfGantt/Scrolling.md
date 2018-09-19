---
layout: post
title: Scrolling | SfGantt | UWP | Syncfusion
platform: uwp
control: SfGantt
documentation: ug
---

# Scrolling

## Scroll to visible region

The [`BringTaskOnVerticalScroll`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~BringTaskOnVerticalScroll.html) property in the SfGantt, enables to scroll to the visible task region when the Gantt chart is vertically scrolled. 

The below code example illustrates how to enable the [`BringTaskOnVerticalScroll`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~BringTaskOnVerticalScroll.html).

{% tabs %}

{% highlight xaml %}

<gantt:SfGantt ItemsSource="{Binding TaskCollection}" BringTaskOnVerticalScroll="True" >
</gantt:SfGantt>

{% endhighlight %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.BringTaskOnVerticalScroll = True;

{% endhighlight %}

{% endtabs %}

## Scroll to particular region

You can also scroll the Gantt chart horizontally to the specific date and vertically to the specific row index using ['ScrollGanttTo'](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfGantt.UWP~Syncfusion.UI.Xaml.Gantt.SfGantt~ScrollGanttTo.html) method in SfGantt. 

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.ScrollGanttTo(new DateTime(2014, 3, 1), 2);

{% endhighlight %}
