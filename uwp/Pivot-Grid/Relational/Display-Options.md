---
layout: post
title: Display Options in UWP Pivot Grid control | Syncfusion
description: Learn here all about Display Options support in Syncfusion UWP Pivot Grid (SfPivotGrid) control and more.
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Display Options in UWP Pivot Grid (SfPivotGrid)

The SfPivotGrid control provides support for PivotComputationInfo to display calculation values in preferred areas of the SfPivotGrid with the help of `DisplayOption` property. The following are the different types of display options available in the SfPivotGrid.

**All option**

This option displays all the calculation values in all columns of the SfPivotGrid. Refer to the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid Name="PivotGrid1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotGrid.PivotCalculations>
        <pivotanalysis:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="All"/>
    </syncfusion:SfPivotGrid.PivotCalculations>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.PivotCalculations[0].DisplayOption = DisplayOption.All;

{% endhighlight %}

{% highlight VB %}

pivotGrid.PivotCalculations(0).DisplayOption = DisplayOption.All

{% endhighlight %}

{% endtabs %}

![PivotComputationinfo-using-All-option](Display-Options_images/PivotComputationinfo-using-All-option.png)

**Summary option**

The summary option is used to display only the calculation values in summary columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid Name="PivotGrid1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotGrid.PivotCalculations>
        <pivotanalysis:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="Summary"/>
    </syncfusion:SfPivotGrid.PivotCalculations>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.PivotCalculations[0].DisplayOption = DisplayOption.Summary;

{% endhighlight %}

{% highlight VB %}

pivotGrid.PivotCalculations(0).DisplayOption = DisplayOption.Summary

{% endhighlight %}

{% endtabs %}

![PivotComputationinfo-using-summary-option](Display-Options_images/PivotComputationinfo-using-summary-option.png)

**Calculations option**

The calculation option displays only the calculation values in value columns other than summary and grand total values of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid Name="PivotGrid1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotGrid.PivotCalculations>
        <pivotanalysis:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="Calculations"/>
    </syncfusion:SfPivotGrid.PivotCalculations>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.PivotCalculations[0].DisplayOption = DisplayOption.Calculations;

{% endhighlight %}

{% highlight VB %}

pivotGrid.PivotCalculations(0).DisplayOption = DisplayOption.Calculations

{% endhighlight %}

{% endtabs %}

![PivotComputationinfo-using-calculations-option](Display-Options_images/PivotComputationinfo-using-calculations-option.png)

**GrandTotal option**

The grand total option is used to display only the calculation values in grand total columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid Name="PivotGrid1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotGrid.PivotCalculations>
        <pivotanalysis:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="GrandTotal"/>
    </syncfusion:SfPivotGrid.PivotCalculations>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.PivotCalculations[0].DisplayOption = DisplayOption.GrandTotal;

{% endhighlight %}

{% highlight VB %}

pivotGrid.PivotCalculations(0).DisplayOption = DisplayOption.GrandTotal

{% endhighlight %}

{% endtabs %}

![PivotComputationinfo-using-Grand-Totals-option](Display-Options_images/PivotComputationinfo-using-Grand-Totals-option.png)

**None option**

This option hides all the calculation values in all columns of the SfPivotGrid.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotGrid Name="PivotGrid1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotGrid.PivotCalculations>
        <pivotanalysis:PivotComputationInfo CalculationName="Total" FieldName="Amount" DisplayOption="None"/>
    </syncfusion:SfPivotGrid.PivotCalculations>
</syncfusion:SfPivotGrid>

{% endhighlight %}

{% highlight C# %}

PivotGrid1.PivotCalculations[0].DisplayOption = DisplayOption.None;

{% endhighlight %}

{% highlight VB %}

pivotGrid.PivotCalculations(0).DisplayOption = DisplayOption.None

{% endhighlight %}

{% endtabs %}

![PivotComputationinfo-using-none-option](Display-Options_images/PivotComputationinfo-using-none-option.png)

A demo sample is available in the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\SummaryDisplay.xaml
