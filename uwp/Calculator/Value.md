---
layout: post
title: Value in UWP Calculator control | Syncfusion®
description: Learn here all about Value support in Syncfusion® UWP Calculator (SfCalculator) control and more.
platform: uwp
control: SfCalculator
documentation: ug
---

# Value in UWP Calculator (SfCalculator)

## Retrieving Computed Value

`Value` property in the `SfCalculator` control is used to retrieve the computed value from the expressions in Calculator. It is a read-only decimal property. It can also be set to display a decimal value as computed value.

{% tabs %}

{% highlight XAML %}

<Grid>

<TextBlock Text="{Binding ElementName=calculator,Path=Value}"/>

<input:SfCalculator x:Name="calculator"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

decimal value = calculator.Value;

{% endhighlight %}

{% highlight VB %}

 Dim calculator As New SfCalculator()

{% endhighlight %}

{% endtabs %}

## Displaying a Default Value

`DefaultValue` property is set to display a default value in the input pane of `SfCalculator` control. It is a decimal property.  

{% tabs %}

{% highlight C# %}

calculator.DefaultValue = 34.67M;

{% endhighlight %}

{% highlight VB %}

calculator.DefaultValue = 34.67D

{% endhighlight %}


{% endtabs %}

![SfCalculator-img4](SfCalculator-images/SfCalculator-img4.jpeg)

## Showing Text in Display Panel

`DisplayText` property is set to display a text in the display pane of `SfCalculator` control.

{% tabs %}

{% highlight XAML %}

<input:SfCalculator x:Name="calculator" DisplayText="Display Text"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calculator.DisplayText = "DisplayText";

{% endhighlight %}

{% highlight VB %}

calculator.DisplayText = "DisplayText"

{% endhighlight %}

{% endtabs %}


## Displaying an Expression

`Expression` property is used to get the mathematical expression that produced the evaluated value in `SfCalculator`. `Expression` can also set to any string property but it is not evaluated to produce result. It is just displayed in the pane.

{% tabs %}

{% highlight XAML %}

<Grid>

<TextBlock Text="{Binding ElementName=calculator,Path=Expression}"/>

<input:SfCalculator x:Name="calculator" Expression="1+2+3+4"/>

</Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calculator.Expression = "1+2+3+4";

string expression = calculator.Expression;

{% endhighlight %}

{% highlight VB %}

calculator.Expression = "1+2+3+4"

Dim expression As String = calculator.Expression

{% endhighlight %}


{% endtabs %}

