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

{% highlight html %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown HorizontalAlignment="Center"

                                 VerticalAlignment="Center"

                                 Width="250" 

                                 ParsingMode="Decimal"

                                 Value="123.459999999999999999"/>

    </Grid>

</Page>

{% endhighlight %}

![](Concepts_images/Concepts_img7.png)
