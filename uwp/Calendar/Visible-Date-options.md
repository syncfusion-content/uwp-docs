---
layout: post
title: Visible Dates in UWP Calendar control | Syncfusion
description: Learn here all about Visible Dates support in Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Visible Dates in UWP Calendar (SfCalendar)

`SfCalendar` provides support for making dates inactive within a range (or) selective dates. It can be achieved by the properties `VisibleMinDate`, `VisibleMaxDate` and `VisibleDates`.

## Setting Minimum Visible Date

`VisibleMinDate` property is used to specify the minimum date in range.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" VisibleMinDate="12/10/2015"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.VisibleMinDate = new DateTime(2015, 12, 10);

{% endhighlight %}

{% highlight VB %}

calendar.VisibleMinDate = New Date(2015, 12, 10)

{% endhighlight %}

{% endtabs %}


![SfCalendar-img9](SfCalendar-images/SfCalendar-img9.jpeg)


## Setting Maximum Visible Date

`VisibleMaxDate` property is used to specify the maximum date in range

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" VisibleMaxDate="12/15/2015"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.VisibleMaxDate = new DateTime(2015, 12, 15);

{% endhighlight %}

{% highlight VB %}

calendar.VisibleMaxDate = New Date(2015, 12, 15)

{% endhighlight %}

{% endtabs %}


![SfCalendar-img10](SfCalendar-images/SfCalendar-img10.jpeg)

## Setting Visible Dates

`VisibleDates` property is used to specify the active dates when they are not continuous and cannot be specified with a start and end date.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

calendar.VisibleDates.Add(new DateTime(2015, 12, 1));

calendar.VisibleDates.Add(new DateTime(2015, 12, 12));

calendar.VisibleDates.Add(new DateTime(2015, 12, 25));

calendar.VisibleDates.Add(new DateTime(2015, 12, 30));

{% endhighlight %}

{% highlight VB %}

calendar.VisibleDates.Add(New Date(2015, 12, 1))

calendar.VisibleDates.Add(New Date(2015, 12, 12))

calendar.VisibleDates.Add(New Date(2015, 12, 25))

calendar.VisibleDates.Add(New Date(2015, 12, 30))

{% endhighlight %}

{% endtabs %}

![SfCalendar-img11](SfCalendar-images/SfCalendar-img11.jpeg)


