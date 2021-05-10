---
layout: post
title: Percent Display Mode in UWP Numeric TextBox control | Syncfusion
description: Learn here all about Percent Display Mode support in Syncfusion UWP Numeric TextBox (SfNumericTextBox) control and more.
platform: uwp
control: SfNumeric TextBox
documentation: ug
---

# Percent Display Mode in UWP Numeric TextBox (SfNumericTextBox)

With the PercentDisplayMode property, you can specify how to display numeric data in Percent mode. It provides the following options:

* Value: Displays the value with percentage symbol.
* Compute: Displays the computed value with percentage symbol.



The following code example and screen shots illustrate the usage of the PercentDisplayMode property.

{% tabs %}

{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfNumericTextBox x:Name="numericTextBox" HorizontalAlignment="Center" VerticalAlignment="Center" Width="200" Value="5" FormatString="P" PercentDisplayMode="Value"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 numericTextBox.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Value;

{% endhighlight %}

{% highlight VB %}

 numericTextBox.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Value

{% endhighlight %}

{% endtabs %}

![PercentDisplayMode Value view](Concepts_images/Concepts_img8.png)

{% tabs %}

{% highlight XAML %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfNumericTextBox HorizontalAlignment="Center" x:Name="numericTextBox"

VerticalAlignment="Center" Width="200" Value="5" FormatString="P"

PercentDisplayMode="Compute"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 numericTextBox.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Compute;

{% endhighlight %}

{% highlight VB %}

 numericTextBox.PercentDisplayMode = Syncfusion.UI.Xaml.Controls.Input.PercentDisplayMode.Compute

{% endhighlight %}

{% endtabs %}

![PercentDisplayMode Compute view](Concepts_images/Concepts_img9.png)
