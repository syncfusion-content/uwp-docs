---
layout: post
title: Week Number | SfSchedule | uwp | Syncfusion
description: Week Number
platform: uwp
control: SfSchedule
documentation: ug
---

# Week Number

You can display the week number of the year in month view by using the **ShowWeekNumber** property. By default value of **ShowWeekNumber** property is false.

>**Note:-ShowWeekNumber is only applicable in Month view.**

{% tabs %}
{% highlight xaml %}

    <schedule:SfSchedule  x:Name="schedule"  ScheduleType="Month"  ShowWeekNumber="True"/>
    
{% endhighlight %}

{% highlight c# %}

            SfSchedule schedule = new SfSchedule();
            schedule.ScheduleType = ScheduleType.Month;
            schedule.ShowWeekNumber = true;
            this.grid.Children.Add(schedule);

{% endhighlight %}
{% endtabs %}

![](Week_Number_images/Week_Number_img1.png)
