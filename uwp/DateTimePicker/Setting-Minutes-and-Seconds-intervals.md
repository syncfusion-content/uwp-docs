---
layout: post
title: Setting Minutes and Seconds Intervals in UWP DateTimePicker control | Syncfusion
description: Learn here all about Setting Minutes and Seconds Intervals support in Syncfusion UWP DateTimePicker (SfDateTimeCombo) control and more.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Setting Minutes and Seconds Intervals in UWP DateTimePicker (SfDateTimeCombo)

MinuteInterval and SecondInterval properties can be used to specify the interval for minutes and seconds to be displayed in the SfDateTimeCombo control

The following code examples and screenshots illustrate this.


{% tabs %}

{% highlight xaml %}

<syncfusion:SfDateTimeCombo FormatString="hmst" x:Name="combo" Width="350" HorizontalAlignment="Left" MinuteInterval="10" SecondsInterval="15"/>   

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

combo.MinuteInterval = 10;

combo.SecondsInterval = 15;

{% endhighlight %}

{% highlight VB %}

combo.MinuteInterval = 10

combo.SecondsInterval = 15

{% endhighlight %}

{% endtabs %}

### MinuteInterval

![Minutes-and-Seconds-intervals_img1](Minutes-and-Seconds-intervals_images/Minutes-and-Seconds-intervals_img1.png)





### SecondInterval

![Minutes-and-Seconds-intervals_img2](Minutes-and-Seconds-intervals_images/Minutes-and-Seconds-intervals_img2.png)





