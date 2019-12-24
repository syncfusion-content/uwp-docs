---
layout: post
title: Add range of points dynamically | SfChart | Winrt | Syncfusion
description: add range of points dynamically
platform: UWP
control: SfChart
documentation: ug
---

# Add range of points dynamically

Whenever you add a data point to [`ItemsSource`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartSeriesBase~ItemsSource.html) dynamically, corresponding data will be updated inside chart series synchronously. This operation will be happening for each and every data point that we add subsequently. You can avoid this by calling [`SuspendSeriesNotification`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartBase~SuspendSeriesNotification.html) method of Chart before adding range of data points and then call [`ResumeSeriesNotification`](https://help.syncfusion.com/cr/cref_files/uwp/Syncfusion.SfChart.UWP~Syncfusion.UI.Xaml.Charts.ChartBase~ResumeSeriesNotification.html) to update all the data points that have been added between these two method calls.


{% highlight c# %}
Chart.SuspendSeriesNotification();

// ...

// Add multiple data points.

// ...

Chart.ResumeSeriesNotification();

{% endhighlight %}
