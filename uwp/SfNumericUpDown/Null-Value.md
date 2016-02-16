---
layout: post
title: Null Value options of SfNumericUpDown control for UWP
description: Null Value options of SfNumericUpDown control for UWP
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# Null Value

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

![](Concepts_images/Concepts_img6.png)