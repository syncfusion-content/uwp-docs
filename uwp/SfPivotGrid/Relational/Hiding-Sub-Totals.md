---
layout: post
title: Hiding Subtotals
description: Hiding subtotals in pivot grid
platform: uwp
control: SfPivotGrid
documentation: ug
---

# Hiding Subtotals

The pivot grid control provides support to show or hide its subtotal values. This support allows users to have an abstract view of the data as per their requirement. The following levels of hiding are supported in pivot grid control.

* Hiding all the subtotals
* Hiding only the row subtotals
* Hiding only the column subtotals
* Hiding the subtotals for the specific pivot item

## Hiding all the subtotals

The subtotal values of both pivot rows and pivot columns can be hidden by using the [ShowSubTotals](https://help.syncfusion.com/cr/wpf/Syncfusion.PivotAnalysis.Wpf~Syncfusion.Windows.Controls.PivotGrid.PivotGridControl~ShowSubTotals.html) property. Refer to the below code sample to hide all the subtotal values in the pivot grid.

{% tabs %}

{% highlight xaml %}

<pivotGrid:SfPivotGrid x:Name="pivotGrid1" ItemSource="{Binding ProductSalesData}" ShowSubTotals="False">
</pivotGrid:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.pivotGrid1.ShowSubTotals = false;

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid1.ShowSubTotals = False

{% endhighlight %}

{% endtabs %}

![Hiding-Sub-Totals_image1](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image1.png)

## Hiding only the row subtotals 

The subtotal values of pivot rows can only be hidden by using the [ShowRowSubTotals](https://help.syncfusion.com/cr/wpf/Syncfusion.PivotAnalysis.Wpf~Syncfusion.Windows.Controls.PivotGrid.PivotGridControl~ShowRowSubTotals.html) property. Refer to the below code sample to hide only the subtotal values of pivot rows in the pivot grid.

{% tabs %}

{% highlight xaml %}

<pivotGrid:SfPivotGrid x:Name="pivotGrid1" ItemSource="{Binding ProductSalesData}" ShowRowSubTotals="False">
</pivotGrid:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.pivotGrid1.ShowRowSubTotals = false;

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid1.ShowRowSubTotals = False

{% endhighlight %}

{% endtabs %}

![Hiding-Sub-Totals_image2](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image2.png)

## Hiding only the column subtotals 

The subtotal values of pivot columns can only be hidden by using the [ShowColumnSubTotals](https://help.syncfusion.com/cr/wpf/Syncfusion.PivotAnalysis.Wpf~Syncfusion.Windows.Controls.PivotGrid.PivotGridControl~ShowColumnSubTotals.html) property. Refer to the below code sample to hide only the subtotal values of pivot columns in the pivot grid.

{% tabs %}

{% highlight xaml %}

<pivotGrid:SfPivotGrid x:Name="pivotGrid1" ItemSource="{Binding ProductSalesData}" ShowColumnSubTotals="False">
</pivotGrid:SfPivotGrid>

{% endhighlight %}

{% highlight c# %}

this.pivotGrid1.ShowColumnSubTotals = false;

{% endhighlight %}

{% highlight vb %}

Me.pivotGrid1.ShowColumnSubTotals = False

{% endhighlight %}

{% endtabs %}

![Hiding-Sub-Totals_image3](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image3.png)

## Hiding the subtotals for specific pivot item

It can be achieved by setting the [ShowSubTotal](https://help.syncfusion.com/cr/wpf/Syncfusion.PivotAnalysis.Base~Syncfusion.PivotAnalysis.Base.PivotItem~ShowSubTotal.html) property to false for the specific pivot item. Refer to the below code sample to hide the subtotal values of "Date" pivot item.

N>
If `ShowSubTotals` property of pivot grid control is set to false, then hiding the subtotals of specific pivot item will do nothing.

Please refer the below code sample.  

{% tabs %}

{% highlight XAML %}

<pivotitem:PivotItem FieldHeader="Date" FieldMappingName="Date" TotalHeader="Total" ShowSubTotal="False"/>
    
{% endhighlight %}

{% highlight c# %}

this.pivotGrid1.PivotRows.Add(new PivotItem { FieldHeader = "Date", FieldMappingName = "Date", TotalHeader = "Total", ShowSubTotal = false });

{% endhighlight %}

{% highlight vb %}

pivotGrid.PivotRows.Add(New PivotItem() With { _
    Key .FieldHeader = "Date", _
    Key .FieldMappingName = "Date", _
    Key .TotalHeader = "Total", _
    Key .ShowSubTotal = False _
})

{% endhighlight %}

{% endtabs %}

![Hiding-Sub-Totals_image4](Hiding-Sub-Totals_images/Hiding-Sub-Totals_image4.png)

A demo sample is available at the following location.
    
{System Drive}:\Users\Public\Documents\Syncfusion\Universal Windows&lt;Version Number&gt;\SampleBrowser\PivotGrid\PivotGrid\View\TotalsHiding.xaml