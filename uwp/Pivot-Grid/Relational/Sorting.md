---
layout: post
title: Sorting in UWP Pivot Grid control | Syncfusion
description: Learn here all about Sorting support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Sorting in UWP Pivot Grid (SfPivotGrid)

Sorting enables you to quickly visualize and understand your data better. Ultimately, it allows you to organize and find the data by which you can make more effective decisions. By default, the SfPivotGrid holds built-in comparers for all data types so that it will populate the data in ascending/descending order based on its data type. You can also define own custom comparer to view the data.

**Sorting using custom comparer**

Sorting can be achieved by defining own custom comparer and initializing its instance to the `Comparer` property of the corresponding pivot item.

For example, a custom comparer named as `ReverseOrderComparer` is defined to sort items in the descending order.

{% tabs %}

{% highlight C# %}

public class ReverseOrderComparer: IComparer
{
    public int Compare(object x, object y) {
        if (x == null && y == null)
            return 0;
        else if (y == null)
            return 1;
        else if (x == null)
            return -1;
        else
            return -x.ToString().CompareTo(y.ToString());
    }
}

{% endhighlight %}

{% highlight vb %}

Public Class ReverseOrderComparer
	Implements IComparer
	Public Function Compare(x As Object, y As Object) As Integer
		If x Is Nothing AndAlso y Is Nothing Then
			Return 0
		ElseIf y Is Nothing Then
			Return 1
		ElseIf x Is Nothing Then
			Return -1
		Else
			Return -x.ToString().CompareTo(y.ToString())
		End If
	End Function
End Class

{% endhighlight %}

{% endtabs %}

To apply this comparer to the pivot item, an instance of `ReverseOrderComparer` is created and assigned to the `Comparer` property of the pivot item as specified in the following code snippet.

{% tabs %}

{% highlight C# %}

PivotGrid1.PivotRows[0].Comparer = new ReverseOrderComparer();

{% endhighlight %}

{% highlight vb %}

PivotGrid1.PivotRows(0).Comparer = New ReverseOrderComparer()

{% endhighlight %}

{% endtabs %}

![Not-Sorted-PivotGrid](Sorting_images/Not-Sorted-PivotGrid.png)

_SfPivotGrid without ReverseOrderComparer_

![Sorted-PivotGrid](Sorting_images/Sorted-PivotGrid.png)

_SfPivotGrid with ReverseOrderComparer_

## Sorting using values

The SfPivotGrid supports sorting based on value fields. The sorting order such as ascending or descending can be specified with the help of `SortDirection` property and the way of sorting is differentiated by using the `SortOption` property.

The following are the different kinds of sorting options available in the SfPivotGrid:

* Sort all columns.
* Sort all columns other than total and grand total columns.
* Sort only total columns.
* Sort only grand total columns.
* Disable sort.

**Sorting all columns**

The `All` option allows you to sort all value columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" SortOption="All"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.SortOption = SortOption.All;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.SortOption = SortOption.All

{% endhighlight %}

{% endtabs %}

![Sorted-PivotGrid-when-using-All-option](Sorting_images/Sorted-PivotGrid-when-using-All-option.png)

**Sorting all columns except total and grandTotal columns**

The `ColumnSorting` option is used to enable sorting for all value columns other than the sub total and grand total columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" SortOption="ColumnSorting"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.SortOption = SortOption.ColumnSorting;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.SortOption = SortOption.ColumnSorting

{% endhighlight %}

{% endtabs %}

![Sorted-PivotGrid-when-using-Column-sorting-option](Sorting_images/Sorted-PivotGrid-when-using-Column-sorting-option.png)

**Sorting only total columns**

The `TotalSorting` option is used to enable sorting only for sub-total columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" SortOption="TotalSorting"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.SortOption = SortOption.TotalSorting;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.SortOption = SortOption.TotalSorting

{% endhighlight %}

{% endtabs %}

![Sorted-PivotGrid-when-using-Total-Sorting](Sorting_images/Sorted-PivotGrid-when-using-Total-Sorting.png)

**Sorting only grand total columns**

The `GrandTotalSorting` option is used to enable sorting only for grand total columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" SortOption="GrandTotalSorting"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.SortOption = SortOption.GrandTotalSorting;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.SortOption = SortOption.GrandTotalSorting

{% endhighlight %}

{% endtabs %}

![Sorted-PivotGrid-when-using-GrandTotal-Sorting-option](Sorting_images/Sorted-PivotGrid-when-using-GrandTotal-Sorting-option.png)

**Disable sorting**

**None** is the default option that disables sorting on all value columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" SortOption="None"/>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.SortOption = SortOption.None;

{% endhighlight %}

{% highlight vb %}

PivotGrid1.SortOption = SortOption.None

{% endhighlight %}

{% endtabs %}
