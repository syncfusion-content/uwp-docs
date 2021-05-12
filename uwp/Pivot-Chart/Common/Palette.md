---
layout: post
title: Palette in UWP Pivot Chart control | Syncfusion
description: Learn here all about Palette support in Syncfusion UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Palette in UWP Pivot Chart (SfPivotChart)

A pre-defined collection or a set of colors can be applied to the chart series. Palette can be used to provide a rich look for your business applications.

**Built-in palette**

The SfPivotChart supports the following 12 types of built-in chart palette:

* Metro
* AutumnBrights
* FloraHues
* Pineapple
* TomatoSpectrum
* RedChrome
* PurpleChrome
* BlueChrome
* GreenChrome
* Elite
* SandyBeach
* LightCandy

The following code snippet shows how to apply the palette to the SfPivotChart control.

{% tabs %}

{% highlight c# %}

PivotChart1.ColorPalette = PivotChartColorPalette.AutumnBrights;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ColorPalette = PivotChartColorPalette.AutumnBrights

{% endhighlight %}

{% endtabs %}

![palette_AutumnBrights](Palette_images/palette_AutumnBrights.png)

**Custom palette**

The SfPivotChart provides a custom option to define own color brushes with your preferred order for the palette. Using the `CustomBrushes` property of the SfPivotChart, you can add a collection of colors to series as shown in the following code snippet.

{% tabs %}

{% highlight c# %}

PivotChart1.ColorPalette = PivotChartColorPalette.Custom;
PivotChart1.CustomBrushes = new List<Brush>();
PivotChart1.CustomBrushes.Add(new SolidColorBrush(Colors.BlueViolet));
PivotChart1.CustomBrushes.Add(new SolidColorBrush(Colors.Violet));
PivotChart1.CustomBrushes.Add(new SolidColorBrush(Colors.DarkViolet));
PivotChart1.CustomBrushes.Add(new SolidColorBrush(Colors.LightBlue));

{% endhighlight %}

{% highlight vb %}

PivotChart1.ColorPalette = PivotChartColorPalette.Custom
PivotChart1.CustomBrushes = New List(Of Brush)()
PivotChart1.CustomBrushes.Add(New SolidColorBrush(Colors.BlueViolet))
PivotChart1.CustomBrushes.Add(New SolidColorBrush(Colors.Violet))
PivotChart1.CustomBrushes.Add(New SolidColorBrush(Colors.DarkViolet))
PivotChart1.CustomBrushes.Add(New SolidColorBrush(Colors.LightBlue))

{% endhighlight %}

{% endtabs %}

![palette_Custom](Palette_images/palette_Custom.png)
