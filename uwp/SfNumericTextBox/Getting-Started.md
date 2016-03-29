---
layout: post
title: Getting Started with SfNumericTextBox control for UWP
description: A quick tour to initial users on SfNumericTextBox control for UWP
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Getting Started

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