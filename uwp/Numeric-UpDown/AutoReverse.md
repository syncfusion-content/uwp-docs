---
layout: post
title: AutoReverse in UWP SfNumericUpDown | Syncfusion®
description: The AutoReverse feature in SfNumericUpDown cycles the value from Minimum once it reaches Maximum and vice versa during incrementing.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# AutoReverse in UWP NumericUpDown

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
