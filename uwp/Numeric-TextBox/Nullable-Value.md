---
layout: post
title: Nullable Value in UWP SfNumericTextBox | Syncfusion®
description: The Nullable Value feature in SfNumericTextBox allows setting null values using the AllowNull property, enabling empty state support.
platform: uwp
control: SfNumericTextBox
documentation: ug
---

# Nullable Value in UWP SfNumericTextBox

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
