---
layout: post
title: Displaying Minimum and Maximum Dates of SfDateTimeCombo control for UWP
description: displaying minimum and maximum dates of SfDateTimeCombo control for UWP
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Displaying Minimum and Maximum Dates

TO display the minimum and maximum dates in SfDateTimeCombo, use DisplayMinDate and DisplayMaxDate properties respectively.

The following code example and screen shots illustrate this.

{% tabs %}

{% highlight html %}

<Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">

<syncfusion:SfDateTimeCombo FormatString="mdy" x:Name="combo" Width="350" HorizontalAlignment="Left"/>   

</Grid> 

{% endhighlight %}

{% highlight c# %}

combo.DisplayMinDate = new DateTime(2012,10,2);

combo.DisplayMaxDate = new DateTime(2013,11,22);

{% endhighlight %}

{% endtabs %}

![](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img1.png)

![](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img2.png)

![](Displaying-Minimum-and-Maximum-Dates_images/Displaying-Minimum-and-Maximum-Dates_img3.png)