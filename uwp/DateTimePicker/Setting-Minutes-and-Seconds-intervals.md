---
layout: post
title: Set Minute and Second Intervals in UWP DateTimePicker | Syncfusion
description: Learn here all about Setting Minutes and Seconds Intervals support in Syncfusion UWP DateTimePicker (SfDateTimeCombo) control and more.
platform: uwp
control: SfDateTimeCombo
documentation: ug
---

# Setting Minutes and Seconds Intervals in UWP DateTimePicker  (SfDateTimeCombo)

MinuteInterval and SecondsInterval properties can be used to specify the interval for minutes and seconds to be displayed in the SfDateTimeCombo control.

The following code examples and screenshots illustrate this.


{% tabs %}

{% highlight XAML %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <syncfusion:SfDateTimeCombo FormatString="hmst" x:Name="combo" Width="350" HorizontalAlignment="Left" MinuteInterval="10" SecondsInterval="15"/>    

</Page>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

using Syncfusion.UI.Xaml.Controls.Input;

combo.MinuteInterval = 10;

combo.SecondsInterval = 15;

{% endhighlight %}

{% highlight VB %}

Imports Syncfusion.UI.Xaml.Controls.Input;

combo.MinuteInterval = 10

combo.SecondsInterval = 15

{% endhighlight %}

{% endtabs %}

### MinuteInterval

![Minutes-and-Seconds-intervals_img1](Minutes-and-Seconds-intervals_images/Minutes-and-Seconds-intervals_img1.png)





### SecondsInterval

![Minutes-and-Seconds-intervals_img2](Minutes-and-Seconds-intervals_images/Minutes-and-Seconds-intervals_img2.png)





