---
layout: post
title: Deside Decimal Digits in UWP Numeric Entry | Syncfusion
description: Here learn how to decide maximum decimal digits and default decimal digits support in UWP NumericTextBox.
platform: UWP
control: NumericTextBox
documentation: ug
---
# Decimal Digits in UWP Numeric Entry

## Set Maximum Number of Decimal Digits in UWP Numeric Entry

The maximum number of digits to be displayed after the decimal point can be specified by using the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfNumericTextBox.html#Syncfusion_UI_Xaml_Controls_Input_SfNumericTextBox_MaximumNumberDecimalDigits) property. 

N> The `MaximumNumberDecimalDigits` property can be provided with positive value only.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123.456" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

SfNumericTextBox numericTextBox=new SfNumericTextBox();
numericTextBox.Value = 123.456;
numericTextBox.MaximumNumberDecimalDigits=2;
this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value](images/MaximumNumberDecimalDigits.png)

## Remove Default Decimal Digits in UWP Numeric Entry

Based on the [`MaximumNumberDecimalDigits`](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfNumericTextBox.html#Syncfusion_UI_Xaml_Controls_Input_SfNumericTextBox_MaximumNumberDecimalDigits) property, the default number of decimal digits is displayed. By disabling the `AllowDefaultDecimalDigits` Boolean property, those default digits can be removed from the numeric entry view.

{% tabs %}

{% highlight xaml %}

	<syncfusion:SfNumericTextBox x:Name="numericTextBox" Value="123" AllowDefaultDecimalDigits="False" MaximumNumberDecimalDigits="2" />
	
{% endhighlight %}

{% highlight c# %}

            SfNumericTextBox numericTextBox = new SfNumericTextBox();
            numericTextBox.Value = 123;
            numericTextBox.MaximumNumberDecimalDigits = 2;
            numericTextBox.AllowDefaultDecimalDigits = false;
            this.Content = numericTextBox;
  
{% endhighlight %}

{% endtabs %}

![Display the textbox value without default decimal digits](images/AllowDefaultDecimalDigits.png)
