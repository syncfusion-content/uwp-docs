---
layout: post
title: Month Navigation on SfCalendar control for UWP
description: Month Navigation on SfCalendar control for UWP
platform: uwp
control: SfCalendar
documentation: ug
---

# Month Navigation

Navigating between months are much simpler with touch. Navigation buttons are also provided.

## Enabling Navigation Button

By default, navigation buttons are collapsed. Navigation button support can be enabled or disabled using the `ShowNavigationButton` property.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" ShowNavigationButton="True"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

SfCalendar calendar = new SfCalendar();

calendar.ShowNavigationButton = true;

{% endhighlight %}

{% endtabs %}

![](SfCalendar-images/SfCalendar-img12.jpeg)


## Navigating to Previous Month

Month navigation can also be done programmatically by invoking `PreviousMonth` method.

{% tabs %}

{% highlight C# %}

calendar.PreviousMonth();


{% endhighlight %}

{% endtabs %}


## Navigating to Next Month

Month navigation can also be done programmatically by invoking `NextMonth` method

{% tabs %}

{% highlight C# %}

calendar.NextMonth();

{% endhighlight %}

{% endtabs %}

## Notifying the Previous Button Click

`PreviousScrollButtonClicked` event is fired when the previous button is clicked.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" ShowNavigationButton="True"
                  PreviousScrollButtonClicked="calendar_PreviousScrollButtonClicked"/>

{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void calendar_PreviousScrollButtonClicked(object sender, SelectionChangedEventArgs e)

{

}

{% endhighlight %}

{% endtabs %}

## Notifying the Next Button Click

`NextScrollButtonClicked` event is fired when the next button is clicked.

{% tabs %}

{% highlight XAML %}

<input:SfCalendar x:Name="calendar" ShowNavigationButton="True"
                  NextScrollButtonClicked="calendar_NextScrollButtonClicked"/>
{% endhighlight %}

{% endtabs %}

{% tabs %}

{% highlight C# %}

private void calendar_NextScrollButtonClicked(object sender, SelectionChangedEventArgs e)

{

}

{% endhighlight %}

{% endtabs %}


