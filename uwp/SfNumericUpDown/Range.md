---
layout: post 
title: Restrict the input values of SfNumerupDown to a specified Range 
description: Restrict the input values of SfNumerupDown to a specified Range 
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# Range

Input values can be restricted to a specific range by setting the Maximum and Minimum properties.

## Maximum

The maximum possible value that user can set to the control.

{% highlight html %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

Maximum="100"

                               Value="120"/>

    </Grid>

</Page>

{% endhighlight %}

## Minimum

The Minimum possible value that user can set to the control.

{% highlight html %}

<Page xmlns:editors="using:Syncfusion.UI.Xaml.Controls.Input">

    <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">



        <editors:SfNumericUpDown x:Name="numericUpDown"

                               HorizontalAlignment="Center"

                               VerticalAlignment="Center"

                               Width="200" 

Minimum="50"

                               Value="5"/>

    </Grid>

</Page>

{% endhighlight %}