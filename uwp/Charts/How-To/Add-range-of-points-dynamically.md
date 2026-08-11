---
layout: post
title: How to add range of points dynamically in UWP Chart | Syncfusion®
description: Add a range of points dynamically in the UWP Chart to update chart data efficiently and reflect changes in real time.
platform: uwp
control: SfChart
documentation: ug
---

# How to add range of points dynamically in UWP Chart

Whenever you add a data point to [`ItemsSource`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ItemsSource) dynamically, corresponding data will be updated inside chart series synchronously. This operation will be happening for each and every data point that we add subsequently. You can avoid this by calling [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_SuspendSeriesNotification) method of Chart before adding range of data points and then call [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartBase.html#Syncfusion_UI_Xaml_Charts_ChartBase_ResumeSeriesNotification) to update all the data points that have been added between these two method calls.

{% highlight c# %}
Chart.SuspendSeriesNotification();

// Code omitted for brevity
// Add multiple data points.

Chart.ResumeSeriesNotification();

{% endhighlight %}
