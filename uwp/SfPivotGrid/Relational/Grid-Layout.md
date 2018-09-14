---
layout: post
title: Grid Layout | SfPivotGrid | UWP | Syncfusion
description: Grid Layout for SfPivotGrid with Relational Data
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Grid Layout

The position of summary cells in the SfPivotGrid can be customized with the help of `GridLayout` property. It can be positioned at the top or bottom of value cells.

The following are the two different types of layouts supported by the SfPivotGrid:

* Normal layout
* Top summary layout

**Normal layout**

The normal layout is the default layout of SfPivotGrid, in which the summary cells are positioned at the bottom of value cells. Refer to the following code snippet to customize the grid layout.

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfPivotGrid Name="PivotGrid1" GridLayout="Normal"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.GridLayout = GridLayout.Normal;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.GridLayout = GridLayout.Normal

{% endhighlight %}

{% endtabs %}

![](Grid-Layout_images/Grid-Layouts_img1.png)

**Top summary layout**

In top summary layout, the summary cells are positioned at the beginning of value cells. The following code snippet illustrates how to set the top summary layout in the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

 <syncfusion:SfPivotGrid Name="PivotGrid1" GridLayout="TopSummary"
                         ItemSource="{Binding ProductSalesData}" PivotAxis="{Binding PivotAxis}"
                         PivotLegend="{Binding PivotLegend}" PivotCalculations="{Binding PivotCalculations}"/>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.GridLayout = GridLayout.TopSummary;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.GridLayout = GridLayout.TopSummary

{% endhighlight %}

{% endtabs %}

![](Grid-Layout_images/Grid-Layouts_img2.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\Relational.xaml