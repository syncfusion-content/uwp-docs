---
layout: post
title: Add range of points dynamically | SfChart | Winrt | Syncfusion
description: add range of points dynamically
platform: UWP
control: SfChart
documentation: ug
---

# Add range of points dynamically

Whenever you add a data point to [`ItemsSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ItemsSource) dynamically, corresponding data will be updated inside chart series synchronously. This operation will be happening for each and every data point that we add subsequently. You can avoid this by calling [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SuspendSeriesNotification) method of Chart before adding range of data points and then call [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_ResumeSeriesNotification) to update all the data points that have been added between these two method calls.


{% highlight c# %}
Chart.SuspendSeriesNotification();

// ...

// Add multiple data points.

// ...

Chart.ResumeSeriesNotification();

{% endhighlight %}

