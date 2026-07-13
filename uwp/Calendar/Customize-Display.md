---
layout: post
title: Customize Display in UWP Calendar control | Syncfusion
description: Learn here all about Customize Display support in the Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Customize Display in UWP Calendar (SfCalendar)

`SfCalendar` allows customizing the first day of the week and the day name display mode.

## Customize First Day of Week

The first day of the week is changeable in SfCalendar. It is set using the `FirstDayofWeek` property. The Refresh method can be used to refresh the layout when setting it at run time doesn't reflect in the UI.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" FirstDayofWeek="Thursday"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.FirstDayofWeek = System.DayOfWeek.Thursday;

{% endhighlight %}

{% highlight VB %}

calendar.FirstDayofWeek = System.DayOfWeek.Thursday

{% endhighlight %}

{% endtabs %}


![SfCalendar-img13](SfCalendar-images/SfCalendar-img13.jpeg)


## Customize Day Name Display Mode

Day names in SfCalendar can be set to either abbreviated or full names using the `DayNameDisplayMode` property.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" DayNameDisplayMode="DayNames"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}


calendar.DayNameDisplayMode = Syncfusion.UI.Xaml.Controls.Input.DayNameDisplayMode.DayNames;

{% endhighlight %}

{% highlight VB %}


calendar.DayNameDisplayMode = Syncfusion.UI.Xaml.Controls.Input.DayNameDisplayMode.DayNames

{% endhighlight %}

{% endtabs %}


![SfCalendar-img14](SfCalendar-images/SfCalendar-img14.jpeg)


