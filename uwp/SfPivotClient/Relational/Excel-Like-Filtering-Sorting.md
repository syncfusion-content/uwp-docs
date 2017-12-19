---
layout: post
title: Excel Like Filtering and Sorting | SfPivotClient | UWP | Syncfusion
description: Excel Like Filtering and Sorting
platform: UWP
control: SfPivotClient
documentation: ug
---

# Excel-Like Filtering and Sorting

SfPivotClient control provides support for excel-like filtering and sorting applied to a PivotItem. We can enable or disable the excel-like sorting and filtering support in SfPivotClient by setting the property of  `AllowMultiFunctionalSortFilter`.

Please refer the below code snippet to enable excel like filtering and sorting.

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

![](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image1.png)

## Multi-Functional Features

**Sort A to Z**

It can be used to sort the corresponding PivotItem in the *Ascending order*.

**Sort Z to A**

It can be used to sort the corresponding PivotItem in the *Descending order*.

**More Sort Options**

It is used to sort the corresponding PivotItem based upon the Grandtotal of the PivotCalculation field.

**Clear filters**

It is used to clear all the filter changes applied to the corresponding PivotItem and could bring back the SfPivotClient to the normal state.

**Label Filters**

It is used to filter the SfPivotClient based on the labels of PivotItem field and it can be achieved by using various options which are listed below.

* Equals
* Does Not Equal
* Begins With
* Does Not Begin With
* Ends with
* Does Not End With
* Contains
* Does Not Contain
* Greater Than
* Greater Than or Equal To
* Less than
* Less than or Equal To
* Between
* Not Between

![](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image4.png)

_Label filter dialog for filtering "Canada" in Country_

![](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image5.png)

_SfPivotClient applied with label filter_

**Value Filters**

It is used to filter the SfPivotClient based on the values of PivotItem field and it can be achieved by using various options which are listed below.

* Equals
* Does Not Equal
* Greater Than
* Greater Than or Equal To
* Less than
* Less than or Equal To
* Between
* Not Between
* Top 10

![](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image6.png)

_Value filter dialog for filtering "France" using its Quantity value "398"_

![](Excel-Like-Filtering-Sorting_images/Excel-like-Filtering-image7.png)

_SfPivotClient applied with value filter_