---
layout: post
title: Show Calculations as Columns in UWP Pivot Client control | Syncfusion®
description: Learn here all about Show Calculations as Columns or Rows support in Syncfusion® UWP Pivot Client (SfPivotClient) control and more.
platform: uwp
control: SfPivotClient
documentation: ug
---

# Show Calculations as Columns or Rows in UWP Pivot Client (SfPivotClient)

The SfPivotClient supports showing the calculation values as columns or rows by using the `ShowCalculationsAsColumns` property. By default, its value is true. To view the calculation values in the row, it should be set to false.

There are two ways to enable or disable this feature as illustrated below.

**Using code**

The calculations can be displayed in columns or rows by setting the `ShowCalculationsAsColumns` property of the SfPivotClient.

Refer to the following code snippet to display the calculations in column.

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

![Show-Calculations-As-Columns_image1](Show-Calculations-As-Columns-Rows_images/Show-Calculations-As-Columns_image1.png)
_PivotClient displaying calculations as columns_

![Show-Calculations-As-Columns_image2](Show-Calculations-As-Columns-Rows_images/Show-Calculations-As-Columns_image2.png)
_PivotClient displaying calculations as rows_
