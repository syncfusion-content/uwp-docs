---
layout: post
title: Drill Operation in UWP Pivot Chart control | Syncfusion
description: Learn here all about Drill Operation support in Syncfusion UWP Pivot Chart (SfPivotChart) control and more.
platform: UWP
control: SfPivotChart
documentation: ug
---

# Drill Operation in UWP Pivot Chart (SfPivotChart)

This is the basic feature of SfPivotChart through which the amount of information can be limited for a better view. It allows you to drill down to access the detailed level of data or drill up to see the summarized data by using the expanders present in primary axis labels.

## Drill down/drill up

Drill up, also called as roll up; it navigates from more detailed data to less detailed data by climbing up a concept hierarchy for a dimension.

Drill down, also called as roll down; it is the reverse of drill up operation which navigates from less detailed data to more detailed data by climbing down the concept hierarchy for the dimension.

While binding hierarchical dimensions (for example, the time dimension includes 3 levels namely year, quarter, and month), the SfPivotChart allows you to visualize the data for different levels by using the collapsible labels which are illustrated in the following screenshot.

![Drill-operation](Drill-Operation_images/Drill-operation.png)

## Drill types

The following drill types are supported in the SfPivotChart:

* Drill member
* Drill position
* Drill replace

**Drill member**

The drill member is the default drilling type performed in the SfPivotChart. When multiple dimensions are added in an axis, expanding a single member expands the corresponding member element across all of its positions. The following code snippet and screenshot illustrate how the elements are drilled in drill member type.

{% tabs %}

{% highlight c# %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillMember;

{% endhighlight %}

{% highlight vb %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillMember

{% endhighlight %}

{% endtabs %}

![Drill-member](Drill-Operation_images/Drill-member.png)

**Drill position**

The drill position type enables users to drill only the current position of the selected member in the OLAP report. This excludes the drilled data of the selected member in other positions by using the MDX query. Refer to the following code snippet.

{% tabs %}

{% highlight c# %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillPosition;

{% endhighlight %}

{% highlight vb %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillPosition

{% endhighlight %}

{% endtabs %}

**Drill replace**

The SfPivotChart supports the drill replace type, in which the control is tend to display only the immediate child members and ancestors on the drill-down. The following code snippet and screenshot illustrate how the elements are drilled in the drill member type.

{% tabs %}

{% highlight c# %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillReplace;

{% endhighlight %}

{% highlight vb %}

pivotChart1.OlapDataManager.CurrentReport.DrillType = DrillType.DrillReplace

{% endhighlight %}

{% endtabs %}

N> The drilled-down member can be replaced with drilled data and it cannot be drilled-up.

![Drill-replace](Drill-Operation_images/Drill-replace.png)

N> Since the `DrillType` property interacts with the `OlapDataManager`, you should call the `DataBind()` method of SfPivotChart after assigning the value to this property.

## Show/hide expanders

The expander refers to the arrow sign prior to a member present in the primary axis labels. The visibility of expanders in the SfPivotChart can be toggled using the `ShowExpanders` property available in the OLAP report.

Refer to the following code snippet to hide the expanders in the SfPivotChart.

{% tabs %}

{% highlight c# %}

pivotChart1.OlapDataManager.CurrentReport.ShowExpanders = false;

{% endhighlight %}

{% highlight vb %}

pivotChart1.OlapDataManager.CurrentReport.ShowExpanders = False

{% endhighlight %}

{% endtabs %}

![Drill-operation-hide-expanders](Drill-Operation_images/Drill-operation-hide-expanders.png)

N> Since the `ShowExpanders` property interacts with the `OlapDataManager`, you should call the `DataBind()` method of SfPivotChart after assigning the value to this property.
