---
layout: post
title: Deals with  Formatting options of SfDatePicker control for UWP
description: Deals with  Formatting options of SfDatePicker control for UWP
platform: uwp
control: SfDatePicker
documentation: ug
---

# Formatting

The SfDatePicker control allows the user to format the display text in various ways.

## Using the FormatString

The FormatString property determines the format specifier by which the display text has to be formatted.

The following code sample shows how to create a date picker with a [month day pattern](http://msdn.microsoft.com/en-us/library/system.globalization.datetimeformatinfo.monthdaypattern(v=vs.71).aspx): 

{% tabs %}

{% highlight xaml %}



<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfDatePicker VerticalAlignment="Center" x:Name="sfdatePicker"

                                   Width="200" Margin="15"

                                   FormatString="M"/>



</Grid>


{% endhighlight  %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 sfdatePicker.FormatString = "M";

{% endhighlight  %}

{% highlight VB %}

 sfdatePicker.FormatString = "M"

{% endhighlight %}

{% endtabs %}

![](Features_images/Features_img1.png)

## Specifying format for the DateSelector

The SelectorFormatString property used to specify format for the DateSelector


{% tabs %}

{% highlight xaml %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <syncfusion:SfDatePicker SelectorFormatString="M"   x:Name="sfdatePicker" VerticalAlignment="Center"  Width="200" Margin="15" />

</Grid>

{% endhighlight  %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

sfdatePicker.SelectorFormatString = "M";

{% endhighlight  %}

{% highlight VB %}

sfdatePicker.SelectorFormatString = "M"

{% endhighlight  %}

{% endtabs %}

![](Features_images/Features_img2.png)


N> A detailed explanation of standard date time formatting is available [here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.
