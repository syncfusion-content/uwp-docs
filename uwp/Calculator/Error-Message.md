---
layout: post
title: Error Message in UWP SfCalculator | Syncfusion®
description: The error message feature in SfCalculator notifies invalid input and syntax errors through the ErrorMessageDisplayed event with customizable NewErrorMessage.
platform: uwp
control: SfCalculator
documentation: ug
---

# Error Message in UWP Calculator

`UWP Calculator` provides `ErrorMessageDisplayed` event to notify invalid input and syntax errors. Default error message is “Invalid input” and it can be modified by setting the event argument NewErrorMessage.

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

{% highlight VB %}

Private Sub calculator_ErrorMessageDisplayed(ByVal Sender As Object, ByVal args As Syncfusion.UI.Xaml.Controls.Input.ErrorDisplayArgs)


args.NewErrorMessage = "Syntax Error"

End Sub

{% endhighlight %}

{% endtabs %}



