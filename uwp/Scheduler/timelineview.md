---
layout: post
title: Timeline View in UWP Scheduler control | Syncfusion
description: Learn here all about Timeline View support in Syncfusion UWP Scheduler (SfSchedule) control and more.
platform: uwp
control: SfSchedule
documentation: ug
---

# Timeline View in UWP Scheduler (SfSchedule)
TimeLine view is used to displays complete TimeLine in selected day, the default visible day of Schedule will be current day. Appointments are added in particular timeslot based on its timeline.

![Timeline View UWP Scheduler](TimeLine-View_images/TimeLineView.png)

## View Header Appearance
You can customize the default appearance of schedule timeline view header using [TimeLineViewHeaderStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeLineViewHeaderStyle) property of `SfSchedule`.

{% tabs %}  
{% highlight xaml %} 

        <schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine">
            <schedule:SfSchedule.TimeLineViewHeaderStyle>
                <schedule:ScheduleTimeLineViewHeaderStyle
                    TimeLineViewCurrentDateBackground="Yellow"
                    TimeLineViewCurrentDateForeground="Blue"
                    TimeLineViewHeaderBackground="LightGray"
                    TimeLineViewHeaderFontFamily="Calibri "
                    TimeLineViewHeaderFontWeight="Bold"
                    TimeLineViewHeaderHeight="50"
                    TimeLineViewHeaderTextColor="Black"
                    TimeLineViewHeaderTextFontStyle="Normal"
                    TimeLineViewHeaderTextHorizontalAlignment="Stretch"
                    TimeLineViewHeaderTextSize="14"
                    TimeLineViewHeaderTextVerticalAlignment="Center" />
            </schedule:SfSchedule.TimeLineViewHeaderStyle>
        </schedule:SfSchedule>


{% endhighlight %} 
{% highlight c# %} 

              schedule.ScheduleType = ScheduleType.TimeLine;
            schedule.TimeLineViewHeaderStyle = new ScheduleTimeLineViewHeaderStyle()
            {
                TimeLineViewCurrentDateBackground = new SolidColorBrush(Colors.Yellow),
                TimeLineViewCurrentDateForeground = new SolidColorBrush(Colors.Blue),
                TimeLineViewHeaderBackground = new SolidColorBrush(Colors.LightGray),
                TimeLineViewHeaderFontFamily = new FontFamily("Calibri"),
                TimeLineViewHeaderFontWeight = FontWeights.Bold,
                TimeLineViewHeaderHeight = 50,
                TimeLineViewHeaderTextColor = new SolidColorBrush(Colors.Black),
                TimeLineViewHeaderTextFontStyle = FontStyle.Normal,
                TimeLineViewHeaderTextHorizontalAlignment = HorizontalAlignment.Center,
                TimeLineViewHeaderTextSize = 14,
                TimeLineViewHeaderTextVerticalAlignment = VerticalAlignment.Center
            };

{% endhighlight %}   
{% endtabs %}

![View Header Appearance](TimeLine-View_images/Header_Customize.png)

## Change Time Interval
You can customize the time intervals of timeslots in timeline by using [TimeInterval](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeInterval) property of `SfSchedule`.

{% tabs %}   
{% highlight xaml %} 

         <schedule:SfSchedule
            x:Name="schedule"
            TimeInterval="FifteenMin"
            ScheduleType="TimeLine" />

{% endhighlight %} 
{% highlight c# %} 

            schedule.ScheduleType = ScheduleType.TimeLine;
            schedule.TimeInterval= TimeInterval.FifteenMin;

{% endhighlight %}   
{% endtabs %}

![TimeInterval UWP TimeLineView](TimeLine-View_images/TimeInterval.png)

You can also set the custom time interval for timeslots  by using [CustomTimeInterval](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CustomTimeInterval) property of `SfSchedule` by making `TimeInterval` as Custom.
{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule
            x:Name="schedule"
            TimeInterval="Custom"
            CustomTimeInterval="120"
            ScheduleType="TimeLine" />


{% endhighlight %} 
{% highlight c# %} 

            schedule.TimeInterval= TimeInterval.Custom;
            schedule.CustomTimeInterval = 120;


{% endhighlight %}   
{% endtabs %}

![Custom TimeInterval UWP TimeLineView](TimeLine-View_images/Custom_TimeInterval.png)

## Change Working Hours
Working hours in `TimeLine` of Schedule control will be differentiated with non-working hours by separate color. By default working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkEndHour) properties of `SfSchedule`.
Non-working hours can be disabled by setting [ShowNonWorkingHours](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ShowNonWorkingHours) to false and non-working hours color can be changed by using [NonWorkingHourBrush](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonWorkingHourBrush) property of `SfSchedule`.

{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule
            x:Name="schedule"
            IsHighLightWorkingHours="True"
            NonWorkingHourBrush="Blue"
            ScheduleType="TimeLine"
            ShowNonWorkingHours="True"
            WorkEndHour="20"
            WorkStartHour="8" />



{% endhighlight %} 
{% highlight c# %} 

            schedule.WorkStartHour = 8;
            schedule.WorkEndHour = 20;
            schedule.IsHighLightWorkingHours = true;
            schedule.NonWorkingHourBrush = new SolidColorBrush(Colors.Blue);
            schedule.ShowNonWorkingHours = true;

{% endhighlight %}   
{% endtabs %}

![Change in Working Hours](TimeLine-View_images/WorkingHours.png)

## Collapse hours

You can collapse the hours in `TimeLineView` and `DayView` by adding hours in the `CollapsedHour` collection using the [CollapsedHours](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.CollapsedHourCollection.html) property.

{% tabs %}
{% highlight c# %}
schedule.CollapsedHours.Add(new ScheduleCollapsedHour() 
    { 
        StartHour = 02, 
        EndHour = 06, 
    }); 
{% endhighlight %}   
{% endtabs %}

![CollapsedHours UWP TimeLineView](TimeLine-View_images/Collapsedhours.png)

## Timeslot Appearance
You can customize the default timeslot appearance in timeline view by changing its stoke dash array by using [MajorTickStrokeDashArray](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickStrokeDashArray) and [MinorTickStrokeDashArray](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickStrokeDashArray) properties of `SfSchedule`. And, you can change the color by using [MajorTickStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickStroke) and [MinorTickStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickStroke) properties of `SfSchedule` control.

{% tabs %}   
{% highlight xaml %} 

         <schedule:SfSchedule
            x:Name="schedule"
            MajorTickStroke="Blue"
            MinorTickStroke="Blue"
            MajorTickStrokeDashArray="10"
            MinorTickStrokeDashArray="10"
            ScheduleType="TimeLine" />


{% endhighlight %} 
{% highlight c# %} 

            schedule.MajorTickStroke = new SolidColorBrush(Colors.Blue);
            schedule.MinorTickStroke = new SolidColorBrush(Colors.Blue);
            schedule.MajorTickStrokeDashArray = new DoubleCollection() {10};
            schedule.MinorTickStrokeDashArray = new DoubleCollection() {10};

{% endhighlight %}   
{% endtabs %}

![Custom_TimeSlot in TimeLine View](TimeLine-View_images/Custom_TimeSlot.png)

## Non-Accessible timeslots.
You can restrict/allocate certain timeslot as Non-accessible block using  [NonAccessibleBlocks](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonAccessibleBlocks)  property of  `SfSchedule`, so that can allocate those timeslots for predefined events/activities like Lunch hour.
{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule ScheduleType="TimeLine">
            <schedule:SfSchedule.NonAccessibleBlocks>
                <schedule:NonAccessibleBlock
                    Background="LightPink"
                    EndHour="8.00"
                    Label="Non Accessible Block"
                    StartHour="6.00" />
            </schedule:SfSchedule.NonAccessibleBlocks>
        </schedule:SfSchedule>



{% endhighlight %} 
{% highlight c# %} 

            schedule.ScheduleType = ScheduleType.TimeLine;
            schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock()
            {
                Background = new SolidColorBrush(Colors.LightPink),
                StartHour = 6.00,
                EndHour = 8.00,
                Label = "Non Accessible Block"
            });


{% endhighlight %}   
{% endtabs %}

![NonAccessibleBlocks in TimeLine View](TimeLine-View_images/NonAccessibleBlocks.png)

## Time Label Formatting
You can customize the default label format of time in timeline view by using [MajorTickTimeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickTimeFormat) and [MinorTickTimeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickTimeFormat) properties of `SfSchedule`.
{% tabs %}   
{% highlight xaml %} 

       <schedule:SfSchedule
            x:Name="schedule"
            MajorTickTimeFormat="HH"
            MinorTickTimeFormat="HH mm"
            ScheduleType="TimeLine" />

{% endhighlight %} 
{% highlight c# %} 

            schedule.ScheduleType = ScheduleType.TimeLine;
            schedule.MajorTickTimeFormat = "HH";
            schedule.MinorTickTimeFormat = "HH mm";

{% endhighlight %}   
{% endtabs %}

![MajorTickTimeFormat](TimeLine-View_images/Label_Format.png)

## Time Label appearance
You can the customize the default color of time label in timeline view by using the [MajorTickLabelStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickLabelStroke) and [MinorTickLabelStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickLabelStroke) properties of `SfSchedule`.

{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule
            x:Name="schedule"
            MajorTickLabelStroke="Blue"
            MinorTickLabelStroke="Blue"
            ScheduleType="TimeLine" />


{% endhighlight %} 
{% highlight c# %} 

            schedule.MajorTickLabelStroke=new SolidColorBrush(Colors.Blue);
            schedule.MinorTickLabelStroke = new SolidColorBrush(Colors.Blue);

{% endhighlight %}   
{% endtabs %}
You can the customize the default font size of time label in timeline view by using the [MajorTickLabelSize](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickLabelSize) and [MinorTickLabelSize](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickLabelSize) properties of `SfSchedule`.

{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule
            x:Name="schedule"
            MajorTickLabelSize="20"
            MinorTickLabelSize="20"
            ScheduleType="TimeLine" />

{% endhighlight %} 
{% highlight c# %} 

            schedule.MajorTickLabelSize=20;
            schedule.MinorTickLabelSize =20;

{% endhighlight %}   
{% endtabs %}

![MajorTickLabelSize](TimeLine-View_images/Label_Customize.png)

## Selection
You can customize the default appearance of selection UI in the timeslots.

*	Selection customization using style
*	Selection customization using custom View.

### Selection customization using style

You can customize the timeslot selection by using [ScheduleSelectionStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleSelectionStyle) property of `SfSchedule`.
{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule ScheduleType="TimeLine">
            <schedule:SfSchedule.ScheduleSelectionStyle>
                <schedule:ScheduleSelectionStyle
                    Background="Blue"
                    BorderBrush="Black"
                    BorderCornerRadius="5"
                    BorderThickness="5" />
            </schedule:SfSchedule.ScheduleSelectionStyle>
        </schedule:SfSchedule>


{% endhighlight %} 
{% highlight c# %} 

        schedule.ScheduleSelectionStyle= new ScheduleSelectionStyle()
            {
                 Background = new SolidColorBrush(Colors.Blue),
                 BorderBrush = new SolidColorBrush(Colors.Black),
                 BorderCornerRadius = new CornerRadius(5),
                 BorderThickness = new Thickness(5)
            };

{% endhighlight %}   
{% endtabs %}

![Schedule SelectionStyle](TimeLine-View_images/Selection_Customize.png)

### Selection customization using custom View.
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.

{% tabs %}   
{% highlight xaml %} 

         <schedule:SfSchedule x:Name="schedule" ScheduleType="TimeLine">
            <schedule:SfSchedule.SelectionView>
                <Button Background="BlueViolet" Content="+NewEvent" />
            </schedule:SfSchedule.SelectionView>
        </schedule:SfSchedule>

{% endhighlight %} 
{% highlight c# %} 

       schedule.SelectionView=new Button()
            {
                Content = "+NewEvent",
                Background = new SolidColorBrush(Colors.BlueViolet)
            };

{% endhighlight %}   
{% endtabs %}

![Selection customization](TimeLine-View_images/Selection_CustomView.png)

## Configuration Resources
The Schedule control allows you to define resources that can be assigned to appointments. Resources let you associate additional information with your appointments. The schedule can group appointments based on the resources associated with them.

*	[Adding resources](#adding-resource)
*	[Customizing resource visibility](#customizing-resource-visibility)
*	[Configuring appointments based on resource](https://help.syncfusion.com/uwp/sfschedule/appointments#configuring-resources)

### Adding resource
Resource can be added to the schedule control by setting Resource and ScheduleResourceTypeCollection of SfSchedule. After that add the ResourceType for ScheduleResourceTypeCollection and assign Resource to ResourceType.
{% tabs %}   
{% highlight xaml %} 

        <schedule:SfSchedule
            x:Name="schedule"
            Resource="Doctors"
            ScheduleType="TimeLine">
            <schedule:SfSchedule.ScheduleResourceTypeCollection>
                <schedule:ResourceType TypeName="Doctors">
                    <schedule:Resource
                        DisplayName="Dr.Jacob"
                        ResourceName="Dr.Jacob"
                        TypeName="Doctors" />
                    <schedule:Resource
                        DisplayName="Dr.Darsy"
                        ResourceName="Dr.Darsy"
                        TypeName="Doctors" />
                </schedule:ResourceType>
            </schedule:SfSchedule.ScheduleResourceTypeCollection>
        </schedule:SfSchedule>


{% endhighlight %} 
{% highlight c# %} 

           var currentDate=DateTime.Now;
            ScheduleAppointment app = new ScheduleAppointment()
            {
                StartTime = currentDate.Date.AddHours(5),
                EndTime = currentDate.Date.AddHours(6),
                Subject = "Meeting",
                Location = "Chennai",
                AppointmentBackground =new SolidColorBrush(Colors.Red)
            };
            app.ResourceCollection.Add(new Resource()
            {
                ResourceName = "Dr.Jacob",
                TypeName = "Doctors"
            });

            ScheduleAppointment app1 = new ScheduleAppointment()
            {
                StartTime = currentDate.Date.AddHours(7),
                EndTime = currentDate.Date.AddHours(8),
                Subject = "Conference",
                Location = "Chennai",
                AppointmentBackground = new SolidColorBrush(Colors.Yellow)
            };
            app1.ResourceCollection.Add(new Resource()
            {
                ResourceName = "Dr.Darsy",
                TypeName = "Doctors"
            });


            schedule.Appointments.Add(app);
            schedule.Appointments.Add(app1);


{% endhighlight %}   
{% endtabs %}

![Resources in TimeLine View](TimeLine-View_images/Resources.png)

### Customizing resource visibility
This feature supports to display ‘N’ number of rows in `TimeLine` view. You can achieve this by specifying the count of resources that needs to be displayed per view. This support is offered for `TimeLine` view alone.
This support can be enabled by using property [TimeLineViewRowCount](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeLineViewRowCount) in `SfSchedule`. By default, its value is “zero”.

{% tabs %}   
{% highlight xaml %} 

         <schedule:SfSchedule
            x:Name="schedule" TimeLineViewRowCount="1"
            Resource="Doctors"
            ScheduleType="TimeLine">
            <schedule:SfSchedule.ScheduleResourceTypeCollection>
                <schedule:ResourceType TypeName="Doctors">
                    <schedule:Resource
                        DisplayName="Dr.Jacob"
                        ResourceName="Dr.Jacob"
                        TypeName="Doctors" />
                    <schedule:Resource
                        DisplayName="Dr.Darsy"
                        ResourceName="Dr.Darsy"
                        TypeName="Doctors" />
                </schedule:ResourceType>
            </schedule:SfSchedule.ScheduleResourceTypeCollection>
        </schedule:SfSchedule>


{% endhighlight %} 
{% highlight c# %} 

            schedule.TimeLineViewRowCount = 1;
            var currentDate=DateTime.Now;
            ScheduleAppointment app = new ScheduleAppointment()
            {
                StartTime = currentDate.Date.AddHours(5),
                EndTime = currentDate.Date.AddHours(6),
                Subject = "Meeting",
                Location = "Chennai",
                AppointmentBackground =new SolidColorBrush(Colors.Red)
            };
            app.ResourceCollection.Add(new Resource()
            {
                ResourceName = "Dr.Jacob",
                TypeName = "Doctors"
            });

            ScheduleAppointment app1 = new ScheduleAppointment()
            {
                StartTime = currentDate.Date.AddHours(7),
                EndTime = currentDate.Date.AddHours(8),
                Subject = "Conference",
                Location = "Chennai",
                AppointmentBackground = new SolidColorBrush(Colors.Yellow)
            };
            app1.ResourceCollection.Add(new Resource()
            {
                ResourceName = "Dr.Darsy",
                TypeName = "Doctors"
            });
            schedule.Appointments.Add(app);
            schedule.Appointments.Add(app1);

{% endhighlight %}   
{% endtabs %}

![Resource Customization](TimeLine-View_images/Resource_RowCount.png)










