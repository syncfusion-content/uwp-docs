---
layout: post
title: Cell Selection in UWP Pivot Grid control | Syncfusion
description: Learn here all about Cell Selection support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Cell Selection in UWP Pivot Grid (SfPivotGrid)

The SfPivotGrid supports cell selection. You can select grid value cells like in Microsoft Excel. This can be achieved by setting the `AllowSelection` property of the SfPivotGrid to true.

On cell selection, the **SelectionChanged** event will be triggered and **PivotGridSelectionChangedEventArgs** will return an IEnumerable collection of column index, row index, and value index of the selected cell. The event argument will return the cell range and selection mode such as mouse-down, mouse-move, mouse-up, etc.

Refer to the following code snippet to enable cell selection.

{% tabs %}

{% highlight xaml %}

<!--Adding SfPivotGrid and enabling cell selection-->
<syncfusion:SfPivotGrid x:Name="PivotGrid1" **AllowSelection="True"**/>

{% endhighlight %}

{% highlight c# %}

this.PivotGrid1.AllowSelection = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.AllowSelection = True

{% endhighlight %}

{% endtabs %}

This is illustrated in the following screenshot.

![cell-selection](Cell-Selection_images/cell-selection.png)

## Multi-row selection

You can select a whole row in the pivot grid by clicking the specific row header. You can also select multiple rows by clicking one row header and dragging it through other row headers.

![selection-of-multiple-rows](Cell-Selection_images/selection-of-multiple-rows.png)

## Multi-column selection

You can select a whole column in the pivot grid by clicking the specific column header. You can also select multiple columns by clicking one column header and dragging it through other column headers.

![selection-of-multiple-columns](Cell-Selection_images/selection-of-multiple-columns.png)

## Selection with headers

The `AllowSelectionWithHeaders` property can be used to achieve the cell selection behavior along with headers. Refer to the following code snippet to enable the cell selection with headers.

N> It is applicable only for relational data source.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid x:Name="PivotGrid1" **AllowSelectionWithHeaders="True"**/>

{% endhighlight %}

{% highlight C# %}

this.PivotGrid1.AllowSelectionWithHeaders = true;

{% endhighlight %}

{% highlight vb %}

Me.PivotGrid1.AllowSelectionWithHeaders = True

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the cell selection along with row headers.

![selection-along-with-row-headers](Cell-Selection_images/selection-along-with-row-headers.png)

The following screenshot illustrates the cell selection along with column headers.

![selection-along-with-column-headers](Cell-Selection_images/selection-along-with-column-headers.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\CellSelection.xaml
