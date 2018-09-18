---
layout: post
title: Appearance | SfPivotGauge | UWP | Syncfusion
description: Appearance
platform: UWP
control: SfPivotGauge
documentation: ug
---

# Appearance

## Layout customization

The SfPivotGauge supports displaying the multiple gauges in a structured layout and this can be achieved by using the `RowsCount` and `ColumnsCount` properties. These properties specify the number of rows and columns required to display the control.

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

## Gauge radius

The SfPivotGauge supports adjusting its radius by assigning a proper value to its `Radius` property. The following code snippet illustrates how to modify the radius of the SfPivotGauge.

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

## Gauge header

The gauge header is the combination of details about the calculation and KPI. The header components of the SfPivotGauge can be hidden by using the `ShowGaugeHeader` property as specified in the following code snippet.

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

## Gauge label

The visibility of gauge labels that are displayed inside the gauge can be toggled with the help of `ShowGaugeLabels` property. The following code snippet shows how to hide labels of the SfPivotGauge.

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

## Gauge factor

The gauge factor component can be hidden by using the `ShowGaugeFactors` property as specified in the following code snippet.

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
