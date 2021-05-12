---
layout: post
title: Built-in Views in UWP Calendar control | Syncfusion
description: Learn here all about Built-in Views support in Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: Calendar
documentation: ug
---

# Built-in Views in UWP Calendar (SfCalendar)

`SfCalendar` control provides four types of views to display dates/years such as month,year,decade,century. It can be assigned to the `SfCalendar` control by using [ViewMode](https://help.syncfusion.com/cr/xamarin-android/Com.Syncfusion.Calendar.SfCalendar.html#Com_Syncfusion_Calendar_SfCalendar_ViewMode) property.

By default `SfCalendar` control is assigned with month view. Based on the user’s preference, `SfCalendar` can be viewed in any one of the available two type.

## Month view

This displays entire dates of a particular month, by default current month will be displayed on Loading. The current date is provided with unique color different from the rest of the dates color in a month. The events availability will be denoted within the cell based on its duration.

The dates in month view can be selected by three ways such as single, multiple and range which can be modified using `SelectionMode`

{% tabs %}

{% highlight xaml %}

<input:SfCalendar x:Name="calendar" ViewMode="Month"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Month;
 
{% endhighlight %}

{% endtabs %}

## Week view

The number of weeks in the month view can be changed by setting the [NumberOfWeeksInView](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_NumberOfWeeksInView) property in SfCalendar. By default, `NumberOfWeeksInView` starts from current week, and this can be modified using the [MoveToDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_MoveToDate) property of calendar. It also supports all existing features such as [FirstDayOfWeek](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_FirstDayOfWeek), [MinDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_MinDate), [MaxDate](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_MaxDate), and [SelectionMode](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_SelectionMode).

N>
* Week number ranges from 1 to 6. If lesser or greater than these range is considered, `NumberOfWeeksInView` will be displayed as 6.
* Inline view considers  `NumberOfWeeksInView` as only 6. For other count, only agenda view will be displayed in calendar.
* Dynamically changing `NumberOfWeeksInView` shows the first row of month view dates. It can be handled using the `MoveToDate` property of calendar
* [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/xamarin/Syncfusion.SfCalendar.XForms.SfCalendar.html#Syncfusion_SfCalendar_XForms_SfCalendar_ShowLeadingAndTrailingDays) is not applicable if the `NumberOfWeeksInView` is lesser than 6.

{% tabs %}

{% highlight xaml %}

<input:SfCalendar x:Name="calendar" NumberOfWeeksInView="2"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.NumberOfWeeksInView = 2;
 
{% endhighlight %}

{% endtabs %}
                                       
## Year view

This displays entire dates/month of a particular year, by default current year will be displayed on loading. The Years can be changed by swiping back and forth or `forward` and `backward` methods can be used. The Months can be navigated quickly by selecting on the particular month in year view.

{% tabs %}

{% highlight xaml %}

<input:SfCalendar x:Name="calendar" ViewMode="Year"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Year;
 
{% endhighlight %}

{% endtabs %}

## Decade view

This view displays the period of 10 years. By default, current year range of 10 years will be displayed on loading. You can easily navigate between month/year view to decade view by tapping the calendar header. The year can be navigated quickly by selecting a particular year from decade view.

{% tabs %}

{% highlight xaml %}

<input:SfCalendar x:Name="calendar" ViewMode="Decade"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Decade;
 
{% endhighlight %}

{% endtabs %}

## Century view

This view displays the period of 100 years. By default, current year range of 100 years will be displayed on loading. You can easily navigate between month/year/decade view to century view by tapping the calendar header. You can easily navigate to decade view by selecting decade years in century view.

{% tabs %}

{% highlight xaml %}

<input:SfCalendar x:Name="calendar" ViewMode="Century"/>

{% endhighlight %}

{% highlight c# %}

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Century;
 
{% endhighlight %}

{% endtabs %}

