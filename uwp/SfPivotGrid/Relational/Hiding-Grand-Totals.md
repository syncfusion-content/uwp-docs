---
layout: post
title: Hiding-Sub-Totals
description: hiding sub-totals
platform: uwp
control: SfPivotGrid
documentation: ug
---

# Hiding Grand totals

Grand totals can be hidden by setting the property of [ShowGrandTotals](https://help.syncfusion.com/cr/wpf/Syncfusion.PivotAnalysis.Base~Syncfusion.PivotAnalysis.Base.PivotEngine~ShowGrandTotals.html) to false. By default, the pivot grid displays the grand total values for both rows and columns.

Refer to the below code sample to hide grand totals in the pivot grid control.

{% highlight c# %}

this.pivotGrid.PivotEngine.ShowGrandTotals = false;

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid.PivotEngine.ShowGrandTotals = False

End Class

{% endhighlight %}

![](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image5.png)