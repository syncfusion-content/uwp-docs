---
layout: post
title: Utilities in SfCalculator control for UWP 
description: Utilities in SfCalculator control for UWP
platform: UWP
control: SfCalculator
documentation: ug
---

# Utilities

Several utility functions are available in `SfCalculator` control.

## Check Function

This method is used to identify the mathematical operation based on the input string.

{% tabs %}

{% highlight XAML %}

<StackPanel>

<TextBlock x:Name="functionText"/>

<input:SfCalculator x:Name="calculator"/>

</StackPanel>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

CalculatorFunctions function = calculator.CheckFunction("/");

functionText.Text = "The function is: " + function.ToString();

{% endhighlight %}

{% endtabs %}

![](Other-utility-functions-images/Other-utility-functions-img1.jpeg)


## Clear

`Clear` function is used to clear both the expression and value in `SfCalculator`.

{% tabs %}

{% highlight C# %}

calculator.Clear();

{% endhighlight %}

{% endtabs %}

## ClearEntry

`ClearEntry` function is used to clear the entered/computed value in `SfCalculator`.

{% tabs %}

{% highlight C# %}

calculator.ClearEntry();

{% endhighlight %}

{% endtabs %}

## Reset

`Reset` function is used to clear and reset the expression.

{% tabs %}

{% highlight C# %}

calculator.Reset();

{% endhighlight %}

{% endtabs %}

## TrailingZeros

`TrailingZeros` method is used to remove the trailing zeroes at the end of value.

{% tabs %}

{% highlight C# %}

calculator.TrailingZeros();

{% endhighlight %}

{% endtabs %}

## Culture

`SfCalculator` has Culture support that allows to have decimal separator symbols based on the culture.

{% tabs %}

{% highlight XAML %}

<input:SfCalculator x:Name="calculator"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calculator.Culture = new System.Globalization.CultureInfo("de-DE");

{% endhighlight %}

{% endtabs %}

![](Other-utility-functions-images/Other-utility-functions-img2.jpeg)


