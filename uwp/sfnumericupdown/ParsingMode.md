---
layout: post
title: ParsingMode options in SfNumericUpDown control 
description:  ParsingMode options in SfNumericUpDown control 
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# ParsingMode

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

![ParsingMode view](Concepts_images/Concepts_img7.png)
