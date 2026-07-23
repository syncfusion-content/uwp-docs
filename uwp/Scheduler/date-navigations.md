---
layout: post
title: Date Navigations in UWP Scheduler control | Syncfusion
description: Learn here all about Date Navigations support in the Syncfusion UWP Scheduler (SfSchedule) control and more.
platform: uwp
control: SfSchedule
documentation: ug
---

# Date Navigations in UWP Scheduler (SfSchedule)

## Enabling Navigation 
By default, Schedule views can be moved backwards and forwards using touch swipe gestures. This navigation gesture can be enabled or disabled by setting the [EnableNavigation](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_EnableNavigationProperty) property of `SfSchedule`. By default, it is enabled.

{% tabs %}   
{% highlight xaml %} 

<Page
    ...
    xmlns:schedule="using:Syncfusion.UI.Xaml.Schedule">

        <schedule:SfSchedule EnableNavigation="False"/>

</Page>
{% endhighlight %}   
{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

         //disabling the navigation gesture
           schedule.EnableNavigation = false;

{% endhighlight %}   
{% endtabs %} 

## Programmatically change to specific dates 
Visible dates can be moved to a specific date using the [MoveToDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MoveToDate_System_DateTime_) method available in `SfSchedule`. It will move to any specific date if the schedule view is Day View; similarly, it will move to the specific week if it is week view, and to the specific month if it is month view.

>**Note:** The specified date should lie between MinDisplayDate and MaxDisplayDate. If the specified date is greater than *MaxDisplayDate*, then the view moves to MaxDisplayDate. Similarly, if the specified date is lesser than *MinDisplayDate*, then the view moves to MinDisplayDate.

 
{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

    schedule.MoveToDate(new DateTime(2018, 1, 1));

{% endhighlight %}   


## Programmatically change to specific time.
You can move the `SfSchedule` to a particular time by passing the TimeSpan value to the [MoveToTime](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MoveToTime_System_TimeSpan_) method. This method is applicable for Day, Week, and TimeLine views of the `SfSchedule` control.

>**Note:** Since this method handles the position of the scroll, it should be called only after the SfSchedule view gets loaded. MoveToTime is only applicable in the day view of Windows Phone.


{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

    schedule.MoveToTime(new TimeSpan(8, 0, 0));

{% endhighlight %}   

## Programmatically change to adjacent dates.
By default, the date can be navigated to the next and previous views using touch gestures, by swiping the control in the right-to-left and left-to-right direction. The view can also be changed programmatically using the [Forward](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Forward) and [Backward](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Backward) methods available in `SfSchedule`. 

*  	Forward
*	Backward

### Forward
You can use the `Forward` method for viewing the next immediate visible dates in the SfSchedule. It will move to the next month if the schedule view is month; similarly, it will move to the next week for week view and the next day for day view.


{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

          //Viewing next immediate visible dates
            schedule.Forward();

{% endhighlight %}   


>**Note: Date can be navigated until it reaches the Min and Max date.**

### Backward
You can use the `Backward` method for viewing the previous immediate visible dates in the `SfSchedule`. It will move to the previous month if the schedule view is month; similarly, it will move to the previous week for week view and the previous day for day view.

{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

           //Viewing previous immediate visible dates
            schedule.Backward();


{% endhighlight %}   


>**Note: Date can be navigated until it reaches the Min and Max date.**

## Range for visible dates
Visible dates can be restricted between a certain range of dates using the [MinimumDisplayDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinimumDisplayDateProperty) and [MaximumDisplayDate](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MaximumDisplayDateProperty) properties available in the `SfSchedule` control. It is applicable in all the schedule views.
Beyond the min and max date range, it will restrict the date navigation features of `Forward`, `Backward`, `MoveToDate`, and also you can't swipe the control using touch gestures beyond the min and max date range.

{% highlight c# %} 

using Syncfusion.UI.Xaml.Schedule;

            schedule.MinimumDisplayDate = (new DateTime(2015, 9, 16));
            schedule.MaximumDisplayDate = (new DateTime(2025, 11, 27));



{% endhighlight %}   


