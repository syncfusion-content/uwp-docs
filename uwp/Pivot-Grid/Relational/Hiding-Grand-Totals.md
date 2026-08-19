---
layout: post
title: Hiding Grand Totals in UWP Pivot Grid | Syncfusion®
description: Hide grand totals in Syncfusion® UWP Pivot Grid control by disabling the ShowGrandTotals property to remove overall row and column summaries.
platform: uwp
control: Pivot Grid
documentation: ug
---

# Hiding Grand Totals in UWP Pivot Grid

You can hide the grand total values of the pivot grid control by setting the `ShowGrandTotals` property to false. By default, the pivot grid displays the grand total values of both rows and columns.

Refer to the following code sample to hide the grand total values of the pivot grid control.

{% tabs %}

{% highlight xaml %}

<pivotGrid:SfPivotGrid x:Name="pivotGrid1" ShowGrandTotals="False" />

{% endhighlight %}

{% highlight c# %}

this.pivotGrid1.ShowGrandTotals = false;

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid1.ShowGrandTotals = False

{% endhighlight %}

{% endtabs %}

![Hiding grand totals in pivot grid](Hiding-Grand-Totals_images/HidingGrandTotals.png)