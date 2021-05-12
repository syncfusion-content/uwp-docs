---
layout: post
title: Null Value in UWP Numeric UpDown control | Syncfusion
description: Learn here all about Null Value support in Syncfusion UWP Numeric UpDown (SfNumericUpDown) control and more.
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# Null Value in UWP Numeric UpDown (SfNumericUpDown)

The control will allow user to set Null Value. The AllowNull property needs to be set to make this behavior work. By default the property value is false.

{% highlight html %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200"

AllowNull="True"

                               Value="{x:Null}"/>

    </Grid>

</Page>

{% endhighlight %}

![NumericUpDown Null value view](Concepts_images/Concepts_img6.png)
