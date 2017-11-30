---
layout: post
title: Display Options | SfPivotGrid | UWP | Syncfusion
description: display options
platform: UWP
control: SfPivotGrid
documentation: ug
---

# Display Options

SfPivotGrid control provides support for PivotComputationInfo to display calculation values in preferred areas of SfPivotGrid with the help of `DisplayOption` property. The following are the different kinds of display options available in SfPivotGrid.

**All Option**

This option displays all the calculation values in all columns of SfPivotGrid. Please refer below the code snippet.

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

![](Display-Options_images/PivotComputationinfo-using-All-option.png)

**Summary Option**

Summary option is used to display only the calculation values in summary columns of SfPivotGrid. Please refer below the code snippet.

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

![](Display-Options_images/PivotComputationinfo-using-summary-option.png)

**Calculations Option**

Calculation option displays only the calculation values in value columns other than summary and grand total of SfPivotGrid. Please refer below the code snippet.

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

![](Display-Options_images/PivotComputationinfo-using-calculations-option.png)

**GrandTotal Option**

GrandTotal option is used to display only the calculation values in grand total columns of SfPivotGrid. Please refer below the code snippet.

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

![](Display-Options_images/PivotComputationinfo-using-Grand-Totals-option.png)

**None Option**

This option hides all the calculation values in all columns of SfPivotGrid. Please refer below the code snippet.

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

![](Display-Options_images/PivotComputationinfo-using-none-option.png)

A demo sample is available at the following location.

{system drive}:\Users\&lt;User Name&gt;\AppData\Local\Syncfusion\EssentialStudio\&lt;Version Number&gt;\Samples\UWP\SampleBrowser\PivotGrid\PivotGrid\View\SummaryDisplay.xaml