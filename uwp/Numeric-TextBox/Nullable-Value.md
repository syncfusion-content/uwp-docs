---
layout: post
title:  Nullable Value options of SfNumericTextBox control for UWP
description: Nullable Value options of SfNumericTextBox control for UWP
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Nullable Value

The control will allow user to set Null Value. The AllowNull property needs to be set to make this behavior work. By default the property value is false.

{% highlight html %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">



    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericTextBox x:Name="numericTextBox"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

AllowNull="True"

                               Value="{x:Null}"/>

    </Grid>

</Page>

{% endhighlight %}

![Nullable NumericTextBox view](Concepts_images/Concepts_img6.png)