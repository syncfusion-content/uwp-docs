---
layout: post
title: Appearance in UWP Pivot Chart | Syncfusion®
description: Appearance in the UWP Pivot Chart allows you to customize chart visuals using palettes, colors, themes, and styling options.
platform: uwp
control: SfPivotChart
documentation: ug
---

# Appearance in UWP Pivot Chart

The SfPivotChart supports customizing the default appearance of the control. You can customize the default style of the control by modifying its properties as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotChart x:Name="PivotChart1" BorderBrush="Black" BorderThickness="3" Background="LightBlue" Padding="10"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotChart>

{% endhighlight %}

{% highlight c# %}

PivotChart1.BorderThickness = new Thickness(3);
PivotChart1.BorderBrush = new SolidColorBrush(Colors.Black);
PivotChart1.Background = new SolidColorBrush(Colors.LightBlue);
PivotChart1.Padding = new Thickness(10);

{% endhighlight %}

{% highlight vb %}

PivotChart1.BorderThickness = New Thickness(3)
PivotChart1.BorderBrush = New SolidColorBrush(Colors.Black)
PivotChart1.Background = New SolidColorBrush(Colors.LightBlue)
PivotChart1.Padding = New Thickness(10)

{% endhighlight %}

{% endtabs %}

![appearance](Appearance_images/appearance.png)
