---
layout: post
title: Show Calculations as Columns or Rows | SfPivotClient | UWP | Syncfusion
description: Show Calculations in Columns or Rows
platform: UWP
control: SfPivotClient
documentation: ug
---

# Show Calculations as Columns or Rows

SfPivotClient provides support to show the calculation values as columns or rows by using the property of `ShowCalculationsAsColumns`. By default, its value is true. To view the calculation values in the row, it should be set as false.

There are two ways to enable or disable this feature as illustrated below:

**Using code**

The calculations can be displayed as columns or rows by setting the "ShowCalculationsAsColumns" property of the SfPivotClient.

Please refer the below code snippet to display the calculations as column.

{% tabs %}

{% highlight xaml %}

<syncfusion:SfPivotClient x:Name="pivotClient" ShowCalculationsAsColumns="True" />

{% endhighlight %}

{% highlight C# %}

this.pivotClient.ShowCalculationsAsColumns = true;

{% endhighlight %}

{% highlight vb %}

Me.pivotClient.ShowCalculationsAsColumns = True

{% endhighlight %}

{% endtabs %}

## Using pivot table field list

You can enable or disable this support by using the "Show Calculations as Column” check box available in the PivotTableFieldList.

![](Show-Calculations-As-Columns-Rows_images/Show-Calculations-As-Columns_image1.png)
_PivotClient displaying calculations as columns_

![](Show-Calculations-As-Columns-Rows_images/Show-Calculations-As-Columns_image2.png)
_PivotClient displaying calculations as rows_