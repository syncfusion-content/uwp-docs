---
layout: post
title: AutoReverse in UWP Numeric UpDown control | Syncfusion
description: Learn here all about AutoReverse support in Syncfusion UWP Numeric UpDown (SfNumericUpDown) control and more.
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# AutoReverse in UWP Numeric UpDown (SfNumericUpDown)

While incrementing, the control will start from Minimum once it reaches the Maximum and vice-versa.

{% tabs %}

{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

        <syncfusion:SfNumericUpDown VerticalAlignment="Center" x:Name="numericUpDown"

                                  HorizontalAlignment="Center"

                                  Width="200" 

                                  Maximum="100"

                                  Minimum="0"

AutoReverse="True"/>



</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.AutoReverse = true;

{% endhighlight %}

{% highlight VB %}

numericUpDown.AutoReverse = True

{% endhighlight %}

{% endtabs %}
