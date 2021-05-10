---
layout: post
title: Excel-Like Filtering and Sorting in UWP Pivot Grid control | Syncfusion
description: Learn here all about Excel-Like Filtering and Sorting support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Excel-Like Filtering and Sorting in UWP Pivot Grid (SfPivotGrid)

The SfPivotGrid control supports Excel-like filtering and sorting applied to a pivot item. You can enable or disable the Excel-like sorting and filtering support by setting the `AllowMultiFunctionalSortFilter` property in the SfPivotGrid.

Refer to the following code snippet to enable Excel-like filtering and sorting.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" **AllowMultiFunctionalSortFilter="True"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.AllowMultiFunctionalSortFilter = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.AllowMultiFunctionalSortFilter = True

{% endhighlight %}

{% endtabs %}

![Excel-like-Filter-Popup](Excel-Like-Filtering-Sorting_images/Excel-like-Filter-Popup.png)

## Multi-functional features

**Sort A to Z**

It is used to sort the corresponding pivot item in the ascending order.

**Sort Z to A**

It is used to sort the corresponding pivot item in the descending order.

**More sort options**

It is used to sort the corresponding pivot item based on the grand total of the pivot calculation field.

![More-sort-options](Excel-Like-Filtering-Sorting_images/More-sort-options.png)

**Clear filters**

It is used to clear all the filter changes applied to the corresponding pivot item and bring back the SfPivotGrid to normal state.

**Label filters**

It is used to filter the SfPivotGrid based on the labels of pivot item field and it can be achieved by using various options listed below:

* Equals.
* Does not equal.
* Begins with.
* Does not begin with.
* Ends with.
* Does not end with.
* Contains.
* Does not contain.
* Greater than.
* Greater than or equal to.
* Less than.
* Less than or equal to.
* Between.
* Not between.

![Label-filter-popup](Excel-Like-Filtering-Sorting_images/Label-filter-popup.png)

_Label Filter pop-up for filtering "Canada" in Country_

![Filtered-PivotGrid-by-using-label-filter](Excel-Like-Filtering-Sorting_images/Filtered-PivotGrid-by-using-label-filter.png)

_SfPivotGrid applied with Label Filter_

**Value filters**

It is used to filter the SfPivotGrid based on the values of pivot item field and it can be achieved by using various options listed below:

* Equals.
* Does not equal.
* Greater than.
* Greater than or equal to.
* Less than.
* Less than or equal to.
* Between.
* Not between.
* Top 10.

![Value-filter-popup](Excel-Like-Filtering-Sorting_images/Value-filter-popup.png)

_Value Filter pop-up for filtering "Canada" using its Quantity value "409"_

![Filtered-PivotGrid-by-using-value-filter](Excel-Like-Filtering-Sorting_images/Filtered-PivotGrid-by-using-value-filter.png)

_SfPivotGrid applied with Value Filter_

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\SummaryDisplay.xaml
