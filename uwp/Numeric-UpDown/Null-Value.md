---
layout: post
title: Null Value in UWP SfNumericUpDown | Syncfusion®
description: The Null Value feature in SfNumericUpDown allows setting null values using the AllowNull property, enabling empty state support.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# Null Value in UWP SfNumericUpDown

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
