---
layout: post
title: DateTime Navigation and Gesture | SfSchedule | uwp | Syncfusion
description: This section describes the complete DateTime Navigation and Gesture support in SfSchedule control in UWP
platform: uwp
control: SfSchedule
documentation: ug
---

# Date Navigations in UWP Scheduler (SfSchedule)

## Enabling Navigation 
By default, Schedule views can be moved backwards and forwards using touch swipe gesture. This navigation gesture can be enabled or disabled by setting [EnableNavigation](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_EnableNavigationProperty) property of `SfSchedule`. By default, it is enabled.

{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule EnableNavigation="False"/>
{% endhighlight %}   
{% highlight c# %} 

         //disabling navigation gesture
           schedule.EnableNavigation = false;

{% endhighlight %}   
{% endtabs %} 

## Programmatic date navigation
You can programmatically navigate dates in scheduler by using the `DisplayDate` property of SfSchedule.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule DisplayDate="2021-03-05 9:0:0"/>
{% endhighlight %}
{% highlight c#%}
this.Schedule.DisplayDate = new DateTime(2021, 03, 05, 9, 0, 0);
{% endhighlight %}
{% endtabs %}

Note>
Date navigation before the minimum date will be reset to the scheduler minimum date and date navigation beyond the maximum date will be rest to the scheduler maximum date.

## Programmatic date selection
You can programmatically select the dates in scheduler by using the `SelectedDate` property of SfSchedule.

{% tabs %}
{% highlight xaml %}
<schedule:SfSchedule SelectedDate="2021-03-05 9:0:0"/>
{% endhighlight %}
{% highlight c#%}
this.Schedule.SelectedDate = new DateTime(2021, 03, 05, 9, 0, 0);
{% endhighlight %}
{% endtabs %}

Note>
Selection before minimum dates and beyond maximum dates using the `SelectedDate` is not possible.

## Programmatically change to specific dates 
Visible dates can be moved to specific date using [MoveToDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MoveToDate_System_DateTime_) method available in `SfSchedule`. It will move to any specific date if the schedule view is Day View, similarly it will move to the specific week if it is week view and to specific month if it is month view

>**Note:** The specified date should lies between MinDisplayDate and MaxDisplayDate, if the specified date is greater than *MaxDisplayDate* then the view moved to MaxDisplayDate similarly if the specified date is lesser than the *MinDisplayDate* then the view moved to MinDisplayDate.

 
{% highlight c# %} 

    schedule.MoveToDate(new DateTime(2018, 1, 1));

{% endhighlight %}   


## Programmatically change to specific time.
You can move the `SfSchedule` to particular time by passing the Timespan value to [MoveToTime](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MoveToTime_System_TimeSpan_) method. This method is applicable for Day, week and TimeLine view of `SfSchedule` control.

>**Note:** Since this method handles the position of scroll, it calls only after SfSchedule view gets loaded and MoveToTime is only applicable in day view of Windows Phone.


{% highlight c# %} 

    schedule.MoveToTime(new TimeSpan(8, 0, 0));

{% endhighlight %}   

## Programmatically change to adjacent dates.
By default the date can be navigated to next and previous view using touch gesture, by swiping the control in right to left and right to left direction. The view can be also changed programmatically using [Forward](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Forward) and [Backward](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Backward) method available in `SfSchedule`. 

*  	Forward
*	Backward

### Forward
You can use the `Forward` method for viewing the next immediate visible dates in the SfSchedule. It will move to next month if the schedule view is month, similarly it will move to next week for week view and next day for day view.


{% highlight c# %} 

          //Viewing next immediate visible dates
            schedule.Forward();

{% endhighlight %}   


>**Note: - Date can be navigated until it reaches the Min Max date.**

### Backward
You can use the `Backward` method for viewing the previous immediate visible dates in the `SfSchedule`. It will move to previous month if the schedule view is month, similarly it will move to previous week for week view and previous day for day view.

{% highlight c# %} 

           //Viewing previous immediate visible dates
            schedule.Backward();


{% endhighlight %}   


>**Note: - Date can be navigated until it reaches the Min Max date.**

## Range for visible dates
Visible dates can be restricted between certain range of dates using [MinimumDisplayDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinimumDisplayDateProperty) and [MaximumDisplayDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MaximumDisplayDateProperty) properties available in `SfSchedule` control. It is applicable in all the schedule views.
So that beyond the min max date range, it will restrict date navigations features of `Forward`, `backward`, `MoveToDate` and also can’t swipe the control using touch gesture beyond the min max date range.

{% highlight c# %} 

            schedule.MinimumDisplayDate = (new DateTime(2015, 9, 16));
            schedule.MaximumDisplayDate = (new DateTime(2025, 11, 27));



{% endhighlight %}   


