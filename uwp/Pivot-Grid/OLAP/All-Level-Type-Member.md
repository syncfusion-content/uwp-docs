---
layout: post
title: All-Level Type Member in UWP Pivot Grid | Syncfusion®
description: All-Level Type Member in Syncfusion® UWP Pivot Grid shows an all parent level across rows and columns to manage hierarchy visibility.
platform: uwp
control: SfPivotGrid
documentation: ug
---

# All-Level Type Member in UWP Pivot Grid

This feature enables you to display the “All” level type member across the rows and columns in the SfPivotGrid. This member behaves as parent to other members in its hierarchy by controlling their visibility through an expander.

To display the “All” level type member, set the `ShowLevelTypeAll` property to true as shown in the following code snippet. By default, it is set as false.

{% tabs %}

{% highlight c# %}

pivotGrid1.OlapDataManager.ShowLevelTypeAll = true;

{% endhighlight %}

{% highlight vb %}

pivotGrid1.OlapDataManager.ShowLevelTypeAll = True

{% endhighlight %}

{% endtabs %}

![PivotGrid_AllTypeEnabled](All-Level-Type-Member_images/PivotGrid_AllTypeEnabled.png)
