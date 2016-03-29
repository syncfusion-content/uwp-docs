---
layout: post
title: AutoReverse options of SfNumericUpDown control for UWP
description: AutoReverse options of SfNumericUpDown control for UWP
platform: uwp
control: SfNumeric UpDown
documentation: ug
---

# AutoReverse

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
