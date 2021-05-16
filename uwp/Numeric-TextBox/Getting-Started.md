---
layout: post
title: Getting Started with UWP Numeric TextBox control | Syncfusion
description: Learn here all about getting started with Syncfusion UWP Numeric TextBox (SfNumericTextBox) control and more.
platform: uwp
control: SfNumericTextBox
documentation: ug
---

# Getting Started with UWP Numeric TextBox (SfNumericTextBox)

Namespace:  Syncfusion.UI.Xaml.Controls.Input
Assembly:  Syncfusion.SfInput.UWP 

Dependent assembly: Syncfusion.SfShared.UWP



The following code sample shows how to create the SfNumericTextBox from code-behind and XAML,
{% tabs %}
{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericTextBox HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

                               Value="123.45"/>



    </Grid>

</Page>

{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox = new SfNumericTextBox();

{% endhighlight %}

{% highlight VB %}

Dim numericTextBox As New SfNumericTextBox()

{% endhighlight %}

{% endtabs %}

## See also

[How to restrict the decimal values in SfNumericTextBox](https://www.syncfusion.com/kb/6957/how-to-restrict-the-decimal-values-in-sfnumerictextbox)