---
layout: post
title: Percent Display Mode in UWP SfNumericUpDown | Syncfusion®
description: The Percent Display Mode in SfNumericUpDown displays numeric data in Percent mode using the PercentDisplayMode property with Value option.
platform: uwp
control: SfNumericUpDown
documentation: ug
---

# Percent Display Mode in UWP NumericUpDown

With the PercentDisplayMode property, you can specify how to display numeric data in Percent mode. It provides the following options:

* Value: Displays the value with percentage symbol.
* Compute: Displays the computed value with percentage symbol.



The following code example and screen shots illustrate the usage of the PercentDisplayMode property.

{% tabs %}

{% highlight  XAML%}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfNumericUpDown x:Name="numericUpDown" HorizontalAlignment="Center" VerticalAlignment="Center" Width="200" Value="5" FormatString="P" PercentDisplayMode="Value"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Value;

{% endhighlight %}

{% highlight VB %}

 numericUpDown.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Value

{% endhighlight %}

{% endtabs %}

![PercentDisplayMode Value view](Concepts_images/Concepts_img8.png)

{% tabs %}

{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfNumericUpDown HorizontalAlignment="Center" x:Name="numericUpDown"

VerticalAlignment="Center" Width="200" Value="5" FormatString="P"

PercentDisplayMode="Compute"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight c# %}

numericUpDown.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Compute;

{% endhighlight %}

{% highlight VB %}

 numericUpDown.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Compute

{% endhighlight %}

{% endtabs %}

![PercentDisplayMode Compute view](Concepts_images/Concepts_img9.png)
