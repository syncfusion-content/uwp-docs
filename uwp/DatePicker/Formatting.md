---
layout: post
title: Formatting in UWP DatePicker control | Syncfusion®
description: Learn here all about Formatting support in Syncfusion® UWP DatePicker (SfDatePicker) control and more.
platform: uwp
control: SfDatePicker
documentation: ug
---

# Formatting in UWP DatePicker (SfDatePicker)

The SfDatePicker control allows the user to format the display text in various ways.

## Using the FormatString

The FormatString property determines the format specifier by which the display text has to be formatted.

The following code sample shows how to create a date picker with a [month day pattern](https://learn.microsoft.com/en-us/dotnet/api/system.globalization.datetimeformatinfo.monthdaypattern?view=net-9.0&redirectedfrom=MSDN#System_Globalization_DateTimeFormatInfo_MonthDayPattern): 

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

![Features_img1](Features_images/Features_img1.png)

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

![Features_img2](Features_images/Features_img2.png)


N> A detailed explanation of standard date time formatting is available [here](https://learn.microsoft.com/en-us/previous-versions/dotnet/netframework-1.1/az4se3k1(v=vs.71)). The result string produced by these format specifiers are influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.
