---
layout: post
title: Built-in Views in UWP Calendar control | Syncfusion
description: Learn here all about Built-in Views support in the Syncfusion UWP Calendar (SfCalendar) control and more.
platform: uwp
control: SfCalendar
documentation: ug
---

# Built-in Views in UWP Calendar (SfCalendar)

The `SfCalendar` control provides four types of views to display dates/years such as month, year, decade, century. It can be assigned to the `SfCalendar` control by using the [ViewMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_ViewMode) property.

By default, the `SfCalendar` control is assigned with month view. Based on the user's preference, `SfCalendar` can be viewed in any one of the available types.

## Month view

This displays entire dates of a particular month; by default, the current month will be displayed on loading. The current date is provided with a unique color different from the rest of the dates' color in a month. The events availability will be denoted within the cell based on its duration.

The dates in the month view can be selected in three ways such as single, multiple, and range, which can be modified using `SelectionMode`.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" ViewMode="Month"/>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar calendar = new SfCalendar();
calendar.ViewMode = ViewMode.Month;
 
{% endhighlight %}

{% endtabs %}

## Week view

The number of weeks in the month view can be changed by setting the [NumberOfWeeksInView](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_NumberOfWeeksInView) property in SfCalendar. By default, `NumberOfWeeksInView` starts from the current week, and this can be modified using the [DisplayDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_DisplayDate) property of the calendar. It also supports all existing features such as [FirstDayofWeek](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_FirstDayofWeek), [VisibleMinDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_VisibleMinDate), [VisibleMaxDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_VisibleMaxDate), and [SelectionMode](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_SelectionMode).

N>
* Week number ranges from 1 to 6. If a lesser or greater count than these ranges is considered, `NumberOfWeeksInView` will be displayed as 6.
* Inline view considers `NumberOfWeeksInView` as only 6. For other counts, only the agenda view will be displayed in the calendar.
* Dynamically changing `NumberOfWeeksInView` shows the first row of month view dates. It can be handled using the `DisplayDate` property of the calendar.
* [ShowLeadingAndTrailingDays](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Controls.Input.SfCalendar.html#Syncfusion_UI_Xaml_Controls_Input_SfCalendar_ShowLeadingAndTrailingDays) is not applicable if the `NumberOfWeeksInView` is lesser than 6.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" NumberOfWeeksInView="2"/>  
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.NumberOfWeeksInView = 2;
{% endhighlight %}

{% endtabs %}
                                       
## Year view

This displays entire dates/months of a particular year; by default, the current year will be displayed on loading. The years can be changed by swiping back and forth, or `NextYear` and `PreviousYear` methods can be used. The months can be navigated quickly by selecting the particular month in year view.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" ViewMode="Year"/>
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar calendar = new SfCalendar();
calendar.ViewMode = ViewMode.Year;
 
{% endhighlight %}

{% endtabs %}

## Decade view

This view displays the period of 10 years. By default, the current year range of 10 years will be displayed on loading. You can easily navigate between month/year view to decade view by tapping the calendar header. The year can be navigated quickly by selecting a particular year from the decade view.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" ViewMode="Decade"/>        
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Decade;

{% endhighlight %}

{% endtabs %}

## Century view

This view displays the period of 100 years. By default, the current year range of 100 years will be displayed on loading. You can easily navigate between month/year/decade view to century view by tapping the calendar header. You can easily navigate to the decade view by selecting the decade years in century view.

{% tabs %}

{% highlight xaml %}

<Page
   ...
   xmlns:input="using:Syncfusion.UI.Xaml.Controls.Input">

    <input:SfCalendar x:Name="calendar" ViewMode="Century"/>       
</Page>

{% endhighlight %}

{% highlight c# %}

using Syncfusion.UI.Xaml.Controls.Input;

SfCalendar sfCalendar = new SfCalendar();
sfCalendar.ViewMode = ViewMode.Century;

{% endhighlight %}

{% endtabs %}

