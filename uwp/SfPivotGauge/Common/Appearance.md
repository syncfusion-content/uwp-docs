---
layout: post
title: Appearance | SfPivotGauge | UWP | Syncfusion
description: Appearance
platform: UWP
control: SfPivotGauge
documentation: ug
---

# Appearance

## Layout Customization

SfPivotGauge provides support to display multiple gauges in a structured layout and it can be achieved by using the properties of `RowsCount` and `ColumnsCount`. These properties specify the number of rows and columns required for displaying the control.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" RowsCount="2" ColumnsCount="2"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.RowsCount = 2;
PivotGauge1.ColumnsCount = 2;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.RowsCount = 2
PivotGauge1.ColumnsCount = 2

{% endhighlight %}

{% endtabs %}

![](Appearance_images/Layout-customization.png)

## Gauge Radius

SfPivotGauge provides support to adjust its radius by assigning a proper value to its `Radius` property. The following code snippet illustrates about how to modify the radius of SfPivotGauge.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" Radius="75"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.Radius = 75;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.Radius = 75

{% endhighlight %}

{% endtabs %}

![](Appearance_images/Gauge-radius.png)

## Gauge Header

Gauge header is the combination of details about calculation and KPI. The header components of SfPivotGauge can be hidden by using the property of `ShowGaugeHeader` as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" ShowGaugeHeaders="False"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.ShowGaugeHeaders = false;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.ShowGaugeHeaders = False

{% endhighlight %}

{% endtabs %}

![](Appearance_images/Gauge-header.png)

## Gauge Label

The visibility of gauge labels that is displayed inside the gauge can be toggled with the help of `ShowGaugeFactors` property. The following code snippet shows how to hide the labels of SfPivotGauge.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" ShowGaugeLabels="False"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.ShowGaugeLabels = false;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.ShowGaugeLabels = False

{% endhighlight %}

{% endtabs %}

![](Appearance_images/Gauge-label.png)

## Gauge Factor

Gauge factor component can be hidden by using the property of `ShowGaugeFactors` as specified in the below code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGauge x:Name="PivotGauge1" ShowGaugeFactors="False"
                         ItemSource="{Binding ProductSalesData}" PivotRows="{Binding PivotRows}"
                         PivotColumns="{Binding PivotColumns}" PivotCalculations="{Binding PivotCalculations}">
</syncfusion:SfPivotGauge>

{% endhighlight %}

{% highlight c# %}

PivotGauge1.ShowGaugeFactors = false;

{% endhighlight %}

{% highlight vb %}

PivotGauge1.ShowGaugeFactors = False

{% endhighlight %}

{% endtabs %}

![](Appearance_images/Gauge-factor.png)
