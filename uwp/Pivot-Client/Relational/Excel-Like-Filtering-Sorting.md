---
layout: post
title: Excel-Like Filtering and Sorting in UWP Pivot Client control | Syncfusion
description: Learn here all about Excel-Like Filtering and Sorting support in Syncfusion UWP Pivot Client (SfPivotClient) control and more.
platform: UWP
control: SfPivotClient
documentation: ug
---

# Excel-Like Filtering and Sorting in UWP Pivot Client (SfPivotClient)

The SfPivotClient control supports Excel-like filtering and sorting that is applied to a pivot item. You can enable or disable the Excel-like sorting and filtering support in the SfPivotClient by setting the `AllowMultiFunctionalSortFilter` property.

Refer to the following code snippet to enable Excel-like filtering and sorting.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotClient x:Name="pivotClient" AllowMultiFunctionalSortFilter="True" />

{% endhighlight %}

{% highlight C# %}

this.pivotClient.AllowMultiFunctionalSortFilter = true;

{% endhighlight %}

{% highlight vb %}

Me.pivotClient.AllowMultiFunctionalSortFilter = True

{% endhighlight %}

{% endtabs %}

![Excel-like-Filtering-image1](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image1.png)

## Multi-functional features

**Sort A to Z**

This allows you to sort the corresponding pivot item in the ascending order.

**Sort Z to A**

This allows you to sort the corresponding pivot item in the descending order.

**More sort options**

This allows you to sort the corresponding pivot item based on the grand total of the pivot calculation field.

**Clear filters**

This allows you to clear all the filter changes that are applied to the corresponding pivot item and bring back the SfPivotClient to the normal state.

**Label filters**

This allows you to filter the SfPivotClient based on labels of the pivot item field and this can be achieved by using various options that are listed below:

* Equals.
* Does Not Equal.
* Begins With.
* Does Not Begin With.
* Ends with.
* Does Not End With.
* Contains.
* Does Not Contain.
* Greater Than.
* Greater Than or Equal To.
* Less than.
* Less than or Equal To.
* Between.
* Not Between.

![Excel-like-Filtering-image4](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image4.png)

_Label filter dialog for filtering "Canada" in Country_

![Excel-like-Filtering-image5](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image5.png)

_SfPivotClient applied with label filter_

**Value filters**

This allows you to filter the SfPivotClient based on values of the pivot item field and this can be achieved by using various options that are listed below:

* Equals.
* Does Not Equal.
* Greater Than.
* Greater Than or Equal To.
* Less than.
* Less than or Equal To.
* Between.
* Not Between.
* Top 10.

![Excel-like-Filtering-image6](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image6.png)

_Value filter dialog for filtering "France" using its Quantity value "398"_

![Excel-like-Filtering-image7](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image7.png)

_SfPivotClient applied with value filter_
