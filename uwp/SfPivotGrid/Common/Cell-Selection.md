---
layout: post
title: Cell Selection | SfPivotGrid | UWP | Syncfusion
description: cell selection
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Cell Selection

SfPivotGrid supports excel like cell selection where you can select grid value cells like in Microsoft Excel. This can be achieved by setting the `AllowSelection` property of SfPivotGrid to true.

On cell selection, **SelectionChanged** event will be triggered and **PivotGridSelectionChangedEventArgs** will return an IEnumerable collection of column index, row index and value index of the corresponding selected cell. The event argument will also return the cell range and the selection mode like mouse-down, mouse-move, mouse-up etc.

Please refer the below code snippet to enable cell selection.

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

This is illustrated in the following screenshot:

![](Cell-Selection_images/cell-selection.png)

## Multi-Row Selection

You can select a whole row in PivotGrid by clicking on the specific row header and you could select multiple rows by clicking on one row header and dragging it through other row headers as per our requirement.

![](Cell-Selection_images/selection-of-multiple-rows.png)

## Multi-Column Selection

You can select a whole column in PivotGrid by clicking on the specific column header and you could select multiple columns by clicking on one column header and dragging it through other column headers as per our requirement.

![](Cell-Selection_images/selection-of-multiple-columns.png)

## Selection With Headers

The `AllowSelectionWithHeaders` property can be used to achieve the cell selection behavior along with headers. Please refer the below code snippet to enable cell selection with headers.

N> It is applicable only for Relational DataSource.

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

This following screenshot illustrates the cell selection along with row headers.

![](Cell-Selection_images/selection-along-with-row-headers.png)

This following screenshot illustrates the cell selection along with column headers.

![](Cell-Selection_images/selection-along-with-column-headers.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\CellSelection.xaml