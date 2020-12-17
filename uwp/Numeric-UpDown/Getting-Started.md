---
layout: post
title: Getting Started with the Syncfusion SfNumericUpDown control for UWP 
description: A quick tour to the initial users on the Syncfusion SfNumericUpDown for UWP Platform and also explains how to set the value for the control.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# Getting Started with SfNumericUpDown

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