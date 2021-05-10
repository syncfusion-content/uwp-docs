---
layout: post
title: ParsingMode in UWP Numeric UpDown control | Syncfusion
description: Learn here all about ParsingMode support in Syncfusion UWP Numeric UpDown (SfNumericUpDown) control and more.
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# ParsingMode in UWP Numeric UpDown (SfNumericUpDown)

Value of the SfNumericUpDown gets parsed based on ParsingMode property. ParsingMode is of type Parsers which is enum of Double and Decimal. DefaultValue for ParsingMode is Double.

{% tabs %}

{% highlight XAML %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown HorizontalAlignment="Center" x:Name="numericUpDown"

                                 VerticalAlignment="Center"

                                 Width="250" 

                                 ParsingMode="Decimal"

                                 Value="123.459999999999999999"/>

    </Grid>

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.ParsingMode = Syncfusion.UI.Xaml.Controls.Input.Parsers.Decimal;

{% endhighlight %}

{% highlight VB %}

numericUpDown.ParsingMode = Syncfusion.UI.Xaml.Controls.Input.Parsers.Decimal

{% endhighlight %}

{% endtabs %}

N>The `ParsingMode` should be set based on the data type. For example, if a `Decimal` type property is bound to Value property of SfNumericUpDown, then the `ParsingMode` should be set as `Decimal`.

![ParsingMode view](Concepts_images/Concepts_img7.png)
