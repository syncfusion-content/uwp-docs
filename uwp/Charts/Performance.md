---
layout: post
title: Performance in UWP Charts control | Syncfusion
description: Learn here all about Performance support in Syncfusion UWP Charts (SfChart) control and more.
platform: uwp
control: SfChart
documentation: ug
---

# Performance in UWP Charts (SfChart)

* When your underlying data object implements INotifyPropertyChanged, you need to enable the [`ListenPropertyChange`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ListenPropertyChange) property of the series, to make the chart listen to the property changes of your data object. However enabling this property registers PropertyChanged event of every object in the data source. Due to this, chart’s loading time is affected when there are a large number of points. By default, [`ListenPropertyChange`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ChartSeriesBase.html#Syncfusion_UI_Xaml_Charts_ChartSeriesBase_ListenPropertyChange) is set to false in order to avoid the event registration unnecessarily.
* In case of a [`LineSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.LineSeries.html), when you have large number of points to plot, you can make use of fast series types like [`FastLineSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FastLineSeries.html) and [`FastLineBitmapSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FastLineBitmapSeries.html).
* In case of a [`ColumnSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.ColumnSeries.html), when you have large number of points to plot, you can make use of [`FastColumnBitmapSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FastColumnBitmapSeries.html).
* You also have Fast Series types for financial charts like [`HiLo`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.HiloSeries.html) and [`HiLoOpenClose`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.HiLoOpenCloseSeries.html) and they are named as [`FastHiLoBitmapSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FastHiLoBitmapSeries.html) and [`FastHiLoOpenCloseBitmapSeries`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Charts.FastHiLoOpenCloseBitmapSeries.html) respectively.



