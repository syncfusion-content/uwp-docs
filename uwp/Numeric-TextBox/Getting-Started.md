---
layout: post
title: Getting Started with UWP Numeric TextBox control | Syncfusion
description: Learn here about getting started with Syncfusion UWP Numeric TextBox (SfNumericTextBox) control, its elements and more.
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

[How to restrict the decimal values in SfNumericTextBox](https://support.syncfusion.com/kb/article/6346/how-to-restrict-the-decimal-values-in-sfnumerictextbox)

N> You can refer to our [UWP Numeric Textbox](https://www.syncfusion.com/uwp-ui-controls/numeric-textbox) feature tour page to know about its other groundbreaking feature representations. You can also explore our [UWP Numeric Textbox example](https://apps.microsoft.com/store/detail/syncfusion-essential-studio-for-uwp/9NBLGGH5WNGV) that shows you how to render and configure the Numeric textbox in UWP.