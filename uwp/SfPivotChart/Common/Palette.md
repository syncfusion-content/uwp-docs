---
layout: post
title: Palette| SfPivotChart | UWP | Syncfusion
description: Palette
platform: UWP
control: SfPivotChart
documentation: ug
---

# Palette

A pre-defined collection or a set of colors can be applied to the chart series. Palette can be used to provide a rich look for your business applications.

**In-built palette**

SfPivotChart supports 12 types of in-built chart palette that are specified as follows:

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

The following code snippet shows how to apply the palette to the SfPivotChart control:

{% tabs %}

{% highlight c# %}

PivotChart1.ColorPalette = PivotChartColorPalette.AutumnBrights;

{% endhighlight %}

{% highlight vb %}

PivotChart1.ColorPalette = PivotChartColorPalette.AutumnBrights

{% endhighlight %}

{% endtabs %}

![](Palette_images/palette_AutumnBrights.png)

**Custom palette**

SfPivotChart provides a custom option to define own color brushes with your preferred order for the palette. Using the `CustomBrushes` property of the SfPivotChart, you can add a collection of colors to series as shown in the following code snippet:

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

![](Palette_images/palette_Custom.png)