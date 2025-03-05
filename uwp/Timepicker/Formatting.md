---
layout: post
title: Formatting in UWP TimePicker control | Syncfusion®
description: Learn here all about Formatting support in Syncfusion® UWP TimePicker (SfTimePicker) control and more.
platform: uwp
control: SfTimePicker
documentation: ug
---

# Formatting in UWP TimePicker (SfTimePicker)

The SfTimePicker control allows users to format the display text in various ways.



## Using the FormatString

The FormatString property determines the format specifier by which the display text has to be formatted.

The example below shows how to create a time picker with a [Long Time pattern](http://msdn.microsoft.com/en-us/library/system.globalization.datetimeformatinfo.longtimepattern(v=vs.71).aspx).

{% tabs %}

{% highlight xaml %}

 
   <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfTimePicker VerticalAlignment="Center" 

                                   Width="200" Margin="15"

                                   FormatString="HH:mm:ss"/>

   </Grid>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 timePicker.FormatString = "HH:mm:ss";

{% endhighlight %}

{% highlight VB %}

 timePicker.FormatString = "HH:mm:ss"

{% endhighlight %}

{% endtabs %}

![Features_img1](Features_images/Features_img1.png)

## Specifying format for the TimeSelector

The SelectorFormatString property used to specify format for the TimeSelector



{% tabs %}

{% highlight xaml %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

    <syncfusion:SfTimePicker HorizontalAlignment="Center" VerticalAlignment="Center" 

                                   Width="200" Margin="15"

                                   SelectorFormatString="HH:mm:ss"/>
</Grid>

{% endhighlight  %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

 timePicker.SelectorFormatString = "HH:mm:ss";

{% endhighlight %}

{% highlight VB %}

 timePicker.SelectorFormatString = "HH:mm:ss"

{% endhighlight %}

{% endtabs %}

![Features_img2](Features_images/Features_img2.png)

N>  A detailed explanation of standard date time formatting is available[here](http://msdn.microsoft.com/en-us/library/az4se3k1(v=vs.71).aspx). The result string produced by these format specifiers is influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.
