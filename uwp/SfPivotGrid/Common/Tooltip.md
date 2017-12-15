---
layout: post
title: Tooltip | SfPivotGrid | UWP | Syncfusion
description: Tooltip
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Tooltip

SfPivotGrid can additionally display the cell information within a tooltip when the mouse pointer is moved over header cells or value cells.

## Header cell tooltip

SfPivotGrid provides information about header cells when the mouse pointer is moved over it. Tooltip over header cells can be enabled by setting the `ShowHeaderCellsToolTip` property of the SfPivotGrid to `true` as shown in the below code snippet:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ShowHeaderCellsToolTip="True"/>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.ShowHeaderCellsToolTip = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowHeaderCellsToolTip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/ToolTip_RelationalHeader.png)

## Value cell tooltip

SfPivotGrid provides information about value cells when the mouse pointer is moved over it. Tooltip over value cells can be enabled by setting the `ShowValueCellToolTip` property of the SfPivotGrid to `true` as shown in the following code snippet:

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" ShowValueCellToolTip="True"/>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.ShowValueCellToolTip = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.ShowValueCellToolTip = True

{% endhighlight %}

{% endtabs %}

![](Tooltip_images/ToolTip_RelationalValueCell.png)

A demo sample is available at the following location:

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\GettingStarted.xaml