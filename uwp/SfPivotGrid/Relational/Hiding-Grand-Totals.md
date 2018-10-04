---
layout: post
title: Hiding Grandtotals
description: hiding grand totals in pivot grid
platform: uwp
control: SfPivotGrid
documentation: ug
---

# Hiding Grand totals

You can hide the grand totals of pivot grid control by setting the `ShowGrandTotals` property to false. By default, the pivot grid displays the grand total values for both rows and columns.

Refer to the following code sample to hide both row and column grand total in the pivot grid.

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

![](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image5.png)