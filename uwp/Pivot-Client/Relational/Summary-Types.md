---
layout: post
title: Summary Types in UWP Pivot Client control | Syncfusion
description: Learn here all about Summary Types support in Syncfusion UWP Pivot Client (SfPivotClient) control and more.
platform: UWP
control: SfPivotClient
documentation: ug
---

# Summary Types in UWP Pivot Client (SfPivotClient)

The SfPivotClient supports summarizing the data for various data types by using the `SummaryType` property. This property should be defined while defining the pivot calculation by using the `PivotComputationInfo` class to specify the summary type. It holds the following summary types:

* **DoubleTotalSum**: Computes the sum of double or integer from pivot values for the corresponding pivot item.
* **DoubleAverage**: Computes the average of double or integer from pivot values for the corresponding pivot item.
* **DoubleMaximum**: Computes the maximum of double or integer from pivot values for the corresponding pivot item.
* **DoubleMinimum**: Computes the minimum of double or integer from pivot values for the corresponding pivot item.
* **DoubleStandardDeviation**: Computes the standard deviation of double or integer from pivot values for the corresponding pivot item.
* **DoubleVariance**: Computes the variance of double or integer from pivot values for the corresponding pivot item.
* **Count**: Computes the count of double or integer from pivot values for the corresponding pivot item.
* **DecimalTotalSum**: Computes the sum of decimal from pivot values for the corresponding pivot item.
* **IntTotalSum**: Computes the sum of integer from pivot values for the corresponding pivot item.
* **Custom**: Specifies that you are using a custom SummaryBase object to define the calculation.
* **DisplayIfDiscreteValuesEqual**: Displays the aggregated value in the pivot computation column if all the values are common.

The following code snippet shows how to set the summary type of the pivot calculation.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotClient Name="PivotClient1" ItemSource="{Binding ProductSalesData}"
                        PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotClient.PivotCalculations>
        <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Amount" Format="C" SummaryType="DoubleTotalSum" />
    </syncfusion:SfPivotClient.PivotCalculations>
</syncfusion:SfPivotClient>

{% endhighlight %}

{% highlight C# %}

PivotClient1.PivotCalculations.Add(new PivotComputationInfo { FieldName = "Amount", Format = "C", SummaryType = SummaryType.DoubleTotalSum });

{% endhighlight %}

{% highlight vb %}

PivotClient1.PivotCalculations.Add(New PivotComputationInfo() With { _
    Key .FieldName = "Amount", _
    Key .Format = "C", _
    Key .SummaryType = SummaryType.DoubleTotalSum _
})

{% endhighlight %}

{% endtabs %}

![custom_summary_type-image1](Summary-Types_images/custom_summary_type-image1.png)

## DisplayIfDiscreteValuesEqual SummaryType

**DisplayIfDiscreteValuesEqual** is a new summary type that displays the aggregated value in the pivot calculation column if all the values are common, else the default value will be displayed as **'*'**.

You can also change the default value to any custom string of your choice by using the `PadString` property as specified in the following code snippet.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotClient Name="PivotClient1" ItemSource="{Binding ProductSalesData}"
                          PivotRows="{Binding PivotRows}" PivotColumns="{Binding PivotColumns}">
    <syncfusion:SfPivotClient.PivotCalculations>
        <syncfusion:PivotComputationInfo CalculationName="Total" FieldName="Quantity" Format="#.##"                                                                     SummaryType="DisplayIfDiscreteValuesEqual" PadString="***"/>
    </syncfusion:SfPivotClient.PivotCalculations>
</syncfusion:SfPivotClient>

{% endhighlight %}

{% highlight C# %}

PivotClient1.PivotCalculations.Add(new PivotComputationInfo
{
    FieldName = "Quantity",
    Format = "#.##",
    SummaryType = SummaryType.DisplayIfDiscreteValuesEqual,
    PadString ="***"
});

{% endhighlight %}

{% highlight vb %}

PivotClient1.PivotCalculations.Add(New PivotComputationInfo() With { _
    Key .FieldName = "Quantity", _
    Key .Format = "#.##", _
    Key .SummaryType = SummaryType.DisplayIfDiscreteValuesEqual, _
    Key .PadString = "***" _
})

{% endhighlight %}

{% endtabs %}

![custom_summary_type-image2](Summary-Types_images/custom_summary_type-image2.png)
