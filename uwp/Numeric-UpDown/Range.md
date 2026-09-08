---
layout: post 
title: Range in UWP SfNumericUpDown | Syncfusion®
description: The Range feature in SfNumericUpDown restricts input values to a specific range using the Maximum and Minimum properties.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# Range in UWP NumericUpDown

Input values can be restricted to a specific range by setting the Maximum and Minimum properties.

## Maximum

The maximum possible value that user can set to the control.

{% tabs %}

{% highlight XAML %}

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

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.Maximum = 100;

{% endhighlight %}

{% highlight VB %}

 numericUpDown.Maximum = 100

{% endhighlight %}

{% endtabs %}

## Minimum

The Minimum possible value that user can set to the control.

{% tabs %}

{% highlight XAML %}

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

{% endtabs %}

{% tabs %}

{% highlight c# %}

 numericUpDown.Minimum = 50;

{% endhighlight %}

{% highlight VB %}

 numericUpDown.Minimum = 50

{% endhighlight %}

{% endtabs %}

## See also

[How to set the maximum and minimum value in UWP NumericUpDown control](https://www.syncfusion.com/kb/6958/how-to-set-the-maximum-and-minimum-value-in-sfnumericupdown-control)

[How to increment and decrement the value of UWP NumericUpDown control](https://www.syncfusion.com/kb/6961/how-to-increment-and-decrement-the-value-of-sfnumericupdown-control)
