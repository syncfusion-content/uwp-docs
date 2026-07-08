---

layout: post
title: Week View in UWP Scheduler control | Syncfusion
description: Learn here all about Week View support in Syncfusion UWP Scheduler (SfSchedule) control and more.
platform: UWP
control: SfSchedule
documentation: ug

---
# Week View in UWP Scheduler (SfSchedule)

WeekView is to view all days of a particular week. Appointments will be arranged based on the dates on the week in respective timeslots.

## ViewHeader Appearance
You can customize the default appearance of view header in [Week](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.ScheduleType.html) by using [DayViewHeaderStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_DayViewHeaderStyle) and [DayViewHeaderHeight](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.ScheduleDayViewHeaderStyle.html#Syncfusion_UI_Xaml_Schedule_ScheduleDayViewHeaderStyle_DayViewHeaderHeightProperty) properties of [SfSchedule](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html).
{% tabs %}
{% highlight C# %}

            SfSchedule schedule = new SfSchedule();
            schedule.ScheduleType = ScheduleType.Week;
            ScheduleDayViewHeaderStyle dayViewHeaderStyle = new ScheduleDayViewHeaderStyle();
            dayViewHeaderStyle.DayViewHeaderTextColor = new SolidColorBrush(Colors.White);
            dayViewHeaderStyle.DayViewHeaderFontFamily = new FontFamily("Arial");
            dayViewHeaderStyle.DayViewHeaderHeight = 50;
            dayViewHeaderStyle.DayViewHeaderTextSize = 15;
            dayViewHeaderStyle.DayViewHeaderBackground = new SolidColorBrush(Colors.Red);
            schedule.DayViewHeaderStyle = dayViewHeaderStyle;
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week">
            <Schedule:SfSchedule.DayViewHeaderStyle>
                <Schedule:ScheduleDayViewHeaderStyle
                    DayViewHeaderBackground="Red"
                    DayViewHeaderFontFamily="Arial"
                    DayViewHeaderHeight="50"
                    DayViewHeaderTextColor="White"
                    DayViewHeaderTextSize="15" />
            </Schedule:SfSchedule.DayViewHeaderStyle>
    </Schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}

![viewheader_week](daymodule_images/viewheader_week.png)

## Change Time Interval
You can customize the interval of timeslots in `WeekView`.

* [TimeInterval customization](#timeInterval-customization)
* [CustomTimeInterval](#customTimeInterval)

### TimeInterval customization
You can customize the interval of timeslots in `WeekView` by setting [TimeInterval](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_TimeInterval) property of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.TimeInterval = TimeInterval.ThirtyMin;
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule
            x:Name="schedule"
            ScheduleType="Week"
            TimeInterval="ThirtyMin" />
{% endhighlight %}
{% endtabs %}

![timeinterval_week](daymodule_images/timeinterval_week.png)

### CustomTimeInterval
You can customize the interval of timeslots in `WeekView` by setting [CustomTimeInterval](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_CustomTimeInterval) property of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.TimeInterval = TimeInterval.Custom;
            schedule.CustomTimeInterval = 120;
{% endhighlight %}

{% highlight XAML %}

     <Schedule:SfSchedule
            x:Name="schedule"
            CustomTimeInterval="120"
            ScheduleType="Week"
            TimeInterval="Custom" />
{% endhighlight %}
{% endtabs %}

![customtimeinterval_week](daymodule_images/customtimeinterval_week.png)

## Change Working hours
Working hours in `WeekView` of Schedule control will be differentiated with non-working hours by separate color. By default, working hours will be between 09 to 18. You can customize the working hours by setting [WorkStartHour](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkStartHour) and [WorkEndHour](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_WorkEndHour) properties of `SfSchedule`.
{% tabs %}
{% highlight C# %}

           schedule.IsHighLightWorkingHours = true;
            schedule.ScheduleType = ScheduleType.Week;
            schedule.WorkStartHour = 10;
            schedule.WorkEndHour = 18;
            schedule.NonWorkingHourBrush = new SolidColorBrush(Colors.LightGray);
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule
            x:Name="schedule"
            IsHighLightWorkingHours="True"
            NonWorkingHourBrush="LightGray"
            ScheduleType="Week"
            WorkEndHour="18"
            WorkStartHour="10" />
{% endhighlight %}
{% endtabs %}

![changeworkinghours_week](daymodule_images/changeworkinghours_week.png)

>**Note**:
`WorkStartHour` and `WorkEndHour` should be in integer value to represent hours.

## Timeslot Appearance
You can customize the appearance of the working hour timeslots by its color using [MajorTickStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickStroke), [MinorTickStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickStroke), [DayViewVerticalLineStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_DayViewVerticalLineStroke),  [MajorTickStrokeDashArray](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickStrokeDashArray),  [MinorTickStrokeDashArray](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickStrokeDashArray) , [IsHighLightWorkingHours](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_IsHighLightWorkingHours),  `WorkStartHour` , `WorkEndHour` and [NonWorkingHourBrush](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonWorkingHourBrush) properties of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.MajorTickStroke = new SolidColorBrush(Colors.Red);
            schedule.MinorTickStroke = new SolidColorBrush(Colors.Green);
            schedule.DayViewVerticalLineStroke = new SolidColorBrush(Colors.Blue);
            schedule.MajorTickStrokeDashArray = new DoubleCollection() { 5, 10 };
            schedule.MinorTickStrokeDashArray = new DoubleCollection() { 10, 10 };
            schedule.IsHighLightWorkingHours = true;
            schedule.WorkStartHour = 9;
            schedule.WorkEndHour = 18;
            schedule.NonWorkingHourBrush = new SolidColorBrush(Colors.LightBlue);
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule
            x:Name="schedule"
            DayViewVerticalLineStroke="Blue"
            IsHighLightWorkingHours="True"
            MajorTickStroke="Red"
            MajorTickStrokeDashArray="5,10"
            MinorTickStroke="Green"
            MinorTickStrokeDashArray="5,5"
            NonWorkingHourBrush="LightBlue"
            ScheduleType="Week"
            WorkEndHour="18"
            WorkStartHour="9" />
{% endhighlight %}
{% endtabs %}
![timeslotappearance_week](daymodule_images/timeslotappearance_week.png)

## Non-Accessible timeslots

You can restrict or allocate certain timeslot as Non-accessible blocks by using [NonAccessibleBlocks](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_NonAccessibleBlocks) of `SfSchedule` so that you can allocate those timeslots for predefined events/activities like Lunch hour.
{% tabs %}
{% highlight C# %}

           schedule.ScheduleType = ScheduleType.Week;
            schedule.NonAccessibleBlocks.Add(new NonAccessibleBlock()
            {
                Background = new SolidColorBrush(Colors.LightPink),
                StartHour = 6.00,
                EndHour = 8.00,
                Label = "Non Accessible Block"
            });
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week">
            <Schedule:SfSchedule.NonAccessibleBlocks>
                <Schedule:NonAccessibleBlock
                    Background="LightPink"
                    EndHour="8.00"
                    Label="Non Accessible Block"
                    StartHour="6.00" />
            </Schedule:SfSchedule.NonAccessibleBlocks>
        </Schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}
![nonaccessibleblock_week](daymodule_images/nonaccessibleblock_week.png)

>**Note**:
Selection and related events will not be working in this blocks.

## Change first day of week

By default, schedule control will be rendered with Sunday as the first day of the week, it can be customized to any day of the week by using [FirstDayOfWeek](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_FirstDayOfWeek) property of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.FirstDayOfWeek = DayOfWeek.Tuesday;
            schedule.ScheduleType = ScheduleType.Week;
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule FirstDayOfWeek="Tuesday" ScheduleType="Week" /> 
{% endhighlight %}
{% endtabs %}
![firstdayofweek_week](daymodule_images/firstdayofweek_week.png)

## Time Label Formatting
You can customize the format for the labels which are mentioning the time, by setting [MajorTickTimeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickTimeFormat) and [MinorTickTimeFormat](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickTimeFormat) properties of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.MajorTickTimeFormat = "hh:mm tt";
            schedule.MinorTickTimeFormat = "mm";
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule
            x:Name="schedule"
            MajorTickTimeFormat="hh:mm tt"
            MinorTickTimeFormat="mm"
            ScheduleType="Week" />
{% endhighlight %}
{% endtabs %}
![timelabelformat_week](daymodule_images/timelabelformat_week.png)

## Time Label Appearance

You can customize the color for the labels which are mentioning the time, by setting [MajorTickLabelStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MajorTickLabelStroke) and  [MinorTickLabelStroke](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_MinorTickLabelStroke) properties of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.MajorTickLabelStroke = new SolidColorBrush(Colors.Blue);
            schedule.MinorTickLabelStroke = new SolidColorBrush(Colors.Blue);
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule
            x:Name="schedule"
            MajorTickLabelStroke="Blue"
            MinorTickLabelStroke="Blue"
            ScheduleType="Week" />
{% endhighlight %}
{% endtabs %}
![timelabelappearance_week](daymodule_images/timelabelappearance_week.png)

## Selection:
You can customize the default appearance of selection UI in the timeslots.

* [Selection customization using style](#selection-customization-using-style)
* [Selection customization using custom View](#selection-customization-using-custom-view)

### Selection customization using style
You can customize the timeslot selection by using [ScheduleSelectionStyle](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleSelectionStyle) property of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            ScheduleSelectionStyle selectionStyle = new ScheduleSelectionStyle();
            selectionStyle.Background = new SolidColorBrush(Colors.Blue);
            selectionStyle.BorderBrush = new SolidColorBrush(Colors.Black);
            selectionStyle.BorderThickness = new Thickness(5);
            selectionStyle.BorderCornerRadius = new CornerRadius(5);
            schedule.ScheduleSelectionStyle = selectionStyle;
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week">
            <Schedule:SfSchedule.ScheduleSelectionStyle>
                <Schedule:ScheduleSelectionStyle
                    Background="Blue"
                    BorderBrush="Black"
                    BorderCornerRadius="5"
                    BorderThickness="5" />
            </Schedule:SfSchedule.ScheduleSelectionStyle>
        </Schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}
![selectionstyle_week](daymodule_images/selectionstyle_week.png)

### Selection customization using custom View:
You can replace the default selection UI with your custom view by setting [SelectionView](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_SelectionView) property of `SfSchedule`.
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            Button selectionView = new Button();
            selectionView.Content = "+NewEvent";
            selectionView.Background = new SolidColorBrush(Colors.BlueViolet);
            schedule.SelectionView = selectionView;
{% endhighlight %}

{% highlight XAML %}

    <Schedule:SfSchedule x:Name="schedule" ScheduleType="Week">
            <Schedule:SfSchedule.SelectionView>
                <Button Background="BlueViolet" Content="+NewEvent" />
            </Schedule:SfSchedule.SelectionView>
        </Schedule:SfSchedule>
{% endhighlight %}
{% endtabs %}
![custoselectionview_week](daymodule_images/custoselectionview_week.png)

>**Note:**
Selection customization is applicable for time slots alone.

## Configuration Resources
The Schedule control allows you to define resources that can be assigned to appointments. Resources let you associate additional information with your appointments. The schedule can group appointments based on the resources associated with them.

* [Adding resource](#adding-resource)
* [Sub Resource](#sub-resource)
* [Changing resource order](#changing-resource-order)

### Adding resource
Resource can be added to the schedule control by setting [Resource](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Resource) and [ScheduleResourceTypeCollection](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_ScheduleResourceTypeCollection) of `SfSchedule`. After that add the [ResourceType](https://help.syncfusion.com/cr/uwp/Syncfusion.UI.Xaml.Schedule.SfSchedule.html#Syncfusion_UI_Xaml_Schedule_SfSchedule_Resource) for `ScheduleResourceTypeCollection` and assign `Resource` to `ResourceType`.
{% tabs %}
{% highlight C# %}

    //setting resource for schedule
            SfSchedule schedule = new SfSchedule();
            schedule.ScheduleType = ScheduleType.Week;
            schedule.Resource = "Doctor";
            //Creating Appointment style 
            ResourceType resourceType = new ResourceType { TypeName = "Doctor" };
            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Jacob", ResourceName = "Dr.Jacob", });
            resourceType.ResourceCollection.Add(new Resource { DisplayName = "Dr.Darsy", ResourceName = "Dr.Darsy" });
            schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;
            //setting resource type
            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };

{% endhighlight %}

{% highlight XAML %}

    <syncfusion:SfSchedule
            Name="schedule"
            Resource="Doctors"
            ScheduleType="Week">
            <syncfusion:SfSchedule.ScheduleResourceTypeCollection>
                <syncfusion:ResourceType TypeName="Doctors">
                    <syncfusion:Resource DisplayName="Dr.Jacob John, M.D " ResourceName="Dr.Jacob" />
                    <syncfusion:Resource DisplayName="Dr.Darsy Mascio, M.D" ResourceName="Dr.Darsy" />
                </syncfusion:ResourceType>
            </syncfusion:SfSchedule.ScheduleResourceTypeCollection>
        </syncfusion:SfSchedule>

{% endhighlight %}
{% endtabs %}
![addresource_week](daymodule_images/addresource_week.png)

### Sub Resource

SubResourceType enables users to view appointments based on their subcategory only in `day`, `week` views and can group appointments under various subcategories.
{% tabs %}
{% highlight C# %}

            SfSchedule schedule = new SfSchedule();
            schedule.ScheduleType = ScheduleType.Week;
            ResourceType resourceType = new ResourceType
            {
                TypeName = "Hospital"
            };
            ResourceType subResourceType = new ResourceType
            {
                TypeName = "Department"
            };
            resourceType.ResourceCollection.Add(new Resource
            {
                DisplayName = "MIOT Hospital",
                ResourceName = "MIOTHospital",
            });
            resourceType.ResourceCollection.Add(new Resource
            {
                DisplayName = "Vijaya  Hospital",
                ResourceName = "VijayaHospital"
            });
            subResourceType.ResourceCollection.Add(new Resource
            {
                DisplayName = "Eye Department",
                ResourceName = "Eye"
            });
            subResourceType.ResourceCollection.Add(new Resource
            {
                DisplayName = "Heart Department",
                ResourceName = "Heart"
            });
            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { resourceType };
            schedule.ScheduleResourceTypeCollection = new ObservableCollection<ResourceType> { subResourceType };
            schedule.Resource = "Hospital";
            schedule.Resource = "Department";

{% endhighlight %}

{% highlight XAML %}

      <syncfusion:SfSchedule
            x:Name="schedule"
            Resource="Hospital"
            ScheduleType="Week">
            <syncfusion:SfSchedule.ScheduleResourceTypeCollection>
                <syncfusion:ResourceType TypeName="Hospital">
                    <syncfusion:ResourceType.ResourceCollection>
                        <syncfusion:Resource DisplayName="MIOT Hospital" ResourceName="MIOTHospital" />
                        <syncfusion:Resource DisplayName="Vijaya  Hospital" ResourceName="VijayaHospital" />
                    </syncfusion:ResourceType.ResourceCollection>
                    <syncfusion:ResourceType.SubResourceType>
                        <syncfusion:ResourceType TypeName="Department">
                            <syncfusion:ResourceType.ResourceCollection>
                                <syncfusion:Resource DisplayName="Eye Department" ResourceName="Eye" />
                                <syncfusion:Resource DisplayName="Heart Department" ResourceName="Heart" />
                            </syncfusion:ResourceType.ResourceCollection>
                        </syncfusion:ResourceType>
                    </syncfusion:ResourceType.SubResourceType>
                </syncfusion:ResourceType>
            </syncfusion:SfSchedule.ScheduleResourceTypeCollection>
        </syncfusion:SfSchedule>
{% endhighlight %}
{% endtabs %}
![subresource_week](daymodule_images/subresource_week.png)

### Changing resource order
#### Order by Date
DayHeaderOrder property is used to set the order by which resources must be displayed. OrderByDate will be displaying the resource based on date. 
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.DayHeaderOrder = DayHeaderOrder.OrderByDate;
{% endhighlight %}

{% highlight XAML %}

    <syncfusion:SfSchedule x:Name="schedule" ScheduleType="Week"
        Resource="Hospital" DayHeaderOrder="OrderByDate"/>
{% endhighlight %}
{% endtabs %}
![orderbydate_week](daymodule_images/orderbydate_week.png)

#### Order by resource
DayHeaderOrder property is used to set the order by which resources must be displayed. OrderByResource will be displaying the resource based on resource collection. 
{% tabs %}
{% highlight C# %}

            schedule.ScheduleType = ScheduleType.Week;
            schedule.DayHeaderOrder = DayHeaderOrder.OrderByResource;
{% endhighlight %}

{% highlight XAML %}

    <syncfusion:SfSchedule x:Name="schedule" ScheduleType="Week"
                       Resource="Hospital" DayHeaderOrder="OrderByResource"/>
{% endhighlight %}
{% endtabs %}
![orderbyresource_week](daymodule_images/orderbyresource_week.png)
