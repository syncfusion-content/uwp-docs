---
layout: post
title: AutoReverse in UWP SfNumericUpDown | Syncfusion®
description: Learn about the AutoReverse feature in the Syncfusion® UWP SfNumericUpDown control that cycles between Minimum and Maximum values.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# AutoReverse in UWP SfNumericUpDown

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
