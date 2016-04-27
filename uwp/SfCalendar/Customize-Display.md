---
layout: post
title: Customize Display on SfCalendar control for UWP
description: Customize Display on SfCalendar control for UWP
platform: uwp
control: SfCalendar
documentation: ug
---

# Customize Display

`SfCalendar` allows to customize the first day of the week and Day name display mode.

## Customize First Day of Week

First day of week is changeable in SfCalendar. It is set using the property `FirstDayOfWeek`. Refresh method can be used to refresh the layout when setting it in run time doesn’t reflected in UI.

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


![](SfCalendar-images/SfCalendar-img13.jpeg)


## Customize Day Name Display Mode

Day names in SfCalendar can be set to either abbreviated or full names using `DayNameDisplayMode` property. 

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


![](SfCalendar-images/SfCalendar-img14.jpeg)


