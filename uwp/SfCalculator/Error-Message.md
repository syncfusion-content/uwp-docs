---
layout: post
title: Error Message of SfCalculator control for UWP 
description: Error Message of SfCalculator control for UWP
platform: uwp
control: SfCalculator
documentation: ug
---

# Error Message

`SfCalculator` provides `ErrorMessageDisplayed` event to notify invalid input and syntax errors. Default error message is “Invalid input” and it can be modified by setting the event argument NewErrorMessage.

{% tabs %}

{% highlight XAML %}

<input:SfCalculator ErrorMessageDisplayed="calculator_ErrorMessageDisplayed"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void calculator_ErrorMessageDisplayed(object Sender, Syncfusion.UI.Xaml.Controls.Input.ErrorDisplayArgs args)

{

args.NewErrorMessage = "Syntax Error";

}

{% endhighlight %}

{% endtabs %}



