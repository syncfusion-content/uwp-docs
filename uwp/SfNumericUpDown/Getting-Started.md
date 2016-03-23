---
layout: post
title: Getting Started with SfNumericUpDown control for UWP 
description: Getting Started with SfNumericUpDown control for UWP 
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# Getting Started

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