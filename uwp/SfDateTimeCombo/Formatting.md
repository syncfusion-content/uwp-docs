---
layout: post
title: Deals with formatting the text of SfDateTimeCombo control for UWP
description: Deals with formatting the text of SfDateTimeCombo control for UWP
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Formatting

The SfDateTimeCombo control allows the user to format the display text in various ways.

## Using the FormatString

The FormatString property determines the format specifier by which the DateTime has to be formatted.

{% highlight html %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

            <syncfusion:SfDateTimeCombo FormatString="hms"

                               Width="350" HorizontalAlignment="Left"/>
</Grid>

{% endhighlight %}

![](Formatting_images/Formatting_img1.png)

N>  The result string produced by these format specifiers is influenced by the settings in the Regional Options control panel. Computers with different cultures or different date and time settings will generate different result strings.