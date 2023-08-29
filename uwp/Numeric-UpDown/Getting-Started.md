---
layout: post
title: Getting Started with UWP Numeric UpDown control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Numeric UpDown (SfNumericUpDown) control, its elements and more.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# Getting Started with UWP Numeric UpDown (SfNumericUpDown)

Namespace:  Syncfusion.UI.Xaml.Controls.Input
Assembly:  Syncfusion.SfInput.UWP

Dependent assembly: Syncfusion.SfShared.UWP

The following code sample shows how to create the SfNumericUpDown from code-behind and XAML,

{% tabs %}
{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

                               Value="123.45"/>

    </Grid>

</Page>

{% endhighlight %}

{% highlight  c# %}

 SfNumericUpDown numericUpDown = new SfNumericUpDown() { Width = 200, Value = 123.45 };

{% endhighlight %}

{% highlight  VB %}

Dim numericUpDown As New SfNumericUpDown() With {
	.Width = 200,
	.Value = 123.45
}

{% endhighlight %}

{% endtabs %}

## See also

[How to restrict the decimal values in SfNumericUpDown](https://www.syncfusion.com/kb/6508/how-to-restrict-the-decimal-values-in-sfnumericupdown)

[How to increment and decrement the value of SfNumericUpDown control](https://www.syncfusion.com/kb/6961/how-to-increment-and-decrement-the-value-of-sfnumericupdown-control)