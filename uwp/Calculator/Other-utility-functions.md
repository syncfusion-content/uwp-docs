---
layout: post
title: Utilities in UWP Calculator control | Syncfusion®
description: Learn here all about Utilities support in Syncfusion® UWP Calculator (SfCalculator) control and more.
platform: UWP
control: SfCalculator
documentation: ug
---

# Utilities in UWP Calculator (SfCalculator)

Several utility functions are available in `SfCalculator` control.

## Identifying the Operation

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

{% highlight VB %}

Dim [function] As CalculatorFunctions = calculator.CheckFunction("/")

functionText.Text = "The function is: " & [function].ToString()

{% endhighlight %}

{% endtabs %}

![Other-utility-functions-img1](Other-utility-functions-images/Other-utility-functions-img1.jpeg)


## Clear the Expression

`Clear` function is used to clear both the expression and value in `SfCalculator`.

{% tabs %}

{% highlight C# %}

calculator.Clear();

{% endhighlight %}

{% highlight VB %}

calculator.Clear()

{% endhighlight %}

{% endtabs %}

## Clear the Value

`ClearEntry` function is used to clear the entered/computed value in `SfCalculator`.

{% tabs %}

{% highlight C# %}

calculator.ClearEntry();

{% endhighlight %}

{% highlight VB %}

calculator.ClearEntry()

{% endhighlight %}

{% endtabs %}

## Clear and Reset the Expression

`Reset` function is used to clear and reset the expression.

{% tabs %}

{% highlight C# %}

calculator.Reset();

{% endhighlight %}

{% highlight VB %}

calculator.Reset()

{% endhighlight %}

{% endtabs %}

## Removing Trailing Zeros

`TrailingZeros` method is used to remove the trailing zeros at the end of value.

{% tabs %}

{% highlight C# %}

calculator.TrailingZeros();

{% endhighlight %}

{% highlight VB %}

calculator.TrailingZeros()

{% endhighlight %}

{% endtabs %}

## Change Separators based on Culture

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

{% highlight VB %}

calculator.Culture = New System.Globalization.CultureInfo("de-DE")

{% endhighlight %}

{% endtabs %}

![Other-utility-functions-img2](Other-utility-functions-images/Other-utility-functions-img2.jpeg)
