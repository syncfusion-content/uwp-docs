---
layout: post
title: Scrolling in UWP Gantt control | Syncfusion
platform: uwp
control: SfGantt
documentation: ug
---

# Scrolling in UWP Gantt (SfGantt)

## Scroll to visible region

The [`BringTaskOnVerticalScroll`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_BringTaskOnVerticalScroll) property in the SfGantt enables you scroll to the visible task region when the Gantt chart is vertically scrolled.

The following code sample demonstrates how to enable the [`BringTaskOnVerticalScroll`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_BringTaskOnVerticalScroll) property.

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

You can scroll the Gantt chart programmatically using the [`ScrollGanttTo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Gantt.SfGantt.html#Syncfusion_UI_Xaml_Gantt_SfGantt_ScrollGanttTo_System_Nullable_System_DateTime__System_Nullable_System_Int32__) method. 

The following parameters allow users to scroll the Gantt chart programmatically:

* `Date` : Specifies date to scroll horizontally.
* `Index` : Specifies row index to scroll vertically.
 
{% tabs %}

{% highlight C# %}

SfGantt sfGantt = new SfGantt();

sfGantt.ItemsSource = (this.DataContext as ProjectTrackerViewModel).TaskCollection;

sfGantt.ScrollGanttTo(new DateTime(2014, 3, 1), 2);

{% endhighlight %}

{% endtabs %}
